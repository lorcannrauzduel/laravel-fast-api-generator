# Laravel Fast API Generator

  - Laravel v.5.7
  - PHP 7.4
  - Node v10.19
  - Composer v1.6

### Installation

Install the dependencies and devDependencies and start the server.

```sh
$ cd  laravel-fast-api-generator
$ composer install
$ npm install -d
$ php artisan serve
```

### Documentation

Run ./api on project root folder

```sh
$ ./api
$ 'Table Name?'
$ 'articles'
$ 'Created Migration: 2020_03_31_232937_create_articles_table'
$ 'Define your table and tap ENTER'

Schema::create('articles', function (Blueprint $table) {
    $table->bigIncrements('id');
    $table->string('title');
    $table->string('description');
    $table->bigInteger('user_id')->unsigned();
    $table->foreign('user_id')->references('id')->on('users');
    $table->timestamps();
});

If you are finished you tap ENTER

$ 'Migrating: 2020_03_31_232937_create_articles_table'
$ 'Migrated:  2020_03_31_232937_create_articles_table'
$ 'Model Name?'
$ 'Article'
$ 'Model Article generated'
$ 'Created API controller.'
$ 'Created API route.'

localhost:8000/api/articles
```

Or you can do it manually


1) Create a migration:
```sh
$ php artisan make:migration create_modeles_table --create=modeles
$ 'Created Migration: 2020_03_31_232937_create_modeles_table'
```

2) Define table :
```sh
Schema::create('modeles', function (Blueprint $table) {
    $table->bigIncrements('id');
    $table->string('name');
    $table->string('description');
    $table->bigInteger('marque_id')->unsigned();
    $table->foreign('marque_id')->references('id')->on('marques');
    $table->string('img_url');
    $table->timestamps();
});
```

3) Run migration
```sh
$ php artisan migrate
$ 'Migrating: 2020_03_31_232937_create_modeles_table'
$ 'Migrated:  2020_03_31_232937_create_modeles_table'
```

3) Create Model from the table
```sh
$ php artisan krlove:generate:model Modele --table-name=modeles
$ 'Model Modele generated'
```

4) Creating API controller and route
```sh
$ php artisan make:api --model=Modele
$ 'Created API controller.'
$ 'Created API route.'


localhost:8000/api/modeles
```


### Table Builder

| Command | Description |
| ------ | ------ |
| $table->bigIncrements('id'); | 	Incrementing ID using a "big integer" equivalent |
| $table->bigInteger('votes'); | 	BIGINT equivalent to the table |
| $table->binary('data'); | 	BLOB equivalent to the table |
| $table->boolean('confirmed'); | 	BOOLEAN equivalent to the table |
| $table->char('name', 4); | 	CHAR equivalent with a length |
| $table->date('created_at'); | 	DATE equivalent to the table |
| $table->dateTime('created_at'); | 	DATETIME equivalent to the table |
| $table->decimal('amount', 5, 2); | 	DECIMAL equivalent with a precision and scale |
| $table->double('column', 15, 8); | 	DOUBLE equivalent with precision, 15 digits in total and 8 after the decimal point |
| $table->enum('choices', ['foo', 'bar']); | 	ENUM equivalent to the table |
| $table->float('amount'); | 	FLOAT equivalent to the table |
| $table->increments('id'); | 	Incrementing ID to the table (primary key) |
| $table->integer('votes'); | 	INTEGER equivalent to the table |
| $table->json('options'); | 	JSON equivalent to the table |
| $table->jsonb('options'); | 	JSONB equivalent to the table |
| $table->longText('description'); | 	LONGTEXT equivalent to the table |
| $table->mediumInteger('numbers'); | 	MEDIUMINT equivalent to the table |
| $table->mediumText('description'); | 	MEDIUMTEXT equivalent to the table |
| $table->morphs('taggable'); | 	Adds INTEGER taggable_id and STRING taggable_type |
| $table->nullableTimestamps(); | 	Same as timestamps(), except allows NULLs |
| $table->smallInteger('votes'); | 	SMALLINT equivalent to the table |
| $table->tinyInteger('numbers'); | 	TINYINT equivalent to the table |
| $table->softDeletes(); | 	Adds deleted_at column for soft deletes |
| $table->string('email'); | 	VARCHAR equivalent column |
| $table->string('name', 100); | 	VARCHAR equivalent with a length |
| $table->text('description'); | 	TEXT equivalent to the table |
| $table->time('sunrise'); | 	TIME equivalent to the table |
| $table->timestamp('added_on'); | 	TIMESTAMP equivalent to the table |
| $table->timestamps(); | 	Adds created_at and updated_at columns |
| $table->rememberToken(); | 	Adds remember_token as VARCHAR(100) NULL |
| ->nullable() |	Designate that the column allows NULL values |
| ->default($value) |	Declare a default value for a column |
| ->unsigned() |	Set INTEGER to UNSIGNED |

### Laravel Package

 - APIGenerator (https://github.com/LaravelDaily/api-generator)
 - Eloquent Model Generator (https://github.com/krlove/eloquent-model-generator)





