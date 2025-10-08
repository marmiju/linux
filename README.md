# 🧰 Linux Filter Commands – Complete Guide

Linux **filter commands** process text data from standard input (`stdin`), perform operations, and send the output to standard output (`stdout`).  
They’re called *filters* because they filter, modify, or analyze data that passes through them — often used in **pipelines**.

Example:
```bash
cat file.txt | grep "error" | sort | uniq
```
This prints lines containing “error”, sorts them, and removes duplicates.

---

## 📜 List of Common Linux Filter Commands

| Command | Description |
|----------|-------------|
| `cat` | Display or combine files |
| `head` | Show first lines |
| `tail` | Show last lines |
| `grep` | Search text patterns |
| `sort` | Sort text |
| `uniq` | Remove duplicates |
| `wc` | Count lines/words/chars |
| `cut` | Extract columns |
| `tr` | Replace/delete characters |
| `awk` | Process text by fields |
| `sed` | Edit text streams |
| `tee` | Save + display output |
| `paste` | Merge lines |
| `nl` | Add line numbers |
| `rev` | Reverse text |

---

## 🔹 1. `cat` – Concatenate and Display Files
```bash
cat file.txt                # Show file content
cat file1.txt file2.txt     # Combine multiple files
cat > newfile.txt           # Create a new file (Ctrl+D to save)
cat -n file.txt             # Show line numbers
```

---

## 🔹 2. `head` – Display First Lines
```bash
head file.txt               # Show first 10 lines (default)
head -n 5 file.txt          # Show first 5 lines
```

---

## 🔹 3. `tail` – Display Last Lines
```bash
tail file.txt               # Show last 10 lines
tail -n 20 file.txt         # Show last 20 lines
tail -f logfile.log         # Follow live log updates
```

---

## 🔹 4. `grep` – Search Patterns
```bash
grep "error" file.txt               # Find lines with 'error'
grep -i "error" file.txt            # Case-insensitive search
grep -n "error" file.txt            # Show line numbers
grep -v "error" file.txt            # Exclude lines with 'error'
grep -r "main" /project/dir         # Recursive search
```

---

## 🔹 5. `sort` – Sort Lines
```bash
sort names.txt                      # Sort alphabetically
sort -r names.txt                   # Reverse order
sort -n numbers.txt                 # Numeric sort
sort -u names.txt                   # Unique (remove duplicates)
```

---

## 🔹 6. `uniq` – Remove Duplicates
```bash
uniq data.txt                       # Remove adjacent duplicates
sort data.txt | uniq                # Sort first, then unique
uniq -c data.txt                    # Show count of each line
```

---

## 🔹 7. `wc` – Word, Line, and Byte Count
```bash
wc file.txt                         # Lines, words, bytes
wc -l file.txt                      # Count lines only
wc -w file.txt                      # Count words only
wc -c file.txt                      # Count characters only
```

---

## 🔹 8. `cut` – Extract Columns or Characters
```bash
cut -c1-5 file.txt                  # Characters 1–5
cut -d"," -f2 file.csv              # Extract 2nd field from CSV
cut -d":" -f1 /etc/passwd           # Extract usernames
```

---

## 🔹 9. `tr` – Translate or Delete Characters
```bash
tr 'a-z' 'A-Z' < file.txt           # Convert to uppercase
tr -d '0-9' < file.txt              # Delete digits
tr -s ' ' < file.txt                # Squeeze multiple spaces
```

---

## 🔹 10. `awk` – Pattern Scanning and Processing
```bash
awk '{print}' file.txt                      # Print all lines
awk '{print $1}' file.txt                   # Print first column
awk -F"," '{print $1, $3}' file.csv         # CSV: print 1st & 3rd fields
awk '/error/ {print $0}' logfile.log        # Print lines with “error”
awk '{sum+=$2} END {print sum}' data.txt    # Sum values in 2nd column
```

---

## 🔹 11. `sed` – Stream Editor
```bash
sed 's/error/issue/' file.txt               # Replace first occurrence
sed 's/error/issue/g' file.txt              # Replace all occurrences
sed '/debug/d' file.txt                     # Delete lines with “debug”
sed -n '1,5p' file.txt                      # Print lines 1–5 only
```

---

## 🔹 12. `tee` – Read and Write Simultaneously
```bash
ls | tee files.txt                          # Display + save output
ls | tee -a files.txt                       # Append instead of overwrite
```

---

## 🔹 13. `paste` – Merge Lines from Files
```bash
paste file1.txt file2.txt                   # Merge line by line
paste -d"," file1.txt file2.txt             # Use comma as delimiter
```

---

## 🔹 14. `nl` – Number Lines
```bash
nl file.txt                                 # Add line numbers
```

---

## 🔹 15. `rev` – Reverse Lines
```bash
rev file.txt                                # Reverse each line
```

---

## ⚙️ Combine Filters with Pipes
You can chain multiple filters together using `|` (pipe):

```bash
cat access.log | grep "404" | cut -d' ' -f1 | sort | uniq -c | sort -nr | head
```
➡️ Finds the **top IP addresses** causing 404 errors.

---

## 🧩 Summary
- Filters are the **core** of Linux text processing.
- You can **combine** them to perform complex data analysis in one line.
- Great for log analysis, automation, and DevOps workflows.

---

## 💡 Pro Tip
Try using `man <command>` for full documentation.  
Example:
```bash
man grep
```

---

### ✅ Author
**Developer Azizar**  
> Made for students and developers learning Linux command-line tools.
