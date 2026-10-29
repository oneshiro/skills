---
date: 2026-10-29
project: myasm
tags:
  - myasm
  - yii
  - yii1
  - skill
  - guide-examples
---

# Yii 1.x Guide Examples

Source dump of Yii 1 official guide / wiki examples. Search by section title or `Source:` path. Used by skill `yii` (see `../SKILL.md`).

---
### Example URL in get format

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

This is an example of a URL in the default 'get' format, where parameters appear in the query string. It is not user-friendly due to non-word characters.

```text
/index.php?r=post/read&id=100
```

--------------------------------

### Example URL in path format

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

This is an example of a URL in the 'path' format, which eliminates the query string and puts GET parameters into the path info part. It is cleaner and more self-explanatory.

```text
/index.php/post/read/id/100
```

--------------------------------

### Example console command class with actions

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Example command class defining index and init actions.

```php
class SitemapCommand extends CConsoleCommand
{
    public function actionIndex($type, $limit=5) { ... }
    public function actionInit() { ... }
}
```

--------------------------------

### Generate translation reports for Guide, Blog, and framework views

Source: https://github.com/yiisoft/yii/wiki/Documentation-translation-guidelines

Run these commands to check if your translation is up to date and get info about what should be updated. The example is for Russian translation. After running, you'll have three reports; do not push them into your repository. Ensure git is installed and added to PATH.

```shell
build translations report --sourcePath="../docs/guide" --translationPath="../docs/guide/ru" --title="Russian guide translation report" > report_guide_ru.html
```

```shell
build translations report --sourcePath="../docs/blog" --translationPath="../docs/blog/ru" --title="Russian blog translation report" > report_blog_ru.html
```

```shell
build translations report --sourcePath="../framework/views" --translationPath="../framework/views/ru" --title="Russian framework views translation report" > report_views_ru.html
```

--------------------------------

### Accessing Component Properties

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.component.txt

Shows how to read and write a component property using the property access syntax. The example gets 'textWidth' and sets 'enableCaching'.

```php
$width=$component->textWidth;     // get the textWidth property
$component->enableCaching=true;   // set the enableCaching property
```

--------------------------------

### Query examples with USE INDEX in joinOptions

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows how to use 'joinOptions' in relation definitions to add USE INDEX clauses for query optimization. Includes three findAll examples with different joinOptions configurations.

```php
$users=User::model()->findAll(array(
	'select'=>'t.id,t.name',
	'with'=>array(
		'posts'=>array(
			'alias'=>'p',
			'select'=>'p.id,p.title',
			'joinOptions'=>'USE INDEX(post__user)',
		),
	),
));

$posts=Post::model()->findAll(array(
	'select'=>'t.id,t.title',
	'with'=>array(
		'tags'=>array(
			'alias'=>'a',
			'select'=>'a.id,a.name',
			'joinOptions'=>'USE INDEX(post_tag__tag) USE INDEX(post_tag__post)',
		),
	),
));

$posts=Post::model()->findAll(array(
	'select'=>'t.id,t.title',
	'with'=>array(
		'tags'=>array(
			'alias'=>'a',
			'select'=>'a.id,a.name',
			'joinOptions'=>array(
				'USE INDEX(post_tag__tag) USE INDEX(post_tag__post)',
				'USE INDEX(tag__name)',
			),
		),
	),
));
```

--------------------------------

### createIndex() example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Creates an index on a single column. The example shows the generated SQL comment and the method call.

```php
// CREATE INDEX `idx_username` ON `tbl_user` (`username`)
createIndex('idx_username', 'tbl_user', 'username')
```

--------------------------------

### Usage examples for HAS_MANY through

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows how to use the relations defined with 'through' to fetch groups with users, roles, and comments. Includes examples for finding all groups with users, all groups with users and roles, and getting users/roles/comments for a specific group.

```php
// get all groups with all users
$groups=Group::model()->with('users')->findAll();

// get all groups with all corresponding users and roles
$groups=Group::model()->with('roles','users')->findAll();

// get all users and roles where group ID is 1
$group=Group::model()->findByPk(1);
$users=$group->users;
$roles=$group->roles;

// get all comments where group ID is 1
$group=Group::model()->findByPk(1);
$comments=$group->comments;
```

--------------------------------

### URL rule set example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

Example rule set with three rules for posts and post reading. Demonstrates how rules map routes and parameters to URLs.

```php
array(
	'posts'=>'post/list',
	'post/<id:\d+>'=>'post/read',
	'post/<year:\d{4}>/<title>'=>'post/read',
)
```

--------------------------------

### join() usage examples

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Examples of using join() and leftJoin(). The join condition syntax is the same as where(). Each join call appends to previous ones.

```php
// JOIN `tbl_profile` ON user_id=id
join('tbl_profile', 'user_id=id')
// LEFT JOIN `pub`.`tbl_profile` `p` ON p.user_id=id AND type=1
leftJoin('pub.tbl_profile p', 'p.user_id=id AND type=:type', array(':type'=>1))
```

--------------------------------

### Access the Guide online for testing translations

Source: https://github.com/yiisoft/yii/wiki/Documentation-translation-guidelines

Use this URL to access the Guide via the included application for testing translations. Point your webserver root to the docs directory first.

```url
http://hostname/index.php?r=guide
```

--------------------------------

### Create table example with abstract types

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Example of creating a table named tbl_user with columns id, username, and location. Uses abstract types 'pk', 'string', and 'point', and appends 'ENGINE=InnoDB' as options. The generated SQL is shown in comments.

```php
// CREATE TABLE `tbl_user` (
//     `id` int(11) NOT NULL AUTO_INCREMENT PRIMARY KEY,
//     `username` varchar(255) NOT NULL,
//     `location` point
// ) ENGINE=InnoDB
createTable('tbl_user', array(
	'id' => 'pk',
	'username' => 'string NOT NULL',
	'location' => 'point',
), 'ENGINE=InnoDB')
```

--------------------------------

### limit() and offset() usage examples

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Examples of using limit() and offset() to set LIMIT and OFFSET clauses. The examples show limit(10), limit(10, 20), and offset(20).

```php
// LIMIT 10
limit(10)
// LIMIT 10 OFFSET 20
limit(10, 20)
// OFFSET 20
offset(20)
```

--------------------------------

### insert() example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Builds and executes an INSERT statement with parameter binding for the values.

```php
// build and execute the following SQL:
// INSERT INTO `tbl_user` (`name`, `email`) VALUES (:name, :email)
$command->insert('tbl_user', array(
	'name'=>'Tester',
	'email'=>'tester@example.com',
));
```

--------------------------------

### from() usage examples

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Examples of using from() with various table specifications: string, array, schema prefixes, aliases, and sub-queries. The comments show the resulting SQL.

```php
// FROM `tbl_user`
from('tbl_user')
// FROM `tbl_user` `u`, `public`.`tbl_profile` `p`
from('tbl_user u, public.tbl_profile p')
// FROM `tbl_user`, `tbl_profile`
from(array('tbl_user', 'tbl_profile'))
// FROM `tbl_user`, (select * from tbl_profile) p
from(array('tbl_user', '(select * from tbl_profile) p'))
```

--------------------------------

### Migration example creating a news table

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Example migration that creates a news table with id, title, and content columns. The down() method drops the table to revert the migration.

```php
class m101129_185401_create_news_table extends CDbMigration
{
	public function up()
	{
		$this->createTable('tbl_news', array(
			'id' => 'pk',
			'title' => 'string NOT NULL',
			'content' => 'text',
		));
	}

	public function down()
	{
		$this->dropTable('tbl_news');
	}
}
```

--------------------------------

### Configuring widget properties with initial values

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.view.txt

This example shows how to configure a widget by passing an array of initial property values. The array keys are property names and values are the initial values.

```php
<?php
$this->widget('CMaskedTextField',array(
	'mask'=>'99/99/9999'
));
?>
```

--------------------------------

### select() usage examples

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Examples of using select() with various column specifications: string, array, aliases, and DB expressions. The comments show the resulting SQL.

```php
// SELECT *
select()
// SELECT `id`, `username`
select('id, username')
// SELECT `tbl_user`.`id`, `username` AS `name`
select('tbl_user.id, username as name')
// SELECT `id`, `username`
select(array('id', 'username'))
// SELECT `id`, count(*) as num
select(array('id', 'count(*) as num'))
```

--------------------------------

### where() usage examples

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Multiple examples of using where() with different operators: string conditions, parameter binding, and/or, in, not in, like, not like, or like, or not like. Each example shows the generated SQL condition.

```php
// WHERE id=1 or id=2
where('id=1 or id=2')
// WHERE id=:id1 or id=:id2
where('id=:id1 or id=:id2', array(':id1'=>1, ':id2'=>2))
// WHERE id=1 OR id=2
where(array('or', 'id=1', 'id=2'))
// WHERE id=1 AND (type=2 OR type=3)
where(array('and', 'id=1', array('or', 'type=2', 'type=3')))
// WHERE `id` IN (1, 2)
where(array('in', 'id', array(1, 2))
// WHERE `id` NOT IN (1, 2)
where(array('not in', 'id', array(1,2)))
// WHERE `name` LIKE '%Qiang%'
where(array('like', 'name', '%Qiang%'))
// WHERE `name` LIKE '%Qiang' AND `name` LIKE '%Xue'
where(array('like', 'name', array('%Qiang', '%Xue')))
// WHERE `name` LIKE '%Qiang' OR `name` LIKE '%Xue'
where(array('or like', 'name', array('%Qiang', '%Xue')))
// WHERE `name` NOT LIKE '%Qiang%'
where(array('not like', 'name', '%Qiang%'))
// WHERE `name` NOT LIKE '%Qiang%' OR `name` NOT LIKE '%Xue%'
where(array('or not like', 'name', array('%Qiang%', '%Xue%')))
```

--------------------------------

### Install Gii module in main.php config

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/prototype.scaffold.txt

Add this configuration to /wwwroot/blog/protected/config/main.php to enable the Gii module. It sets a password for accessing the module. Remove this code on production machines; only use it on development machines.

```php
return array(
	......
	'import'=>array(
		'application.models.*',
		'application.components.*',
	),

	'modules'=>array(
		'gii'=>array(
			'class'=>'system.gii.GiiModule',
			'password'=>'pick up a password here',
		),
	),
);
```

--------------------------------

### Filter class example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.controller.txt

Shows how to define a filter as a class extending CFilter, with preFilter and postFilter methods.

```php
class PerformanceFilter extends CFilter
{
	protected function preFilter($filterChain)
	{
		// logic being applied before the action is executed
		return true; // false if the action should not be executed
	}

	protected function postFilter($filterChain)
	{
		// logic being applied after the action is executed
	}
}
```

--------------------------------

### Example theme directory structure

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

Shows the directory organization for an application with two themes, basic and fancy. Each theme contains views, layouts, and site views mirroring the application's view structure.

```text
WebRoot/
	assets
	protected/
		.htaccess
		components/
		controllers/
		models/
		views/
			layouts/
				main.php
			site/
				index.php
	themes/
		basic/
			views/
				.htaccess
				layouts/
					main.php
				site/
					index.php
		fancy/
			views/
				.htaccess
				layouts/
					main.php
				site/
					index.php
```

--------------------------------

### update() example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Builds and executes an UPDATE statement with parameter binding for the WHERE clause.

```php
// build and execute the following SQL:
// UPDATE `tbl_user` SET `name`=:name WHERE id=:id
$command->update('tbl_user', array(
	'name'=>'Tester',
), 'id=:id', array(':id'=>1));
```

--------------------------------

### dropIndex() example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Drops an index. The example shows the generated SQL comment and the method call.

```php
// DROP INDEX `idx_username` ON `tbl_user`
dropIndex('idx_username', 'tbl_user')
```

--------------------------------

### Migration using safeUp() and safeDown()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Shows the recommended way to get transaction support by implementing safeUp() and safeDown() instead of up() and down(). Yii automatically starts a transaction and rolls back on error.

```php
class m101129_185401_create_news_table extends CDbMigration
{
	public function safeUp()
	{
		$this->createTable('tbl_news', array(
			'id' => 'pk',
			'title' => 'string NOT NULL',
			'content' => 'text',
		));
	}

	public function safeDown()
	{
		$this->dropTable('tbl_news');
	}
}
```

--------------------------------

### Usage example for HAS_ONE through

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows how to use the 'address' relation defined with 'through' to get the address of a user with ID 1.

```php
// get address of a user whose ID is 1
$user=User::model()->findByPk(1);
$address=$user->address;
```

--------------------------------

### delete() example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Builds and executes a DELETE statement with parameter binding for the WHERE clause.

```php
// build and execute the following SQL:
// DELETE FROM `tbl_user` WHERE id=:id
$command->delete('tbl_user', 'id=:id', array(':id'=>1));
```

--------------------------------

### selectDistinct() example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Example of using selectDistinct() with 'id, username' which generates the SQL: SELECT DISTINCT `id`, `username`.

```php
SELECT DISTINCT `id`, `username`
```

--------------------------------

### addForeignKey example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Adds a foreign key constraint. Parameters include $name, $table, $columns, $refTable, $refColumns, $delete, and $update. The example shows the SQL comment and the method call.

```php
// ALTER TABLE `tbl_profile` ADD CONSTRAINT `fk_profile_user_id`
// FOREIGN KEY (`user_id`) REFERENCES `tbl_user` (`id`)
// ON DELETE CASCADE ON UPDATE CASCADE
addForeignKey('fk_profile_user_id', 'tbl_profile', 'user_id',
	'tbl_user', 'id', 'CASCADE', 'CASCADE')
```

--------------------------------

### group() usage examples

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Examples of using group() with a string and an array. Column names are quoted unless they contain parentheses.

```php
// GROUP BY `name`, `id`
group('name, id')
// GROUP BY `tbl_profile`.`name`, `id`
group(array('tbl_profile.name', 'id'))
```

--------------------------------

### Executing a query with queryAll()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Example of executing a query built with the query builder using queryAll(). This retrieves all rows from the tbl_user table.

```php
$users = Yii::app()->db->createCommand()
	->select('*')
	->from('tbl_user')
	->queryAll();
```

--------------------------------

### dropTable example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Drops a table. The $table parameter is quoted properly. The example shows the SQL comment and the method call.

```php
// DROP TABLE `tbl_user`
dropTable('tbl_user')
```

--------------------------------

### URL rule with pattern as array element

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

Starting from version 1.1.7, a rule can be specified with the pattern as an array element, allowing multiple rules with the same pattern. This example shows the format.

```php
array('route1', 'pattern'=>'pattern1', 'urlSuffix'=>'.xml', 'caseSensitive'=>false)
```

--------------------------------

### Fixture data for Post table in Post.php

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/test.fixture.txt

Example fixture file for the 'Post' table, returning an array of rows with aliases 'sample1' and 'sample2'. The 'id' column is omitted because it is auto-incremental.

```php
<?php
return array(
	'sample1'=>array(
		'title'=>'test post 1',
		'content'=>'test post content 1',
		'createTime'=>1230952187,
		'authorId'=>1,
	),
	'sample2'=>array(
		'title'=>'test post 2',
		'content'=>'test post content 2',
		'createTime'=>1230952287,
		'authorId'=>1,
	),
);
```

--------------------------------

### order() usage examples

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Examples of using order() with a string and an array. The method automatically quotes column names unless they contain parentheses (DB expression).

```php
// ORDER BY `name`, `id` DESC
order('name, id desc')
// ORDER BY `tbl_profile`.`name`, `id` DESC
order(array('tbl_profile.name', 'id desc'))
```

--------------------------------

### Translate blockquote tokens in Guide and Blog

Source: https://github.com/yiisoft/yii/wiki/Documentation-translation-guidelines

Do not translate the tokens like '> Note:' or '> Tip:'. Instead, append the translation of the token word and use '|' as the separator. The example shows the format for 'note' and 'tip'.

```markdown
> Note|translation for 'note': ....


> Tip|translation for 'tip': ......
```

--------------------------------

### Class constants example

Source: https://github.com/yiisoft/yii/wiki/Core-framework-code-style

Shows the required all-uppercase with underscore separators for class constants, as used in Yii core classes.

```php
<?php
class Foo
{
    const VERSION='1.0';
    const DATE_APPROVED='2012-06-01';
}
```

--------------------------------

### HAS_ONE through example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Defines a User model with a 'profile' relation and an 'address' relation that uses 'through' to get the address via the profile. This allows accessing $user->address directly.

```php
class User extends CActiveRecord
{
	...
	public function relations()
	{
		return array(
			'profile'=>array(self::HAS_ONE,'Profile','user_id'),
			'address'=>array(
				self::HAS_ONE,'Address',array('id'=>'profile_id'),
					'through'=>'profile'
			),
		);
	}
}
```

--------------------------------

### Create a CDbCommand instance

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Creates a new CDbCommand instance using the DB connection. This is the starting point for building queries with the Query Builder.

```php
$command = Yii::app()->db->createCommand();
```

--------------------------------

### SQL to create the tbl_post table

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Defines the database table used in the examples. For MySQL, replace AUTOINCREMENT with AUTO_INCREMENT.

```sql
CREATE TABLE tbl_post (
	id INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
	title VARCHAR(128) NOT NULL,
	content TEXT NOT NULL,
	create_time INTEGER NOT NULL
);
```

--------------------------------

### dropForeignKey example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Drops a foreign key constraint. The $name and $table parameters are used. The example shows the method call.

```php
dropForeignKey('fk_profile_user_id', 'tbl_profile')
```

--------------------------------

### union() usage example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Example of using union() to append a SELECT statement. Calling union() multiple times appends multiple SQLs.

```php
// UNION (select * from tbl_profile)
union('select * from tbl_profile')
```

--------------------------------

### having() usage examples

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Examples of using having() with a string condition and an array condition. The array form uses the 'or' operator.

```php
// HAVING id=1 or id=2
having('id=1 or id=2')
// HAVING id=1 OR id=2
having(array('or', 'id=1', 'id=2'))
```

--------------------------------

### truncateTable example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Truncates a table. The $table parameter is quoted properly. The example shows the SQL comment and the method call.

```php
// TRUNCATE TABLE `tbl_user`
truncateTable('tbl_user')
```

--------------------------------

### Relational query without selecting related models

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Use with() with select=>false and a join condition to filter by related models without loading them. This example gets users who have published posts.

```php
$users=User::model()->with(array(
	'posts'=>array(
		// we don't want to select posts
		'select'=>false,
		// but want to get only users with published posts
		'joinType'=>'INNER JOIN',
		'condition'=>'posts.published=1',
	),
))->findAll();
```

--------------------------------

### Cache tag example: profile fragment

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.prado.txt

Example of a cache tag with a duration property, and the corresponding translated PHP code using beginCache and endCache.

```php
<cache:profile duration={3600}>
	// user profile information here
</cache:profile >
```

```php
<?php if($this->beginCache('profile', array('duration'=>3600))): ?>
	// user profile information here
<?php $this->endCache(); endif; ?>
```

--------------------------------

### dropColumn example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Drops a column from a table. The $table and $column parameters are used; both names are quoted. The example shows the SQL comment and the method call.

```php
// ALTER TABLE `tbl_user` DROP COLUMN `location`
dropColumn('tbl_user', 'location')
```

--------------------------------

### Access the Blog tutorial online for testing translations

Source: https://github.com/yiisoft/yii/wiki/Documentation-translation-guidelines

Use this URL to access the Blog tutorial via the included application for testing translations. Point your webserver root to the docs directory first.

```url
http://hostname/index.php?r=blog
```

--------------------------------

### Usage example for self-referencing through relation

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows how to retrieve all students taught by a specific teacher using the 'students' relation defined in the User model.

```php
// get all students taught by teacher whose ID is 1
$teacher=User::model()->findByPk(1);
$students=$teacher->students;
```

--------------------------------

### Enter console directory and show help

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Navigate to the protected directory and display a list of available console commands.

```bash
cd protected
yiic help
```

--------------------------------

### Usage example for console-normalizer

Source: https://github.com/yiisoft/yii/blob/master/framework/vendors/console-normalizer/README.md

Include the normalizeconsole.min.js script and use console methods like group, time, log, info, warn, error, timeEnd, and groupEnd. This example shows that console.log does not blow up if IE console is closed, and console.log.apply does not cause an Invocation error.

```html
<script src="normalizeconsole.min.js"></script>
    <script>
        console.group('Play around');
        console.time('timer');

        console.log('hello'); // does not blow up if IE console is closed

        console.log.apply(console, ['one', 'two', 'three']); // does not cause an Invocation error

        typeof(console.log); // function (some things you shouldn't have to say...)

        console.info();
        console.warn();
        console.error();

        console.timeEnd('timer');
        console.groupEnd();
    </script>
```

--------------------------------

### Configure migrate command globally in console config

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Modify the console application configuration file to set migration options globally. The example sets migrationPath, migrationTable, connectionID, and templateFile.

```php
return array(
	'commandMap'=>array(
		'migrate'=>array(
			'class'=>'system.cli.commands.MigrateCommand',
			'migrationPath'=>'application.migrations',
			'migrationTable'=>'tbl_migration',
			'connectionID'=>'db',
			'templateFile'=>'application.migrations.template',
		),
	),
);
```

--------------------------------

### Layout view with header and footer

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.view.txt

This is an example of a layout view that contains common UI parts. The $content variable holds the rendering result of the view that is being decorated.

```php
......header here......
<?php echo $content; ?>
......footer here......
```

--------------------------------

### Rename table example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Example of renaming table tbl_users to tbl_user. The comment shows the generated SQL: RENAME TABLE `tbl_users` TO `tbl_user`.

```php
// RENAME TABLE `tbl_users` TO `tbl_user`
renameTable('tbl_users', 'tbl_user')
```

--------------------------------

### Create web application with configuration file

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.application.txt

Pass the configuration file name to Yii::createWebApplication() to create the application instance. Usually done in the entry script.

```php
$app=Yii::createWebApplication($configFile);
```

--------------------------------

### Massive Assignment Example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Shows how to massively assign user-submitted data to a model's attributes using the attributes property.

```php
$model=new LoginForm;
if(isset($_POST['LoginForm']))
	$model->attributes=$_POST['LoginForm'];
```

--------------------------------

### addColumn example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Adds a new column to a table. The $table, $column, and $type parameters are used; the table and column names are quoted. The example shows the SQL comment and the method call.

```php
// ALTER TABLE `tbl_user` ADD `email` varchar(255) NOT NULL
addColumn('tbl_user', 'email', 'string NOT NULL')
```

--------------------------------

### CHANGELOG entry for enhancement

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Example of a CHANGELOG entry for an enhancement. Replace #999 with the issue number and add a description and your name.

```text
Enh #999: a description of the enhancement (Your Name)
```

--------------------------------

### Create skeleton application with yiic

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/start.testdrive.txt

Command to create a skeleton application under /wwwroot/blog. The output shows the prompt and confirmation.

```bash
% /wwwroot/yii/framework/yiic webapp /wwwroot/blog
Create a Web application under '/wwwroot/blog'? [Yes|No]y
......
```

--------------------------------

### Generated MySQL queries with USE INDEX

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows the SQL queries generated by the previous PHP examples, including USE INDEX clauses for optimizing joins.

```sql
SELECT
	`t`.`id` AS `t0_c0`, `t`.`name` AS `t0_c1`,
	`p`.`id` AS `t1_c0`, `p`.`title` AS `t1_c2`
FROM `tbl_user` `t`
LEFT OUTER JOIN `tbl_post` `p`
	USE INDEX(post__user) ON (`p`.`user_id`=`t`.`id`);

SELECT
	`t`.`id` AS `t0_c0`, `t`.`title` AS `t0_c2`,
	`a`.`id` AS `t1_c0`, `a`.`name` AS `t1_c1`
FROM `tbl_post` `t`
LEFT OUTER JOIN `tbl_post_tag` `tags_a`
	USE INDEX(post_tag__tag) USE INDEX(post_tag__post) ON (`t`.`id`=`tags_a`.`post_id`)
LEFT OUTER JOIN `tbl_tag` `a` ON (`a`.`id`=`tags_a`.`tag_id`);

SELECT
	`t`.`id` AS `t0_c0`, `t`.`title` AS `t0_c2`,
	`a`.`id` AS `t1_c0`, `a`.`name` AS `t1_c1`
FROM `tbl_post` `t`
LEFT OUTER JOIN `tbl_post_tag` `tags_a`
	USE INDEX(post_tag__tag) USE INDEX(post_tag__post) ON (`t`.`id`=`tags_a`.`post_id`)
LEFT OUTER JOIN `tbl_tag` `a` ON (`a`.`id`=`tags_a`.`tag_id`);
```

--------------------------------

### Extend CTabView for custom CSS

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.create.txt

This example shows how to extend CTabView to set a default CSS file, publishing it as an asset if not explicitly configured by the user.

```php
class MyTabView extends CTabView
{
	public function init()
	{
		if($this->cssFile===null)
		{
			$file=dirname(__FILE__).DIRECTORY_SEPARATOR.'tabview.css';
			$this->cssFile=Yii::app()->getAssetManager()->publish($file);
		}
		parent::init();
	}
}
```

--------------------------------

### Property naming example

Source: https://github.com/yiisoft/yii/wiki/Core-framework-code-style

Illustrates camelCase property names with private properties prefixed by an underscore, as required by the Yii core style.

```php
<?php
class Foo
{
    public $publicProp;
    protected $protectedProp;
    private $_privateProp;
}
```

--------------------------------

### Predefined Validator Usage Examples

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Examples of using predefined validators in Yii validation rules, including required, length, compare, and authenticate validators.

```php
// username is required
array('username', 'required'),
// username must be between 3 and 12 characters
array('username', 'length', 'min'=>3, 'max'=>12),
// when in register scenario, password must match password2
array('password', 'compare', 'compareAttribute'=>'password2', 'on'=>'register'),
// when in login scenario, password must be authenticated
array('password', 'authenticate', 'on'=>'login'),
```

--------------------------------

### Component tag example: CCaptcha widget

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.prado.txt

Example of a component tag for the CCaptcha widget. The showRefreshButton property uses {false} to denote a boolean false, not a string.

```php
<com:CCaptcha captchaAction="captcha" showRefreshButton={false} />
```

```php
<?php $this->widget('CCaptcha', array(
	'captchaAction'=>'captcha',
	'showRefreshButton'=>false)); ?>
```

--------------------------------

### URL rule with custom options

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

A URL rule can be specified with custom options like 'urlSuffix' and 'caseSensitive'. This example shows a rule with a pattern, route, and options.

```php
'pattern1'=>array('route1', 'urlSuffix'=>'.xml', 'caseSensitive'=>false)
```

--------------------------------

### Configure db component for SQLite in main.php

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/prototype.database.txt

Use this configuration in /wwwroot/blog/protected/config/main.php to set up the 'db' component with a SQLite connection string and a table prefix. The 'tablePrefix' property enables the use of {{post}} tokens in SQL statements, which are translated to tbl_post.

