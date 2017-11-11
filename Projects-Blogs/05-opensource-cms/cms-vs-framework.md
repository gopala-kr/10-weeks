
## CMS VS web-framework

The question in your case is whether to use a ready made CMS or to create your own system using a framework. The right answer depends on the following:

* budget
* number of users you will have (long term performance concerns)
* further maintenance
* total number of details (bells and whistles) you want to provide on the site
* implementation with third party/custom APIs
* special/custom features that require high level of freedom (example: StackOverflow reward points and badgets)
* As this is a question most of us face pretty often, here are cons and pros of a ready made CMS vs a framework:

**Ready made CMS**

Pros

* faster start and development time if your project generally fits in what the CMS provides
* available modules and themes
* backed up by community, meaning that new features, bugfixes, support, tutorials etc. will be provided to you free of charge
* unified set of standards - it's easier to continue working on an existing CMS site than to take someone else's custom application (this is relative, but the point is that in a site that uses an existing CMS most of the things/setup will be familiar to you while in a custom app the previous developer had more freedom)
* security is something you do not need to worry that much as in a custom app

Cons

* if your requirements are very specific, you will need to override the default workflow of the system; in some cases this can be tricky and will make you spend more time than to write your own
* redundant code in modules/plugins
* performance - a ready made CMS will rarely be as fast as a custom made application
* not suitable for every large website (unless you fit in almost everything that the CMS provides)
* steep learning curve in some cases (Typo3, Drupal)

**Custom application**

Pros

* it's up to you to define the structure and the logic of the application
* app design is made especially for the project you are working on - so there is no redundant code
* freedom to do anything you want

Cons

* expensive - in most cases you/your client will need much more money for a custom app
* further maintenance will be harder
* changes and modifications of the structure can be very time consuming
* if you aren't using a CMF you will have to reinvent the wheel in some aspects

**Bottom line**

Spend a couple of days and learn something about the CMSs out there, such as:

* Drupal
* WordPress
* Typo3 
* Joomla 
* SilverStripe
* MODX
* Concrete5


I think that any bigger and serious project, which will have at least 1-2 programmers to take care of the system at all times, should be custom. Exceptions are only if it fits exactly in what an existing CMS offers already.
