# Reference
Community is a hugo theme intended for small community and meetup groups to easily get going. The theme is heavily driven around the concept of events and speakers, and would be well-suited to conferences, or groups that hold talks.

This guide is intended for those that wish to use the theme.

## Site Config Settings

Coming soon.

## Archetypes

Archetypes are a concept within Hugo. They are templates which can be easily used when you want to create new content. You can find more about Archetypes in Hugo [here](https://gohugo.io/content-management/archetypes/).

The Community theme leverages a number of archetypes to deliver the site's content. Please refer to the information below on how to use archetypes, so that you can add additional content to your site.

### Event

To create a new event, use the following command in your site folder

```
hugo new --kind event event/your-intended-directory-name
```

The event archetype contains a bundle of files, including - 
* The _index.md file which contains information about the event itself.
* A subfolder called activities, which can contain many files. These files represent individual sessions/talks/etc. To create more activities, just copy/paste the files in the activities subfolder.
* A subfolder called sponsors, which can contain many files. These files represent sponsors of this particular event. To create more sponsors, just copy/paste the files in the organizers subfolder.

Rather than duplicating effort, we have provided clear comments inline in the files on which fields are required, optional, and should be left untouched. You can find that information in the [archetypes/event folder](https://github.com/chrisreddington/hugo-community/tree/main/archetypes/event). You can find this information by looking at the raw version of the file (rather than any markdown rendered view, as the comments will be stripped).

### Group


To create a new group, use the following command in your site folder

```
hugo new --kind group group/your-intended-directory-name
```

The group archetype contains a bundle of files, including - 
* The _index.md file which contains information about the group itself.
* Several additional optional markdown files in the **your-intended-directory-name** folder. These can be shown using the tabbed interface of the Group page. Do take note of the frontmatter that drives this functionality. Details on these can be found in the comments of the example markdown files in the [archetypes/group folder](https://github.com/chrisreddington/hugo-community/tree/main/archetypes/group) folder.
* A subfolder called activities, which can contain many files. These files represent individual sessions/talks/etc. To create more activities, just copy/paste the files in the activities subfolder.
* A subfolder called organizers, which can contain many files. These files represent organizers of this particular event. To create more organizers, just copy/paste the files in the organizers subfolder.
* A subfolder called sponsors, which can contain many files. These files represent sponsors of this particular event. To create more sponsors, just copy/paste the files in the organizers subfolder.

Rather than duplicating effort, we have provided clear comments inline in the files on which fields are required, optional, and should be left untouched. You can find that information in the [archetypes/group folder](https://github.com/chrisreddington/hugo-community/tree/main/archetypes/group). You can find this information by looking at the raw version of the file (rather than any markdown rendered view, as the comments will be stripped).

### Speaker

To create a new group, use the following command in your site folder

```
hugo new speaker/speaker-name.md
```

**Note:** Be aware of the different syntax between events/groups and speakers. The speaker example does not require the --kind parameter, as it is a single page, rather than a bundle. This is also why we need to specify the .md extension, to represent that we wish to create a markdown file.

Rather than duplicating effort, we have provided clear comments inline in the [archetypes/speaker.md file](https://github.com/chrisreddington/hugo-community/tree/main/archetypes/speaker.md). You can find this information by looking at the raw version of the file (rather than any markdown rendered view, as the comments will be stripped).