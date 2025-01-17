# Exercise 02

Description: There's a web server access log file at `/home/admin/access.log`. The file consists of one line per HTTP request, with the requester's IP address at the beginning of each line.

Task: Find the IP address with most requests in access.log file and write the solution to `/home/admin/highestip.txt`.

# Solution

```bash
awk '{print $1}' /home/admin/access.log | sort | uniq -c | sort -r | awk '{print $2}' | head -n 1 > /home/admin/highestip.txt
```

## Explanation

Take only the IP address from the access.log file. Sort it and count occurrences, then sort it again based the on number of requests, then show only the IP with the mosts requests and redirect the output to /home/admin/highestip.txt.
