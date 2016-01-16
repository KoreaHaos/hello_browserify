# Hello Browserify

Here's a bash script that sets up the example:

```bash
# Create a directory structure.
mkdir pgs
mkdir js

# Create an example javascript file.
cat > js/main.js << EOF
var unique = require('uniq');
var data = [1, 2, 2, 3, 4, 5, 5, 5, 6];
console.log(unique(data));
EOF

# Use node package manager to install required module
npm install uniq

# Use browserify to create a javascript file that includes all the node modules.
browserify js/main.js -o js/bundle.js

# Create a html file to demo the example
cat > pgs/index.html << EOF
<!DOCTYPE html PUBLIC "-//IETF//DTD HTML 2.0//EN">
<HTML>
   <HEAD>
      <TITLE>
         Page1:Hello Browserify
      </TITLE>
   </HEAD>
<BODY>
   <H1>Hello Browserify</H1>
   <P>Learning Browserify.</P>
   <script src="../js/bundle.js"></script></BODY>
</HTML>
EOF

# Create a html file to link to the hello world example. 
cat > index.html << EOF
<!DOCTYPE html PUBLIC "-//IETF//DTD HTML 2.0//EN">
<HTML>

<HEAD>
   <TITLE>
      Hello Browserify
   </TITLE>
</HEAD>

<BODY>
   <H1>Hello Browserify</H1>
   <P>Learning Browserify.</P>
   <ul>
      <li>Page
         <a href="pgs/index.html" target="_blank">1</a>.</li>
   </ul>
</HTML>
EOF
# Thats it.

```
