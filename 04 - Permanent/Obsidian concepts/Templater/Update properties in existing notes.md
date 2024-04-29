```
<%*
const file = tp.file.find_tfile(tp.file.path(true));
await app.fileManager.processFrontMatter(file, (frontmatter) => {
  // Update or create key "father"
  frontmatter["father"] = "Hi!";
  // Update or create key "son"
  frontmatter["son"] = "Hey there...";
  // Delete key "mother" (if present)
  delete frontmatter["mother"];
})
-%>
```

https://forum.obsidian.md/t/new-properties-and-templater-prompts-and-commands/66425/17