```php
return array(
	......
	'components'=>array(
		......
		'db'=>array(
			'connectionString'=>'sqlite:/wwwroot/blog/protected/data/blog.db',
			'tablePrefix'=>'tbl_',
		),
	),
	......
);
```

--------------------------------

### dropForeignKey() example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Drops a foreign key constraint. The $name parameter is the constraint name, $table is the table name. The query builder quotes both properly. Example shows the generated SQL comment and the method call.

```php
// ALTER TABLE `tbl_profile` DROP FOREIGN KEY `fk_profile_user_id`
dropForeignKey('fk_profile_user_id', 'tbl_profile')
```

--------------------------------

### Defining an Event Method

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.component.txt

Shows how to define an event method 'onClicked' that raises the event. The method name starts with 'on'.

```php
public function onClicked($event)
{
	$this->raiseEvent('onClicked', $event);
}
```

--------------------------------

### Binding parameters with bindParam to prevent SQL injection

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.dao.txt

Illustrates how to prepare an SQL statement with named placeholders and bind parameters using bindParam(). Parameters are automatically quoted by the database driver, so no manual quoting is needed. Binding must occur before execution. The example shows reusing the same command with different parameter values.

```php
// an SQL with two placeholders ":username" and ":email"
$sql="INSERT INTO tbl_user (username, email) VALUES(:username,:email)";
$command=$connection->createCommand($sql);
// replace the placeholder ":username" with the actual username value
$command->bindParam(":username",$username,PDO::PARAM_STR);
// replace the placeholder ":email" with the actual email value
$command->bindParam(":email",$email,PDO::PARAM_STR);
$command->execute();
// insert another row with a new set of parameters
$command->bindParam(":username",$username2,PDO::PARAM_STR);
$command->bindParam(":email",$email2,PDO::PARAM_STR);
$command->execute();
```

--------------------------------

### Building an authorization hierarchy with authManager

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/ro/topics.auth.txt

Creates operations, tasks, and roles, establishes parent-child relationships, and assigns roles to users. Demonstrates the use of createOperation, createTask, createRole, addChild, and assign methods. The example includes a business rule for the updateOwnPost task.

```php
$auth=Yii::app()->authManager;

$auth->createOperation('createPost','create a post');
$auth->createOperation('readPost','read a post');
$auth->createOperation('updatePost','update a post');
$auth->createOperation('deletePost','delete a post');

$bizRule='return Yii::app()->user->id==$params["post"]->authID;';
$task=$auth->createTask('updateOwnPost','update a post by author himself',$bizRule);
$task->addChild('updatePost');

$role=$auth->createRole('reader');
$role->addChild('readPost');

$role=$auth->createRole('author');
$role->addChild('reader');
$role->addChild('createPost');
$role->addChild('updateOwnPost');

$role=$auth->createRole('editor');
$role->addChild('reader');
$role->addChild('updatePost');

$role=$auth->createRole('admin');
$role->addChild('editor');
$role->addChild('author');
$role->addChild('deletePost');

$auth->assign('reader','readerA');
$auth->assign('author','authorB');
$auth->assign('editor','editorC');
$auth->assign('admin','adminD');
```

--------------------------------

### renameColumn example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Renames a column in a table. The $table, $name, and $newName parameters are used; table and column names are quoted. The example shows the SQL comment and the method call.

```php
// ALTER TABLE `tbl_users` CHANGE `name` `username` varchar(255) NOT NULL
renameColumn('tbl_user', 'name', 'username')
```

--------------------------------

### alterColumn example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Alters a column definition. The $table, $column, and $type parameters are used; table and column names are quoted. The example shows the SQL comment and the method call.

```php
// ALTER TABLE `tbl_user` CHANGE `username` `username` varchar(255) NOT NULL
alterColumn('tbl_user', 'username', 'string NOT NULL')
```

--------------------------------

### Global widget customization example: CLinkPager with maxButtonCount and cssFile

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

Shows how to create a CLinkPager widget with custom initial properties (maxButtonCount=5, cssFile=false) directly in a view. This is the baseline customization that can be replaced by global configuration.

```php
$this->widget('CLinkPager', array(
	'pages'=>$pagination,
    'maxButtonCount'=>5,
    'cssFile'=>false,
));
```

--------------------------------

### Using transactions with beginTransaction, commit, and rollback

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.dao.txt

Shows the recommended transaction workflow: begin a transaction, execute queries, commit on success, and rollback on exception. Updates are not visible to the outside world until commit. The catch block rolls back the transaction if any query fails.

```php
$transaction=$connection->beginTransaction();
try
{
	$connection->createCommand($sql1)->execute();
	$connection->createCommand($sql2)->execute();
	//.... other SQL executions
	$transaction->commit();
}
catch(Exception $e) // an exception is raised if a query fails
{
	$transaction->rollback();
}
```

--------------------------------

### Short PHP tags: expression and statement examples

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.prado.txt

Shows the source syntax for short PHP tags and the translated PHP code. The expression tag becomes echo, and the statement tag becomes a foreach loop.

```php
<%= CHtml::textField($name,'value'); %>
<% foreach($models as $model): %>
```

```php
<?php echo CHtml::textField($name,'value'); ?>
<?php foreach($models as $model): ?>
```

--------------------------------

### Including the number in plural output

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.i18n.txt

Shows how to include the number in the plural output using the {n} placeholder. The example prints '1 cucumber'.

```php
echo Yii::t('test', '{n} cucumber|{n} cucumbers', 1);
```

--------------------------------

### Choice format example with plural forms

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.i18n.txt

Example of a translated message using choice format for plural forms. When calling Yii::t() with the number 2, it returns 'many books' because the expression 'n>1' evaluates to true.

```php
'n==1#one book|n>1#many books'
```

```php
Yii::t('app', 'n==1#one book|n>1#many books', array(1));
//or since 1.1.6
Yii::t('app', 'n==1#one book|n>1#many books', 1);
```

--------------------------------

### Login and logout actions using UserIdentity

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.auth.txt

Shows how to create a UserIdentity with submitted credentials, call authenticate(), and log the user in via Yii::app()->user->login() on success or display the error message on failure. Also demonstrates logging out with Yii::app()->user->logout().

```php
// Login a user with the provided username and password.
$identity=new UserIdentity($username,$password);
if($identity->authenticate())
	Yii::app()->user->login($identity);
else
	echo $identity->errorMessage;
......
// Logout the current user
Yii::app()->user->logout();
```

--------------------------------

### CHANGELOG entry for bug fix

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Example of a CHANGELOG entry for a bug fix. Replace #999 with the issue number and add a description and your name.

```text
Bug #999: a description of the bug fix (Your Name)
```

--------------------------------

### Retrieving the generated SQL with getText()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Example of retrieving the SQL statement of a query using the 'text' property. Bound parameters can be retrieved via the params property.

```php
$sql = Yii::app()->db->createCommand()
	->select('*')
	->from('tbl_user')
	->text;
```

--------------------------------

### Run migrate with command line options

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Execute the migrate command with options specified in the format --option=value. Boolean options like interactive require 1 or 0.

```bash
yiic migrate up --option1=value1 --option2=value2 ...
```

```bash
yiic migrate up --migrationPath=ext.forum.migrations
```

```bash
yiic migrate --interactive=0
```

--------------------------------

### Implement an ActiveRecord behavior

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.create.txt

This example demonstrates a custom behavior extending CActiveRecordBehavior that automatically updates create_time or update_time attributes during the save process.

```php
class TimestampBehavior extends CActiveRecordBehavior
{
	public function beforeSave($event)
	{
		if($this->owner->isNewRecord)
			$this->owner->create_time=time();
		else
			$this->owner->update_time=time();
	}
}
```

--------------------------------

### Declaring Safe Attributes with Scenarios

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Example validation rules that declare safe attributes for login and register scenarios.

```php
array('username', 'password', 'required', 'on'=>'login, register'),
array('email', 'required', 'on'=>'register'),
```

--------------------------------

### Parameterized route rules with named parameters

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

Defines URL rules with named parameters `_c` and `_a` to match controller and action IDs. The rules parse URLs like `/index.php/post/123/create` into route `post/create` with GET parameter `id=123`, and create URLs like `/index.php/comments?page=2` from route `comment/list` with GET parameter `page=2`.

```php
array(
	'<_c:(post|comment)>/<id:\d+>/<_a:(create|update|delete)>' => '<_c>/<_a>',
	'<_c:(post|comment)>/<id:\d+>' => '<_c>/read',
	'<_c:(post|comment)>s' => '<_c>/list',
)
```

--------------------------------

### Massive Assignment in Login and Register Scenarios

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Shows how to perform massive assignment in login and register scenarios using the User model.

```php
// in login scenario
$model=new User('login');
if(isset($_POST['User']))
	$model->attributes=$_POST['User'];

// in register scenario
$model=new User('register');
if(isset($_POST['User']))
	$model->attributes=$_POST['User'];
```

--------------------------------

### Retrieve a value from cache with get()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Retrieves a cached value by ID. If the value is false, it is not available and must be regenerated.

```php
$value=Yii::app()->cache->get($id);
if($value===false)
{
	// regenerate $value because it is not found in cache
	// and save it in cache for later use:
	// Yii::app()->cache->set($id,$value);
}
```

--------------------------------

### Count, countBySql, and exists methods

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Provides convenience methods to get row counts and check existence without loading rows.

```php
// get the number of rows satisfying the specified condition
$n=Post::model()->count($condition,$params);
// get the number of rows using the specified SQL statement
$n=Post::model()->countBySql($sql,$params);
// check if there is at least a row satisfying the specified condition
$exists=Post::model()->exists($condition,$params);
```

--------------------------------

### Commands to execute tests with PHPUnit

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/test.overview.txt

Provides console commands to run individual tests, all tests under a directory, and generate code coverage reports. The last command requires the Xdebug extension to be installed and enabled.

```text
% cd testdrive/protected/tests
% phpunit functional/PostTest.php    // executes an individual test
% phpunit --verbose functional       // executes all tests under 'functional'
% phpunit --coverage-html ./report unit
```

--------------------------------

### Fragment caching with requestTypes option

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.fragment.txt

Cache a fragment only for GET requests by setting the 'requestTypes' option to array('GET'). This prevents caching POST requests, which may contain user input.

```php
[php]
...other HTML content...
<?php if($this->beginCache($id, array('requestTypes'=>array('GET')))) { ?>
...content to be cached...
<?php $this->endCache(); } ?>
...other HTML content...

```

--------------------------------

### Configure Gii module in application configuration

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.gii.txt

Add the gii module to the modules section of the application configuration. Set a password for security and optionally configure ipFilters, newFileMode, and newDirMode. Gii should only be installed on a development machine.

```php
return array(
	......
	'modules'=>array(
		'gii'=>array(
			'class'=>'system.gii.GiiModule',
			'password'=>'pick up a password here',
			// 'ipFilters'=>array(...a list of IPs...),
			// 'newFileMode'=>0666,
			// 'newDirMode'=>0777,
		),
	),
);
```

--------------------------------

### Passing additional parameters to plural forms

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.i18n.txt

Demonstrates passing additional parameters to the plural form using an array. The example replaces {username} with 'samdark'.

```php
Yii::t('test', '{username} has a cucumber|{username} has {n} cucumbers',
array(5, '{username}' => 'samdark'));
```

--------------------------------

### Configuring CLogRouter with log routes

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.logging.txt

Example application configuration that preloads the CLogRouter component and defines two log routes: CFileLogRoute for trace/info messages with category 'system.*', and CEmailLogRoute for error/warning messages sent to admin@example.com.

```php
array(
	......
	'preload'=>array('log'),
	'components'=>array(
		......
		'log'=>array(
			'class'=>'CLogRouter',
			'routes'=>array(
				array(
					'class'=>'CFileLogRoute',
					'levels'=>'trace, info',
					'categories'=>'system.*',
				),
				array(
					'class'=>'CEmailLogRoute',
					'levels'=>'error, warning',
					'emails'=>'admin@example.com',
				),
			),
		),
	),
)
```

--------------------------------

### Using Component with Getters and Setters

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.component.txt

Demonstrates usage of the component defined with getters and setters: reading/writing textWidth, reading textHeight, and writing completed.

```php
$document=new Document();

// we can write and read textWidth
$document->textWidth=100;
echo $document->textWidth;

// we can only read textHeight
echo $document->textHeight;

// we can only write completed
$document->completed=true;
```

--------------------------------

### Set column value via property

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Access column values as properties of an AR instance. The example sets the 'title' attribute of a new Post instance.

```php
$post=new Post;
$post->title='a sample post';
```

--------------------------------

### Enable asset symlinking in main.php config

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.performance.txt

Configures the 'assetManager' component with 'linkAssets' => true to use symbolic links instead of file copies, improving performance. Place in 'protected/config/main.php'.

```php
return array(
	// ...
	'components' => array(
		// ...
		'assetManager' => array(
			'linkAssets' => true,
		),
	),
);
```

--------------------------------

### PostTest functional test class

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/test.functional.txt

Example functional test class for the blog demo. It extends WebTestCase, declares the Post fixture, and tests the post display feature by opening a post URL and verifying the title and comment form text.

```php
class PostTest extends WebTestCase
{
	public $fixtures=array(
		'posts'=>'Post',
	);

	public function testShow()
	{
		$this->open('post/1');
	    // verify the sample post title exists
	    $this->assertTextPresent($this->posts['sample1']['title']);
	    // verify comment form exists
	    $this->assertTextPresent('Leave a Comment');
	}

	......
}
```

--------------------------------

### Install access control filter in PostController

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.auth.txt

Overrides CController::filters to apply the 'accessControl' filter to all actions of PostController. This is the first step in setting up access control.

```php
class PostController extends CController
{
	......
	public function filters()
	{
		return array(
			'accessControl',
		);
	}
}
```

--------------------------------

### Accessing Form Elements

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Shows how to access form elements using array syntax. The first example retrieves the 'username' element from the root form, the second accesses the 'email' element inside the 'user' sub-form, and the third demonstrates the simplified array access for both.

```php
$username = $form->elements['username'];
```

```php
$email = $form->elements['user']->elements['email'];
```

```php
$username = $form['username'];
$email = $form['user']['email'];
```

--------------------------------

### Console command with run and getHelp

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.create.txt

Defines a console command extending CConsoleCommand, implementing run and getHelp methods. run receives command-line arguments as an array; getHelp returns usage information. Use this to create custom console commands.

```php
class MyCommand extends CConsoleCommand
{
	public function run($args)
	{
		// $args gives an array of the command-line arguments for this command
	}

	public function getHelp()
	{
		return 'Usage: how to use this command';
	}
}
```

--------------------------------

### Eager loading multiple relationships

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Pass multiple relationship names to with() to bring back all related models in one shot. The example loads posts with their authors and categories.

```php
$posts=Post::model()->with('author','categories')->findAll();
```

--------------------------------

### Show help for a specific command

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Display usage information for a particular console command.

```bash
yiic help <command-name>
```

--------------------------------

### Insert a new row into tbl_post using Active Record

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Shows how to create and save a new Post record by setting attributes and calling save(). The example assumes the Post AR class is already defined and the db connection is configured.

```php
$post=new Post;
$post->title='sample post';
$post->content='post body content';
$post->save();
```

--------------------------------

### Nested eager loading with with()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Use a hierarchical array to eager load nested relationships. This example loads posts with authors, categories, and each author's profile and posts.

```php
$posts=Post::model()->with(
	'author.profile',
	'author.posts',
	'categories')->findAll();
```

--------------------------------

### Query with table prefix using {{TableName}}

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.dao.txt

Uses the table prefix feature by writing {{user}} in the SQL. The prefix is configured via CDbConnection::tablePrefix. This example queries all rows from the tbl_user table when tbl_ is the configured prefix.

```php
$sql='SELECT * FROM {{user}}';
$users=$connection->createCommand($sql)->queryAll();
```

--------------------------------

### Navigate to Yii framework directory (Windows)

Source: https://github.com/yiisoft/yii/blob/master/README.md

Change to the framework directory on Windows to run the yiic tool.

```bash
cd YiiPath\framework
```

--------------------------------

### Run yiic shell to generate model and CRUD

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/quickstart.first-app-yiic.txt

Starts the yiic shell and runs the 'model User tbl_user' and 'crud User' sub-commands to generate a model class, fixtures, unit test, and CRUD code. The output shows the generated files and the URL to access the CRUD.

```shell
% cd WebRoot/testdrive
% protected/yiic shell
Yii Interactive Tool v1.1
Please type 'help' for help. Type 'exit' to quit.
>> model User tbl_user
   generate models/User.php
   generate fixtures/tbl_user.php
   generate unit/UserTest.php

The following model classes are successfully generated:
    User

If you have a 'db' database connection, you can test these models now with:
    $model=User::model()->find();
    print_r($model);

>> crud User
   generate UserController.php
   generate UserTest.php
   mkdir D:/testdrive/protected/views/user
   generate create.php
   generate update.php
   generate index.php
   generate view.php
   generate admin.php
   generate _form.php
   generate _view.php

Crud 'user' has been successfully created. You may access it via:
http://hostname/path/to/index.php?r=user
```

--------------------------------

### Plural forms for languages with complex rules (Russian)

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.i18n.txt

Shows how the number of plural expressions varies by language. The example uses Russian, which requires 4 plural forms instead of 2, and demonstrates the output for different numbers.

```php
Yii::t('app', '{n} cucumber|{n} cucumbers', 62);
Yii::t('app', '{n} cucumber|{n} cucumbers', 1.5);
Yii::t('app', '{n} cucumber|{n} cucumbers', 1);
Yii::t('app', '{n} cucumber|{n} cucumbers', 7);
```

```php
'{n} cucumber|{n} cucumbers' => '{n} огурец|{n} огурца|{n} огурцов|{n} огурца',
```

```text
62 огурца
1.5 огурца
1 огурец
7 огурцов
```

--------------------------------

### Raising an Exception

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.error.txt

Use this syntax to raise an exception in Yii. The example shows throwing a CHttpException with a 404 status code to report a user error, such as an invalid post ID.

```php
throw new CHttpException(404,'The specified post cannot be found.');
```

--------------------------------

### Invoke sitemap index action with various options

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Different ways to call the sitemap index action, showing option handling and defaults.

```bash
yiic sitemap index --type=News --limit=5

// $limit takes default value
yiic sitemap index --type=News

// $limit takes default value
// because 'index' is a default action, we can omit the action name
yiic sitemap --type=News

// the order of options does not matter
yiic sitemap index --limit=5 --type=News
```

--------------------------------

### Configure db component for MySQL in main.php

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/prototype.database.txt

Alternative configuration for using MySQL instead of SQLite. Create a MySQL database named 'blog' using the provided SQL file, then replace the db component configuration with this one.

```php
return array(
    ......
    'components'=>array(
        ......
        'db'=>array(
            'connectionString' => 'mysql:host=localhost;dbname=blog',
            'emulatePrepare' => true,
            'username' => 'root',
            'password' => '',
            'charset' => 'utf8',
            'tablePrefix' => 'tbl_',
        ),
    ),
	......
);
```

--------------------------------

### Cache multiple queries with $queryCount parameter

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Demonstrates using the $queryCount parameter (set to 2) to enforce query caching for the next two queries. The second query in this example will use query caching.

```php
// ...
$rows = Yii::app()->db->cache(1000, $dependency, 2)->createCommand($sql)->queryAll();
// query caching WILL be used
$rows = Yii::app()->db->createCommand($sql)->queryAll();
```

--------------------------------

### Navigate to Yii framework directory (Linux)

Source: https://github.com/yiisoft/yii/blob/master/README.md

Change to the framework directory on Linux to run the yiic tool.

```bash
cd YiiPath/framework
```

--------------------------------

### Replacing the number parameter with a custom function

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.i18n.txt

Shows how to replace the number parameter with a custom value using a function. The example defines a convertNumber() function and passes its result as the {n} parameter.

```php
function convertNumber($number)
{
	// convert number to word
	return $number;
}

Yii::t('test', '{n} cucumber|{n} cucumbers',
array(5, '{n}' => convertNumber(5)));
```

--------------------------------

### Console application configuration with components

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Configure console application components, such as DB, in the console configuration file.

```php
return array(
	......
	'components'=>array(
		'db'=>array(
			......
		),
	),
);
```

--------------------------------

### Register third-party autoloader before Yii autoloader

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.integration.txt

To avoid PHP warnings from conflicting autoloaders, register third-party autoloaders before the Yii autoloader. This example shows the required order.

```php
require_once('PHPUnit/Autoload.php'); // register 3rd-party autoloader
require_once('/path/to/framework/yii.php'); // register Yii autoloader
```

--------------------------------

### Konfigurera db-applikationskomponent

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/sv/database.dao.txt

Konfigurerar en 'db'-komponent i applikationskonfigurationen med klass, DSN, användarnamn, lösenord och emulatePrepare. Används för att dela en enda DB-anslutning via Yii::app()->db.

```php
array(
	......
	'components'=>array(
		......
		'db'=>array(
			'class'=>'CDbConnection',
			'connectionString'=>'mysql:host=localhost;dbname=testdb',
			'username'=>'root',
			'password'=>'password',
			'emulatePrepare'=>true,  // erfordras i vissa MySQL-installationer
		),
	),
)
```

--------------------------------

### Nested fragment caching example

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.fragment.txt

Shows how to nest fragment caches. The inner cache is enclosed within the outer cache. Different caching options can be set for each, and the inner cache may remain valid even if the outer cache is invalidated.

```php
[php]
...other HTML content...
<?php if($this->beginCache($id1)) { ?>
...outer content to be cached...
	<?php if($this->beginCache($id2)) { ?>
	...inner content to be cached...
	<?php $this->endCache(); } ?>
...outer content to be cached...
<?php $this->endCache(); } ?>
...other HTML content...

```

--------------------------------

### Flash Player Embedding and Version Check

Source: https://github.com/yiisoft/yii/blob/master/demos/phonebook/flex/html-template/index.template.html

This template embeds a Flash application with version detection. It checks for the required Flash version, redirects to the installer if needed, and provides alternate content for unsupported browsers.

```html
<!DOCTYPE html>
<html>
<head>
    <title>${title}</title>
    <style>
        body { margin: 0px; overflow:hidden }
    </style>
</head>
<body>
    <!-- ... -->
</body>
</html>
```

--------------------------------

### actionView and loadModel in PostController

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.display.txt

The actionView method renders the view for a single post. The loadModel method retrieves the post by ID from the GET parameter, applying a condition for guests to only see published or archived posts, and throws a 404 CHttpException if the post is not found or not accessible.

```php
public function actionView()
{
	$post=$this->loadModel();
	$this->render('view',array(
		'model'=>$post,
	));
}

private $_model;

public function loadModel()
{
	if($this->_model===null)
	{
		if(isset($_GET['id']))
		{
			if(Yii::app()->user->isGuest)
				$condition='status='.Post::STATUS_PUBLISHED
					.' OR status='.Post::STATUS_ARCHIVED;
			else
				$condition='';
			$this->_model=Post::model()->findByPk($_GET['id'], $condition);
		}
		if($this->_model===null)
			throw new CHttpException(404,'The requested page does not exist.');
	}
	return $this->_model;
}
```

--------------------------------

### Redirect to returnUrl after login

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.auth.txt

Redirect the browser back to the page that caused the authorization failure after a successful login. Uses the returnUrl property of the user component to get the original URL.

```php
Yii::app()->request->redirect(Yii::app()->user->returnUrl);
```

--------------------------------

### Basic fragment caching with beginCache/endCache

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.fragment.txt

Wrap content to cache with beginCache() and endCache(). If beginCache() returns false, cached content is inserted; otherwise the inner content is executed and cached on endCache().

```php
...other HTML content...
<?php if($this->beginCache($id)) { ?>
...content to be cached...
<?php $this->endCache(); } ?>
...other HTML content...
```

--------------------------------

### Configure loginUrl for user component

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.auth.txt

Configure the loginUrl property of the user component to redirect unauthenticated users to the login page. The array specifies the route to the login action and can include additional GET parameters.

```php
array(
	......
	'components'=>array(
		'user'=>array(
			// this is actually the default value
			'loginUrl'=>array('site/login'),
		),
	),
)
```

--------------------------------

### Fetch latest code from upstream

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Fetches the latest code from the main Yii repository's master branch. Do this at the start of every contribution to ensure you're working with the latest code.

```bash
git fetch upstream
```

--------------------------------

### Comment Tag Syntax

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.prado.txt

Comment tags are used to write view comments visible only to developers. They are stripped off when the view is displayed to end users. The syntax is shown in the example.

```html
<!---
view comments that will be stripped off
--->
```

--------------------------------

### Pre-import classes with Yii::$classMap

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.namespace.txt

Pre-imports user classes via a class map. Must be executed before CWebApplication::run() is invoked.

```php
Yii::$classMap=array(
	'ClassName1' => 'path/to/ClassName1.php',
	'ClassName2' => 'path/to/ClassName2.php',
	......
);
```

--------------------------------

### Define access rules in PostController

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.auth.txt

Overrides CController::accessRules to specify authorization rules. The rules are evaluated in order; the first matching rule determines access. The example denies anonymous users from create/edit, allows admin to delete, and denies everyone else from delete.

```php
class PostController extends CController
{
	......
	public function accessRules()
	{
		return array(
			array('deny',
				'actions'=>array('create', 'edit'),
				'users'=>array('?'),
			),
			array('allow',
				'actions'=>array('delete'),
				'roles'=>array('admin'),
			),
			array('deny',
				'actions'=>array('delete'),
				'users'=>array('*'),
			),
		);
	}
}
```

--------------------------------

### Create a new Yii web application (Linux)

Source: https://github.com/yiisoft/yii/blob/master/README.md

Use the yiic command to create a new web application on Linux.

```bash
./yiic webapp ../testdrive
```

--------------------------------

### Consume Web service with SoapClient

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.webservice.txt

Creates a PHP SOAP client to consume the stock quote service. It calls getPrice with 'GOOGLE' and echoes the result, which is 350. The client can be run in Web or console mode.

```php
$client=new SoapClient('http://hostname/path/to/index.php?r=stock/quote');
echo $client->getPrice('GOOGLE');
```

--------------------------------

### Execute a console command

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Run a console command with optional parameters.

```bash
yiic <command-name> [parameters...]
```

--------------------------------

### Disable PHP include path usage

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.integration.txt

Set Yii::$enableIncludePath to false before starting the application to avoid problems with third-party autoloaders that disable PHP include path usage.

```php
require_once('/path/to/framework/yii.php');
$configFile='/path/to/config/main.php';
Yii::$enableIncludePath = false; // disable PHP include path usage
Yii::createWebApplication($configFile)->run();
```

--------------------------------

### index view with tag header and CListView

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.display.txt

The index view displays a header 'Posts Tagged with' when a tag is specified in the GET parameter, and uses CListView to render the post list with the '_view' partial view and a template that shows items and pager.

```php
<?php if(!empty($_GET['tag'])): ?>
<h1>Posts Tagged with <i><?php echo CHtml::encode($_GET['tag']); ?></i></h1>
<?php endif; ?>

<?php $this->widget('zii.widgets.CListView', array(
	'dataProvider'=>$dataProvider,
	'itemView'=>'_view',
	'template'=>"{items}\n{pager}",
)); ?>
```

