# ПРАКТИЧЕСКАЯ 1

## Задание 1
```
grep -o '^[^:]*' /etc/passwd | sort
```
## Результат:
<img width="512" height="838" alt="image" src="https://github.com/user-attachments/assets/64d97765-aa97-4768-964c-b80e1d978ee8" />

## Задание 2
```
 cat /etc/protocols | awk '{print $2, $1}' | sort -nr | head -5
```

## Результат: 
142 rohc
141 wesp
140 shim6
139 hip
138 manet

## Задание 3
```
nano banner

!/bin/bash

text="$1"
length=${#text}

border="+$(printf '%*s' "$((length + 2))" '' | tr ' ' '-')+"

echo "$border"
echo "| $text |"
echo "$border"
```

## Результат: 
<img width="520" height="151" alt="image" src="https://github.com/user-attachments/assets/f7bd5a3e-31f5-4b06-9d5f-d972bf19ca05" />

## Задание 4
```
nano identifiers

#!/bin/bash

grep -o '[A-Za-z_][A-Za-z0-9_]*' "$1" | sort -u

nano hello.c

#include <stdio.h>

int main(void) {
    printf("hello world\n");
    return 0;
}

./identifiers hello.c
```

## Результат
<img width="638" height="304" alt="image" src="https://github.com/user-attachments/assets/f7ff7e0d-8e19-4282-8fc1-dab23e37af01" />

## Задание 5
```
nano reg

#!/bin/bash

chmod +x "$1"
sudo cp "$1" /usr/local/bin/

./reg banner
ls -l /usr/local/bin/banner
banner "Hello"
```

## Результат
<img width="764" height="179" alt="image" src="https://github.com/user-attachments/assets/d4e57105-fdf7-491d-a4f1-e1a1fa8405ee" />

## Задание 6
```
nano comments

#!/bin/bash

for file in *.c *.js *.py; do
    [ -e "$file" ] || continue

    first_line=$(head -n 1 "$file")

    case "$file" in
        *.c|*.js)
            if echo "$first_line" | grep -qE '^[[:space:]]*(//|/\*)'; then
                echo "$file: comment found"
            else
                echo "$file: no comment"
            fi
            ;;
        *.py)
            if echo "$first_line" | grep -qE '^[[:space:]]*#'; then
                echo "$file: comment found"
            else
                echo "$file: no comment"
            fi
            ;;
    esac
done

nano test.c
// comment
int main() {
    return 0;
}

nano test.js
/* comment */
console.log("hello");

nano test.py
print("hello")
```

## Результат
<img width="435" height="224" alt="image" src="https://github.com/user-attachments/assets/b87b1bf9-5f2b-4846-bb76-f1304d127823" />

## Задание 7
```

```

## Результат
