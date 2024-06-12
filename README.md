# Git-Version-Control

There are two philosophies of version control systems:

- One utilizes a centralized system, like CVS or Subversion: In this type of system, there is only one central repository of versions. The server centralizes all project files and contains the version history. Users retrieve a version of the files to their local machine and work on that version. When desired, they synchronize their code with the central repository to update it. This system has several drawbacks, notably the difficulty of working without a connection.

- The other is a decentralized system, such as Git or Mercurial: In these systems, each user has a complete copy of the repository with its full history. While it may take longer to clone a repository, users can work locally on their machines without an internet connection. Additionally, in case of central server failure, the code and its history are not lost because every user has a complete copy of the source code.

Git is the most well-known and widely used version control system today. It is a decentralized VCS created by Linus Torvalds for managing the Linux kernel. Interestingly, Git was developed in a few weeks after BitKeeper decided to make its version control tool proprietary.