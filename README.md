## demo-xcodegen-app 

This app exists to demonstrate a bug in Xcodegen, so that I can link it to an issue in Xcodegen repo

The bug is that when we have paths with a dot in it, Xcodegen treats it as a resource and
puts the files inside that folder in copy bundle resources phase when it should have been in
Compile Sources phase, because the folder contains swift files.

## Steps to reproduce the bug

- Clone this repo
- Run xcodegen on the root of the directory where the project.yml exists
- Observe that the `FolderWithDot2.0` gets added to copy bundle resources
  when it should have been in Compile sources