--------------------------------

### Configure application to import AR classes from protected/models

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Shows how to import the whole models directory using the 'import' configuration key, so AR classes are available without individual includes.

```php
return array(
	'import'=>array(
		'application.models.*',
	),
);
```

--------------------------------

### Set default value for AR property

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Declare a property in the AR class to override the static default value from the table schema. The example shows a default title and its output.

```php
class Post extends CActiveRecord
{
	public $title='please enter a title';
	......
}

$post=new Post;
echo $post->title;  // this would display: please enter a title
```

--------------------------------

### Shorthand numeric plural notation

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.i18n.txt

Uses a number as a shorthand for the expression 'n==Number'. The example shows a translated message with two plural forms: one for exactly one book and another for more than one.

```php
'1#one book|n>1#many books'
```

--------------------------------

### Using CLinkPager with default and classic skins

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

Shows how to create CLinkPager widgets with and without specifying the 'skin' property. The first widget uses the 'default' skin, the second uses the 'classic' skin.

```php
<?php $this->widget('CLinkPager'); ?>

<?php $this->widget('CLinkPager', array('skin'=>'classic')); ?>
```

--------------------------------

### Using beginWidget() and endWidget() for widgets

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.view.txt

Use this snippet to embed a widget that captures body content. The widget's init() and run() methods are called by beginWidget() and endWidget() respectively.

```php
<?php $this->beginWidget('path.to.WidgetClass'); ?>
...body content that may be captured by the widget...
<?php $this->endWidget(); ?>
```

--------------------------------

### Create a new Yii web application (Windows)

Source: https://github.com/yiisoft/yii/blob/master/README.md

Use the yiic command to create a new web application on Windows.

```bash
yiic webapp ..\testdrive
```

--------------------------------

### Dynamic relational query options with eager loading (order ASC)

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Use this snippet to override the default 'order' option of a relation during eager loading. The example sets 'posts.create_time ASC' to override the descending order defined in the relation.

```php
User::model()->with(array(
	'posts'=>array('order'=>'posts.create_time ASC'),
	'profile',
))->findAll();
```

--------------------------------

### Use widget in view

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.use.txt

Shows how to use a widget in a view, both without body content and with body content using beginWidget and endWidget.

```php
// widget that does not need body content
<?php $this->widget('ext.xyz.XyzClass', array(
    'property1'=>'value1',
    'property2'=>'value2')); ?>

// widget that can contain body content
<?php $this->beginWidget('ext.xyz.XyzClass', array(
    'property1'=>'value1',
    'property2'=>'value2')); ?>

...body content of the widget...

<?php $this->endWidget(); ?>
```

--------------------------------

### CLDR plural forms with Yii::t()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.i18n.txt

Demonstrates the CLDR-based plural choice format with the Yii::t() method. The example shows how to define plural forms for English (cucumber/cucumbers) and the output for counts 1, 2, and 0.

```php
Yii::t('test', 'cucumber|cucumbers', 1);
Yii::t('test', 'cucumber|cucumbers', 2);
Yii::t('test', 'cucumber|cucumbers', 0);
```

```text
cucumber
cucumbers
cucumbers
```

--------------------------------

### Build query with createCommand array parameter

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Uses an array passed to createCommand() to initialize command properties and build a SELECT query with parameters.

```php
$row = Yii::app()->db->createCommand(array(
	'select' => array('id', 'username'),
	'from' => 'tbl_user',
	'where' => 'id=:id',
	'params' => array(':id'=>1),
))->queryRow();
```

--------------------------------

### actionIndex in PostController

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.display.txt

The actionIndex method creates a CDbCriteria to fetch published posts ordered by update time descending, with the commentCount relation. It adds a search condition for the 'tags' attribute if a 'tag' GET parameter is present, and uses a CActiveDataProvider with pagination set to 5 posts per page.

```php
public function actionIndex()
{
	$criteria=new CDbCriteria(array(
		'condition'=>'status='.Post::STATUS_PUBLISHED,
		'order'=>'update_time DESC',
		'with'=>'commentCount',
	));
	if(isset($_GET['tag']))
		$criteria->addSearchCondition('tags',$_GET['tag']);

	$dataProvider=new CActiveDataProvider('Post', array(
		'pagination'=>array(
			'pageSize'=>5,
		),
		'criteria'=>$criteria,
	));

	$this->render('index',array(
		'dataProvider'=>$dataProvider,
	));
}
```

--------------------------------

### Create a feature branch from upstream master

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Creates a new branch based on the latest upstream master. The branch name should start with the issue number and be descriptive. This ensures you can submit multiple pull requests.

```bash
git checkout upstream/master
git checkout -b 999-name-of-your-branch-goes-here
```

--------------------------------

### Default single-query caching behavior with CDbConnection::cache()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Shows that by default cache() only marks the next SQL query for caching; subsequent queries without cache() are not cached. The second query in this example will not use query caching.

```php
$sql = 'SELECT * FROM tbl_post LIMIT 20';
$dependency = new CDbCacheDependency('SELECT MAX(update_time) FROM tbl_post');

$rows = Yii::app()->db->cache(1000, $dependency)->createCommand($sql)->queryAll();
// query caching will NOT be used
$rows = Yii::app()->db->createCommand($sql)->queryAll();
```

--------------------------------

### Apply all new migrations

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Command to apply all available new migrations. It shows the list of new migrations and asks for confirmation before running up() methods in timestamp order.

```shell
yiic migrate
```

--------------------------------

### Define a site controller with index and contact actions

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.controller.txt

Shows how to define a controller class extending CController with action methods. The default action is 'index' unless changed via CController::defaultAction.

```php
class SiteController extends CController
{
	public function actionIndex()
	{
		// ...
	}

	public function actionContact()
	{
		// ...
	}
}
```

--------------------------------

### Application configuration to configure 'forum' module with 'postPerPage'

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.module.txt

Configures the 'forum' module with an initial property value 'postPerPage' set to 20. The module class must have a property named 'postPerPage'.

```php
return array(
	......
	'modules'=>array(
	    'forum'=>array(
	        'postPerPage'=>20,
	    ),
	),
	......
);
```

--------------------------------

### Return configuration array from PHP script

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.application.txt

Inside a configuration PHP script (e.g., protected/config/main.php), return the configuration array. This is the standard way to provide the configuration.

```php
return array(...);
```

--------------------------------

### Configure CProfileLogRoute for profiling results

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.logging.txt

Configuration for enabling performance profiling results display. Set 'report' to 'summary' to list execution time of every marked code block, or 'callstack' for call stack information.

```php
array(
	......
	'preload'=>array('log'),
	'components'=>array(
		......
		'log'=>array(
			'class'=>'CLogRouter',
			'routes'=>array(
				array(
					'class'=>'CProfileLogRoute',
					'report'=>'summary',
					// lists execution time of every marked code block
					// report can also be set to callstack
				),
				...other log routes...
			),
		),
	),
)
```

--------------------------------

### Disambiguate related table column in order with 't.create_time, comments.create_time'

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Use this snippet when you need to order by columns from both the primary model (alias 't') and a related model (relation name as alias). The example orders posts and their comments by their respective 'create_time' columns.

```php
$posts=Post::model()->with('comments')->findAll(array(
	'order'=>'t.create_time, comments.create_time'
));
```

--------------------------------

### Create a new Yii application with yiic webapp

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/quickstart.first-app.txt

Run the yiic command line tool to create a new Yii application under WebRoot/testdrive. On Mac OS, Linux, or Unix, you may need to make the yiic file executable or run it with PHP as shown in the second command.

```bash
% YiiRoot/framework/yiic webapp WebRoot/testdrive
```

```bash
% cd WebRoot
% php YiiRoot/framework/yiic.php webapp testdrive
```

--------------------------------

### Konfigurasi GiiModule::generatorPaths untuk jalur pencarian generator

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/id/topics.gii.txt

Konfigurasi aplikasi untuk menambahkan jalur pencarian generator kustom ke GiiModule::generatorPaths. Gunakan saat ingin menambahkan direktori generator kustom, misalnya 'application.gii', selain lokasi default 'system.gii.generators'.

```php
return array(
	'modules'=>array(
		'gii'=>array(
			'class'=>'system.gii.GiiModule',
			'generatorPaths'=>array(
				'application.gii',   // sebuah alias path
			),
		),
	),
);
```

--------------------------------

### Attach behavior via application configuration

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.use.txt

Shows how to attach a behavior to an application component by configuring the 'behaviors' property in the application configuration. The component will attach the behavior during initialization.

```php
return array(
    // 'preload'=>array('xyz',...),
    'components'=>array(
        'db'=>array(
            'class'=>'CDbConnection',
            'behaviors'=>array(
                'xyz'=>array(
                    'class'=>'ext.xyz.XyzBehavior',
                    'property1'=>'value1',
                    'property2'=>'value2',
                ),
            ),
        ),
        //....
    ),
);
```

--------------------------------

### Override CController::filters() to define action filters

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.controller.txt

Override the filters() method in a controller to return an array of filter configurations. The example defines a method-based filter 'postOnly' applied to 'edit' and 'create' actions, and an object-based filter 'application.filters.PerformanceFilter' applied to all actions except 'edit' and 'create', with its 'unit' property set to 'second'.

```php
[php]
class PostController extends CController
{
	......
	public function filters()
	{
		return array(
			'postOnly + edit, create',
			array(
				'application.filters.PerformanceFilter - edit, create',
				'unit'=>'second',
			),
		);
	}
}
```

--------------------------------

### Build a SELECT query with Query Builder

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Shows how to use the Query Builder to create a SELECT statement with select, from, join, and where methods. The query retrieves a row from the user table joined with profile.

```php
$user = Yii::app()->db->createCommand()
	->select('id, username, profile')
	->from('tbl_user u')
	->join('tbl_profile p', 'u.id=p.user_id')
	->where('id=:id', array(':id'=>$id))
	->queryRow();
```

--------------------------------

### Configure theme in application config

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/final.future.txt

Set the 'theme' parameter in the application configuration array to 'classic' to enable the theme. This is required for the blog to use the custom theme.

```php
return array(
	......
	'theme'=>'classic',
	......
);
```

--------------------------------

### Directory structure for class-based actions

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.controller.txt

Shows a recommended directory layout for organizing controller actions as separate classes under the protected/controllers directory.

```text
protected/
    controllers/
        PostController.php
        UserController.php
        post/
            CreateAction.php
            ReadAction.php
            UpdateAction.php
        user/
            CreateAction.php
            ListAction.php
            ProfileAction.php
            UpdateAction.php
```

--------------------------------

### Retrieve and send cookies via CHttpRequest::cookies

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.security.txt

Use this snippet to retrieve a cookie by name and send a new cookie through Yii's request cookies collection. Accessing cookies this way enables Yii's cookie validation scheme. The example shows retrieving the cookie value and creating a new CHttpCookie to send.

```php
// retrieve the cookie with the specified name
$cookie=Yii::app()->request->cookies[$name];
$value=$cookie->value;
......
// send a cookie
$cookie=new CHttpCookie($name,$value);
Yii::app()->request->cookies[$name]=$cookie;
```

--------------------------------

### Class-based action with run() parameter binding

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.controller.txt

Shows how to define a class-based action with a run() method that automatically receives the named request parameter.

```php
class UpdateAction extends CAction
{
	public function run($id)
	{
		// $id will be populated with $_GET['id']
	}
}
```

--------------------------------

### Generate application skeleton with Git support

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/quickstart.first-app.txt

Run this command to generate a new Yii web application with Git version control files (.gitignore and .gitkeep). The third parameter 'git' enables Git support; use 'hg' for Mercurial (available since 1.1.11).

```text
% YiiRoot/framework/yiic webapp WebRoot/testdrive git
```

--------------------------------

### Using a Console Command Extension via commandMap

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.use.txt

Configure the console application's configuration to use a console command extension. The 'yiic' tool then has an additional command 'xyz'.

```php
return array(
	'commandMap'=>array(
		'xyz'=>array(
			'class'=>'ext.xyz.XyzClass',
			'property1'=>'value1',
			'property2'=>'value2',
		),
		// other commands
	),
);
```

--------------------------------

### Application config import for models and components

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/prototype.auth.txt

Application configuration snippet showing the 'import' array that adds the models and components directories to the PHP include_path, enabling automatic class loading for classes like User and UserIdentity.

```php
return array(
    ......
    'import'=>array(
        'application.models.*',
        'application.components.*',
    ),
    ......
);
```

--------------------------------

### Create a new migration with yiic migrate create

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Run the migrate command to create a new migration. The name parameter is a brief description used as part of the PHP class name and should only contain letters, digits, and underscores.

```bash
yiic migrate create <name>
```

```bash
yiic migrate create create_news_table
```

--------------------------------

### Scenario list syntax for on and except

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Demonstrates two ways to specify scenario lists: as an arbitrary array of scenario names or as a comma-separated string. The 'except' parameter blacklists scenarios.

```php
// arbitrary array with scenario names
'on'=>array('update', 'create'),
// string with scenario names separated with commas (spaces are ignored)
'except'=>'ignore, this, scenarios, at-all',
```

--------------------------------

### Define default roles with business rules

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/pt_br/topics.auth.txt

Create default roles 'authenticated' and 'guest' with business rules that check the user's authentication status. The business rules return true for the appropriate user type.

```php
$bizRule='return !Yii::app()->user->isGuest;';
$auth->createRole('authenticated', 'authenticated user', $bizRule);

$bizRule='return Yii::app()->user->isGuest;';
$auth->createRole('guest', 'guest user', $bizRule);
```

--------------------------------

### Show migration history and new migrations

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Displays the migration history or the list of new migrations. The optional limit parameter specifies how many to show; if omitted, all are shown.

```shell
yiic migrate history [limit]
yiic migrate new [limit]
```

--------------------------------

### Configure theme in application configuration

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

Sets the active theme to 'basic' in the application configuration. The layout and site index view will be taken from the theme's views directory, falling back to protected/views if not found.

```php
return array(
	'theme'=>'basic',
	......
);
```

--------------------------------

### Console command action format

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Format for executing a specific action with options.

```bash
yiic <command-name> <action-name> --option1=value1 --option2=value2 ...
```

--------------------------------

### Test bootstrap script (bootstrap.php)

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/test.overview.txt

Shows the contents of the bootstrap.php file, which acts as the entry script for executing a set of tests. It includes the Yii framework's yiit.php, loads the test configuration, includes WebTestCase.php, and creates the web application.

```php
$yiit='path/to/yii/framework/yiit.php';
$config=dirname(__FILE__).'/../config/test.php';
require_once($yiit);
require_once(dirname(__FILE__).'/WebTestCase.php');
Yii::createWebApplication($config);
```

--------------------------------

### Configure database connection as application component

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.dao.txt

Configure a 'db' application component with class CDbConnection, connectionString, username, password, and optional emulatePrepare. The driverName is required for ODBC connections to disambiguate the DBMS type.

```php
array(
	......
	'components'=>array(
		......
		'db'=>array(
			'class'=>'CDbConnection'
			'driverName'=>'mysql',
			'connectionString'=>'odbc:Driver={MySQL};Server=127.0.0.1;Database=test',
			'username'=>'',
			'password'=>'',
		),
	),
)
```

--------------------------------

### Create feature branch, commit changes, and push

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Use these commands to create a feature branch, make changes, commit them, pull upstream changes, and push the branch to your fork. Replace '999-name-of-your-branch-goes-here' with your branch name and update the commit message as needed.

```bash
git fetch upstream
git checkout upstream/master
git checkout -b 999-name-of-your-branch-goes-here
 
/* do your magic, update changelog if needed */

git add path/to/my/file.php
git commit -m "A brief description of this change which fixes #42 goes here"
git pull upstream master
git push -u origin 999-name-of-your-branch-goes-here
```

--------------------------------

### Manual parameter retrieval in actionCreate

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.controller.txt

Shows the verbose way to retrieve and validate $_GET parameters before the action parameter binding feature was used.

```php
class PostController extends CController
{
	public function actionCreate()
	{
		if(isset($_GET['category']))
			$category=(int)$_GET['category'];
		else
			throw new CHttpException(404,'invalid request');

		if(isset($_GET['language']))
			$language=$_GET['language'];
		else
			$language='en';

		// ... fun code starts here ...
	}
}
```

--------------------------------

### Метод actionView() та newComment() у PostController

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/uk/comment.create.txt

Змінює метод actionView() контролера PostController, щоб обробити створення коментаря. Викликає newComment() для створення екземпляра Comment та додавання його до запису через $post->addComment().

```php
public function actionView()
{
	$post=$this->loadModel();
	$comment=$this->newComment($post);

	$this->render('view',array(
		'model'=>$post,
		'comment'=>$comment,
	));
}

protected function newComment($post)
{
	$comment=new Comment;
	if(isset($_POST['Comment']))
	{
		$comment->attributes=$_POST['Comment'];
		if($post->addComment($comment))
		{
			if($comment->status==Comment::STATUS_PENDING)
				Yii::app()->user->setFlash('commentSubmitted','Дякуємо за ваш коментар. 
					Ваш коментар зʼявиться одразу після ухвалення.');
			$this->refresh();
		}
	}
	return $comment;
}
```

--------------------------------

### Create CLinkPager widget with skin and initial properties

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

Creates a CLinkPager widget with initial property values that are merged with the 'classic' skin. The resulting pager will have 'header' set to an empty string, 'maxButtonCount' set to 6, and 'cssFile' set to false.

```php
<?php $this->widget('CLinkPager', array(
    'skin'=>'classic',
    'maxButtonCount'=>6,
    'cssFile'=>false,
)); ?>
```

--------------------------------

### Specifying a dropdownlist input with items and prompt

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Configures a dropdown list for 'gender' using the 'dropdownlist' type, with items from User::getGenderOptions() and a prompt 'Please select:'. The User model method returns an array of options.

```php
'gender'=>array(
    'type'=>'dropdownlist',
    'items'=>User::model()->getGenderOptions(),
    'prompt'=>'Please select:',
),
```

```php
class User extends CActiveRecord
{
	public function getGenderOptions()
	{
		return array(
			0 => 'Male',
			1 => 'Female',
		);
	}
}
```

--------------------------------

### Configure database connection in main.php

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/nl/quickstart.first-app.txt

This snippet shows the database component configuration in the application configuration file. It sets the connection string to a SQLite database file. The database must exist and the PDO SQLite extension must be enabled.

```php
return array(
	......
	'components'=>array(
		......
		'db'=>array(
			'connectionString'=>'sqlite:protected/data/testdrive.db',
		),
	),
	......
);
```

--------------------------------

### actionView

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.display.txt

Displays a single post. It loads the post model using loadModel() and renders the 'view' view with the model.

```APIDOC
## actionView

### Description
Displays a single post. It loads the post model using loadModel() and renders the 'view' view with the model.

### Method
GET

### Endpoint
/post/view

### Parameters
#### Query Parameters
- **id** (integer) - Required - The ID of the post to display.

### Request Example
GET /post/view?id=1

### Response
#### Success Response (200)
- **model** (Post) - The post model instance.

#### Response Example
{
  "model": {
    "id": 1,
    "title": "Example Post",
    "content": "Post content",
    "status": 2,
    "tags": "tag1, tag2",
    "update_time": 1234567890
  }
}

### Error Handling
- **404 Not Found** - Thrown when the post does not exist or is not accessible to the current user.
```

--------------------------------

### Action parameter binding with defaults

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.controller.txt

Shows the concise way to use automatic parameter binding in an action method, with a default value for the language parameter.

```php
class PostController extends CController
{
	public function actionCreate($category, $language='en')
	{
		$category=(int)$category;

		// ... fun code starts here ...
	}
}
```

--------------------------------

### Console command run method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

The signature of the run() method that receives command line parameters.

```php
public function run($args) { ... }
```

--------------------------------

### Cache tag cloud with COutputCache

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/final.future.txt

Wrap the tag cloud widget in beginCache/endCache to cache its output for 3600 seconds. This reduces database queries and PHP execution for the tag cloud portlet.

```php
<?php if($this->beginCache('tagCloud', array('duration'=>3600))) { ?>

	<?php $this->widget('TagCloud', array(
		'maxTags'=>Yii::app()->params['tagCloudCount'],
	)); ?>

<?php $this->endCache(); } ?>
```

--------------------------------

### actionLogin method for login form

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.action.txt

Creates a LoginForm model, populates it with POST data, validates, and redirects on success. Renders the login view otherwise.

```php
public function actionLogin()
{
	$model=new LoginForm;
	if(isset($_POST['LoginForm']))
	{
		// collects user input data
		$model->attributes=$_POST['LoginForm'];
		// validates user input and redirect to previous page if validated
		if($model->validate())
			$this->redirect(Yii::app()->user->returnUrl);
	}
	// displays the login form
	$this->render('login',array('model'=>$model));
}
```

--------------------------------

### Login action using CForm

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Creates a CForm object with the login form configuration and handles form submission and validation. Redirects to site/index on success, otherwise renders the login view.

```php
public function actionLogin()
{
	$model = new LoginForm;
	$form = new CForm('application.views.site.loginForm', $model);
	if($form->submitted('login') && $form->validate())
		$this->redirect(array('site/index'));
	else
		$this->render('login', array('form'=>$form));
}
```

--------------------------------

### Legacy configuration for enabling widget skins (pre-1.1.3)

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

For Yii versions prior to 1.1.3, use this configuration to enable widget skinning by setting the widgetFactory class to 'CWidgetFactory'.

```php
return array(
    'components'=>array(
        'widgetFactory'=>array(
            'class'=>'CWidgetFactory',
        ),
    ),
);
```

--------------------------------

### Alternative syntax: select property assignment

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Shows two equivalent ways to set the SELECT clause: using the select() method or assigning to the select property on a CDbCommand instance.

```php
$command->select(array('id', 'username'));
$command->select = array('id', 'username');
```

--------------------------------

### Using TagCloud widget in column2.php layout

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/portlet.tags.txt

Shows how to use the TagCloud portlet in the layout file. It checks if the user is not a guest to display UserMenu, then renders the TagCloud widget with a maxTags parameter from application parameters.

```php
......
<div id="sidebar">

	<?php if(!Yii::app()->user->isGuest) $this->widget('UserMenu'); ?>

	<?php $this->widget('TagCloud', array(
		'maxTags'=>Yii::app()->params['tagCloudCount'],
	)); ?>

</div>
......
```

--------------------------------

### Reuse command with reset()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Demonstrates reusing a CDbCommand instance for multiple queries by calling reset() between them.

```php
$command = Yii::app()->db->createCommand();
$users = $command->select('*')->from('tbl_users')->queryAll();
$command->reset();  // clean up the previous query
$posts = $command->select('*')->from('tbl_posts')->queryAll();
```

--------------------------------

### Array type hinting for action parameters

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.controller.txt

Shows how to use the array type hint to ensure a parameter is always an array, even if a string is passed via $_GET.

```php
class PostController extends CController
{
	public function actionCreate(array $categories)
	{
		// Yii will make sure that $categories is an array
	}
}
```

--------------------------------

### Migration with explicit transaction

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Shows how to manually wrap migration code in a DB transaction using beginTransaction(), commit(), and rollback(). Use when you need explicit control over transaction boundaries or when safeUp() is not suitable.

```php
class m101129_185401_create_news_table extends CDbMigration
{
	public function up()
	{
		$transaction=$this->getDbConnection()->beginTransaction();
		try
		{
			$this->createTable('tbl_news', array(
				'id' => 'pk',
				'title' => 'string NOT NULL',
				'content' => 'text',
			));
			$transaction->commit();
		}
		catch(Exception $e)
		{
			echo "Exception: ".$e->getMessage()."\n";
			$transaction->rollback();
			return false;
		}
	}

	// ...similar code for down()
}
```

--------------------------------

### Supply array values via repeated options

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Repeat the same option in the command line to pass an array value to the action.

```bash
yiic sitemap index --types=News --types=Article
```

--------------------------------

### Create and execute SQL command with CDbCommand

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.dao.txt

Create a CDbCommand instance using CDbConnection::createCommand() with a SQL statement. The connection can be accessed via Yii::app()->db or explicitly created with new CDbConnection(). The SQL statement can be updated via $command->text.

```php
$connection=Yii::app()->db;   // assuming you have configured a "db" connection
// If not, you may explicitly create a connection:
// $connection=new CDbConnection($dsn,$username,$password);
$command=$connection->createCommand($sql);
// if needed, the SQL statement may be updated as follows:
// $command->text=$newSQL;
```

--------------------------------

### Importing a Generic Component Class

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.use.txt

Use Yii::import to include the class file of a generic component extension before creating an instance or extending it.

```php
Yii::import('ext.xyz.XyzClass');
```

--------------------------------

### Clone your fork of Yii

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Clones your forked Yii repository from GitHub to your local development environment. Replace YOUR-GITHUB-USERNAME with your actual GitHub username.

```bash
git clone git@github.com:YOUR-GITHUB-USERNAME/yii.git
```

--------------------------------

### Set application name and defaultController properties

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.application.txt

Configuration array that sets the 'name' and 'defaultController' properties of the application instance. Use this when customizing the application via a configuration file.

```php
array(
	'name'=>'Yii Framework',
	'defaultController'=>'site',
)
```

--------------------------------

### Using a Controller Extension via controllerMap

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.use.txt

Configure the CWebApplication::controllerMap property in the application configuration to use a controller extension. The action 'a' is accessed via the route 'xyz/a'.

```php
return array(
	'controllerMap'=>array(
		'xyz'=>array(
			'class'=>'ext.xyz.XyzClass',
			'property1'=>'value1',
			'property2'=>'value2',
		),
		// other controllers
	),
);
```

--------------------------------

### Find all rows with various methods

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Shows findAll, findAllByPk, findAllByAttributes, and findAllBySql methods. Returns an empty array if no rows match.

```php
// find all rows satisfying the specified condition
$posts=Post::model()->findAll($condition,$params);
// find all rows with the specified primary keys
$posts=Post::model()->findAllByPk($postIDs,$condition,$params);
// find all rows with the specified attribute values
$posts=Post::model()->findAllByAttributes($attributes,$condition,$params);
// find all rows using the specified SQL statement
$posts=Post::model()->findAllBySql($sql,$params);
```

--------------------------------

### Application configuration to enable 'forum' module

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.module.txt

Declares the 'forum' module in the application's 'modules' property. This is required to use the module.

```php
return array(
	......
	'modules'=>array('forum',...),
	......
);
```

--------------------------------

### Register a PSR-0 namespace alias for Imagine

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.integration.txt

Use this to register a path alias for a namespaced library like Imagine. The alias name must match the first namespace part of the library.

```php
Yii::setPathOfAlias('Imagine',Yii::getPathOfAlias('application.vendors.Imagine'));

// Then standard code from Imagine guide:
// $imagine = new Imagine\Gd\Imagine();
// etc.
```

--------------------------------

### Defining a custom widget class

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.view.txt

