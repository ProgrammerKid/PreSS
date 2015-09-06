#!/usr/bin/python
import json
import sys

filename = sys.argv[1]
if len(sys.argv) > 2:
    json_data = open(sys.argv[2]).read()
else:
    json_data = open("config.json").read()

pss = open(filename + ".pss").read()

config = json.loads(json_data)
output = pss
keys = []

while (True):
    for line in output.split(";"):
        try:
            start = line.index("</")
            end = line.index("/>")
        except ValueError:
            start = -1
            end = -1
        
        if start >= 0 and start >= 0:
            key = line[start + 2 : end]
            keys.append(key)
        
    print keys
    for key in keys:
        key_pointer = key
        key_pointer = key_pointer.replace('[', '["')
        key_pointer = key_pointer.replace(']', '"]')
        output = output.replace("</" + key + "/>", eval("config" + key_pointer))
    if "</" in output and "/>" in output:
        print("Recompiling")
    else:
        break

writer = open(filename + ".css", "w")
writer.write(output)
