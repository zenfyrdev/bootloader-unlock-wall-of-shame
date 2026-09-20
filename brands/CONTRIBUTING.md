
Companies are grouped under their directories to avoid clutter. The directory must be a lowercase name of the company.

This document describes the guidelines for maintaining the main `README.md`. Additional files are checked case-by-case.

### Grouping
In some situations, a phone farm such as BBK Electronics (now split into Vivo and Oppo) may have multiple phone brands under its belt. If the unlocking process or technology stack is similar, the companies can be grouped together: Oppo and Realme (BBK, using the same OS), Vivo and IQOO (BBK, but using a different OS).

### Verdict

Companies that do not allow unlocking must have the "🍅 Terrible" verdict.

Sometimes, while it's possible to unlock, the process can be so complicated that a company will be recommended to avoid. (See: Realme, Xiaomi)

Companies that use some sort of online service to unlock must be "⚠️ Proceed with caution!", regardless of reputation. 

A company is considered "safe" if it follows the standard Android (or SOC) procedure with no additional restrictions. Bonus points for support of custom AVB keys.

### Brief History
If the company allowed unlocking in the past, or had different unlocking methods, it may be useful to devote a paragraph to a historical review.

### Guides

Brand Pages on the Wall may provide their own unlock instructions, but the instructions should be separated into a separate file and fully describe the process. A troubleshooting section is encouraged.

The generic unlock guide to base your own on can be found here: [generic-unlock.md](./../misc/generic-unlock.md).

### Additional Info (Not related to unlocking)
The main focus of this list is bootloader unlocking, but other related topics may also be mentioned. It's best to mention them in one sentence and link to a source, rather than explaining them at length.

Related topics include, but are not limited to: rooting, custom operating systems, ADB.

### Links

Links to external resources should be formatted as Markdown reference links. Links to other pages on the Wall can be formatted using the regular `[Example](./brands/...)` syntax.

```
An [Example Link][example-link] in the middle.

*** <- Bottom of the page.

[example-link]:https:...
```

Or you can do this:

```
An [Example Link] in the middle.

*** <- Bottom of the page.

[Example Link]:https:...
```

### Images
It's fine to use images in brand pages, but they should have descriptive alt text and be small. The smaller size can be achieved by converting your images to lossy `.webp`.

Also, avoid using the markdown `![]()` syntax as it does not provide a way to set the `width` and `height` of the image.