This snippet shows how to define a new widget by extending CWidget and overriding init() and run(). The init() method is called by CController::beginWidget() and run() by CController::endWidget().

```php
class MyWidget extends CWidget
{
	public function init()
	{
		// this method is called by CController::beginWidget()
	}

	public function run()
	{
		// this method is called by CController::endWidget()
	}
}
```

--------------------------------

### userMenu view file

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/portlet.menu.txt

The view file for the UserMenu portlet, containing an unordered list of menu links for authenticated users: Create New Post, Manage Posts, Approve Comments (with pending comment count), and Logout.

```php
<ul>
	<li><?php echo CHtml::link('Create New Post',array('post/create')); ?></li>
	<li><?php echo CHtml::link('Manage Posts',array('post/admin')); ?></li>
	<li><?php echo CHtml::link('Approve Comments',array('comment/index'))
		. ' (' . Comment::model()->pendingCommentCount . ')'; ?></li>
	<li><?php echo CHtml::link('Logout',array('site/logout')); ?></li>
</ul>
```

--------------------------------

### Kustomisasi templat model.php untuk attributeLabels() dengan Yii::t()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/id/topics.gii.txt

Templat kode model yang dimodifikasi untuk menghasilkan metode attributeLabels() dengan Yii::t() untuk menerjemahkan label atribut. Gunakan sebagai contoh kustomisasi templat kode generator model, dengan mengakses variabel $labels yang disediakan oleh generator.

```php
public function attributeLabels()
{
	return array(
<?php foreach($labels as $name=>$label): ?>
			<?php echo "'$name' => Yii::t('application', '$label'),\n"; ?>
<?php endforeach; ?>
	);
}
```

--------------------------------

### Enabling widget skins via widgetFactory configuration

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

Enables the skin feature by setting 'enableSkin' to true in the widgetFactory component configuration. Required to use skins for widgets.

```php
return array(
    'components'=>array(
        'widgetFactory'=>array(
            'enableSkin'=>true,
        ),
    ),
);
```

--------------------------------

### Find using array configuration

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Passes an array to find() as an alternative to CDbCriteria. The array keys and values correspond to criteria properties.

```php
$post=Post::model()->find(array(
	'select'=>'title',
	'condition'=>'postID=:postID',
	'params'=>array(':postID'=>10),
));
```

--------------------------------

### Transaction with findByPk and save

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Shows how to wrap a find and save operation in a transaction to ensure consistency. The transaction is committed if the save succeeds, otherwise rolled back. An exception triggers a rollback and rethrow.

```php
$model=Post::model();
$transaction=$model->dbConnection->beginTransaction();
try
{
	// find and save are two steps which may be intervened by another request
	// we therefore use a transaction to ensure consistency and integrity
	$post=$model->findByPk(10);
	$post->title='new post title';
	if($post->save())
		$transaction->commit();
	else
		$transaction->rollback();
}
catch(Exception $e)
{
	$transaction->rollback();
	throw $e;
}
```

--------------------------------

### Nginx server block for Yii with PHP-FPM

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/quickstart.apache-nginx-config.txt

Sample Nginx host configuration that defines the bootstrap file and makes Yii catch all requests to unexisting files for nice-looking URLs. It also prevents serving dotfiles and passes PHP scripts to FastCGI on 127.0.0.1:9000.

```nginx
server {
    set $host_path "/www/mysite";
    access_log  /www/mysite/log/access.log  main;

    server_name  mysite;
    root   $host_path/htdocs;
    set $yii_bootstrap "index.php";

    charset utf-8;

    location / {
        index  index.html $yii_bootstrap;
        try_files $uri $uri/ /$yii_bootstrap?$args;
    }

    location ~ ^/(protected|framework|themes/\w+/views) {
        deny  all;
    }

    #avoid processing of calls to unexisting static files by yii
    location ~ \.(js|css|png|jpg|gif|swf|ico|pdf|mov|fla|zip|rar)$ {
        try_files $uri =404;
    }

    # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
    #
    location ~ \.php {
        fastcgi_split_path_info  ^(.+\.php)(.*)$;

        #let yii catch the calls to unexising PHP files
        set $fsn /$yii_bootstrap;
        if (-f $document_root$fastcgi_script_name){
            set $fsn $fastcgi_script_name;
        }

        fastcgi_pass   127.0.0.1:9000;
        include fastcgi_params;
        fastcgi_param  SCRIPT_FILENAME  $document_root$fsn;

        #PATH_INFO and PATH_TRANSLATED can be omitted, but RFC 3875 specifies them for CGI
        fastcgi_param  PATH_INFO        $fastcgi_path_info;
        fastcgi_param  PATH_TRANSLATED  $document_root$fsn;
    }

    # prevent nginx from serving dotfiles (.htaccess, .svn, .git, etc.)
    location ~ /\. {
        deny all;
        access_log off;
        log_not_found off;
    }
}
```

--------------------------------

### Configure scriptMap to merge JavaScript files

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.performance.txt

Maps individual JavaScript files to a single merged URL '/js/all.js' to reduce requests. Configure the 'scriptMap' property of the 'clientScript' component.

```php
$cs=Yii::app()->clientScript;
$cs->scriptMap=array(
	'jquery.js'=>'/js/all.js',
	'jquery.ajaxqueue.js'=>'/js/all.js',
	'jquery.metadata.js'=>'/js/all.js',
	......
);
```

--------------------------------

### Create URL with createUrl

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

Use this snippet to dynamically generate a URL in a controller. The route and parameters are passed to createUrl, which returns a relative URL. For an absolute URL, prefix with Yii::app()->request->hostInfo or use createAbsoluteUrl.

```php
$url=$this->createUrl($route,$params);
```

--------------------------------

### Alternative yiic command with full PHP path

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/start.testdrive.txt

Alternative command to run yiic when CLI PHP is not on the command search path.

```bash
path/to/php /wwwroot/yii/framework/yiic.php webapp /wwwroot/blog
```

--------------------------------

### Component tag syntax for widgets

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.prado.txt

Shows the general syntax for component tags used to insert widgets. The opening and closing tags wrap the widget body, and a self-closing variant is available for widgets without content.

```php
<com:WidgetClass property1=value1 property2=value2 ...>
	// body content for the widget
</com:WidgetClass>

// a widget without body content
<com:WidgetClass property1=value1 property2=value2 .../>
```

--------------------------------

### Attach and call a behavior method

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.component.txt

Shows how to attach a behavior to a component and call one of its methods. The behavior is identified by a unique name, and the method is called directly on the component.

```php
// $name uniquely identifies the behavior in the component
$component->attachBehavior($name,$behavior);
// test() is a method of $behavior
$component->test();
```

--------------------------------

### Define an action class extending CAction

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.controller.txt

Shows how to define a reusable action class by extending CAction and implementing the run() method. The action logic goes inside run().

```php
class UpdateAction extends CAction
{
	public function run()
	{
		// place the action logic here
	}
}
```

--------------------------------

### Perform validation in the 'register' scenario

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Create a User model in the 'register' scenario, populate it with user input, and trigger validation. The validate() method returns whether validation succeeded.

```php
// creates a User model in register scenario. It is equivalent to:
// $model=new User;
// $model->scenario='register';
$model=new User('register');

// populates the input values into the model
$model->attributes=$_POST['User'];

// performs the validation
if($model->validate())   // if the inputs are valid
    ...
else
    ...
```

--------------------------------

### limit() and offset() method signatures

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Signatures of limit() and offset() methods that specify LIMIT and OFFSET. Note that some DBMS may not support these syntaxes; the Query Builder rewrites the SQL to simulate them.

```php
function limit($limit, $offset=null)
function offset($offset)
```

--------------------------------

### Find using CDbCriteria for complex conditions

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Creates a CDbCriteria instance to specify select, condition, and params, then passes it to find(). The $params argument is not needed when using CDbCriteria.

```php
$criteria=new CDbCriteria;
$criteria->select='title';  // only select the 'title' column
$criteria->condition='postID=:postID';
$criteria->params=array(':postID'=>10);
$post=Post::model()->find($criteria); // $params is not needed
```

--------------------------------

### Entry script index.php

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/start.testdrive.txt

The entry script for the skeleton application. It includes the Yii bootstrap and runs the application.

```php
<?php
$yii='/wwwroot/framework/yii.php';
$config=dirname(__FILE__).'/protected/config/main.php';

// remove the following line when in production mode
defined('YII_DEBUG') or define('YII_DEBUG',true);

require_once($yii);
Yii::createWebApplication($config)->run();
```

--------------------------------

### join() and variants method signatures

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Signatures of join(), leftJoin(), rightJoin(), crossJoin(), and naturalJoin() methods. These specify how to join tables using different join types.

```php
function join($table, $conditions, $params=array())
function leftJoin($table, $conditions, $params=array())
function rightJoin($table, $conditions, $params=array())
function crossJoin($table)
function naturalJoin($table)
```

--------------------------------

### Executing SQL statements with CDbCommand::execute and query methods

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.dao.txt

Shows how to execute non-query SQL (INSERT, UPDATE, DELETE) with execute() and query SQL (SELECT) with query(), queryAll(), queryRow(), queryColumn(), and queryScalar(). The execute() method returns the number of affected rows, while query() returns a CDbDataReader instance. An exception is raised if an error occurs during execution.

```php
$rowCount=$command->execute();   // execute the non-query SQL
$dataReader=$command->query();   // execute a query SQL
$rows=$command->queryAll();      // query and return all rows of result
$row=$command->queryRow();       // query and return the first row of result
$column=$command->queryColumn(); // query and return the first column of result
$value=$command->queryScalar();  // query and return the first field in the first row
```

--------------------------------

### Relation declaration with joinOptions

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows how to set the $joinOptions query option in a relation declaration for the Post model, using USE INDEX for the tags relation.

```php
class Post extends CActiveRecord
{
	public function relations()
	{
		return array(
			'user' => array(self::BELONGS_TO, 'User', 'user_id'),
			'tags' => array(self::MANY_MANY, 'Tag', '{{post_tag}}(post_id, tag_id)',
				'joinOptions' => array(
					'USE INDEX(post_tag__tag) USE INDEX(post_tag__post)',
					'USE INDEX(tag__name)',
				),
			),
		);
	}
}
```

--------------------------------

### Eager loading statistical queries with with()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Eagerly loads commentCount and categoryCount for all posts using with(). Executes three SQL queries total, avoiding the 2*N+1 problem of lazy loading.

```php
$posts=Post::model()->with('commentCount', 'categoryCount')->findAll();
```

--------------------------------

### Configure scriptMap to disable local jQuery and use Google CDN

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.performance.txt

Maps jQuery files to false to prevent Yii from including them locally, then explicitly loads them from Google's CDN using CGoogleApi.

```php
$cs=Yii::app()->clientScript;
$cs->scriptMap=array(
	'jquery.js'=>false,
	'jquery.ajaxqueue.js'=>false,
	'jquery.metadata.js'=>false,
	......
);
```

```php
<head>
<?php echo CGoogleApi::init(); ?>

<?php echo CHtml::script(
	CGoogleApi::load('jquery','1.3.2') . "\n" .
	CGoogleApi::load('jquery.ajaxqueue.js') . "\n" .
	CGoogleApi::load('jquery.metadata.js')
); ?>
......
</head>
```

--------------------------------

### Equivalent attribute assignments

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.action.txt

Shows the manual equivalent of mass assignment for username, password, and rememberMe attributes.

```php
$model->username=$_POST['LoginForm']['username'];
$model->password=$_POST['LoginForm']['password'];
$model->rememberMe=$_POST['LoginForm']['rememberMe'];
```

--------------------------------

### Login view script

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Simple view script that renders the form object. The echo $form is equivalent to $form->render() due to __toString magic method.

```php
<h1>Login</h1>

<div class="form">
<?php echo $form; ?>
</div>
```

--------------------------------

### Skin file for CLinkPager widget

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

Defines two skins ('default' and 'classic') for the CLinkPager widget in a PHP file named CLinkPager.php under protected/views/skins. The 'default' skin is applied when no skin is specified, and 'classic' when the skin property is set to 'classic'.

```php
<?php
return array(
    'default'=>array(
        'nextPageLabel'=>'next',
        'prevPageLabel'=>'prev',
    ),
    'classic'=>array(
        'header'=>'',
        'maxButtonCount'=>5,
    ),
);
```

--------------------------------

### Minimal Yii Entry Script

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.entry.txt

Use this script as the bootstrap for a Yii web application. It defines the YII_DEBUG constant (commented out for production), includes the framework bootstrap file, and creates and runs the application with a configuration file. The comment indicates that the debug constant line should be removed in production mode.

```php
// remove the following line when in production mode
defined('YII_DEBUG') or define('YII_DEBUG',true);
// include Yii bootstrap file
require_once('path/to/yii/framework/yii.php');
// create application instance and run
$configFile='path/to/config/file.php';
Yii::createWebApplication($configFile)->run();
```

--------------------------------

### Configure the db application component for Active Record

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Shows the application configuration for the db component using CDbConnection. The schemaCachingDuration option is commented out but can be enabled to improve performance.

```php
return array(
	'components'=>array(
		'db'=>array(
			'class'=>'system.db.CDbConnection',
			'connectionString'=>'sqlite:path/to/dbfile',
			// turn on schema caching to improve performance
			// 'schemaCachingDuration'=>3600,
		),
	),
);
```

--------------------------------

### createTable method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Shows the signature of the createTable method, which builds and executes a SQL statement for creating a table. The $table parameter specifies the table name, $columns specifies columns as name-definition pairs, and $options appends extra SQL.

```php
function createTable($table, $columns, $options=null)
```

--------------------------------

### Using widget() for widgets without body content

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.view.txt

Use this snippet when the widget does not need any body content. It calls the widget's run() method directly.

```php
<?php $this->widget('path.to.WidgetClass'); ?>
```

--------------------------------

### insert() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Shows the signature of the insert() method, which builds and executes an INSERT SQL statement.

```php
function insert($table, $columns)
```

--------------------------------

### Using UserMenu in layout column2.php

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/portlet.menu.txt

Shows how to embed the UserMenu portlet in the sidebar of the layout. It only renders the widget when the user is not a guest (i.e., authenticated).

```php
......
<div id="sidebar">
	<?php if(!Yii::app()->user->isGuest) $this->widget('UserMenu'); ?>
</div>
......
```

--------------------------------

### Find records using find methods

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Use find, findByPk, findByAttributes, and findBySql methods to read data. The static model() method returns an AR instance for class-level access.

```php
// find the first row satisfying the specified condition
$post=Post::model()->find($condition,$params);
// find the row with the specified primary key
$post=Post::model()->findByPk($postID,$condition,$params);
// find the row with the specified attribute values
$post=Post::model()->findByAttributes($attributes,$condition,$params);
// find the first row using the specified SQL statement
$post=Post::model()->findBySql($sql,$params);
```

--------------------------------

### LoginForm with validation rules and authenticate method

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Extends the LoginForm model with validation rules: username and password are required, rememberMe must be boolean, and password is validated by the authenticate method. The authenticate method creates a UserIdentity and adds an error if authentication fails.

```php
class LoginForm extends CFormModel
{
	public $username;
	public $password;
	public $rememberMe=false;

	private $_identity;

	public function rules()
	{
		return array(
			array('username, password', 'required'),
			array('rememberMe', 'boolean'),
			array('password', 'authenticate'),
		);
	}

	public function authenticate($attribute,$params)
	{
		$this->_identity=new UserIdentity($this->username,$this->password);
		if(!$this->_identity->authenticate())
			$this->addError('password','Incorrect username or password.');
	}
}
```

--------------------------------

### Define a stock quoting service provider with @soap method

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.webservice.txt

Defines the StockController service provider with a getPrice method marked @soap. The method returns a stock price for a given symbol. The provider class extends CController, though not required. The doc comment specifies parameter and return types.

```php
class StockController extends CController
{
	/**
	 * @param string the symbol of the stock
	 * @return float the stock price
	 * @soap
	 */
	public function getPrice($symbol)
	{
		$prices=array('IBM'=>100, 'GOOGLE'=>350);
		return isset($prices[$symbol])?$prices[$symbol]:0;
	    //...return stock price for $symbol
	}
}
```

--------------------------------

### Create tbl_user table

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/nl/quickstart.first-app.txt

This SQL statement creates the tbl_user table used by the test-drive application. It defines columns for id, username, password, and email. The id column is an auto-incrementing primary key.

```sql
CREATE TABLE tbl_user (
	id INTEGER NOT NULL PRIMARY KEY AUTOINCREMENT,
	username VARCHAR(128) NOT NULL,
	password VARCHAR(128) NOT NULL,
	email VARCHAR(128) NOT NULL
);
```

--------------------------------

### Set defaultController to 'post' in application configuration

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/final.deployment.txt

Modify the application configuration to use the post list page as the home page. The 'defaultController' is set to 'post', and because PostController declares 'index' as its default action, the home page will show the index action output.

```php
return array(
	......
	'defaultController'=>'post',
	......
);
```

--------------------------------

### Widget class with client script registration

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.create.txt

Shows a widget class extending CWidget with a registerClientScript method that publishes and registers CSS and JavaScript files using Yii's clientScript. Use this when creating a widget that needs to include assets in the page.

```php
class MyWidget extends CWidget
{
	protected function registerClientScript()
	{
		// ...publish CSS or JavaScript file here...
		$cs=Yii::app()->clientScript;
		$cs->registerCssFile($cssFile);
		$cs->registerScriptFile($jsFile);
	}
}
```

--------------------------------

### views/index.php form view

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.gii.txt

Displays a form using CCodeForm widget, collecting the className input. Includes a tooltip and sticky input field.

```php
<h1>Widget Generator</h1>

<?php $form=$this->beginWidget('CCodeForm', array('model'=>$model)); ?>

	<div class="row">
		<?php echo $form->labelEx($model,'className'); ?>
		<?php echo $form->textField($model,'className',array('size'=>65)); ?>
		<div class="tooltip">
			Widget class name must only contain word characters.
		</div>
		<?php echo $form->error($model,'className'); ?>
	</div>

<?php $this->endWidget(); ?>
```

--------------------------------

### Module directory structure for 'forum'

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.module.txt

Typical directory structure for a module named 'forum'. The module class file is named ForumModule.php, and the default controller is DefaultController.php.

```text
forum/
   ForumModule.php            the module class file
   components/                containing reusable user components
      views/                  containing view files for widgets
   controllers/               containing controller class files
      DefaultController.php   the default controller class file
   extensions/                containing third-party extensions
   models/                    containing model class files
   views/                     containing controller view and layout files
      layouts/                containing layout view files
      default/                containing view files for DefaultController
         index.php            the index view file
```

--------------------------------

### Bootstrap Yii in a third-party system

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.integration.txt

Use this bootstrap code to integrate Yii into an external system like WordPress or Joomla. It creates the web application but does not call run(), allowing Yii features to be used.

```php
require_once('path/to/yii.php');
Yii::createWebApplication('path/to/config.php');
```

--------------------------------

### Global option via public member variable

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Declare a public member variable in the command class to make it a global option available to all actions.

```php
class SitemapCommand extends CConsoleCommand
{
	public $verbose=false;
	public function actionIndex($type) {...}
}
```

--------------------------------

### Disable and enable a behavior

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.component.txt

Shows how to temporarily disable a behavior so its methods are unavailable, then re-enable it. Calling a disabled behavior's method throws an exception.

```php
$component->disableBehavior($name);
// the following statement will throw an exception
$component->test();
$component->enableBehavior($name);
// it works now
$component->test();
```

--------------------------------

### Path alias dot syntax

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.namespace.txt

Shows the dot syntax used to specify a path alias, where RootAlias is the alias of an existing directory.

```text
RootAlias.path.to.target
```

--------------------------------

### Enable logging context information with CLogFilter

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.logging.txt

Configuration for enabling context information logging by setting the 'filter' property of a log route to 'CLogFilter'. This logs variables like $_GET and $_SERVER. Each log route can have its own filter; by default, no filter is applied.

```php
array(
	......
	'preload'=>array('log'),
	'components'=>array(
		......
		'log'=>array(
			'class'=>'CLogRouter',
			'routes'=>array(
				array(
					'class'=>'CFileLogRoute',
					'levels'=>'error',
					'filter'=>'CLogFilter',
				),
				...other log routes...
			),
		),
	),
)
```

--------------------------------

### Insert dynamic content with CController::renderDynamic()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.dynamic.txt

Use this snippet to insert dynamic content inside a fragment cache block. The $callback must be a valid PHP callback (method name, global function, or array) and should return the dynamic content. Additional parameters passed to renderDynamic() are forwarded to the callback.

```php
...other HTML content...
<?php if($this->beginCache($id)) { ?>
...fragment content to be cached...
	<?php $this->renderDynamic($callback); ?>
...fragment content to be cached...
<?php $this->endCache(); } ?>
...other HTML content...
```

--------------------------------

### Configure CMemCache component with multiple servers

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.application.txt

Configuration array that adds a 'cache' component using CMemCache with multiple memcache servers. Use this to customize the cache component.

```php
array(
	......
	'components'=>array(
		......
		'cache'=>array(
			'class'=>'CMemCache',
			'servers'=>array(
				array('host'=>'server1', 'port'=>11211, 'weight'=>60),
				array('host'=>'server2', 'port'=>11211, 'weight'=>40),
			),
		),
	),
)
```

--------------------------------

### Using globally customized CLinkPager widget in a view

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

Creates a CLinkPager widget without specifying custom properties, relying on the global widgetFactory configuration. The global settings are applied automatically.

```php
$this->widget('CLinkPager', array(
	'pages'=>$pagination,
));
```

--------------------------------

### Authenticate and login with UserIdentity

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/prototype.auth.txt

Creates a UserIdentity instance with the provided username and password, calls authenticate(), and checks the error code. If authentication succeeds (ERROR_NONE), it logs the user in via Yii::app()->user->login($identity). The switch statement handles the error code, with the case for ERROR_NONE performing the login. This snippet is used in the blog demo to test authentication against the tbl_user table.

```php
$identity=new UserIdentity($username,$password);
$identity->authenticate();
switch($identity->errorCode)
{
	case UserIdentity::ERROR_NONE:
		Yii::app()->user->login($identity);
		break;
	......
}
```

--------------------------------

### Yii test configuration (test.php) with fixture manager and test database

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/test.overview.txt

Configuration file for Yii tests that merges the main configuration and adds a fixture component. Uncomment the db section and set the connectionString to a test database DSN to avoid interfering with development or production data.

```php
return CMap::mergeArray(
	require(dirname(__FILE__).'/main.php'),
	array(
		'components'=>array(
			'fixture'=>array(
				'class'=>'system.test.CDbFixtureManager',
			),
			/* uncomment the following to provide test database connection
			'db'=>array(
				'connectionString'=>'DSN for test database',
			),
			*/
		),
	)
);
```

--------------------------------

### Defining Component Properties with Getters and Setters

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.component.txt

Shows a component class using getter/setter methods to define properties with additional logic. Includes read-only and write-only properties.

```php
class Document extends CComponent
{
    private $_textWidth;
    protected $_completed=false;

    public function getTextWidth()
    {
        return $this->_textWidth;
    }

    public function setTextWidth($value)
    {
        $this->_textWidth=$value;
    }

    public function getTextHeight()
    {
        // calculates and returns text height
    }

    public function setCompleted($value)
    {
        $this->_completed=$value;
    }
}
```

--------------------------------

### Deny rule for all contexts

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.auth.txt

Add a matching-all deny rule at the end of the rule set to ensure the 'delete' action is not executed when no other rule matches. This is a safety measure because if no rule matches, the action would otherwise be executed.

```php
return array(
    // ... other rules...
    // the following rule denies 'delete' action for all contexts
    array('deny',
        'actions'=>array('delete'),
    ),
);
```

--------------------------------

### Fetching query results with CDbDataReader::read, foreach, and readAll

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.dao.txt

Demonstrates how to retrieve rows from a CDbDataReader instance after calling query(). Use read() in a while loop until it returns false, traverse with foreach, or fetch all rows at once with readAll(). Note that queryXXX() methods return data directly, unlike query().

```php
$dataReader=$command->query();
// calling read() repeatedly until it returns false
while(($row=$dataReader->read())!==false) { ... }
// using foreach to traverse through every row of data
foreach($dataReader as $row) { ... }
// retrieving all rows at once in a single array
$rows=$dataReader->readAll();
```

--------------------------------

### Eager loading with array in findAll()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Pass the with option as an array directly to findAll(). This is equivalent to using CDbCriteria::with and brings back posts with authors, categories, and nested relations.

```php
$posts=Post::model()->findAll(array(
	'with'=>array(
		'author.profile',
		'author.posts',
		'categories',
	)
));
```

--------------------------------

### Apply a specific number of migrations

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Applies the specified number of new migrations. Replace 3 with the desired count.

```shell
yiic migrate up 3
```

--------------------------------

### Define getPosts API method with @soap annotations

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/uk/topics.webservice.txt

Shows a controller action returning an array of Post objects, with @soap annotations on the method and model properties to expose them via SOAP.

```php
class PostController extends CController
{
	/**
	 * @return Post[] список записів
	 * @soap
	 */
	public function getPosts()
	{
		return Post::model()->findAll();
	}
}

class Post extends CActiveRecord
{
	/**
	 * @var integer ID запису
	 * @soap
	 */
	public $id;
	/**
	 * @var string заголовок запису
	 * @soap
	 */
	public $title;

	public static function model($className=__CLASS__)
	{
		return parent::model($className);
	}
}
```

--------------------------------

### Check UTF-8 encoding of translation files

Source: https://github.com/yiisoft/yii/wiki/Documentation-translation-guidelines

Run this command to list every translation file that appears to have incorrect UTF-8 encoding. Use it to verify your translations are correctly encoded.

```shell
build utf8 checkencoding
```

--------------------------------

### Configure CDbFixtureManager in application configuration

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/test.fixture.txt

Configure the 'fixture' component with class 'system.test.CDbFixtureManager' in the application configuration to enable database fixtures for tests.

```php
return array(
	'components'=>array(
		'fixture'=>array(
			'class'=>'system.test.CDbFixtureManager',
		),
	),
);
```

--------------------------------

### Access the generated Yii application in a browser

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/quickstart.first-app.txt

After creating the application, open this URL in a web browser to test drive the application without writing any code. The application includes homepage, about, contact, and login pages.

```text
http://hostname/testdrive/index.php
```

--------------------------------

### Using default scope with findAll

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Calls findAll on Content model, which automatically applies the default scope defined in defaultScope.

```php
$contents=Content::model()->findAll();
```

--------------------------------

### CarUrlRule class implementation

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

Custom URL rule class that implements CBaseUrlRule. It handles /Manufacturer/Model URLs by checking manufacturer and model parameters in createUrl and parsing the path in parseUrl. Must implement both abstract methods.

