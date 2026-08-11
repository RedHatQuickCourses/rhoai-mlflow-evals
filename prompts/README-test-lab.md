The test-lab.md prompt performs QA on a hands-on activity (a lab) with the goal of determining if the instructions are complete and sufficient for learners to perform by themselves.

It relies on test-lab-web.md, which testes browser-based UIs using the playwright mcp, and test-lab-cli.md, which tests shell commands in a terminal using pty-mcp.

Install the MCP server and related CLI tools before attempting to run these prompts:

- Install playright
- Install the playright mcp server:
$ claude mcp add playwright npx @playwright/mcp@latest

- Install pty-mcp
- Install the pyt-mcp mcp server:
$ claude mcp add pty-mcp -- pty-mcp

Numerous articles on the internet claim that using the playright CLI + a playwright skill would more efficient than the playwright mcp, but I got better performance (measured in wall clock time) and more predictable results from the mcp.

To test shell commands, you must provide a container named test-lab which is already configured with all prerequisites, such as a Python runtime.
It was tested using a container named evals-lab, based on Fedora Linux 44 and its Containerfile is in this directory.

Start the container detached, so pty-mcp can podman exec into it:

$ podman run -d --name test-lab localhost/evals-lab

Reusing the container enables testing activities which depend on outcomes from previous ones, such as installing a CLI tool.
But that means you must manage the container, possibly deleting and recreting it to restart end-to-end testing.

It should enable testing activities which alternate between a browser and a shell, but currently there's no integration between the two, for example: downloading a file from the browser won't make it available within the container.
It should be possible to overcome such limitation with a specially crafted browser profile and podman volumes.

The pty-mcp should allow testing of hands-on activities using a local or remote VM, for example a RHDP bastion host or ROLE workstation and server machines, but these prompts were not tested in such scenarios.

TODO

- Provide scripts to check prereqs and create the reports directory -- things that are deterministic and are a waste of tokens to do from prompts.

- Test prompt variantes which start SSH sessions to RHDP bastion hosts.