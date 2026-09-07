# Bash Cheatsheet
## 1. Variables, Substitution & Arithmetic

### Variables

Bash variables are untyped. **No spaces** around the `=` sign.

```bash
# Declaration
NAME="Terminal"
AGE=21

# Usage
echo "Hello $NAME"
```

### Command Substitution

Capturing the output of a command into a variable.

```bash
# Modern (Preferred - easy to nest)
CURRENT_DIR=$(pwd)
FILES_COUNT=$(wc -l $(find . -name "*.txt"))

# Legacy (Backticks - hard to nest)
CURRENT_DATE=`date +%F`
```

### Arithmetic Operations

```bash
# Modern Substitution (Preferred)
echo "Age in 5 years: $((AGE + 5))"

# C-style evaluation (modifies variable directly, returns exit status)
(( AGE += 10 ))
(( AGE++ ))

# 'let' command (Built-in)
let "AGE = AGE + 5"

# 'expr' command (Legacy, prints to stdout)
TOTAL=$(expr 5 + 10)
```

## 2. Special Variables

|**Variable**|**Description**|
|---|---|
|`$0`|Name of the script|
|`$1` to `$9`|Arguments passed to the script (e.g., `$1` is the first)|
|`$#`|Number of arguments passed|
|`$@`|All arguments as a list|
|`$?`|Exit status of the last executed command (0 = success)|
|`$$`|Process ID (PID) of the current script|

## 3. Conditionals & Logic

### If / Elif / Else

```bash
# Modern (Double brackets - safer, supports pattern matching)
if [[ $NAME == "Root" ]]; then
    echo "Access Granted"
elif [[ $NAME == "Admin" && $AGE -gt 18 ]]; then
    echo "Partial Access"
else
    echo "Access Denied"
fi

# POSIX Standard / Legacy (Single brackets or 'test')
if [ "$NAME" = "Admin" ]; then
    echo "Strict quoting required here"
fi

if test "$NAME" = "Admin"; then
    echo "Alternative POSIX syntax"
fi
```

### Evaluation Operators

|**Type**|**Operators**|**Example**|
|---|---|---|
|**String**|`==`, `!=`, `-z` (empty), `-n` (not empty)|`[[ -z "$VAR" ]]`|
|**Integer**|`-eq` (==), `-ne` (!=), `-lt` (<), `-le` (<=), `-gt` (>), `-ge` (>=)|`[[ $AGE -ge 18 ]]`|
|**File**|`-e` (exists), `-f` (is file), `-d` (is dir), `-x` (executable)|`[[ -f "/etc/hosts" ]]`|

### Inline Conditional Execution (Short-Circuiting)

```bash
# AND (&&): Execute right side ONLY if left side succeeds
mkdir /tmp/test_dir && cd /tmp/test_dir

# OR (||): Execute right side ONLY if left side fails
ping -c 1 8.8.8.8 > /dev/null || echo "Network down!"

# Combined (Ternary-like)
[[ -f "config.yml" ]] && echo "Found" || echo "Missing"
```

## 4. Loops

### Standard `for` Loop

```bash
# Iterate over a list or range
for i in {1..5}; do
    echo "Iteration $i"
done

# Iterate over files
for file in *.txt; do
    echo "Processing $file"
done
```

### C-Style `for` Loop

```bash
# Standard increment
for (( i=0; i<5; i++ )); do
    echo "Index: $i"
done

# Custom step and multiple variables
for (( i=0, j=10; i<=5; i++, j-=2 )); do
    echo "Up: $i, Down: $j"
done
```

### `while` and `until` Loops

```bash
# While: Executes as long as condition is TRUE
COUNT=1
while [[ $COUNT -le 5 ]]; do
    echo "Count: $COUNT"
    ((COUNT++))
done

# Read file line-by-line
while read -r line; do
    echo "Line: $line"
done < input.txt

# Until: Executes as long as condition is FALSE
until [[ -f "ready.flag" ]]; do
    echo "Waiting..."
    sleep 1
done
```

## 5. Switch Case

```bash
read -p "Start the server? (y/n): " CHOICE

case "$CHOICE" in
    y|Y ) 
        echo "Starting..."
        ;;
    n|N ) 
        echo "Aborting."
        ;;
    * ) 
        echo "Invalid input."
        ;;
esac
```

## 6. Arrays

```bash
# Declaration
PORTS=(80 443 8080 22)

# Add an element
PORTS+=(3306)

# Access elements
echo "First port: ${PORTS[0]}"
echo "All ports: ${PORTS[@]}"
echo "Number of ports: ${#PORTS[@]}"
```

## 7. Functions

```bash
# Declaration
check_status() {
    local TARGET=$1  # Keep variable scoped to the function
    if ping -c 1 "$TARGET" &> /dev/null; then
        echo "$TARGET is up"
    fi
}

# Calling the function
check_status "8.8.8.8"
```

## 8. Redirection & Piping

|**Syntax**|**Action**|
|---|---|
|`>`|Redirect `stdout` to a file (overwrite)|
|`>>`|Redirect `stdout` to a file (append)|
|`2>`|Redirect `stderr` to a file|
|`&>`|Redirect both `stdout` and `stderr` to a file|
|`/dev/null`|The "black hole" (discards any output sent to it)|
|`\|`|Pipe `stdout` of one command to `stdin` of the next|