```php
class CarUrlRule extends CBaseUrlRule
{
	public $connectionID = 'db';

	public function createUrl($manager,$route,$params,$ampersand)
	{
		if ($route==='car/index')
		{
			if (isset($params['manufacturer'], $params['model']))
				return $params['manufacturer'] . '/' . $params['model'];
			else if (isset($params['manufacturer']))
				return $params['manufacturer'];
		}
		return false;  // this rule does not apply
	}

	public function parseUrl($manager,$request,$pathInfo,$rawPathInfo)
	{
		if (preg_match('%^(\w+)(/(\w+))?$%', $pathInfo, $matches))
		{
			// check $matches[1] and $matches[3] to see
			// if they match a manufacturer and a model in the database
			// If so, set $_GET['manufacturer'] and/or $_GET['model']
			// and return 'car/index'
		}
		return false;  // this rule does not apply
	}
}
```

--------------------------------

### Call the _form view script

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Use renderPartial to include the _form view script, passing the form object as a variable. This is the standard way to render the form in a view.

```php
<div class="form">
<?php $this->renderPartial('_form', array('form'=>$form)); ?>
</div>
```

--------------------------------

### Enable schema caching with CDbCache and schemaCachingDuration

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/final.deployment.txt

Add a 'cache' component using CDbCache (default SQLite storage) and set 'schemaCachingDuration' to 3600 seconds on the 'db' component. This caches parsed database schema metadata to avoid repeated analysis in production.

```php
return array(
	......
	'components'=>array(
		......
		'cache'=>array(
			'class'=>'CDbCache',
		),
		'db'=>array(
			'class'=>'system.db.CDbConnection',
			'connectionString'=>'sqlite:/wwwroot/blog/protected/data/blog.db',
			'schemaCachingDuration'=>3600,
		),
	),
);
```

--------------------------------

### UserMenu class extending CPortlet

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/portlet.menu.txt

Defines the UserMenu class that extends CPortlet. It overrides init() to set the title to the current user's name and renderContent() to render the 'userMenu' view. Requires importing CPortlet from the zii library.

```php
Yii::import('zii.widgets.CPortlet');

class UserMenu extends CPortlet
{
	public function init()
	{
		$this->title=CHtml::encode(Yii::app()->user->name);
		parent::init();
	}

	protected function renderContent()
	{
		$this->render('userMenu');
	}
}
```

--------------------------------

### Configure urlManager with path format and rules

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/final.url.txt

Modify the application configuration to set urlFormat to 'path' and define rules for post/view, post/index, and default controller/action routing. This enables two-way URL parsing and generation for SEO-friendly URLs.

```php
return array(
	......
	'components'=>array(
		......
		'urlManager'=>array(
			'urlFormat'=>'path',
			'rules'=>array(
        		'post/<id:\d+>/<title:.*?>'=>'post/view',
        		'posts/<tag:.*?>'=>'post/index',
        		'<controller:\w+>/<action:\w+>'=>'<controller>/<action>',
			),
		),
	),
);
```

--------------------------------

### Login form configuration array

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Returns a PHP array configuration for CForm, specifying elements and buttons for the login form. The array is returned from the loginForm.php file.

```php
return array(
	'title'=>'Please provide your login credential',

    'elements'=>array(
        'username'=>array(
            'type'=>'text',
            'maxlength'=>32,
        ),
        'password'=>array(
            'type'=>'password',
            'maxlength'=>32,
        ),
        'rememberMe'=>array(
            'type'=>'checkbox',
        )
    ),

    'buttons'=>array(
        'login'=>array(
            'type'=>'submit',
            'label'=>'Login',
        ),
    ),
);
```

--------------------------------

### Check for UTF-8 BOM header in translation files

Source: https://github.com/yiisoft/yii/wiki/Documentation-translation-guidelines

Run this command to list every translation file that contains a UTF-8 BOM header. Use it to identify files that need BOM removal.

```shell
build utf8 checkbom
```

--------------------------------

### Use Zend_Search_Lucene in a controller action

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.integration.txt

After including the Lucene class, this snippet shows how to instantiate it and perform a search. The $pathOfIndex variable should be set to the index path.

```php
$lucene=new Zend_Search_Lucene($pathOfIndex);
$hits=$lucene->find(strtolower($keyword));
```

--------------------------------

### Register Form Configuration File

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Configuration file for the register form, defining sub-forms for user and profile with their respective fields and a submit button. The 'title' property is used by the default rendering to enclose each sub-form in a fieldset.

```php
return array(
	'elements'=>array(
		'user'=>array(
			'type'=>'form',
			'title'=>'Login information',
			'elements'=>array(
	        'username'=>array(
	            'type'=>'text',
	        ),
	        'password'=>array(
	            'type'=>'password',
	        ),
	        'email'=>array(
	            'type'=>'text',
	        )
			),
		),

		'profile'=>array(
			'type'=>'form',
			'title'=>'Profile information',
			'elements'=>array(
	        'firstName'=>array(
	            'type'=>'text',
	        ),
	        'lastName'=>array(
	            'type'=>'text',
	        ),
			),
		),
	),

    'buttons'=>array(
        'register'=>array(
            'type'=>'submit',
            'label'=>'Register',
        ),
    ),
);
```

--------------------------------

### Menggunakan Widget CHtmlPurifier untuk Memurnikan Konten

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/id/topics.security.txt

Contoh penggunaan widget CHtmlPurifier untuk memurnikan konten yang ditampilkan dalam badan tampilan. Konten yang dimasukkan pengguna akan disaring untuk menghapus kode berbahaya.

```php
<?php $this->beginWidget('CHtmlPurifier'); ?>
...display user-entered content here...
<?php $this->endWidget(); ?>
```

--------------------------------

### Configure import component with setImport

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.application.txt

Configuration array that sets the 'import' property using the setImport method. Use this to define import paths for the application.

```php
array(
	'import'=>array(
		'application.components.*',
	),
)
```

--------------------------------

### createIndex() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Signature for creating an index. Parameters: $name (index name), $table (table name), $column (column or comma-separated columns), $unique (whether unique). The query builder quotes table, index, and column names.

```php
function createIndex($name, $table, $column, $unique=false)
```

--------------------------------

### Test directory structure generated by yiic webapp

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/test.overview.txt

Shows the directory layout created when using the 'yiic webapp' console command to set up a new Yii application for testing. The 'tests' directory contains subdirectories for fixtures, functional tests, unit tests, and reports, along with bootstrap and configuration files.

```text
testdrive/
   protected/                containing protected application files
      tests/                 containing tests for the application
         fixtures/           containing database fixtures
         functional/         containing functional tests
         unit/               containing unit tests
         report/             containing coverage reports
         bootstrap.php       the script executed at the very beginning
         phpunit.xml         the PHPUnit configuration file
         WebTestCase.php     the base class for Web-based functional tests
```

--------------------------------

### Insert a new record with save()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Create a new AR instance, set its properties, and call save() to insert a row. After insertion, the primary key is updated if auto-incremental.

```php
$post=new Post;
$post->title='sample post';
$post->content='content for the sample post';
$post->create_time=time();
$post->save();
```

--------------------------------

### URL rules configuration array

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

Configuration array for URL rules, including standard patterns and a custom rule using CarUrlRule. The custom rule handles /Manufacturer/Model format. Standard rules map actions and controllers.

```php
array(
	// a standard rule mapping '/' to 'site/index' action
	'' => 'site/index',

	// a standard rule mapping '/login' to 'site/login', and so on
	'<action:(login|logout|about)>' => 'site/<action>',

	// a custom rule to handle '/Manufacturer/Model'
	array(
	    'class' => 'application.components.CarUrlRule',
	    'connectionID' => 'db',
	),

	// a standard rule to handle 'post/update' and so on
	'<controller:\w+>/<action:\w+>' => '<controller>/<action>',
),
```

--------------------------------

### Redo migrations

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Redoes the specified number of migrations by first reverting and then applying them. The optional step parameter defaults to 1.

```shell
yiic migrate redo [step]
```

--------------------------------

### Clip tag syntax

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.prado.txt

Shows the syntax for clip tags, which are shortcuts to beginClip and endClip. The clipID uniquely identifies the clip content.

```php
<clip:clipID>
	// content for this clip
</clip:clipID >
```

```php
<?php $this->beginClip('clipID'); ?>
	// content for this clip
<?php $this->endClip(); ?>
```

--------------------------------

### Return exit codes from console command

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Return an integer from an action or run() method to set the exit code; 0 for success, non-zero for errors.

```php
if (/* error */) {
    return 1; // exit with error code 1
}
// ... do something ...
return 0; // exit successfully
```

--------------------------------

### Clone and add upstream remote for Yii repository

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Clone your fork and add the upstream remote to keep your local repository in sync with the main Yii repository. Replace 'YOUR-GITHUB-USERNAME' with your GitHub username.

```bash
git clone git@github.com:YOUR-GITHUB-USERNAME/yii.git
git remote add upstream git://github.com/yiisoft/yii.git
```

--------------------------------

### Generated application directory structure

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/quickstart.first-app.txt

Shows the directory structure created by the yiic webapp command. It includes entry scripts, assets, protected application files, controllers, models, views, and configuration files. See the linked conventions for a detailed explanation.

```text
testdrive/
   index.php                 Web application entry script file
   index-test.php            entry script file for the functional tests
   assets/                   containing published resource files
   css/                      containing CSS files
   images/                   containing image files
   themes/                   containing application themes
   protected/                containing protected application files
      yiic                   yiic command line script for Unix/Linux
      yiic.bat               yiic command line script for Windows
      yiic.php               yiic command line PHP script
      commands/              containing customized 'yiic' commands
         shell/              containing customized 'yiic shell' commands
      components/            containing reusable user components
         Controller.php      the base class for all controller classes
         UserIdentity.php    the 'UserIdentity' class used for authentication
      config/                containing configuration files
         console.php         the console application configuration
         main.php            the Web application configuration
         test.php            the configuration for the functional tests
      controllers/           containing controller class files
         SiteController.php  the default controller class
      data/                  containing the sample database
         schema.mysql.sql    the DB schema for the sample MySQL database
         schema.sqlite.sql   the DB schema for the sample SQLite database
         testdrive.db        the sample SQLite database file
      extensions/            containing third-party extensions
      messages/              containing translated messages
      models/                containing model class files
         LoginForm.php       the form model for 'login' action
         ContactForm.php     the form model for 'contact' action
      runtime/               containing temporarily generated files
      tests/                 containing test scripts
      views/                 containing controller view files
         layouts/            containing layout view files
            main.php         the base layout shared by all pages
            column1.php      the layout for pages using a single column
            column2.php      the layout for pages using two columns
         site/               containing view files for the 'site' controller
            pages/           containing "static" pages
               about.php     the view for the "about" page
            contact.php      the view for 'contact' action
            error.php        the view for 'error' action (displaying external errors)
            index.php        the view for 'index' action
            login.php        the view for 'login' action
```

--------------------------------

### NGINX Unit configuration for Yii

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/quickstart.apache-nginx-config.txt

Sample NGINX Unit configuration that routes requests to a Yii application, excluding assets, protected, and themes directories. It uses a PHP application with a fallback to index.php.

```json
{
    "listeners": {
        "*:80": {
            "pass": "routes/yii"
        }
    },

    "routes": {
        "yii": [
            {
                "match": {
                    "uri": [
                        "!/assets/*",
                        "!/protected/*",
                        "!/themes/*",
                        "*.php",
                        "*.php/*"
                    ]
                },

                "action": {
                    "pass": "applications/yii/direct"
                }
            },
            {
                "action": {
                    "share": "/path/to/app/",
                    "fallback": {
                        "pass": "applications/yii/index"
                    }
                }
            }
        ]
    },

    "applications": {
        "yii": {
            "type": "php",
            "user": "www-data",
            "targets": {
                "direct": {
                    "root": "/path/to/app/"
                },
                "index": {
                    "root": "/path/to/app/",
                    "script": "index.php"
                }
            }
        }
    }
}
```

--------------------------------

### actionAdmin() - Display posts in admin grid

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/id/post.admin.txt

Displays all posts in a tabular view with sorting and pagination. Creates a Post model with the 'search' scenario, assigns user-supplied filter attributes from $_GET['Post'], and renders the 'admin' view. This method is generated by the yiic tool without modification.

```php
public function actionAdmin()
{
	$model=new Post('search');
	if(isset($_GET['Post']))
		$model->attributes=$_GET['Post'];
	$this->render('admin',array(
		'model'=>$model,
	));
}
```

--------------------------------

### Array parameter declaration in actionIndex

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Declare an action parameter with array type hinting to accept multiple values from repeated command line options.

```php
public function actionIndex(array $types) { ... }
```

--------------------------------

### update() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Shows the signature of the update() method, which builds and executes an UPDATE SQL statement.

```php
function update($table, $columns, $conditions='', $params=array())
```

--------------------------------

### Synchronize requirement checker messages

Source: https://github.com/yiisoft/yii/wiki/Documentation-translation-guidelines

Run this command to synchronize requirement checker messages. Similar procedure to the core messages synchronization.

```shell
build message ../requirements/messages/config.php
```

--------------------------------

### Enable error logging with CLogRouter and CFileLogRoute

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/final.logging.txt

Modify the application configuration to preload the 'log' component and set up a CLogRouter with a CFileLogRoute route that logs 'error' and 'warning' levels to a file. The log file is saved under /wwwroot/blog/protected/runtime. This configuration is used to capture errors and warnings in a production environment.

```php
return array(
	'preload'=>array('log'),

	......

	'components'=>array(
		'log'=>array(
			'class'=>'CLogRouter',
			'routes'=>array(
				array(
					'class'=>'CFileLogRoute',
					'levels'=>'error, warning',
				),
			),
		),
		......
	),
);
```

--------------------------------

### Migrate to a specific version

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Migrates the database to the version identified by the timestamp part of the migration name. Applies all migrations up to that version, or reverts if already applied.

```shell
yiic migrate to 101129_185401
```

--------------------------------

### Defining a Component Property with Public Member

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.component.txt

Defines a simple component class with a public property 'textWidth'. This is the simplest way to define a property.

```php
class Document extends CComponent
{
    public $textWidth;
}
```

--------------------------------

### Define validation rules with the 'on' option

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Specify which scenarios a rule applies to using the 'on' option. If omitted, the rule applies to all scenarios.

```php
public function rules()
{
	return array(
		array('username, password', 'required'),
		array('password_repeat', 'required', 'on'=>'register'),
		array('password', 'compare', 'on'=>'register'),
	);
}
```

--------------------------------

### Massive Assignment Equivalent Loop

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Equivalent foreach loop that manually assigns each safe attribute from the POST data.

```php
foreach($_POST['LoginForm'] as $name=>$value)
{
	if($name is a safe attribute)
		$model->$name=$value;
}
```

--------------------------------

### Відображення коментарів у view.php

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/uk/comment.create.txt

Змінює відображення /wwwroot/blog/protected/views/post/view.php, щоб показати список коментарів та форму створення. Використовує renderPartial() для виведення _comments та перевіряє наявність коментарів через $model->commentCount.

```php
…основна частина відображення post…

<div id="comments">
	<?php if($model->commentCount>=1): ?>
		<h3>
			<?php echo $model->commentCount . 'comment(s)'; ?>
		</h3>

		<?php $this->renderPartial('_comments',array(
			'post'=>$model,
			'comments'=>$model->comments,
		)); ?>
	<?php endif; ?>
</div>
```

--------------------------------

### Add URL rules for path-format URLs

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.gii.txt

Add these URL rules to the front of existing rules when the application uses path-format URLs. This allows accessing Gii via http://hostname/path/to/index.php/gii.

```php
'components'=>array(
	......
	'urlManager'=>array(
		'urlFormat'=>'path',
		'rules'=>array(
			'gii'=>'gii',
			'gii/<controller:\w+>'=>'gii/<controller>',
			'gii/<controller:\w+>/<action:\w+>'=>'gii/<controller>/<action>',
			...existing rules...
		),
	),
)
```

--------------------------------

### Import a directory with Yii::import

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.namespace.txt

Imports a whole directory so that class files under it are automatically included when needed. Note that subdirectories are not imported.

```php
Yii::import('system.web.*');
```

--------------------------------

### Access Gii module via URL

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/prototype.scaffold.txt

Visit this URL in your browser to access the Gii module. You will be prompted to enter the password set in the main.php config file.

```text
http://www.example.com/blog/index.php?r=gii
```

--------------------------------

### Eager loading via CDbCriteria::with

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Specify the with property in a CDbCriteria object to eager load relationships. This is an alternative to passing the with array directly to findAll().

```php
$criteria=new CDbCriteria;
$criteria->with=array(
	'author.profile',
	'author.posts',
	'categories',
);
$posts=Post::model()->findAll($criteria);
```

--------------------------------

### Global widget customization configuration for widgetFactory

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

Configures the widgetFactory component to globally set initial properties for CLinkPager and CJuiDatePicker widgets. The 'widgets' array maps widget class names to property arrays.

```php
return array(
    'components'=>array(
        'widgetFactory'=>array(
            'widgets'=>array(
                'CLinkPager'=>array(
                    'maxButtonCount'=>5,
                    'cssFile'=>false,
                ),
                'CJuiDatePicker'=>array(
                    'language'=>'ru',
                ),
            ),
        ),
    ),
);
```

--------------------------------

### Anonymous parameters with $args

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Declare a parameter named $args to capture anonymous command line parameters.

```php
public function actionIndex($limit=10, $args=array()) {...}
```

--------------------------------

### Include Zend_Search_Lucene class file

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.integration.txt

Use this snippet to include a third-party class file like Zend_Search_Lucene. It requires setting the PHP include path via Yii::import before require_once to locate the file correctly.

```php
Yii::import('application.vendors.*');
require_once('Zend/Search/Lucene.php');
```

--------------------------------

### Update an existing record

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Loads a record with findByPk, modifies a property, and saves it back. save() updates if the instance is from a find call, inserts if new.

```php
$post=Post::model()->findByPk(10);
$post->title='new post title';
$post->save(); // save the change to database
```

--------------------------------

### Generated migration class template

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Initial code generated by the migrate create command. The class name matches the file name with pattern m<timestamp>_<name>. The down() method returns false to indicate the migration is irreversible, and the commented safeUp/safeDown methods are provided for transactional support.

```php
class m101129_185401_create_news_table extends CDbMigration
{
	public function up()
	{
	}

    public function down()
    {
		echo "m101129_185401_create_news_table does not support migration down.\n";
		return false;
    }

	/*
	// implement safeUp/safeDown instead if transaction is needed
	public function safeUp()
	{
	}

	public function safeDown()
	{
	}
	*/
}
```

--------------------------------

### actionIndex

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.display.txt

Displays a list of published posts, optionally filtered by a tag. Uses CDbCriteria and CActiveDataProvider for pagination and sorting.

```APIDOC
## actionIndex

### Description
Displays a list of published posts, optionally filtered by a tag. Uses CDbCriteria and CActiveDataProvider for pagination and sorting.

### Method
GET

### Endpoint
/post/index

### Parameters
#### Query Parameters
- **tag** (string) - Optional - The tag to filter posts by.

### Request Example
GET /post/index?tag=php

### Response
#### Success Response (200)
- **dataProvider** (CActiveDataProvider) - The data provider containing the list of posts.

#### Response Example
{
  "dataProvider": {
    "data": [
      {
        "id": 1,
        "title": "Example Post",
        "content": "Post content",
        "status": 2,
        "tags": "php, yii",
        "update_time": 1234567890,
        "commentCount": 3
      }
    ],
    "pagination": {
      "pageSize": 5,
      "currentPage": 0
    }
  }
}
```

--------------------------------

### delete() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Shows the signature of the delete() method, which builds and executes a DELETE SQL statement.

```php
function delete($table, $conditions='', $params=array())
```

--------------------------------

### Run yiic with explicit php.ini to fix PDO driver error

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/quickstart.first-app-yiic.txt

Workaround for 'could not find driver' errors when running yiic, even if the requirement checker shows PDO enabled. Use the -c flag to specify the correct php.ini file.

```shell
% php -c path/to/php.ini protected/yiic.php shell
```

--------------------------------

### Structure of a code generator directory

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.gii.txt

Shows the typical directory layout for a code generator, including the code model, generator controller, views, and templates. The generator name is the directory name.

```text
model/                       the model generator root folder
   ModelCode.php             the code model used to generate code
   ModelGenerator.php        the code generation controller
   views/                    containing view scripts for the generator
      index.php              the default view script
   templates/                containing code template sets
      default/               the 'default' code template set
         model.php           the code template for generating model class code
```

--------------------------------

### Execute command with global verbose option

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.console.txt

Use the global option in the command line to set the public member variable.

```bash
yiic sitemap index --verbose=1 --type=News
```

--------------------------------

### Accessing fixture data in tests

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/test.unit.txt

Shows how to access fixture data in test methods using the fixture name as a property or array index. The first usage returns all rows from the 'Comment' fixture table, the second returns a specific row by alias, and the third returns an active record instance for that row.

```php
// return all rows in the 'Comment' fixture table
$comments = $this->comments;
// return the row whose alias is 'sample1' in the `Post` fixture table
$post = $this->posts['sample1'];
// return the AR instance representing the 'sample1' fixture data row
$post = $this->posts('sample1');
```

--------------------------------

### Access module property 'postPerPage' from controller

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.module.txt

Shows how to access the module instance and its 'postPerPage' property from a controller. The commented line shows an alternative using $this when inside a controller.

```php
$postPerPage=Yii::app()->controller->module->postPerPage;
// or the following if $this refers to the controller instance
// $postPerPage=$this->module->postPerPage;
```

--------------------------------

### dropTable method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Shows the signature of the dropTable method, which builds and executes a SQL statement for dropping a table.

```php
function dropTable($table)
```

--------------------------------

### Manually place individual form elements

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

For irregular layouts, manually echo each form element by its name between custom HTML. This approach still benefits from the form configuration file even though it requires more manual code.

```php
some complex UI elements here

<?php echo $form['username']; ?>

some complex UI elements here

<?php echo $form['password']; ?>

some complex UI elements here
```

--------------------------------

### User model password validation and hashing methods

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/prototype.auth.txt

Adds validatePassword() and hashPassword() methods to the User model. Uses CPasswordHelper to verify and hash passwords, storing hashes instead of plain text.

```php
class User extends CActiveRecord
{
	......
	public function validatePassword($password)
	{
		return CPasswordHelper::verifyPassword($password,$this->password);
	}

	public function hashPassword($password)
	{
		return CPasswordHelper::hashPassword($password);
	}
}
```

--------------------------------

### Escaping LIKE wildcards in user input

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Shows how to escape % and _ characters in user input before using it in a LIKE condition to prevent them from being treated as wildcards.

```php
$keyword=$_GET['q'];
// escape % and _ characters
$keyword=strtr($keyword, array('%'=>'\%', '_'=>'\_'));
$command->where(array('like', 'title', '%'.$keyword.'%'));
```

--------------------------------

### Define business rules for default roles

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.auth.txt

Creates two default roles with business rules: 'authenticated' applies to non-guest users, and 'admin' applies when the username is 'admin'. The business rule return value determines if the role applies.

```php
$bizRule='return !Yii::app()->user->isGuest;';
$auth->createRole('authenticated', 'authenticated user', $bizRule);

$bizRule='return Yii::app()->user->name === "admin";';
$auth->createRole('admin', 'admin user', $bizRule);
```

--------------------------------

### View script _form to render a form

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

A view script that renders a form by iterating over its elements. It echoes the begin and end tags and each element's render output.

```php
<?php
echo $form->renderBegin();

foreach($form->getElements() as $element)
	echo $element->render();

echo $form->renderEnd();
```

--------------------------------

### Configure CMemCache with two servers

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.overview.txt

Application configuration specifying a cache component using CMemCache with two memcache servers. Access the component via Yii::app()->cache.

```php
array(
	......
	'components'=>array(
		......
		'cache'=>array(
			'class'=>'system.caching.CMemCache',
			'servers'=>array(
				array('host'=>'server1', 'port'=>11211, 'weight'=>60),
				array('host'=>'server2', 'port'=>11211, 'weight'=>40),
			),
		),
	),
);
```

--------------------------------

### PHP: Enable Filter.ExtractStyleBlocks and save extracted styles

Source: https://github.com/yiisoft/yii/blob/master/framework/vendors/htmlpurifier/standalone/HTMLPurifier/ConfigSchema/schema/Filter.ExtractStyleBlocks.txt

Sample usage of the Filter.ExtractStyleBlocks directive. It sets the configuration, purifies HTML, retrieves extracted styles from the context, and writes them to files in a styles directory. Includes a warning about imagecrash attacks via CSS.

```php
<?php
    header('Content-type: text/html; charset=utf-8');
    echo '<?xml version="1.0" encoding="UTF-8"?>';
?>
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" lang="en" xml:lang="en">
<head>
  <title>Filter.ExtractStyleBlocks</title>
<?php
    require_once '/path/to/library/HTMLPurifier.auto.php';
    require_once '/path/to/csstidy.class.php';

    $dirty = '<style>body {color:#F00;}</style> Some text';

    $config = HTMLPurifier_Config::createDefault();
    $config->set('Filter', 'ExtractStyleBlocks', true);
    $purifier = new HTMLPurifier($config);

    $html = $purifier->purify($dirty);

    // This implementation writes the stylesheets to the styles/ directory.
    // You can also echo the styles inside the document, but it's a bit
    // more difficult to make sure they get interpreted properly by
    // browsers; try the usual CSS armoring techniques.
    $styles = $purifier->context->get('StyleBlocks');
    $dir = 'styles/';
    if (!is_dir($dir)) mkdir($dir);
    $hash = sha1($_GET['html']);
    foreach ($styles as $i => $style) {
        file_put_contents($name = $dir . $hash . "_$i");
        echo '<link rel="stylesheet" type="text/css" href="'.$name.'" />';
    }
?>
</head>
<body>
  <div>
    <?php echo $html; ?>
  </div>
</body>
</html>
```

--------------------------------

### Delete an AR instance with delete()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Loads a Post by primary key 10 and deletes the row. After deletion, the AR instance remains unchanged but the database row is gone.

```php
$post=Post::model()->findByPk(10); // assuming there is a post whose ID is 10
$post->delete(); // delete the row from the database table
```

--------------------------------

### Configure CPradoViewRenderer in application config

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.prado.txt

Add the viewRenderer component with class CPradoViewRenderer to the application configuration. This enables the alternative template syntax for views.

```php
return array(
	'components'=>array(
		......,
		'viewRenderer'=>array(
			'class'=>'CPradoViewRenderer',
		),
	),
);
```

--------------------------------

### Skapa databasanslutning med CDbConnection

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/sv/database.dao.txt

Skapar en CDbConnection-instans med DSN, användarnamn och lösenord. Aktivera anslutningen genom att sätta active=true och stäng den med active=false. Fånga undantag vid fel.

```php
$connection=new CDbConnection($dsn,$username,$password);
// establish connection. You may try...catch possible exceptions
$connection->active=true;
......
$connection->active=false;  // close connection
```

--------------------------------

### actionApprove() in CommentController

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.admin.txt

Handles POST requests to approve a comment by loading the model and calling approve(), then redirects to the index. Throws CHttpException for non-POST requests.

