help me write a webpack plugin (for nextjs), it should be written in typescript

what it should do:

1. remove the first line if it's "use api" fregment

2. generate a next route in `api/` based on the file name that you found in the previous point

3. generate the submit handler function inside the relevant component or file (that uses the exported functions from the file that you found in the first point)

4. replace the function usage with the handler function (in point 3)