Test if a person would be able to successfully follow the instructions provided by the hands-on activities in the current open lab file by performing these instructions as a learner would do.

If there are instructions requiring a web browser, follow additional instructions from @prompts/test-lab-web.md.

If there are instructions requiring running shell commands in a terminal, follow additional instructions from @prompts/test-lab-cli.md.

Use the demo environment access credentials from @prompts/demo-env.md

If any step from the lab does not work *exactly* as described, do NOT attempt to guess missing information.
Do NOT attempt to click anywhere else and do NOT attempt to fill in any additional field.
Do NOT attempt to run additional shell commands.
Just report at which step you had to stop and why.

Skip instructions stated as optional, alternative, or inside admonitions.

Verify that, for each step, the outputs match the results described by the lab.
If the outputs do not match the results, report the mismatch but continue following the instructions.

Save a report of issues found during testing in a file named qa-issues.md in a directory named qa-[lab file name]-yyyymmdd-HHMM.md under the @prompts/reports/[lab chapter name] directory.
Also save screenshots of all browser-based actions in the same directory.
Create a report named qa-outputs.html with links to the screenshots and also with the text output from shell commands.
Each screenshot and text output should refer to its step and substep from the lab.