```php
public function actionApprove()
{
	if(Yii::app()->request->isPostRequest)
	{
		$comment=$this->loadModel();
		$comment->approve();
		$this->redirect(array('index'));
	}
	else
		throw new CHttpException(400,'Invalid request...');
}
```

--------------------------------

### Configure Gii generatorPaths to add custom path

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.gii.txt

Adds 'common.gii' to the generatorPaths array so Gii searches for generators in that directory in addition to the default locations. The path earlier in the list takes precedence if two generators share the same name.

```php
return array(
	'modules'=>array(
		'gii'=>array(
			'class'=>'system.gii.GiiModule',
			'generatorPaths'=>array(
				'common.gii',   // a path alias
			),
		),
	),
);
```

--------------------------------

### Use cache as an array with ArrayAccess

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Uses the cache component as an array via ArrayAccess. Assigning to an array key stores the value, and reading a key retrieves it.

```php
$cache=Yii::app()->cache;
$cache['var1']=$value1;  // equivalent to: $cache->set('var1',$value1);
$value2=$cache['var2'];  // equivalent to: $value2=$cache->get('var2');
```

--------------------------------

### Namespaced module file structure

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.namespace.txt

Shows the directory layout for a namespaced module. The module class and controller are namespaced, while views remain in the standard location.

```text
/var/www/common/mynamespace/modules
  testmodule
    controllers
      DefaultController.php
    views
      default
        index.php
    TestmoduleModule.php
```

--------------------------------

### Register View Script

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Simple view script that outputs the form object. It includes an HTML heading and a div with class 'form' that echoes the form.

```php
<h1>Register</h1>

<div class="form">
<?php echo $form; ?>
</div>
```

--------------------------------

### AJAX валідація у _form.php

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/uk/comment.create.txt

Налаштовує AJAX валідацію у відображенні /wwwroot/blog/protected/views/comment/_form.php, встановлюючи enableAjaxValidation у true для CActiveForm.

```php
<div class="form">

<?php $form=$this->beginWidget('CActiveForm', array(
	'id'=>'comment-form',
	'enableAjaxValidation'=>true,
)); ?>
…
<?php $this->endWidget(); ?>

</div><!-- form -->
```

--------------------------------

### Accessing post author and comments

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.model.txt

Shows how to access the author and comments of a post using the declared relations.

```php
$author=$post->author;
echo $author->username;

$comments=$post->comments;
foreach($comments as $comment)
	echo $comment->content;
```

--------------------------------

### Configure urlManager for path format

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

Configure the urlManager component with 'urlFormat'=>'path' to switch to the path URL format. This makes URLs cleaner and more user-friendly.

```php
array(
	'components'=>array(
		'urlManager'=>array(
			'urlFormat'=>'path',
		),
	),
);
```

--------------------------------

### Dynamic relational query options with lazy loading (condition status=1)

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Use this snippet to perform a relational query with dynamic options using the lazy loading approach. The method name matches the relation name and accepts an array of query options, here filtering by 'status=1'.

```php
$user=User::model()->findByPk(1);
$posts=$user->posts(array('condition'=>'status=1'));
```

--------------------------------

### Override behaviors() method to attach behaviors

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.use.txt

Shows how to attach behaviors by overriding the behaviors() method in CController, CFormModel, or CActiveRecord classes. The classes will automatically attach the declared behaviors during initialization.

```php
public function behaviors()
{
	return array(
		'xyz'=>array(
			'class'=>'ext.xyz.XyzBehavior',
			'property1'=>'value1',
			'property2'=>'value2',
		),
	);
}
```

--------------------------------

### Access an attached behavior as a property

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.component.txt

Demonstrates how to retrieve a behavior object from a component using its name as a property, with an equivalent call to asa().

```php
$behavior=$component->tree;
// equivalent to the following:
// $behavior=$component->asa('tree');
```

--------------------------------

### CommentTest class with fixtures

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/test.unit.txt

Defines a unit test class extending CDbTestCase with a fixtures array mapping fixture names to model classes or table names. The fixtures are used to reset database tables to a known state before each test method.

```php
class CommentTest extends CDbTestCase
{
	protected $fixtures=array(
		'posts'=>'Post',
		'comments'=>'Comment',
	);

	......
}
```

--------------------------------

### Hostname parameterized URL rule

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

Declares a URL rule with hostname parameters, extracting `user` from the hostname and `lang` from the path info. The rule maps to the `user/profile` route. Note that `CUrlManager::showScriptName` is ignored when creating URLs with such rules, and the rule should not include the sub-folder if the app is under a sub-folder.

```php
array(
	'http://<user:\w+>.example.com/<lang:\w+>/profile' => 'user/profile',
)
```

--------------------------------

### Import a class with Yii::import

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.namespace.txt

Imports the CController class using its path alias. The class is not actually included until first referenced, thanks to PHP autoloading.

```php
Yii::import('system.web.CController');
```

--------------------------------

### Declaring relationships in Post and User classes

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows how to declare relationships in the Post and User AR classes using the relations() method. The Post class defines BELONGS_TO for author and MANY_MANY for categories, while the User class defines HAS_MANY for posts and HAS_ONE for profile.

```php
class Post extends CActiveRecord
{
	......

	public function relations()
	{
		return array(
			'author'=>array(self::BELONGS_TO, 'User', 'author_id'),
			'categories'=>array(self::MANY_MANY, 'Category',
				'tbl_post_category(post_id, category_id)'),
		);
	}
}

class User extends CActiveRecord
{
	......

	public function relations()
	{
		return array(
			'posts'=>array(self::HAS_MANY, 'Post', 'author_id'),
			'profile'=>array(self::HAS_ONE, 'Profile', 'owner_id'),
		);
	}
}
```

--------------------------------

### Enforcing single SQL with together()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/zh_cn/database.arr.txt

Shows how to use the together() method after with() to enforce that only a single SQL statement is generated for HAS_MANY and MANY_MANY relations.

```php
$posts=Post::model()->with(
	'author.profile',
	'author.posts',
	'categories')->together()->findAll();
```

--------------------------------

### Store a value with expiration using set()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Stores a value with an expiration time of 30 seconds. After that period, the data is removed from cache.

```php
// keep the value in cache for at most 30 seconds
Yii::app()->cache->set($id, $value, 30);
```

--------------------------------

### Revert migrations

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Reverts the last one or several applied migrations. The optional step parameter defaults to 1.

```shell
yiic migrate down [step]
```

--------------------------------

### Model definitions for post-JOIN operations

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Defines User, Post, and Tag models with relations to demonstrate post-JOIN operations. The Tag model uses a MANY_MANY relation with a pivot table.

```php
class User extends CActiveRecord
{
	public function relations()
	{
		return array(
			'posts' => array(self::HAS_MANY, 'Post', 'user_id'),
		);
	}
}

class Post extends CActiveRecord
{
	public function relations()
	{
		return array(
			'user' => array(self::BELONGS_TO, 'User', 'user_id'),
			'tags' => array(self::MANY_MANY, 'Tag', '{{post_tag}}(post_id, tag_id)'),
		);
	}
}

class Tag extends CActiveRecord
{
	public function relations()
	{
		return array(
			'posts' => array(self::MANY_MANY, 'Post', '{{post_tag}}(tag_id, post_id)'),
		);
	}
}
```

--------------------------------

### Chaining named scopes with findAll

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Uses the published and recently named scopes in a chain to find recently published posts. Named scopes must appear to the left of a find method call.

```php
$posts=Post::model()->published()->recently()->findAll();
```

--------------------------------

### Eager loading: with('author')

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Use with() together with find() or findAll() to eager load related models in a single join query. This avoids the N+1 query problem of lazy loading.

```php
$posts=Post::model()->with('author')->findAll();
```

--------------------------------

### Fragment caching with duration option

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.fragment.txt

Set the 'duration' option to cache for a specific number of seconds. If not set, defaults to 60 seconds. Duration 0 removes existing cache; negative disables caching but keeps existing content.

```php
...other HTML content...
<?php if($this->beginCache($id, array('duration'=>3600))) { ?>
...content to be cached...
<?php $this->endCache(); } ?>
...other HTML content...
```

--------------------------------

### Define getPosts Web API returning Post array

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.webservice.txt

Shows a controller action and model class for a Web API that returns an array of Post objects. The Post class extends CActiveRecord and marks its public properties with @soap to expose them as composite type properties.

```php
class PostController extends CController
{
	/**
	 * @return Post[] a list of posts
	 * @soap
	 */
	public function getPosts()
	{
		return Post::model()->findAll();
	}
}

class Post extends CActiveRecord
{
	/**
	 * @var integer post ID
	 * @soap
	 */
	public $id;
	/**
	 * @var string post title
	 * @soap
	 */
	public $title;

	public static function model($className=__CLASS__)
	{
		return parent::model($className);
	}
}
```

--------------------------------

### Store a value in cache with set()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Stores a variable in cache with a unique ID. The data remains indefinitely unless removed by caching policy.

```php
Yii::app()->cache->set($id, $value);
```

--------------------------------

### Apply named scopes to main model in relational query

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Applies named scopes 'published' and 'recently' to the main Post model, then eager loads 'comments'. Returns recently published posts with their comments.

```php
$posts=Post::model()->published()->recently()->with('comments')->findAll();
```

--------------------------------

### Create WidgetGenerator class

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.gii.txt

Defines the WidgetGenerator controller class that extends CCodeGenerator and specifies the code model class via the $codeModel property. This class coordinates the code generation process.

```php
class WidgetGenerator extends CCodeGenerator
{
	public $codeModel='application.gii.widget.WidgetCode';
}
```

--------------------------------

### Cache tag syntax

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.prado.txt

Shows the syntax for cache tags used for fragment caching. The fragmentID uniquely identifies the cached content, and property-value pairs configure the cache.

```php
<cache:fragmentID property1=value1 property2=value2 ...>
	// content being cached
</cache:fragmentID >
```

--------------------------------

### Push branch to GitHub

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Pushes your branch to your GitHub fork. The -u flag sets the upstream so future pushes can be done with just 'git push'.

```bash
git push -u origin 999-name-of-your-branch-goes-here
```

--------------------------------

### Display comments in post view

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.create.txt

Modify /wwwroot/blog/protected/views/post/view.php to display a list of comments for the current post. Uses renderPartial() to render the _comments partial view and checks commentCount to conditionally show the comment list.

```php
...post view here...

<div id="comments">
	<?php if($model->commentCount>=1): ?>
		<h3>
			<?php echo $model->commentCount . 'comment(s)'; ?>
		</h3>

		<?php $this->renderPartial('_comments',array(
			'post'=>$model,
			'comments'=>$model->comments,
		)); ?>
	<?php endif; ?>
</div>
```

--------------------------------

### union() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Signature of the union() method that specifies the UNION part of a query. It appends the given SQL using UNION.

```php
function union($sql)
```

--------------------------------

### TagCloud class definition in TagCloud.php

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/portlet.tags.txt

Defines the TagCloud class extending CPortlet. It imports the CPortlet widget, sets default title and maxTags, and overrides renderContent() to output tag links with font sizes based on weight. The class does not use a view; presentation is done directly in renderContent().

```php
Yii::import('zii.widgets.CPortlet');

class TagCloud extends CPortlet
{
	public $title='Tags';
	public $maxTags=20;

	protected function renderContent()
	{
		$tags=Tag::model()->findTagWeights($this->maxTags);

		foreach($tags as $tag=>$weight)
		{
			$link=CHtml::link(CHtml::encode($tag), array('post/index','tag'=>$tag));
			echo CHtml::tag('span', array(
				'class'=>'tag',
				'style'=>"font-size:{$weight}pt",
			), $link)."\n";
		}
	}
}
```

--------------------------------

### Configure authManager with CDbAuthManager

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/ro/topics.auth.txt

Configures the authManager application component to use CDbAuthManager, which stores authorization data in a database. The 'db' component must be configured with a valid connection string.

```php
return array(
	'components'=>array(
		'db'=>array(
			'class'=>'CDbConnection',
			'connectionString'=>'sqlite:path/to/file.db',
		),
		'authManager'=>array(
			'class'=>'CDbAuthManager',
			'connectionID'=>'db',
		),
	),
);
```

--------------------------------

### Delete AR rows with deleteAll and deleteByPk

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Class-level methods to delete rows without loading them first: deleteAll and deleteByPk. $condition and $params are as described in the previous subsection.

```php
// delete the rows matching the specified condition
Post::model()->deleteAll($condition,$params);
// delete the rows matching the specified condition and primary key(s)
Post::model()->deleteByPk($pk,$condition,$params);
```

--------------------------------

### order() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Signature of the order() method that specifies the ORDER BY part of a query. The $columns parameter can be a string or array of columns with optional ASC/DESC directions.

```php
function order($columns)
```

--------------------------------

### Set path alias for custom namespace

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.namespace.txt

Defines a path alias so that classes under the 'mynamespace' namespace can be autoloaded from the specified directory. Use this before referencing any namespaced class.

```php
Yii::setPathOfAlias('mynamespace', '/var/www/common/mynamespace/');
```

--------------------------------

### Passing data to a view with CController::render()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.view.txt

Use this snippet to render a view and pass variables to it. The second array parameter is extracted into local variables in the view script, so you can access $var1 and $var2 directly.

```php
$this->render('edit', array(
	'var1'=>$value1,
	'var2'=>$value2,
));
```

--------------------------------

### Configure classMap for CWebServiceAction

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.webservice.txt

Configures the classMap property of CWebServiceAction to map WSDL types to PHP classes, enabling the service to receive composite type parameters from clients.

```php
class PostController extends CController
{
	public function actions()
	{
		return array(
			'service'=>array(
				'class'=>'CWebServiceAction',
				'classMap'=>array(
					'Post'=>'Post',  // or simply 'Post'
				),
			),
		);
	}
	......
}
```

--------------------------------

### Add upstream remote for Yii

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Adds the main Yii repository as a remote named 'upstream' so you can fetch the latest changes. Run this from the directory where you cloned Yii.

```bash
git remote add upstream git://github.com/yiisoft/yii.git
```

--------------------------------

### from() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Signature of the from() method. It specifies the FROM part of a query. The $tables parameter can be a string of comma-separated table names or an array. Table names are automatically quoted unless they contain parentheses (sub-query or DB expression).

```php
function from($tables)
```

--------------------------------

### .htaccess to protect protected directory

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/start.testdrive.txt

Content of .htaccess file to deny access to the protected directory for Apache.

```apache
deny from all
```

--------------------------------

### Batch update view with tabular input fields

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.table.txt

View that renders an HTML form with a table of input fields for each model instance. Uses CHtml::activeTextField and activeTextArea with array notation like "[$i]name" to generate field names.

```php
<div class="form">
<?php echo CHtml::beginForm(); ?>
<table>
<tr><th>Name</th><th>Price</th><th>Count</th><th>Description</th></tr>
<?php foreach($items as $i=>$item): ?>
<tr>
<td><?php echo CHtml::activeTextField($item,"[$i]name"); ?></td>
<td><?php echo CHtml::activeTextField($item,"[$i]price"); ?></td>
<td><?php echo CHtml::activeTextField($item,"[$i]count"); ?></td>
<td><?php echo CHtml::activeTextArea($item,"[$i]description"); ?></td>
</tr>
<?php endforeach; ?>
</table>

<?php echo CHtml::submitButton('Save'); ?>
<?php echo CHtml::endForm(); ?>
</div><!-- form -->
```

--------------------------------

### Event Handler Signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.component.txt

Shows the required signature for an event handler method. The parameter is an event object.

```php
function methodName($event)
{
    ......
}
```

--------------------------------

### Declare CWebServiceAction in StockController

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.webservice.txt

Declares a 'quote' action using CWebServiceAction in StockController. This exposes the getPrice method as a Web service API. The action is accessible via URL with r=stock/quote.

```php
class StockController extends CController
{
	public function actions()
	{
		return array(
			'quote'=>array(
				'class'=>'CWebServiceAction',
			),
		);
	}

	/**
	 * @param string the symbol of the stock
	 * @return float the stock price
	 * @soap
	 */
	public function getPrice($symbol)
	{
	    //...return stock price for $symbol
	}
}
```

--------------------------------

### Update AR records with updateAll, updateByPk, updateCounters

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Shows three class-level methods to update rows without loading them: updateAll, updateByPk, and updateCounters. $attributes is an array of column values indexed by column names; $counters is an array of incremental values; $condition and $params are as described in the previous subsection.

```php
// update the rows matching the specified condition
Post::model()->updateAll($attributes,$condition,$params);
// update the rows matching the specified condition and primary key(s)
Post::model()->updateByPk($pk,$attributes,$condition,$params);
// update counter columns in the rows satisfying the specified conditions
Post::model()->updateCounters($counters,$condition,$params);
```

--------------------------------

### Customize accessRules() in PostController

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.create.txt

Customizes access control for PostController. Allows all users to access 'index' and 'view' actions, allows authenticated users any action, and denies all other users. Rules are evaluated in order; the first matching rule decides access.

```php
public function accessRules()
{
	return array(
		array('allow',  // allow all users to perform 'list' and 'show' actions
			'actions'=>array('index', 'view'),
			'users'=>array('*'),
		),
		array('allow', // allow authenticated users to perform any action
			'users'=>array('@'),
		),
		array('deny',  // deny all users
			'users'=>array('*'),
		),
	);
}
```

--------------------------------

### Namespaced controller class

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.namespace.txt

Defines a controller under a namespace. Note the explicit backslash before global classes like \CController.

```php
// define namespace:
namespace mynamespace\controllers;

// since class is now under namespace, global namespace
// should be referenced explicitly using "\":
class TestController extends \CController
{
	public function actionIndex()
	{
		echo 'This is TestController from \mynamespace\controllers';
	}
}
```

--------------------------------

### Validation rule format

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Shows the format of a validation rule: an array with attribute list, validator, optional 'on' parameter for scenarios, and additional options for validator initialization.

```php
array('AttributeList', 'Validator', 'on'=>'ScenarioList', ...additional options)
```

--------------------------------

### testApprove method for Comment model

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/test.unit.txt

Tests the approve() method of the Comment model. It inserts a comment in pending status, verifies it is pending, calls approve(), and verifies the status changes to approved.

```php
public function testApprove()
{
	// insert a comment in pending status
	$comment=new Comment;
	$comment->setAttributes(array(
		'content'=>'comment 1',
		'status'=>Comment::STATUS_PENDING,
		'createTime'=>time(),
		'author'=>'me',
		'email'=>'me@example.com',
		'postId'=>$this->posts['sample1']['id'],
	),false);
	$this->assertTrue($comment->save(false));

	// verify the comment is in pending status
	$comment=Comment::model()->findByPk($comment->id);
	$this->assertTrue($comment instanceof Comment);
	$this->assertEquals(Comment::STATUS_PENDING,$comment->status);

	// call approve() and verify the comment is in approved status
	$comment->approve();
	$this->assertEquals(Comment::STATUS_APPROVED,$comment->status);
	$comment=Comment::model()->findByPk($comment->id);
	$this->assertEquals(Comment::STATUS_APPROVED,$comment->status);
}
```

--------------------------------

### Mengaktifkan Validasi CSRF di Konfigurasi Aplikasi

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/id/topics.security.txt

Konfigurasi ini mengaktifkan validasi CSRF pada komponen CHttpRequest. Secara default, penjagaan CSRF dimatikan; atur 'enableCsrfValidation' menjadi true untuk mengaktifkannya.

```php
return array(
	'components'=>array(
		'request'=>array(
			'enableCsrfValidation'=>true,
		),
	),
);
```

--------------------------------

### Access generated user admin page

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/quickstart.first-app-yiic.txt

URL to view the user admin page, which shows entries in a tabular format with sorting, pagination, and CRUD actions.

```text
http://hostname/testdrive/index.php?r=user/admin
```

--------------------------------

### Configure controllerMap with namespaced controller

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.namespace.txt

Adds a namespaced controller to the application's controllerMap in the config file. The controller class is loaded from the specified namespace, bypassing normal controller loading.

```php
// adding "mynamespace" namespace
Yii::setPathOfAlias('mynamespace', '/var/www/common/mynamespace/');

return array(
	'basePath'=>dirname(__FILE__).DIRECTORY_SEPARATOR.'..',
	'name'=>'My Web Application',

	'controllerMap' => array(
		'test' => '\mynamespace\controllers\TestController',
	),
```

--------------------------------

### Enable query caching with DAO using CDbConnection::cache()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Enables query caching for a single DAO query by calling CDbConnection::cache() with a duration of 1000 seconds and a CDbCacheDependency. Yii checks the cache for a valid result based on the SQL statement, expiration, and dependency before executing the query.

```php
$sql = 'SELECT * FROM tbl_post LIMIT 20';
$dependency = new CDbCacheDependency('SELECT MAX(update_time) FROM tbl_post');
$rows = Yii::app()->db->cache(1000, $dependency)->createCommand($sql)->queryAll();
```

--------------------------------

### Keep user logged in for 7 days with allowAutoLogin

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.auth.txt

Sets the login duration to 7 days, requiring allowAutoLogin to be true in the user component. The user remains logged in even after closing the browser, provided cookies are accepted.

```php
// Keep the user logged in for 7 days.
// Make sure allowAutoLogin is set true for the user component.
Yii::app()->user->login($identity,3600*24*7);
```

--------------------------------

### Mixing plain SQL with Query Builder (not working)

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Demonstrates that you cannot modify an existing query specified as a SQL statement. The where method will not append a WHERE clause to the SQL.

```php
$command = Yii::app()->db->createCommand('SELECT * FROM tbl_user');
// the following line will NOT append WHERE clause to the above SQL
$command->where('id=:id', array(':id'=>$id));
```

--------------------------------

### Lookup model with items and item methods

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.model.txt

Modifies the Lookup model to provide static methods for retrieving textual representations of statuses.

```php
class Lookup extends CActiveRecord
{
......

	private static $_items=array();

	public static function items($type)
	{
		if(!isset(self::$_items[$type]))
			self::loadItems($type);
		return self::$_items[$type];
	}

	public static function item($type,$code)
	{
		if(!isset(self::$_items[$type]))
			self::loadItems($type);
		return isset(self::$_items[$type][$code]) ? self::$_items[$type][$code] : false;
	}

	private static function loadItems($type)
	{
		self::$_items[$type]=array();
		$models=self::model()->findAll(array(
			'condition'=>'type=:type',
			'params'=>array(':type'=>$type),
			'order'=>'position',
		));
		foreach($models as $model)
			self::$_items[$type][$model->code]=$model->name;
	}
}
```

--------------------------------

### WidgetCode model class

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.gii.txt

Defines the WidgetCode class extending CCodeModel. It declares a className attribute with validation rules and a prepare() method that generates a widget class file under protected/components.

```php
class WidgetCode extends CCodeModel
{
	public $className;

	public function rules()
	{
		return array_merge(parent::rules(), array(
			array('className', 'required'),
			array('className', 'match', 'pattern'=>'/^\w+$/'),
		));
	}

	public function attributeLabels()
	{
		return array_merge(parent::attributeLabels(), array(
			'className'=>'Widget Class Name',
		));
	}

	public function prepare()
	{
		$path=Yii::getPathOfAlias('application.components.' . $this->className) . '.php';
		$code=$this->render($this->templatepath.'/widget.php');

		$this->files[]=new CCodeFile($path, $code);
	}
}
```

--------------------------------

### approve() method in Comment model

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.admin.txt

Sets the comment status to approved and saves it to the database using the update() method.

```php
public function approve()
{
	$this->status=Comment::STATUS_APPROVED;
	$this->update(array('status'));
}
```

--------------------------------

### having() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Signature of the having() method that specifies the HAVING part of a query. Its usage is the same as where().

```php
function having($conditions, $params=array())
```

--------------------------------

### Cache with file dependency using CFileCacheDependency

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Stores a value with a file dependency. The value expires after 30 seconds or earlier if the dependent file's modification time changes.

```php
// the value will expire in 30 seconds
// it may also be invalidated earlier if the dependent file is changed
Yii::app()->cache->set($id, $value, 30, new CFileCacheDependency('FileName'));
```

--------------------------------

### Define an Active Record class for the tbl_post table

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Minimal AR class extending CActiveRecord. The model() method is required for every AR class, and tableName() returns the table name.

```php
class Post extends CActiveRecord
{
	public static function model($className=__CLASS__)
	{
		return parent::model($className);
	}

	public function tableName()
	{
		return 'tbl_post';
	}
}
```

--------------------------------

### Apply named scopes to related models in relational query

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows three equivalent ways to eager load comments with named scopes 'recently' and 'approved' applied to the related Comment model. The first uses colon syntax, the second uses 'scopes' key in with(), the third uses 'with' in the main query options.

```php
$posts=Post::model()->with('comments:recently:approved')->findAll();
// or since 1.1.7
$posts=Post::model()->with(array(
	'comments'=>array(
		'scopes'=>array('recently','approved')
	),
))->findAll();
// or since 1.1.7
$posts=Post::model()->findAll(array(
	'with'=>array(
		'comments'=>array(
			'scopes'=>array('recently','approved')
		),
	),
));
```

--------------------------------

### Access generated user list page

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/quickstart.first-app-yiic.txt

URL to browse the generated user list page, which displays entries from the tbl_user table.

```text
http://hostname/testdrive/index.php?r=user
```

--------------------------------

### Mark migration history to a specific version

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.migration.txt

Use this command to set the migration history to a specific version without applying or reverting migrations. It only modifies the migration history table.

```bash
yiic migrate mark 101129_185401
```

--------------------------------

### Login form using CHtml helpers

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.view.txt

This is the main login form view using CHtml helper methods. It creates a form with error summary, active labels, text fields, a password field, a checkbox, and a submit button. The form uses the $model variable representing a LoginForm instance.

```php
<div class="form">
<?php echo CHtml::beginForm(); ?>

	<?php echo CHtml::errorSummary($model); ?>

	<div class="row">
		<?php echo CHtml::activeLabel($model,'username'); ?>
		<?php echo CHtml::activeTextField($model,'username') ?>
	</div>

	<div class="row">
		<?php echo CHtml::activeLabel($model,'password'); ?>
		<?php echo CHtml::activePasswordField($model,'password') ?>
	</div>

	<div class="row rememberMe">
		<?php echo CHtml::activeCheckBox($model,'rememberMe'); ?>
		<?php echo CHtml::activeLabel($model,'rememberMe'); ?>
	</div>

	<div class="row submit">
		<?php echo CHtml::submitButton('Login'); ?>
	</div>

<?php echo CHtml::endForm(); ?>
</div><!-- form -->
```

--------------------------------

### Filter method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.controller.txt

Shows the required signature for a filter method, which must call $filterChain->run() to continue execution.

```php
public function filterAccessControl($filterChain)
{
	// call $filterChain->run() to continue filter and action execution
}
```

--------------------------------

### Verify URI checksum with hash_hmac

Source: https://github.com/yiisoft/yii/blob/master/framework/vendors/htmlpurifier/standalone/HTMLPurifier/ConfigSchema/schema/URI.MungeSecretKey.txt

