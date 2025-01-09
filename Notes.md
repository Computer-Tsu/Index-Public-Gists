# Automaticaly make a list of your gists.

Use the workflow file, make your own personal access token with org, gists, and repo.

by default, this runs weekly and if no changes, it won't perform an update/commit of the REAME.md in the repository.

## License

1) You are encourged to use the code.
2) Give credit. Thank you.

## Notes about the code

I used sed mostly, awk had trouble when the descriptions had multiple words (spaces). JSON is likely a good choice as an alternative.<br>
The gh cli output varies some by OS. For example, in GitHub workflows (ubuntu) the modification is a zulu date-time format but in Windows it says 'a few months ago'.

There is one character escape, the pipe | because I formated with markdown tales and that seemed to throw off my parsing early on. Beware of other possible characters that will give odd markdown results.

To use this for your Private gists, some instances of 'Public' are changed to 'Secret' and other context use 'Private'
