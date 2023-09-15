# Template to test pull to data-conversion tool

This template will work with:
 - Most Unix based OS
 - Recent Mac OS

This can be used to make tests for/before making pull requests to
a data conversion tool repository. Download zip or clone the repo
locally. Edit the "config-variables.sh" file to run test.
<br>
It is recommended that you at least have an intermediate knowledge of
the following before using this repository to build your test:
 1. bash scripting
 2. Makefile
 3. Data conversion tool being tested

<strong>IMPORTANT</strong>:<br>
This is not specific to any current repositroy. The current 
"config-variables.sh" contents is for example purposes. So it 
is important that you edit the "config-variables.sh" file 
before running test.

<strong>IMPORTANT</strong>: <br>
There are safe guards if you ```make full``` test. They are:
 - Max build sized - 50 MB
 - Max build time  - 900 seconds (*15 minutes*)

## INSTRUCTIONS
### Local Test Instructions
1. Make repo based on this template repo.
2. Either
   - Upload test files that will be converted to data/quick-test directories.
      - gen - general files tested
      - unq - any unique or focus files tested
   - Use a ready made config for a command previously tested. Use pre-configs below:
      - `` make roffit ``
      - `` make asciidoctor ``
3. Read and agree to terms in USAGE_AGREEMENT.md. Either:
   - ``` cat USAGE_AGREEMENT.md ```
   - Click [link to file](https://github.com/jhauga/data-conversion-tool/blob/master/USAGE_AGREEMENT.md)
4. Change variables in "config-variables.sh".
   - See commented instructions in the file.
   - **IMPORTANT** - the function `` _commandSyntax `` uses variables defined in main script that are passed as arguments to function. Use the pre-configurred examples in the function as a guide to to arrange the syntax for the test.
   - **IMPORTANT** - if more than three elements are needed to run the command for test, then edit the main script file "data-test".
5. Ensure necessary dependencies are installed for test.
6. Run either:
   - `` make quick ``
   - `` make full ``
7. Run a local host and open in browser to view test results.
8. Additionally to clean to reset repo:   
   - `` make clean ``
   - `` make retest ``
      
### Codespace Test Instruction
1. Make repo based on this template repo.
2. Either
   - Upload test files that will be converted to data/quick-test directories.
      - gen - general files tested
      - unq - any unique or focus files tested
   - Use a ready made config for a command previously tested. Use pre-configs below:
      - `` make roffit ``
      - `` make asciidoctor ``
 3. After naming new repo open it in codespace.
 4. Read and agree to terms in USAGE_AGREEMENT.md. Either:
    - ``` cat USAGE_AGREEMENT.md ```
    - Click [link to file](https://github.com/jhauga/data-conversion-tool/blob/master/USAGE_AGREEMENT.md)
 5. Change variables in "config-variables.sh".
    - See commented instructions in the file.
    - **IMPORTANT** - the function `` _commandSyntax `` uses variables defined in main script that are passed as arguments to function. Use the pre-configurred examples in the function as a guide to to arrange the syntax for the test.
    - **IMPORTANT** - if more than three elements are needed to run the command for test, then edit the main script file "data-test".
 6. Install necessary dependencies
 7. Copy paste below line:
    - `` chmod a+x Makefile agree data-test *.sh *.js config/*.sh data/ready/*.sh data/ready/*/*.sh ``
 8. Run either:
    - `` make quick ``
    - `` make full ``
 9. Run server with:
    - `` node server.js ``
    - Or use GitHub pages environment
      - `` php -S localhost:3000 `` should work
 10. Additionally to clean to reset repo:   
    - `` make clean ``
    - `` make retest ``

### View resulte
1. If final test repo is uploaded to GitHub:
   - To see output from test there will be a link generated and included at the top of the new README.md file.
2. If final test remains local use method for localhost:
   - For example - ```php -S localhost:8000```

### Additional Notes
  - Once the test has completed a new README.md file will be generated, which gives a brief overview of the test procedure.
  - The README.md that was used in the original template repository will be copied to INSTRUCTIONS.md