Use this PHP code to verify that a URI has been processed by HTML Purifier when URI.MungeSecretKey is set. It compares the checksum in the URI (represented by %t) against a freshly computed HMAC-SHA256 hash of the URL using the secret key. If the comparison returns TRUE, the redirector should accept the URI.

```php
$checksum === hash_hmac("sha256", $url, $secret_key)
```

--------------------------------

### Logging messages with Yii::log and Yii::trace

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.logging.txt

Use Yii::log to log a message with a specified level and category, and Yii::trace to log only in debug mode. Category should follow the path alias format like 'system.web.CController'.

```php
Yii::log($message, $level, $category);
Yii::trace($message, $category);
```

--------------------------------

### Using an Action Extension in a Controller

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.use.txt

Override the CController::actions method to use an action extension. The action is accessed via the route 'test/xyz'.

```php
class TestController extends CController
{
	public function actions()
	{
		return array(
			'xyz'=>array(
				'class'=>'ext.xyz.XyzClass',
				'property1'=>'value1',
				'property2'=>'value2',
			),
			// other actions
		);
	}
}
```

--------------------------------

### Generate theme image URL using baseUrl

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

Inside a theme view, use the active theme's baseUrl property to link resource files such as images. Concatenate the baseUrl with the relative path to the file.

```php
Yii::app()->theme->baseUrl . '/images/FileName.gif'
```

--------------------------------

### Define Tag::string2array and Tag::array2string

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.model.txt

Helper methods in Tag model to convert between comma-separated string and array of tags.

```php
public static function string2array($tags)
{
	return preg_split('/\s*,\s*/',trim($tags),-1,PREG_SPLIT_NO_EMPTY);
}

public static function array2string($tags)
{
	return implode(', ',$tags);
}
```

--------------------------------

### Creating a Nested Form Action

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Action method for user registration that creates a nested form, assigns User and Profile models to sub-forms, validates, and saves both models. It retrieves models via the 'model' property of sub-form objects and skips validation on save.

```php
public function actionRegister()
{
	$form = new CForm('application.views.user.registerForm');
	$form['user']->model = new User;
	$form['profile']->model = new Profile;
	if($form->submitted('register') && $form->validate())
	{
		$user = $form['user']->model;
		$profile = $form['profile']->model;
		if($user->save(false))
		{
			$profile->userID = $user->id;
			$profile->save(false);
			$this->redirect(array('site/index'));
		}
	}

	$this->render('register', array('form'=>$form));
}
```

--------------------------------

### Disambiguate column names in relational query

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Illustrates how to use the 'with' method in a relational AR query to load related comments, where the primary table alias is 't' and the relational table alias is the relation name 'comments'.

```php
$posts=Post::model()->with('comments')->findAll();
```

--------------------------------

### UserIdentity class for database authentication

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.auth.txt

Defines a UserIdentity class that authenticates a user by looking up the username in the database, verifying the password with CPasswordHelper, and storing the user ID and title in state. Overrides getId() to return the stored ID instead of the username.

```php
class UserIdentity extends CUserIdentity
{
	private $_id;
	public function authenticate()
	{
		$record=User::model()->findByAttributes(array('username'=>$this->username));
		if($record===null)
			$this->errorCode=self::ERROR_USERNAME_INVALID;
		else if(!CPasswordHelper::verifyPassword($this->password,$record->password))
			$this->errorCode=self::ERROR_PASSWORD_INVALID;
		else
		{
			$this->_id=$record->id;
			$this->setState('title', $record->title);
			$this->errorCode=self::ERROR_NONE;
		}
		return !$this->errorCode;
    }

	public function getId()
	{
		return $this->_id;
	}
}
```

--------------------------------

### Check access for createPost operation

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/pt_br/topics.auth.txt

Use Yii::app()->user->checkAccess('createPost') to verify if the current user has the createPost permission. The code block shows the if statement that would contain the post creation logic.

```php
if(Yii::app()->user->checkAccess('createPost'))
{
	// create post
}
```

--------------------------------

### templates/default/widget.php code template

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.gii.txt

The code template used to generate the widget class. It outputs the class definition with the user-entered class name.

```php
<?php echo '<?php'; ?>

class <?php echo $this->className; ?> extends CWidget
{
	public function run()
	{

	}
}
```

--------------------------------

### renameTable method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Shows the signature of the renameTable method, which builds and executes a SQL statement for renaming a table. The $table parameter is the current table name and $newName is the new name.

```php
function renameTable($table, $newName)
```

--------------------------------

### UserIdentity class with authenticate() and getId()

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/prototype.auth.txt

Custom UserIdentity class that authenticates against the User ActiveRecord model. It overrides authenticate() to look up the user by lowercase username, validate the password with User::validatePassword(), and set the internal _id. Also overrides getId() to return the database id instead of the username.

```php
<?php
class UserIdentity extends CUserIdentity
{
	private $_id;

	public function authenticate()
	{
		$username=strtolower($this->username);
		$user=User::model()->find('LOWER(username)=?',array($username));
		if($user===null)
			$this->errorCode=self::ERROR_USERNAME_INVALID;
		else if(!$user->validatePassword($this->password))
			$this->errorCode=self::ERROR_PASSWORD_INVALID;
		else
		{
			$this->_id=$user->id;
			$this->username=$user->username;
			$this->errorCode=self::ERROR_NONE;
		}
		return $this->errorCode==self::ERROR_NONE;
	}

	public function getId()
	{
		return $this->_id;
	}
}
```

--------------------------------

### select() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Signature of the select() method. It specifies the SELECT part of a query. The $columns parameter can be a string of comma-separated columns or an array of column names. Column names are automatically quoted unless they contain parentheses (DB expression).

```php
function select($columns='*')
```

--------------------------------

### Configure URL rules for user-friendly URLs

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

Specify URL rules in the urlManager component to create user-friendly URLs. The rules are an array of pattern-route pairs, where the pattern matches the path info and the route is a valid controller route.

```php
array(
	'components'=>array(
		'urlManager'=>array(
			'urlFormat'=>'path',
			'rules'=>array(
				'pattern1'=>'route1',
				'pattern2'=>'route2',
				'pattern3'=>'route3',
			),
		),
	),
);
```

--------------------------------

### Render status dropdown in _form.php

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.create.txt

Renders a dropdown list for the 'status' attribute in the post form. Options are provided by Lookup::items('PostStatus').

```php
<?php echo $form->dropDownList($model,'status',Lookup::items('PostStatus')); ?>
```

--------------------------------

### Batch update action for tabular input

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.table.txt

Controller action that retrieves items to update, assigns POST data to each model, validates them all, and renders the batch update view. Uses $_POST['Item'][$i] to access per-model input.

```php
public function actionBatchUpdate()
{
	// retrieve items to be updated in a batch mode
	// assuming each item is of model class 'Item'
	$items=$this->getItemsToUpdate();
	if(isset($_POST['Item']))
	{
		$valid=true;
		foreach($items as $i=>$item)
		{
			if(isset($_POST['Item'][$i]))
				$item->attributes=$_POST['Item'][$i];
			$valid=$item->validate() && $valid;
		}
		if($valid)  // all items are valid
			// ...do something here
	}
	// displays the view to collect tabular input
	$this->render('batchUpdate',array('items'=>$items));
}
```

--------------------------------

### Customize Post::rules() method

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.model.txt

Customized validation rules for the Post model. Specifies required attributes, length limit for title, status range, tag pattern, and a safe rule for search.

```php
public function rules()
{
	return array(
		array('title, content, status', 'required'),
		array('title', 'length', 'max'=>128),
		array('status', 'in', 'range'=>array(1,2,3)),
		array('tags', 'match', 'pattern'=>'/^[\w\s,]+$/',
			'message'=>'Tags can only contain word characters.'),
		array('tags', 'normalizeTags'),

		array('title, status', 'safe', 'on'=>'search'),
	);
}
```

--------------------------------

### Register namespaced module in application config

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.namespace.txt

Adds the namespaced module to the application's module list in the config file. The module class is referenced with a leading backslash to indicate the global namespace.

```php
// adding "mynamespace" namespace
Yii::setPathOfAlias('mynamespace', '/var/www/common/mynamespace/');

return array(
	'basePath'=>dirname(__FILE__).DIRECTORY_SEPARATOR.'..',
	'name'=>'My Web Application',

	'modules'=>array(
		'testmodule' => array(
			'class' => '\mynamespace\modules\testmodule\TestModuleModule',
		),
	),
```

--------------------------------

### Configuring Error Handler Component

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.error.txt

Configure the 'errorHandler' component in the application configuration to set the 'errorAction' property to a route like 'site/error'. This routes error display to a controller action.

```php
return array(
	'components'=>array(
		'errorHandler'=>array(
			'errorAction'=>'site/error',
		),
	),
);
```

--------------------------------

### Add files to staging area

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Adds a specific file to the Git staging area. Use the -p option to select specific changes if needed.

```bash
git add path/to/my/file.php
```

--------------------------------

### andWhere() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Declares the andWhere() method signature that appends a condition to the WHERE part with AND. Behavior is similar to where() but appends instead of replaces.

```php
function andWhere($conditions, $params=array())
```

--------------------------------

### Modify actionView and add newComment method

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.create.txt

Modify PostController::actionView() to load the post, create a new comment via newComment(), and render the view. The newComment() method handles comment submission, sets status based on approval setting, and refreshes the page on success.

```php
public function actionView()
{
	$post=$this->loadModel();
	$comment=$this->newComment($post);

	$this->render('view',array(
		'model'=>$post,
		'comment'=>$comment,
	));
}

protected function newComment($post)
{
	$comment=new Comment;
	if(isset($_POST['Comment']))
	{
		$comment->attributes=$_POST['Comment'];
		if($post->addComment($comment))
		{
			if($comment->status==Comment::STATUS_PENDING)
				Yii::app()->user->setFlash('commentSubmitted','Thank you for your comment. Your comment will be posted once it is approved.');
			$this->refresh();
		}
	}
	return $comment;
}
```

--------------------------------

### Synchronize Yii core messages

Source: https://github.com/yiisoft/yii/wiki/Documentation-translation-guidelines

Run this command to extract original messages from Yii framework and merge them with translations under the 'messages' directory. Check the merged file for changes since your last translation.

```shell
build message ../framework/messages/config.php
```

--------------------------------

### Modified actionIndex() in CommentController

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.admin.txt

Shows all comments, ordering pending approval first. Uses CActiveDataProvider with a criteria that joins the post relation and orders by status and creation time, disambiguating columns with the 't' alias.

```php
public function actionIndex()
{
	$dataProvider=new CActiveDataProvider('Comment', array(
		'criteria'=>array(
			'with'=>'post',
			'order'=>'t.status, t.create_time DESC',
		),
	));

	$this->render('index',array(
		'dataProvider'=>$dataProvider,
	));
}
```

--------------------------------

### Using parameterized named scope

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Retrieves the 3 most recent published posts by passing 3 to the recently scope. Without the argument, it would return 5.

```php
$posts=Post::model()->published()->recently(3)->findAll();
```

--------------------------------

### Check access with business rule parameters for updateOwnPost

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/pt_br/topics.auth.txt

Pass additional parameters required by a business rule via the $params array. Here, the post data is passed to checkAccess for the updateOwnPost operation.

```php
$params=array('post'=>$post);
if(Yii::app()->user->checkAccess('updateOwnPost',$params))
{
	// update post
}
```

--------------------------------

### Modify posts relationship in User model

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows how to declare the 'posts' and 'profile' relations in the User model's relations() method, using options like 'order' and 'with'. The 'posts' relation uses HAS_MANY with 'Post' and 'author_id', ordering by 'posts.create_time DESC' and eager loading 'categories'. The 'profile' relation uses HAS_ONE with 'Profile' and 'owner_id'.

```php
class User extends CActiveRecord
{
	public function relations()
	{
		return array(
			'posts'=>array(self::HAS_MANY, 'Post', 'author_id',
							'order'=>'posts.create_time DESC',
							'with'=>'categories'),
			'profile'=>array(self::HAS_ONE, 'Profile', 'owner_id'),
		);
	}
}
```

--------------------------------

### Profile code blocks with Yii::beginProfile and Yii::endProfile

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.logging.txt

Mark the beginning and end of a code block to be profiled. The blockID must uniquely identify the block, and blocks must be properly nested (parallel or fully enclosed).

```php
Yii::beginProfile('blockID');
...code block being profiled...
Yii::endProfile('blockID');
```

--------------------------------

### Specifying Sub-form Configuration

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Configuration array for a root form with 'user' and 'profile' sub-forms, each with their own elements. The 'user' sub-form includes username, password, and email fields; 'profile' is left with an ellipsis placeholder. This demonstrates how to structure nested forms in Yii's CForm configuration.

```php
return array(
    'elements'=>array(
		......
        'user'=>array(
            'type'=>'form',
            'title'=>'Login Credential',
            'elements'=>array(
            	'username'=>array(
            		'type'=>'text',
            	),
            	'password'=>array(
            		'type'=>'password',
            	),
            	'email'=>array(
            		'type'=>'text',
            	),
            ),
        ),

        'profile'=>array(
        	'type'=>'form',
        	......
        ),
        ......
    ),
	......
);
```

--------------------------------

### Anonymous Event Handler

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.component.txt

Shows attaching an anonymous function as an event handler, supported in PHP 5.3+.

```php
$component->onClicked=function($event) {
	......
}
```

--------------------------------

### Namespaced module controller

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.namespace.txt

Defines a controller within a namespaced module. The controller extends the global \Controller class and renders the 'index' view.

```php
<?php
// define namespace:
namespace mynamespace\modules\testmodule\controllers;

// since class is now under namespace, global namespace
// should be referenced explicitly using "\":
class DefaultController extends \Controller
{
	public function actionIndex()
	{
		$this->render('index');
	}
}
```

--------------------------------

### Defining a relation with 'through' option

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows the syntax for defining a relation with the 'through' option. The 'comments' relation uses 'through' => 'posts' to traverse from User to Comment via Post.

```php
'comments'=>array(self::HAS_MANY,'Comment',array('key1'=>'key2'),'through'=>'posts'),
```

--------------------------------

### Login form using CActiveForm widget

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.view.txt

This is the rewritten version of the login form using the CActiveForm widget. It provides seamless client-side validation and uses active form methods like activeLabel, textField, passwordField, and checkBox. The form is wrapped in beginWidget and endWidget.

```php
<div class="form">
<?php $form=$this->beginWidget('CActiveForm'); ?>

	<?php echo $form->errorSummary($model); ?>

	<div class="row">
		<?php echo $form->label($model,'username'); ?>
		<?php echo $form->textField($model,'username') ?>
	</div>

	<div class="row">
		<?php echo $form->label($model,'password'); ?>
		<?php echo $form->passwordField($model,'password') ?>
	</div>

	<div class="row rememberMe">
		<?php echo $form->checkBox($model,'rememberMe'); ?>
		<?php echo $form->label($model,'rememberMe'); ?>
	</div>

	<div class="row submit">
		<?php echo CHtml::submitButton('Login'); ?>
	</div>

<?php $this->endWidget(); ?>
</div><!-- form -->
```

--------------------------------

### Defining relations with named scopes in 'with' option

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows two ways to define a relation with a named scope in the 'with' option: using the string syntax 'comments:approved' and the array syntax with 'scopes' key (since 1.1.7). Both achieve the same result.

```php
class User extends CActiveRecord
{
	public function relations()
	{
		return array(
			'posts'=>array(self::HAS_MANY, 'Post', 'author_id',
				'with'=>'comments:approved'),
		);
	}
}

// or since 1.1.7
class User extends CActiveRecord
{
	public function relations()
	{
		return array(
		    'posts'=>array(self::HAS_MANY, 'Post', 'author_id',
				'with'=>array(
					'comments'=>array(
						'scopes'=>'approved'
					),
				),
			),
		);
	}
}
```

--------------------------------

### Display comment form with flash message

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.create.txt

Further modify /wwwroot/blog/protected/views/post/view.php to show a flash message if a comment was submitted, otherwise render the comment form partial. Uses Yii::app()->user->hasFlash() and getFlash().

```php
......
<div id="comments">
	......
	<h3>Leave a Comment</h3>

	<?php if(Yii::app()->user->hasFlash('commentSubmitted')): ?>
		<div class="flash-success">
			<?php echo Yii::app()->user->getFlash('commentSubmitted'); ?>
		</div>
	<?php else: ?>
		<?php $this->renderPartial('/comment/_form',array(
			'model'=>$comment,
		)); ?>
	<?php endif; ?>

</div><!-- comments -->
```

--------------------------------

### group() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Signature of the group() method that specifies the GROUP BY part of a query. The $columns parameter can be a string or array of columns.

```php
function group($columns)
```

--------------------------------

### Passing parameters to relational named scopes

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows how to pass parameters to a named scope in a relational query. The 'rated' scope in Post accepts a minimum rating, and it is used in the 'with' option of User::findAll().

```php
$users=User::model()->findAll(array(
	'with'=>array(
		'posts'=>array(
			'scopes'=>array(
				'rated'=>5,
			),
		),
	),
));

class Post extends CActiveRecord
{
	......

	public function rated($rating)
	{
		$this->getDbCriteria()->mergeWith(array(
			'condition'=>'rating=:rating',
			'params'=>array(':rating'=>$rating),
		));
		return $this;
	}

	......
}
```

--------------------------------

### Assign unsafe attributes individually

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

For attributes that are not safe, assign them individually using separate statements.

```php
$model->permission='admin';
$model->id=1;
```

--------------------------------

### Attaching an Event Handler

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.component.txt

Attaches a callback to the 'onClicked' event. The callback can be a global function or a class method.

```php
$component->onClicked=$callback;
```

--------------------------------

### Delete local and remote branches after contribution

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Use these commands to clean up branches from your local repository and origin after your code was accepted or declined. Replace '999-name-of-your-branch-goes-here' with your actual branch name.

```bash
git checkout master
git branch -D 999-name-of-your-branch-goes-here
git push origin --delete 999-name-of-your-branch-goes-here
```

--------------------------------

### beforeSave() method for Comment model

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.model.txt

Overrides beforeSave() to set the creation time for new records. Returns true if the parent's beforeSave() succeeds, otherwise false.

```php
protected function beforeSave()
{
	if(parent::beforeSave())
	{
		if($this->isNewRecord)
			$this->create_time=time();
		return true;
	}
	else
		return false;
}
```

--------------------------------

### selectDistinct() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Signature of the selectDistinct() method. It is similar to select() but turns on the DISTINCT flag.

```php
function selectDistinct($columns)
```

--------------------------------

### Configure COutputCache filter for page caching

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.page.txt

Configure the COutputCache filter in a controller's filters() method to cache the entire page output for 100 seconds, varying by the 'id' parameter. This filter applies to all actions in the controller unless limited with the plus operator.

```php
public function filters()
{
	return array(
		array(
			'COutputCache',
			'duration'=>100,
			'varyByParam'=>array('id'),
		),
	);
}
```

--------------------------------

### LoginForm model class definition

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Defines a LoginForm model with attributes for username, password, and rememberMe. The rememberMe attribute defaults to false, making the corresponding option unchecked initially.

```php
class LoginForm extends CFormModel
{
	public $username;
	public $password;
	public $rememberMe=false;
}
```

--------------------------------

### Fragment caching with dependency

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.fragment.txt

Specify a dependency (e.g., CDbCacheDependency) to invalidate the cache when the underlying data changes. The dependency can be an object or a configuration array.

```php
...other HTML content...
<?php if($this->beginCache($id, array('dependency'=>array(
		'class'=>'system.caching.dependencies.CDbCacheDependency',
		'sql'=>'SELECT MAX(lastModified) FROM Post')))) { ?>
...content to be cached...
<?php $this->endCache(); } ?>
...other HTML content...
```

--------------------------------

### Choice format message syntax

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.i18n.txt

A translated message using choice format consists of expression-message pairs separated by '|'. Each expression evaluates to a boolean, and the first true expression's message is returned. The variable 'n' holds the number passed as the first message parameter.

```php
'expr1#message1|expr2#message2|expr3#message3'
```

--------------------------------

### Apache rewrite rules to hide index.php

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.url.txt

Configures Apache to rewrite URLs to `index.php` when the requested file or directory does not exist. This enables hiding the entry script `index.php` from URLs. The same content can be placed in the Apache configuration within the `Directory` element for `/wwwroot/blog`.

```apache
RewriteEngine on

# if a directory or a file exists, use it directly
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d

# otherwise forward it to index.php
RewriteRule . index.php
```

--------------------------------

### Override afterSave() and afterFind() in Post model

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.create.txt

Updates tag frequencies after saving and stores old tags in afterFind() to detect changes. afterSave() calls Tag::updateFrequency() with old and new tags.

```php
protected function afterSave()
{
	parent::afterSave();
	Tag::model()->updateFrequency($this->_oldTags, $this->tags);
}

private $_oldTags;

protected function afterFind()
{
	parent::afterFind();
	$this->_oldTags=$this->tags;
}
```

--------------------------------

### Use query caching with ActiveRecord via CActiveRecord::cache()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Uses query caching with ActiveRecord by calling CActiveRecord::cache(), which is a shortcut to CDbConnection::cache(). The first call caches the basic findAll() query; the second caches a relational query with the 'author' relation.

```php
$dependency = new CDbCacheDependency('SELECT MAX(update_time) FROM tbl_post');
$posts = Post::model()->cache(1000, $dependency)->findAll();
// relational AR query
$posts = Post::model()->cache(1000, $dependency)->with('author')->findAll();
```

--------------------------------

### admin view - CGridView with custom columns

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/id/post.admin.txt

View for the admin grid. Uses CGridView with a search data provider and filter model. Customizes columns: title is rendered as a hyperlink using CHtml::link and CHtml::encode, status uses Lookup::item, create_time is formatted as datetime, and a CButtonColumn provides action buttons. CHtml::encode prevents cross-site scripting.

```php
<?php
$this->breadcrumbs=array(
	'Manage Posts',
);
?>
<h1>Manage Posts</h1>

<?php $this->widget('zii.widgets.grid.CGridView', array(
	'dataProvider'=>$model->search(),
	'filter'=>$model,
	'columns'=>array(
		array(
			'name'=>'title',
			'type'=>'raw',
			'value'=>'CHtml::link(CHtml::encode($data->title), $data->url)'
		),
		array(
			'name'=>'status',
			'value'=>'Lookup::item("PostStatus",$data->status)',
			'filter'=>Lookup::items('PostStatus'),
		),
		array(
			'name'=>'create_time',
			'type'=>'datetime',
			'filter'=>false,
		),
		array(
			'class'=>'CButtonColumn',
		),
	),
)); ?>
```

--------------------------------

### Advanced log route configuration with exclude feature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.logging.txt

Shows how to use the 'except' feature (Yii 1.1.13+) to exclude categories from log routes. The first route emails all errors/warnings except CModule logs; the second shows all db logs except the ar subcategory.

```php
	'routes'=>array(
		array(
			'class'=>'CEmailLogRoute',
			'levels'=>'error, warning',
			'except'=>'system.CModule.*', // Will email everything except any CModule logs
			'emails'=>'admin@example.com',
		),
		array(
			'class'=>'CWebLogRoute',
			'categories'=>'system.db.*',
			'except'=>'system.db.ar.*', // shows all db level logs but nothing in the ar category
		),
	)
```

--------------------------------

### Embed RecentComments portlet in layout

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/portlet.comments.txt

Modifies the layout file /wwwroot/blog/protected/views/layouts/column2.php to embed the RecentComments portlet in the sidebar, passing the maxComments parameter from the application parameters.

```php
......
<div id="sidebar">

	<?php if(!Yii::app()->user->isGuest) $this->widget('UserMenu'); ?>

	<?php $this->widget('TagCloud', array(
		'maxTags'=>Yii::app()->params['tagCloudCount'],
	)); ?>

	<?php $this->widget('RecentComments', array(
		'maxComments'=>Yii::app()->params['recentCommentCount'],
	)); ?>

</div>
......
```

--------------------------------

### Validator class implementing validateAttribute

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.create.txt

Shows a validator extending CValidator with a validateAttribute method. Use this to create custom validators that check an attribute and add an error message if validation fails.

```php
class MyValidator extends CValidator
{
	protected function validateAttribute($model,$attribute)
	{
		$value=$model->$attribute;
		if($value has error)
			$model->addError($attribute,$errorMessage);
	}
}
```

--------------------------------

### Mass assign attributes from POST array

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Uses the attributes property to mass-assign column values from an array indexed by column names, assuming $_POST['Post'] is such an array. Then saves the record.

```php
// assume $_POST['Post'] is an array of column values indexed by column names
$post->attributes=$_POST['Post'];
$post->save();
```

--------------------------------

### Customize Post::relations() method

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.model.txt

Customized relations for Post: author (BELONGS_TO), approved comments (HAS_MANY), and comment count (STAT).

```php
public function relations()
{
	return array(
		'author' => array(self::BELONGS_TO, 'User', 'author_id'),
		'comments' => array(self::HAS_MANY, 'Comment', 'post_id',
			'condition'=>'comments.status='.Comment::STATUS_APPROVED,
			'order'=>'comments.create_time DESC'),
		'commentCount' => array(self::STAT, 'Comment', 'post_id',
			'condition'=>'status='.Comment::STATUS_APPROVED),
	);
}
```

--------------------------------

### Handle AJAX validation request in newComment()

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.create.txt

In the newComment() method, check for the POST variable 'ajax' and if it matches 'comment-form', output the validation results using CActiveForm::validate() and end the application.

```php
protected function newComment($post)
{
	$comment=new Comment;

	if(isset($_POST['ajax']) && $_POST['ajax']==='comment-form')
	{
		echo CActiveForm::validate($comment);
		Yii::app()->end();
	}

	if(isset($_POST['Comment']))
	{
		$comment->attributes=$_POST['Comment'];
		if($post->addComment($comment))
		{
			if($comment->status==Comment::STATUS_PENDING)
				Yii::app()->user->setFlash('commentSubmitted','Thank you for your comment. Your comment will be posted once it is approved.');
			$this->refresh();
		}
	}
	return $comment;
}
```

--------------------------------

### PHP: newComment method for comment creation

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/id/comment.create.txt

Handles comment form submission in a Yii controller. Validates via AJAX if requested, saves the comment through the post model, sets a flash message for pending status, and refreshes the page. Returns the comment object.

```php
protected function newComment($post)
{
	$comment=new Comment;

	if(isset($_POST['ajax']) && $_POST['ajax']==='comment-form')
	{
		echo CActiveForm::validate($comment);
		Yii::app()->end();
	}

	if(isset($_POST['Comment']))
	{
		$comment->attributes=$_POST['Comment'];
		if($post->addComment($comment))
		{
			if($comment->status==Comment::STATUS_PENDING)
				Yii::app()->user->setFlash('commentSubmitted','Thank you...');
			$this->refresh();
		}
	}
	return $comment;
}
```

--------------------------------

### Configure CHttpCacheFilter for Last-Modified header

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.page.txt

