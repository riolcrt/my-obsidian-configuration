#resource/repository 

## Create a task in todoist each time a note with the text "Tarea" is added to onedrive

I have my obsidian fully backed on onedrive, so it is perpetually synced in all my computers. It also allows me to run scripts based on the file creation.

This script is done in [[Microsoft Power Automate]] within my personal account.

https://emea.flow.microsoft.com/manage/environments/ea2d3815-80ef-4523-9ec3-779dede982d0/flows/cf5415ca-885e-46d6-8983-0f7cf884c0d4

## Add tag to the file based on its title

I developed this one using [[Rust]]. It is a console application witch take 2 parameters. Word to search in the title and tag to add.

For it I have to learn [[Rust]] first so I created [[Doc - STREAM - Learning RUST from the ABSOLUTE beginning|this document]] to follow the adventure 

- [x] Create the application and start the development 📅 2022-05-25 ✅ 2022-05-25
- [x] Learn how to read arguments from command line ✅ 2022-05-25
- [x] Learn how to retrieve a list of documents given a path ✅ 2022-05-25
- [x] Learn how to make it recursive ✅ 2022-05-26
	- [x] Learn how to diff between a directory and a file ✅ 2022-05-26


```bash
cargo run 
```