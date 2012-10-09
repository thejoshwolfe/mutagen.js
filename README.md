mutagen.js
==========

npm package wrapping the [mutagen](http://code.google.com/p/mutagen/) library.

    var mutagen = require('mutagen');
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

Requies that you already have mutagen installed. Check with this command:

    python -c "import mutagen"

If you don't, try this in Ubuntu:

    sudo apt-get install python-mutagen