Configure the CHttpCacheFilter filter to set the Last-Modified header based on the latest post update time. The filter is applied only to the 'index' action. The lastModified value can be an integer Unix timestamp or a string parseable by strtotime().

```php
public function filters()
{
    return array(
        array(
            'CHttpCacheFilter + index',
            'lastModified'=>Yii::app()->db->createCommand("SELECT MAX(`update_time`) FROM {{post}}")->queryScalar(),
        ),
    );
}
```

--------------------------------

### Using a Filter Extension in a Controller

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.use.txt

Override the CController::filters method to use a filter extension. Plus and minus operators can be used in the first array element to apply the filter to limited actions.

```php
class TestController extends CController
{
	public function filters()
	{
		return array(
			array(
				'ext.xyz.XyzClass',
				'property1'=>'value1',
				'property2'=>'value2',
			),
			// other filters
		);
	}
}
```

--------------------------------

### Find a single row with condition and params

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Uses Post::model()->find() with a string condition and parameter array to retrieve a row by primary key. Returns null if no row matches.

```php
// find the row with postID=10
$post=Post::model()->find('postID=:postID', array(':postID'=>10));
```

--------------------------------

### Override actions() to register an action class

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.controller.txt

Shows how to override the actions() method in a controller to make it aware of an action class. The path alias 'application.controllers.post.UpdateAction' points to the action class file.

```php
class PostController extends CController
{
	public function actions()
	{
		return array(
			'edit'=>'application.controllers.post.UpdateAction',
		);
	}
}
```

--------------------------------

### Comment status constants

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.admin.txt

Defines the status constants used in the Comment model: STATUS_PENDING and STATUS_APPROVED.

```php
class Comment extends CActiveRecord
{
	...
	
	const STATUS_PENDING=1;
	const STATUS_APPROVED=2;
	
	..
}
```

--------------------------------

### Apache .htaccess mod_rewrite rules for Yii

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/quickstart.apache-nginx-config.txt

Use this .htaccess configuration to hide the bootstrap file (index.php) in URLs and prevent Apache from serving dotfiles. It rewrites all requests to index.php unless a file or directory exists.

```apache
RewriteEngine on

# prevent httpd from serving dotfiles (.htaccess, .svn, .git, etc.)
RedirectMatch 403 /\..*$
# if a directory or a file exists, use it directly
RewriteCond %{REQUEST_FILENAME} !-f
RewriteCond %{REQUEST_FILENAME} !-d
# otherwise forward it to index.php
RewriteRule . index.php
```

--------------------------------

### where() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Declares the where() method signature that specifies the WHERE part of a query. The $conditions parameter can be a string or an array, and $params binds parameters to the whole query.

```php
function where($conditions, $params=array())
```

--------------------------------

### Save AR record with validation check

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Typical workflow for saving a record: if save() returns true, data is valid and inserted/updated; otherwise, call getErrors() to retrieve error messages.

```php
if($post->save())
{
	// data is valid and is successfully inserted/updated
}
else
{
	// data is invalid. call getErrors() to retrieve error messages
}
```

--------------------------------

### Specifying a single input element in CForm::elements

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Configures a text input field for the 'username' attribute with a maxlength of 32. The 'type' option determines the input field type, and any non-property option becomes an HTML attribute.

```php
'username'=>array(
    'type'=>'text',
    'maxlength'=>32,
),
```

--------------------------------

### Use CDbExpression for SQL expression

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Assign a CDbExpression to an attribute before save() to store a raw SQL expression like NOW(). Using a string would treat it as a literal string.

```php
$post=new Post;
$post->create_time=new CDbExpression('NOW()');
// $post->create_time='NOW()'; will not work because
// 'NOW()' will be treated as a string
$post->save();
```

--------------------------------

### Yii::t() with extension category

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.i18n.txt

Use this format when translating messages for an extension class named Xyz. The category is specified as 'Xyz.categoryName' and the message file is expected at BasePath/messages/LanguageID/categoryName.php.

```php
Yii::t('Xyz.categoryName', 'message to be translated')
```

--------------------------------

### Inserting static text between input elements

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Shows how to insert a horizontal rule as static text between the 'password' and 'rememberMe' inputs in the CForm::elements array. Static text is used for irregular HTML decorations.

```php
return array(
    'elements'=>array(
		......
        'password'=>array(
            'type'=>'password',
            'maxlength'=>32,
        ),

        '<hr />',

        'rememberMe'=>array(
            'type'=>'checkbox',
        )
    ),
	......
);
```

--------------------------------

### WebTestCase base class definition

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/test.functional.txt

Defines the WebTestCase class that sets the base URL for functional tests. It extends CWebTestCase and uses the TEST_BASE_URL constant. This class is generated by the yiic webapp command and serves as the base for all functional test classes.

```php
define('TEST_BASE_URL','http://localhost/yii/demos/blog/index-test.php/');

class WebTestCase extends CWebTestCase
{
	/**
	 * Sets up before each test method runs.
	 * This mainly sets the base URL for the test application.
	 */
	protected function setUp()
	{
		parent::setUp();
		$this->setBrowserUrl(TEST_BASE_URL);
	}

	......
}
```

--------------------------------

### Message translation with Yii::t() and parameter placeholder

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.i18n.txt

Translates a message using the 'app' category, replacing the '{alias}' placeholder with the actual alias value. The source language defaults to the application's source language, and the target language to the application's language. Translation is skipped if source and target languages are the same.

```php
Yii::t('app', 'Path alias "{alias}" is redefined.',
	array('{alias}'=>$alias))
```

--------------------------------

### Namespaced module class

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/basics.namespace.txt

Defines a module class under a namespace. Sets the controllerNamespace property to point to the namespaced controllers directory.

```php
// define namespace:
namespace mynamespace\modules\testmodule;

// since class is now under namespace, global namespace
// should be referenced explicitly using "\":
class TestmoduleModule extends \CWebModule
{
	// setting non-global controllers namespace (also can be done via config)
	public $controllerNamespace = '\mynamespace\modules\testmodule\controllers';

	// usual module code
}
```

--------------------------------

### orWhere() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Declares the orWhere() method signature that appends a condition to the WHERE part with OR. Behavior is similar to where() but appends instead of replaces.

```php
function orWhere($conditions, $params=array())
```

--------------------------------

### Adding url property to Post model

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.model.txt

Adds a getUrl() method to the Post class to generate a URL for viewing the post.

```php
class Post extends CActiveRecord
{
	public function getUrl()
	{
		return Yii::app()->createUrl('post/view', array(
			'id'=>$this->id,
			'title'=>$this->title,
		));
	}
}
```

--------------------------------

### Cache both queries of relational AR query with $queryCount

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Caches both DB queries of a relational AR query by supplying the extra parameter 2 to cache(). This ensures the second query for comments is also cached.

```php
$posts = Post::model()->cache(1000, $dependency, 2)->with('comments')->findAll(array(
	'limit'=>20,
));
```

--------------------------------

### Sticky validation rule in rules()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.gii.txt

Declares a 'sticky' validation rule for baseClass and actions attributes to make input fields sticky.

```php
public function rules()
{
	return array_merge(parent::rules(), array(
		......
		array('baseClass, actions', 'sticky'),
	));
}
```

--------------------------------

### dropIndex() method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Signature for dropping an index. Parameters: $name (index name), $table (table name). The query builder quotes both properly.

```php
function dropIndex($name, $table)
```

--------------------------------

### Overriding global widget customization for CLinkPager

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.theming.txt

Shows how to override the global maxButtonCount setting for a specific CLinkPager widget by passing a new value directly in the widget call.

```php
$this->widget('CLinkPager', array(
	'pages'=>$pagination,
	'maxButtonCount'=>2,
));
```

--------------------------------

### Error Action Implementation

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.error.txt

Implement the 'error' action in SiteController to handle error display. It retrieves the error from Yii::app()->errorHandler->error and renders the 'error' view with the error data.

```php
public function actionError()
{
	if($error=Yii::app()->errorHandler->error)
		$this->render('error', $error);
}
```

--------------------------------

### Post status constants

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.model.txt

Declares constants for post statuses to be used throughout the code.

```php
class Post extends CActiveRecord
{
	const STATUS_DRAFT=1;
	const STATUS_PUBLISHED=2;
	const STATUS_ARCHIVED=3;
	......
}
```

--------------------------------

### Sticky CSS class in view

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.gii.txt

Adds a CSS class 'sticky' to the container div of the input field to make it sticky.

```php
<div class="row sticky">
	...input field here...
</div>
```

--------------------------------

### Lazy loading: retrieve post author

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Accessing the author property of a Post instance triggers a relational query on first access. If no related instance exists, the property is null for BELONGS_TO and HAS_ONE, or an empty array for HAS_MANY and MANY_MANY.

```php
// retrieve the post whose ID is 10
$post=Post::model()->findByPk(10);
// retrieve the post's author: a relational query will be performed here
$author=$post->author;
```

--------------------------------

### actionDelete() - Delete post with AJAX support

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/id/post.admin.txt

Deletes a post, only via POST request. If the request is not AJAX (i.e., $_POST['ajax'] is not set), redirects to the index action. Otherwise, no redirect is performed. Throws a 400 CHttpException for non-POST requests. Generated by yiic without changes.

```php
public function actionDelete()
{
	if(Yii::app()->request->isPostRequest)
	{
		// we only allow deletion via POST request
		$this->loadModel()->delete();

		if(!isset($_POST['ajax']))
			$this->redirect(array('index'));
	}
	else
		throw new CHttpException(400,'Invalid request. Please do not repeat this request again.');
}
```

--------------------------------

### Assign form data to AR properties

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Assigns submitted form values to AR properties before saving. Shows individual assignments for title and content, then save().

```php
$post->title=$_POST['title'];
$post->content=$_POST['content'];
$post->save();
```

--------------------------------

### Remove UTF-8 BOM header from a translation file

Source: https://github.com/yiisoft/yii/wiki/Documentation-translation-guidelines

Run this command to remove the UTF-8 BOM header from a specified translation file. Replace the path with the actual file path.

```shell
build utf8 fixbom /path/to/translation/file
```

--------------------------------

### Bind query result columns to variables

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.dao.txt

Binds the first two columns of a query result to PHP variables, then iterates over rows. Use when you need to access column values as variables inside a loop. The read() method returns false when there are no more rows.

```php
$sql="SELECT username, email FROM tbl_user";
$dataReader=$connection->createCommand($sql)->query();
// bind the 1st column (username) with the $username variable
$dataReader->bindColumn(1,$username);
// bind the 2nd column (email) with the $email variable
$dataReader->bindColumn(2,$email);
while($dataReader->read()!==false)
{
    // $username and $email contain the username and email in the current row
}
```

--------------------------------

### Override CForm::render to render all elements

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.builder.txt

Override the render() method in a custom CForm subclass to iterate over getElements() and render each element between renderBegin() and renderEnd(). This gives full control over the form output while keeping the configuration separate.

```php
class MyForm extends CForm
{
	public function render()
	{
		$output = $this->renderBegin();

		foreach($this->getElements() as $element)
			$output .= $element->render();

		$output .= $this->renderEnd();

		return $output;
	}
}
```

--------------------------------

### Declare statistical queries in Post::relations()

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Declares two statistical relations (commentCount and categoryCount) in the Post model's relations() method. commentCount counts comments (HAS_MANY), categoryCount counts categories (MANY_MANY via post_category). The relation type is STAT.

```php
class Post extends CActiveRecord
{
	public function relations()
	{
		return array(
			'commentCount'=>array(self::STAT, 'Comment', 'post_id'),
			'categoryCount'=>array(
				self::STAT, 'Category', 'post_category(post_id, category_id)'
			),
		);
	}
}
```

--------------------------------

### Cache only first query of relational AR query

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Applies query caching to a relational AR query without the $queryCount parameter. Only the first DB query (selecting posts) will be cached; the second query for comments will not be cached.

```php
$posts = Post::model()->cache(1000, $dependency)->with('comments')->findAll(array(
	'limit'=>20,
));
```

--------------------------------

### where() condition array format

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.query-builder.txt

Shows the array format for the $conditions parameter: array(operator, operand1, operand2, ...). The operator determines how operands are combined.

```php
array(operator, operand1, operand2, ...)
```

--------------------------------

### Commit changes with descriptive message

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Commits your staged changes with a message that references the issue number using #XXX so GitHub links the commit to the issue.

```bash
git commit -m "A brief description of this change which fixes #42 goes here"
```

--------------------------------

### RecentComments class definition

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/portlet.comments.txt

Defines the RecentComments portlet class in /wwwroot/blog/protected/components/RecentComments.php. It sets the title and maxComments properties, provides a getRecentComments method that calls Comment::model()->findRecentComments(), and renders the 'recentComments' view.

```php
Yii::import('zii.widgets.CPortlet');

class RecentComments extends CPortlet
{
	public $title='Recent Comments';
	public $maxComments=10;

	public function getRecentComments()
	{
		return Comment::model()->findRecentComments($this->maxComments);
	}

	protected function renderContent()
	{
		$this->render('recentComments');
	}
}
```

--------------------------------

### Using named scope in relation with 'with' option

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Shows how to apply a named scope to a related model in a relation definition. The scope 'approved' is applied to the 'comments' relation of Post, so accessing $user->posts returns posts with approved comments.

```php
// note the repetition of the relationship name, which is necessary
$approvedComments = $post->comments('comments:approved');
```

--------------------------------

### attributeLabels() method for Comment model

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.model.txt

Maps attribute names to display labels for the Comment model. If a label is not declared, Yii generates one automatically (e.g., 'Create Time' for 'create_time').

```php
public function attributeLabels()
{
	return array(
		'id' => 'Id',
		'content' => 'Comment',
		'status' => 'Status',
		'create_time' => 'Create Time',
		'author' => 'Name',
		'email' => 'Email',
		'url' => 'Website',
		'post_id' => 'Post',
	);
}
```

--------------------------------

### Self-referencing through relation in User model

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Defines a self-referencing relation where a User mentors other Users through the Mentorship model. The 'students' relation uses 'through' to link via 'mentorships'.

```php
class User extends CActiveRecord
{
	...
	public function relations()
	{
		return array(
			'mentorships'=>array(
				self::HAS_MANY,'Mentorship','teacher_id','joinType'=>'INNER JOIN'
			),
			'students'=>array(
				self::HAS_MANY,'User',array('student_id'=>'id'),
					'through'=>'mentorships','joinType'=>'INNER JOIN'
			),
		);
	}
}
```

--------------------------------

### Register third-party autoloader with Yii::registerAutoloader

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.integration.txt

Use Yii::registerAutoloader to register a third-party autoloader function or method. Yii will prepend it before its own autoloader automatically.

```php
require_once('/path/to/framework/yii.php'); // register Yii autoloader
...
Yii::registerAutoloader(array('SomeLibrary','autoload')); // register 3rd-party autoloader
...
```

--------------------------------

### Dynamically set 'together'=>false during eager loading

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Use this snippet to dynamically set the 'together' option to false when performing eager loading, overriding the default behavior. This forces separate SQL statements for the 'comments' relation.

```php
$posts = Post::model()->with(
			array('comments'=>array(
				'together'=>false
			))
		)->findAll();
```

--------------------------------

### Override primaryKey() for custom primary key

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Override primaryKey() in an AR class to specify the primary key column(s) when the table has no primary key. Return a string for single key or an array for composite key.

```php
public function primaryKey()
{
	return 'id';
	// For composite primary key, return an array like the following
	// return array('pk1', 'pk2');
}
```

--------------------------------

### Declaring named scopes in Post model

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Declares two named scopes, 'published' and 'recently', in the Post model's scopes() method. Each scope is an array that initializes a CDbCriteria instance.

```php
class Post extends CActiveRecord
{
	......
	public function scopes()
	{
		return array(
			'published'=>array(
				'condition'=>'status=1',
			),
			'recently'=>array(
				'order'=>'create_time DESC',
				'limit'=>5,
			),
		);
	}
}
```

--------------------------------

### Declare an attribute unsafe with the 'unsafe' rule

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Use the 'unsafe' rule to explicitly mark an attribute as unsafe, which is rarely needed and is an exception to the safe attribute definition.

```php
array('permission', 'unsafe')
```

--------------------------------

### Declare a safe attribute with the 'safe' rule

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Use the 'safe' rule to declare an attribute safe when no specific validation rule exists, allowing arbitrary user input.

```php
array('content', 'safe')
```

--------------------------------

### CHtml::textField with submit option

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.view.txt

This snippet shows how to use CHtml::textField with the 'submit' option to create a text input that automatically submits the form when its value changes, avoiding manual JavaScript.

```php
CHtml::textField($name,$value,array('submit'=>''));
```

--------------------------------

### actionDelete() method in PostController

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.admin.txt

The actionDelete() method handles post deletion via POST request. It checks if the request is POST, deletes the model, and redirects unless the request is AJAX. If not POST, it throws a CHttpException with status 400. This code is generated by Gii without change.

```php
public function actionDelete()
{
	if(Yii::app()->request->isPostRequest)
	{
		// we only allow deletion via POST request
		$this->loadModel()->delete();

		if(!isset($_GET['ajax']))
			$this->redirect(array('index'));
	}
	else
		throw new CHttpException(400,'Invalid request. Please do not repeat this request again.');
}
```

--------------------------------

### Enable AJAX validation in _form.php

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.create.txt

Set enableAjaxValidation to true when creating the CActiveForm widget in the view file to enable AJAX validation for the form.

```php
<div class="form">

<?php $form=$this->beginWidget('CActiveForm', array(
	'id'=>'comment-form',
	'enableAjaxValidation'=>true,
)); ?>
......
<?php $this->endWidget(); ?>

</div><!-- form -->
```

--------------------------------

### Relational AR query with HAS_MANY relationship

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/caching.data.txt

Performs a relational AR query with a HAS_MANY relationship between Post and Comment, which executes two DB queries: one for posts limited to 20 and one for their comments.

```php
$posts = Post::model()->with('comments')->findAll(array(
	'limit'=>20,
));
```

--------------------------------

### Validator method signature

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/form.model.txt

Shows the required signature for a validator method in a model class. The method receives the attribute name and validation rule options.

```php
/**
 * @param string $attribute the name of the attribute to be validated
 * @param array $params options specified in the validation rule
 */
public function ValidatorName($attribute,$params) { ... }
```

--------------------------------

### Using a Validator Extension in a Model

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/extension.use.txt

Override the CModel::rules method in a model class (extending CActiveRecord or CFormModel) to use a validator extension.

```php
class MyModel extends CActiveRecord // or CFormModel
{
	public function rules()
	{
		return array(
			array(
				'attr1, attr2',
				'ext.xyz.XyzClass',
				'property1'=>'value1',
				'property2'=>'value2',
			),
			// other validation rules
		);
	}
}
```

--------------------------------

### Define normalizeTags validator in Post

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.model.txt

Method-based validator that normalizes user-entered tags by splitting, deduplicating, and rejoining them with commas.

```php
public function normalizeTags($attribute,$params)
{
	$this->tags=Tag::array2string(array_unique(Tag::string2array($this->tags)));
}
```

--------------------------------

### Declare 'together'=>false in relation to use separate SQL statements

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Use this snippet in the model's relations() method to force separate SQL statements for eager loading, even when LIMIT is not used. This avoids redundant data when the related table has many rows per primary record.

```php
public function relations()
{
	return array(
		'comments' => array(self::HAS_MANY, 'Comment', 'post_id',
						'together'=>false),
	);
}
```

--------------------------------

### rules() method for Comment model validation

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.model.txt

Defines validation rules for the Comment model: required fields (content, author, email), length constraints (max 128 for author, email, url), email format validation, and URL format validation.

```php
public function rules()
{
	return array(
		array('content, author, email', 'required'),
		array('author, email, url', 'length', 'max'=>128),
		array('email','email'),
		array('url','url'),
	);
}
```

--------------------------------

### Define a default scope in CActiveRecord

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/id/database.ar.txt

Defines a default scope for the Content model that filters queries by the current application language. The second snippet shows how the scope is automatically applied when calling findAll(). Note that default scopes only affect SELECT queries and not INSERT, UPDATE, or DELETE.

```php
class Content extends CActiveRecord
{
	public function defaultScope()
	{
		return array(
			'condition'=>"language='".Yii::app()->language."'",
		);
	}
}
```

```php
$contents=Content::model()->findAll();
```

--------------------------------

### Configure default roles in authManager

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/topics.auth.txt

Declares 'authenticated' and 'admin' as default roles in the authManager component configuration. These roles are implicitly assigned to every user and checked first by checkAccess.

```php
return array(
	'components'=>array(
		'authManager'=>array(
			'class'=>'CDbAuthManager',
			'defaultRoles'=>array('authenticated', 'admin'),
		),
	),
);
```

--------------------------------

### Configure default roles in authManager

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/pt_br/topics.auth.txt

Declare default roles in the 'defaultRoles' property of the authManager component. This configuration sets 'authenticated' and 'guest' as default roles for all users.

```php
return array(
	'components'=>array(
		'authManager'=>array(
			'class'=>'CDbAuthManager',
			'defaultRoles'=>array('authenticated', 'guest'),
		),
	),
);
```

--------------------------------

### Setting HTML.DefinitionID and adding a custom attribute

Source: https://github.com/yiisoft/yii/blob/master/framework/vendors/htmlpurifier/standalone/HTMLPurifier/ConfigSchema/schema/HTML.DefinitionID.txt

Use this snippet when you need to modify the HTML definition using the advanced API. It sets the DefinitionID to '1' and adds a 'tabindex' attribute to the 'a' element. This directive is required to use advanced API features and prevents cache conflicts with default configurations.

```php
$config = HTMLPurifier_Config::createDefault();
$config->set('HTML', 'DefinitionID', '1');
$def = $config->getHTMLDefinition();
$def->addAttribute('a', 'tabindex', 'Number');
```

--------------------------------

### Pull latest code from upstream master

Source: https://github.com/yiisoft/yii/wiki/Git-workflow-for-Yii-contributors

Pulls the latest code from the upstream master branch into your current branch. Resolve any merge conflicts and commit again if necessary.

```bash
git pull upstream master
```

--------------------------------

### afterDelete() - Clean up comments and tags

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/id/post.admin.txt

Overrides afterDelete() in the Post model to clean up related data: deletes all comments with the same post_id and updates the tag frequency table for the deleted post's tags.

```php
protected function afterDelete()
{
	parent::afterDelete();
	Comment::model()->deleteAll('post_id='.$this->id);
	Tag::model()->updateFrequency($this->tags, '');
}
```

--------------------------------

### Override tableName() for table prefix

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Override the tableName() method in an AR class to return the table name without prefix, enclosed in double curly brackets, to use the table prefix feature.

```php
public function tableName()
{
    return '{{post}}';
}
```

--------------------------------

### Check access in controller action

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/ro/topics.auth.txt

Checks if the current user can delete a post using the RBAC hierarchy and assignment. The checkAccess method returns true if the user has the required permission.

```php
if(Yii::app()->user->checkAccess('deletePost'))
{
	// delete the post
}
```

--------------------------------

### Parameterized named scope recently

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Defines a parameterized named scope 'recently' that accepts a limit parameter. The method merges the criteria with the given limit and returns $this for chaining.

```php
public function recently($limit=5)
{
	$this->getDbCriteria()->mergeWith(array(
		'order'=>'create_time DESC',
		'limit'=>$limit,
	));
	return $this;
}
```

--------------------------------

### HAS_MANY through with multiple relations

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Defines a Group model with relations 'roles', 'users', and 'comments' using 'through' to traverse intermediate relations. This allows querying users and comments associated with a group.

```php
class Group extends CActiveRecord
{
	...
	public function relations()
	{
		return array(
			'roles'=>array(self::HAS_MANY,'Role','group_id'),
			'users'=>array(
				self::HAS_MANY,'User',array('user_id'=>'id'),'through'=>'roles'
			),
			'comments'=>array(
				self::HAS_MANY,'Comment',array('id'=>'user_id'),'through'=>'users'
			),
		);
	}
}
```

--------------------------------

### Override beforeSave() in Post model

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/post.create.txt

Overrides beforeSave() in the Post model to automatically set create_time, update_time, and author_id for new records, and update_time for existing records.

```php
protected function beforeSave()
{
	if(parent::beforeSave())
	{
		if($this->isNewRecord)
		{
			$this->create_time=$this->update_time=time();
			$this->author_id=Yii::app()->user->id;
		}
		else
			$this->update_time=time();
		return true;
	}
	else
		return false;
}
```

--------------------------------

### Default scope for Content model

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.ar.txt

Overrides defaultScope to filter queries by the current language. This default scope applies to all SELECT queries for the model.

```php
class Content extends CActiveRecord
{
	public function defaultScope()
	{
		return array(
			'condition'=>"language='".Yii::app()->language."'",
		);
	}
}
```

--------------------------------

### Add addComment method to Post model

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/comment.create.txt

Add the addComment() method to the Post model class. It sets the comment status based on the commentNeedApproval parameter and saves the comment with the post_id set.

```php
public function addComment($comment)
{
	if(Yii::app()->params['commentNeedApproval'])
		$comment->status=Comment::STATUS_PENDING;
	else
		$comment->status=Comment::STATUS_APPROVED;
	$comment->post_id=$this->id;
	return $comment->save();
}
```

--------------------------------

### Comment::findRecentComments method

Source: https://github.com/yiisoft/yii/blob/master/docs/blog/portlet.comments.txt

Adds a findRecentComments method to the Comment model that retrieves approved comments with their related posts, ordered by creation time descending, limited by the given limit.

```php
class Comment extends CActiveRecord
{
	......
	public function findRecentComments($limit=10)
	{
		return $this->with('post')->findAll(array(
			'condition'=>'t.status='.self::STATUS_APPROVED,
			'order'=>'t.create_time DESC',
			'limit'=>$limit,
		));
	}
}
```

--------------------------------

### Declaring relation with 'together'=>false

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/zh_cn/database.arr.txt

Declares a HAS_MANY relation with the 'together' option set to false, causing the relation to be fetched in a separate SQL statement instead of joining with the primary query.

```php
public function relations()
{
	return array(
		'comments' => array(self::HAS_MANY, 'Comment', 'post_id', 'together'=>false),
	);
}
```

--------------------------------

### Disambiguate nested relation aliases in order with 'group.name, author.name, t.title'

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Use this snippet when ordering by columns from nested relations. The alias for a nested relation is the relation name only (e.g., 'group' for 'author.group'), not prefixed with the parent relation.

```php
$posts=Post::model()->with('author', 'author.group')->findAll(array(
	'order'=>'group.name, author.name, t.title'
));
```

--------------------------------

### Avoid alias collision by specifying 'alias' property in relation

Source: https://github.com/yiisoft/yii/blob/master/docs/guide/database.arr.txt

Use this snippet to avoid table alias collisions when eager loading multiple relations that share the same table. The 'alias' property is set for the nested relation 'post.author' to 'p_author'.

```php
$comments=Comment::model()->with(array(
	'author',
	'post',
	'post.author'=>array('alias'=>'p_author')))->findAll(array(
	'order'=>'author.name, p_author.name, post.title'
));
```