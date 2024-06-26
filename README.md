# anki-apkg-export

Browser-only fork of [anki-apkg-export](https://github.com/repeat-space/anki-apkg-export) to run in the browser without webpack or outdated webpack modules. It is a javascript library for generating decks for Anki.


## Required libraries
- filesaver
- jszip@3.10.1
- js-sha
- sql.js@0.5.0

## Usage

```html
<!DOCTYPE html>
<html>
    <head>
        <script src="https://cdn.jsdelivr.net/npm/file-saver@2.0.5/dist/FileSaver.js"></script>
        <script src="https://cdn.jsdelivr.net/npm/jszip@3.10.1/dist/jszip.min.js"></script>
        <script src="https://cdn.jsdelivr.net/npm/js-sha1@0.7.0/src/sha1.min.js"></script>
        <script src="https://cdn.jsdelivr.net/npm/sql.js@0.5.0"></script>
        <script src="/src/index.js"></script>
    </head>
    <script>
      const apkg = new window.apkgExport("deck-name")

      apkg.addCard('card #1 front', 'card #1 back');
      apkg.addCard('card #2 front', 'card #2 back', { tags: ['nice', 'better card'] });
      apkg
      .save()
      .then(zip => {
           saveAs(zip, "output.apkg")
           console.log(`Package has been generated: output.pkg`);
       })
       .catch(err => console.log(err.stack || err));
    </script>
</html>
```
## License

MIT © [ewnd9](http://ewnd9.com), [aboutdavid](https://aboutdavid.me)

