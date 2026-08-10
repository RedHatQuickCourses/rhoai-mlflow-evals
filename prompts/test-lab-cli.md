All commands must be run in a container named `test-lab` using pty-mcp on the same interactive session started from: `podman exec -it test-lab bash`.
When the lab is completed, run the `exit` command to finish the interactive podman exec session.

If you need to oc an oc command, first log in the demo environment access credentials from @prompts/demo-env.md with the command `oc login -u <username> -p '<password>' --insecure-skip-tls-verify <api URL>` 
