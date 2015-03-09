##Zen and the Art of Drupal Commerce Migration




###Andy Giles
####[@andyg5000](http://twitter.com/andyg5000)

History

  * Web Developer and Systems Administrator

  * Working with Drupal for around 5 years

Blue Oak Interactive

  * Working on Drupal exclusively

  * Drupal Commerce custom integrations

![logo](/images/logo.png "Logo")



###Commerce Experience

Drupal Commerce for 2 years

Shipping and payment gateway integrations

Drupal Commerce Migration Experience

  * OSCommerce

  * Ubercart & D2D

  * Flat file

  * MSSQL



Migrate Miagrane module
  Migration base claseses
    User, Node, Entity, Term
  Migration maps
    Source ID (primary keys)
    Destination ID (primary keys)
  Import/Rollback



Source data
  Schemas
    Users
    Products
    Orders
    Line Items



Destination data
  Schemas
    Users
    Products
    Nodes
    Files/Images
    Profiles
    Orders
    Line Items
      Product
      Shipping
      Coupon/Discount
      Tax
    Payment Transactions



Helpers
  Migrate extras
  Commerce migrate
  Date Migrate
  Other field modules
  Custom source and destination handlers



Structure
  Abstract Base Class
    Set up common settings & logic applicable to all classes
    Common field mappings
    Source conntection
    Normalization and cleanup functions
      Datatype conversion
      Data mapping
  Abstract Destination Classes
    Set up common settings & logic applicable to destination classes
    Setting common fields on all entities (ie: node->title).
  Entity Classes
    Build migrate map, source, destination, and field mappings
    Field Mappings
      Source Migrations
    prepareRow(), prepare(), and complete()



Edge Cases
  User dedupe
  Normalization
    Dealing with raw user input
    SELECT DISTICT From Source and create maps.
    ->separator(',')
  Duplicate source records
  Files in volume!
  Dates



Commerce Tidbits of Joy and Misery
  Migrating order entity first resets order total to 0 (@see order.inc)
  Line items entities and order line item reference fields
  Load product by SKU
  Field mappings for commerce customer address (addressfield)
  includes/iso.inc and _country_get_predefined_list()

  Common Problems
    HOOKS! node_update
    No line items on order
    $0 order total
    Compounding line items price on order total
    Line items without products



/**
 * Notes
 */

Ask Ryan about the tax handlers on commerce_price fields and use with migration.
Using stub nodes.
Check into ->separator() and ->sourceMigration()
