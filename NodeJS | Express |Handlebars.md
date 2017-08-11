# NodeJS | Express |Handlebars


## Install NodeJS


Go to [nodejs.org ](https://nodejs.org)and download mature and dependable version
![Image](https://content.screencast.com/users/paulhanna33/folders/Jing/media/fead33b3-872a-4d9f-8f1a-ab8816c693c8/00000008.png)


Check if installed

```git
node -v //will output version
```


Create directory where project folder will reside

```git
mkdir projectName && cd projectName
```


Inside terminal NPM install [express generator](https://expressjs.com/en/starter/generator.html)  with handlebars inside root of project folder. Handlebars is the templating engine for express

```git
express projectName --hbs
```


![Image](https://content.screencast.com/users/paulhanna33/folders/Jing/media/07cf5732-117b-4009-aa1b-96293033d92c/00000011.png)


In terminal cd into created project

```git
cd projectName
```


Install dependencies 

```git
npm install
```


Open project inside of text editor (atom, sublime)
![Image](https://content.screencast.com/users/paulhanna33/folders/Jing/media/822e4d7b-6ad3-46a5-8807-a903527cae40/00000012.png)


Start server

```git
npm start
```


In browser type localhost:8000
![Image](https://content.screencast.com/users/paulhanna33/folders/Jing/media/c6179b10-e6a3-41a4-ba12-a74ba3f85e9f/00000013.png)


## Implement bootstrap & jQuery
1. Get bootstrap minified css cdn [here](http://getbootstrap.com/getting-started/#download)
1. Add cdn link into your views > layouts.hbs main rendering page below title and above style.css link
1. Get bootstrap minfied javascript cdn [here](http://getbootstrap.com/getting-started/#download)
1. Add cdn link into your views/layouts.hbs main rendering page at the bottom of the body tag before it ends
1. Get jQuery minified cdn [here](http://code.jquery.com/)
1. Add cdn script above javascript script tag (end of body)
1. Delete all css from public/stylesheets/style.css to state with a clean slate.


## Create Navbar
1. Go to bootstrap and get navbar from [here](http://getbootstrap.com/components/#navbar)
1. Create partials folder in views directory
1. Inside partials create file called header.hbs
1. Paste your navbar code from bootstrap into the header.hbs file
1. Replace handlebars default templating engine with another 3rd party handlebars which has more features: 

```git
npm install --save express-handlebars
```
6. Require package in app.js

```javascript
var expressHbs = require('express-handlebars');
```
7. Remove and replace default view engine code setup in app.js - line 14

```javascript
// from this
app.set('views', path.join(__dirname, 'views')); 
app.set('view engine', 'hbs');

// to this
app.engine('.hbs', expressHbs({defaultLayout: 'layout', extname: '.hbs'}));
app.set('view engine', '.hbs');
```
8. Create new subfolder in views called layouts and move your layouts.hbs in partials to the layouts folder
9. Simplify navbar by removed some features. Refactor to the code below

```markup
<nav class="navbar navbar-default">
   <div class="container-fluid">
      <!-- Brand and toggle get grouped for better mobile display -->
      <div class="navbar-header">
         <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
        <span class="sr-only">Toggle navigation</span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
      </button>
         <a class="navbar-brand" href="#">Brand</a>
      </div>

      <!-- Collect the nav links, forms, and other content for toggling -->
      <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">

         <ul class="nav navbar-nav navbar-right">
            <li><a href="#">Shopping Cart</a></li>
            <li class="dropdown">
               <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">User Management <span class="caret"></span></a>
               <ul class="dropdown-menu">
                  <li><a href="#">User Account</a></li>
                  <li role="separator" class="divider"></li>
                  <li><a href="#">Logout</a></li>
               </ul>
            </li>
         </ul>
      </div>
      <!-- /.navbar-collapse -->
   </div>
   <!-- /.container-fluid -->
</nav>
```


## Add Fontawesome Icons to navbar categories
1. Get font awesome CDN [here](https://www.bootstrapcdn.com/fontawesome/)
1. Add font awesome CDN into layouts.hbs head
1. Find user icon and paste before User Management inside <a> tag

```markup
<i class="fa fa-user" aria-hidden="true"></i>
```
4. Find shopping cart icon and paste before Shopping Cart inside <a> tag

```markup
<i class="fa fa-shopping-cart" aria-hidden="true"></i>
```


## Add Product Thumbnails
1. Create sub folder in views called shop
1. Move index.hbs inside of shop 
1. In index.js file change Get Home Page router (line 4-6) to:

```javascript
res.render('shop/index',
```
4. Go to bootrap and get thumnail code [here](http://getbootstrap.com/components/#thumbnails)

```markup
<div class="row">
  <div class="col-sm-6 col-md-4">
    <div class="thumbnail">
      <img src="..." alt="...">
      <div class="caption">
        <h3>Thumbnail label</h3>
        <p>...</p>
        <p><a href="#" class="btn btn-primary" role="button">Button</a> <a href="#" class="btn btn-default" role="button">Button</a></p>
      </div>
    </div>
  </div>
</div>
```
5. Remove the code inside of index.hbs (inside shop directory) and replace it with the thumnail code above. 
6. Inside of layout.hbs create div container to wrap body tag like so:

```markup
<div class="container">
      {{{body}}}
   </div>
```
7. Add any image url inside thumnail in index.hbs in the img src="...". Use following URL to start: 

```markup
https://images-na.ssl-images-amazon.com/images/I/915vV-zIhmL._AC_SX430_.jpg
```
8. Style css for thumbnail:

```markup
.thumbnail img {
    max-height: 300px;
}

.thumbnail .description {
   color: #7f7f7f;
}

.price {
   font-weight: bold;
   font-size: 16px;
}
```
9. Thumbnail after some changes:

```markup
<div class="row">
   <div class="col-sm-6 col-md-4">
      <div class="thumbnail">
         <img src="https://images-na.ssl-images-amazon.com/images/I/915vV-zIhmL._AC_SX430_.jpg" class="img-responsive">
         <div class="caption">
            <h3>Grand Theft Auto V - PlayStation 4</h3>
            <p class="description">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>

            <div class="clearfix">
               <div class="price pull-left">$12</div>
               <a href="#" class="btn btn-succes pull-right" role="button">Button</a>
            </div>
         </div>
      </div>
   </div>
</div>
```
10. Copy thumbnail html above 5 more times in index.hbs to have 2 rows of 3 thumbnails per row. 


## Install & Implement MongoDB
1. Install Brew [here](https://brew.sh/)
1. Install MongoDB with Brew [here](https://treehouse.github.io/installation-guides/mac/mongo-mac.html)
1. run mongod in one terminal and mongo in another


## Install mongoose package
1. cd into project directory and npm install mongoose

```git
npm install --save mongoose
```
2. Require mongoose in app.js file

```javascript
var mongoose = require('mongoose');
```
3. Connect mongoose to mongodb server in app.js file - under var app = express(); 

```javascript
mongoose.connect('localhost:27017/shopping');
```


## Create product schema
1. Create new directory in project root directory callec models
1. In models folder create file called product.js
1. set following requirements in product.js

```javascript
var mongoose = require('mongoose');
var Schema = mongoose.Schema;
```
4. Create new schema for products

```javascript
var schema = new Schema({
   imagePath: {type: String, required: true},
   title: {type: String, required: true},
   description: {type: String, required: true},
   price: {type: Number, required: true}
});
```
5. Export product schema module at bottom of product.js

```javascript
module.exports = mongoose.model('Product', schema);
```


## Create seed data
1. Create new directory in project root directory called seed
1. Inside seed directory create file called product-seeder.js
1. Inside product-seeder.js require product model

```javascript
var Product = require('../models/product');
```
4. Copy seed data below and paste it into product-seeder.js

```javascript
var products = [
   new Product({
      imagePath: 'https://images-na.ssl-images-amazon.com/images/I/915vV-zIhmL._AC_SX430_.jpg',
      title: 'Grand Theft Auto V - PlayStation 4',
      description: 'Awesome game!!!',
      price: 10
   }),
   new Product({
      imagePath: 'https://images-na.ssl-images-amazon.com/images/I/91MGuwCqffL._AC_SL1500_.jpg',
      title: 'Spider-Man - PlayStation 4',
      description: 'An experienced Spider-Man with several years of crime fighting under his belt, Peter Parker has sheer mastery of his powerful spider-sense, dynamic skills, acrobatic abilities, and new suit.',
      price: 20
   }),
   new Product({
      imagePath: 'https://images-na.ssl-images-amazon.com/images/I/61vi7cLSYWL._SX215_.jpg',
      title: 'LEGO Marvel Super Heroes - PlayStation 4',
      description: 'Smash, swing and fly in the first LEGO videogame featuring more than 100 of your favorite super heroes and super villains from the Marvel Universe',
      price: 30
   }),
   new Product({
      imagePath: 'https://images-na.ssl-images-amazon.com/images/I/91odvdK1hoL._AC_SX430_.jpg',
      title: 'Assassins Creed Unity - PlayStation 4',
      description: 'UNIQUE CO-OP EXPERIENCE YOU MUST PLAY TO BELIEVE: In addition to an epic single-player campaign, join with up to three friends online and experience the open world of 18th-century Paris',
      price: 40
   }),
   new Product({
      imagePath: 'https://images-na.ssl-images-amazon.com/images/I/71Ijse14wPL._AC_SX430_.jpg',
      title: 'Super Mega Baseball (3-Way Cross Buy) - PS4',
      description: 'Awesome Super Mega Baseball game!!!',
      price: 50
   }),
   new Product({
      imagePath: 'https://images-na.ssl-images-amazon.com/images/I/91SRQuJiRWL._AC_SX430_.jpg',
      title: 'Ni No Kuni II: Revenant Kingdom - PlayStation 4',
      description: 'LEVEL-5 mastery of the RPG genre is combined with music composed by the renowned Joe Hisaishi and character designs by animation artist Yoshiyuki Momose',
      price: 60
   })
];
```
5. Loops through seed data by inserting the following forloop below the seed data array.

```javascript
for (var i = 0; i < products.length; i++) {
   products[i].save();
}
```
6. Require mongoose at top of product-seeder.js file and copy mongoose connect logic from app.js file

```javascript
var mongoose = require('mongoose');
mongoose.connect('localhost:27017/shopping');
```
7. At the end of the file disconnect mongoose as a callback through for loop

```javascript
var done = 0;
for (var i = 0; i < products.length; i++) {
   products[i].save(function(err, result) {
      done++;
      if (done === products.length) {
         exit();
      }
   });
}

function exit() {
   mongoose.disconnect();
}
```
8. cd into seed directory and run product-seeder file in terminal

```javascript
node product-seeder.js
```
9. Check to see if seed data seeded correctly by opening mongo terminal

```git
use shopping // switch to shopping db 
db.products.find() // displays all data in products
```


## Loop product data
1. Require Product inside routes/index.js

```javascript
var Product = require('../models/product');
```
2. Fetch products by changing router.get

```javascript
router.get('/', function(req, res, next) {
   Product.find(function(err, docs) {
      var productChunks = [];
      var chunkSize = 3;
      for (var i = 0; i < docs.length; i += chunkSize) {
         productChunks.push(docs.slice(i, i + chunkSize));
      }
      res.render('shop/index', { title: 'Shopping Cart', products: productChunks });
   });
});
```
3. In views/shop/index.hbs remove all thumbnails but one. Restructure html as follows: 

```markup
{{# each products }}
   <div class="row">
      {{# each this }}
         <div class="col-sm-6 col-md-4">
            <div class="thumbnail">
               <img src="{{this.imagePath}}" class="img-responsive">
               <div class="caption">
                  <h3>{{this.title}}</h3>
                  <p class="description">{{this.description}}</p>

                  <div class="clearfix">
                     <div class="price pull-left">${{this.price}}.00</div>
                     <a href="#" class="btn btn-success pull-right" role="button">Buy Now</a>
                  </div>
               </div>
            </div>
         </div>
         {{/each}}
   </div>
   {{/each}}

```


## User Login
1. Create user folder in views directory
1. in user directory create files signup.hbs, signin.hbs & profile.hbs
1. Paste the following in signup.hbs

```markup
<div class="row">
   <div class="col-md-4 col-md-offset-4">
      <h1>Sign Up</h1>
      Validation Errors
      <form action="" method="post">
         <div class="form-group">
            <label for="email">E-Mail</label>
            <input type="text" name="email" id="email" class="form-control">
         </div>
         <div class="form-group">
            <label for="password">Password</label>
            <input type="password" name="password" id="password" class="form-control">
         </div>
         <button type="submit">Sign Up</button>
      </form>

   </div>

</div>
```
4. In models directory create a file called user.js
5. In user.js set requirements, schema and module export:

```javascript
var mongoose = require('mongoose');
var Schema = mongoose.Schema;

var userSchema = new Schema({
   email: {type: String, required: true},
   password: {type: String, required: true}
});

module.exports = mongoose.model('User', userSchema);
```
6. npm install 3rd party csrf protection package 

```git
npm install csurf --save
```
7. Require csurf in routes/index.js

```javascript
var csrf = require('csurf');

var csrfProtection = csrf();
```
8. Above module.exports = router at bottom of page create router.get for csrf

```javascript
router.get('/user/signup', function(req, res, next) {
   res.render('user/signup', {csrfToken: req.csrfToken()});
});
```
9. npm install

```git
npm install --save express-session
```
10. Require in app.js

```javascript
var session = require('express-session');
```
11. Add code  below app.use(cookieParser());

```javascript
app.use(session({secret: 'mysupersecret', resave: false, saveUninitialized: false}));
```
12. In routes/index.js file inclue router.use below var csrfProtection

```javascript
router.use(csrfProtection);
```
13. signup.hbs should be changed to the code below: 

```markup
 <div class="row">
   <div class="col-md-4 col-md-offset-4">
      <h1>Sign Up</h1>
      Validation Errors
      <form action="/user/signup" method="post">
         <div class="form-group">
            <label for="email">E-Mail</label>
            <input type="text" name="email" id="email" class="form-control">
         </div>
         <div class="form-group">
            <label for="password">Password</label>
            <input type="password" name="password" id="password" class="form-control">
         </div>
         <input type="hidden" name="_csrf" value="{{csrfToken}}">
         <button type="submit" class="btn btn-primary">Sign Up</button>
      </form>

   </div>

</div>
```
13. In routes/index.js above module.exports at bottom of the page add router.post:

```javascript
router.post('/user/signup', function(req, res, next) {
   res.redirect('/');
});
```


## Passport Authentication
1. npm install

```git
npm install --save passport
npm install --save bcrypt-nodejs
npm install --save connect-flash
npm install --save passport-local
```
2. require these pakages in app.js

```javascript
var passport = require('passport');
var flash = require('connect-flash');
```
3. after initializing session in app.use(session: 'mysupersecret add: 

```javascript
app.use(flash());
app.use(passport.initialize());
app.use(passport.session());
```
4. Create directory in project root called config
5. in config create passport.js
6. In models/user.js replace page code with the code below: 

```javascript
var mongoose = require('mongoose');
var Schema = mongoose.Schema;
var bcrypt = require('bcrypt-nodejs');

var userSchema = new Schema({
   email: {type: String, required: true},
   password: {type: String, required: true}
});

userSchema.methods.encryptPassword = function(password) {
   return bcrypt.hashSync(password, bcrypt.genSaltSync(5), null);
};

userSchema.methods.validPassword = function(password) {
   return bcrypt.compareSync(password, this.password);
}

module.exports = mongoose.model('User', userSchema);
```
7. Inside config/passport.js include the following code: 

```javascript
var passport = require('passport');
var User = require('../models/user');
var LocalStrategy = require('passport-local').Strategy;

passport.serializeUser(function(user, done) {
   done(null, user.id);
});

passport.deserializeUser(function(id, done) {
   User.findById(id, function(err, user) {
      done(err, user);
   });
});

passport.use('local.signup', new LocalStrategy({
   usernameField: 'email',
   passwordField: 'password',
   passReqToCallBack: true
}, function(req, email, password, done) {
   User.findOne({'email': email}, function(err, user) {
      if (err) {
         return done(err);
      }
      if (user) {
         return done(null, false, {message: 'Email is already in use'});
      }
      var newUser = new User();
      newUser.email = email;
      newUser.password = newUser.encryptPassword(password);
      newUser.save(function(err, result) {
         if (err) {
            return done(err);
         }
         return done(null, newUser);
      })
   });

}));
```
8. Inside of routes/index.js remove res.redirect('/'); from router.post above module.exports

```javascript
router.post('/user/signup', passport.authenticate('local.signup', {
   successRedirect: 'user/profile',
   failureRedirect: 'user/signup',
   failureFlash: true
}));
```
9. Inside of routes/index.js require passport

```javascript
var passport = require('passport');
```
10. Render user/profile above module.exports in index.js

```javascript
router.get('user/profile', function(req, res, next) {
   res.render('user/profile');
});
```
11. In app.js file under mongoose.connect add: 

```javascript
require('./config/passport');
```
































