mutagen.js
==========

npm package wrapping the [mutagen](http://code.google.com/p/mutagen/) library.
```javascript
var mutagen = require('mutagen');
// reading tags
mutagen.read('path/to/file.mp3', function(err, tags) {
    if (err) {
        return console.log(err);
    }
    console.log('Artist: ' + tags['artist'][0]);
    console.log('Album: ' + tags['album'][0]);
    console.log('Title: ' + tags['title'][0]);
    console.log('Track Number: ' + tags['tracknumber'][0]);
    console.log('All Tags:');
    console.log(tags);
});

// editing tags
var edits = {
    artist: 'New Artist',
    // falsy values indicate deletion:
    album: '',
    // any unmentioned tags will be unaffected.
};
mutagen.edit('path/to/file.mp3', edits, function(err) {
    if (err) {
        return console.log(err);
    }
    console.log('done');
});
```

This package requies that you already have mutagen installed. Check with this command:

    python -c "import mutagen"

If you get an ImportError, try this in Ubuntu:

    sudo apt-get install python-mutagen
