# ICC 2023 Git Workshop

This document includes the procedure for folks who are following along with the workshop.

## Setup

1.  Open Terminal.
2.  Clone the workshop repository.

        git clone https://github.com/JoeDo/git-workshop.git

3.  Navigate inside the `git-workshop/devops` directory.

        cd git-workshop/devops

4.  Open the directory in Visual Studio Code to better see these instructions.

        code .

5.  Open `README.md`, and click `Ctrl-K` followed by `v` to get a Markdown preview of this documentation.

6.  Using Terminal, replace the contents of the `secrets/TOKEN` file with the value provided during the workshop. **_Make sure to keep the single quotation marks._**

        echo 'replace_me' > ./secrets/TOKEN

7.  Authenticate with a Docker repository provided for this workshop and configure environment variables.

        cat ./secrets/TOKEN | docker login --username WorkshopToken --password-stdin factorystackdevmgmtjoe.azurecr.io

8.  Configure an environment variable that will be used by `docker compose`.

        export USERNAME=$(echo $USER | sed 's/.*\\//')

9.  Launch the Ignition instances via `docker compose`.

        docker compose up -d

10. Navigate to the following URLs in your web browser:

-   http://dev.localtest.me:8088/data/perspective/client/GitWorkshop
-   http://prod.localtest.me:8089/data/perspective/client/GitWorkshop

9. Navigate to the following URL, replacing `USER` with the assigned username you used to login to Amazon WorkSpaces (e.g., `instructor381`).

-   <https://git.datadash.4ir.dev/workshop/ignition/src/branch/USER-dev>
