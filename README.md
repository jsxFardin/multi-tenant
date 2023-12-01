## Multi Tenant 

Multi-tenancy is the ability to provide your service to multiple users (tenants) from a single hosted instance of the application. This is contrasted with deploying the application separately for each user.

#### package : [tenancy](https://tenancyforlaravel.com/docs/v3/quickstart)

### Instalation Process


1. Install composer packages

```
composer install
```

2. Create and setup .env file

```
make a copy of .env.example
$ copy .env.example .env
$ php artisan key:generate
put database credentials in .env file
```

3. Migrate and insert records

```
$ php artisan migrate
```

4. Serving application
```
$ php artisan serve
$ npm run hot
```

### Tenants Creating Process

```
    php artisan tinker
    >>> $tenant1 = App\Models\Tenant::create(['id' => 'foo']);
    >>> $tenant1->domains()->create(['domain' => 'foo.localhost']);
    >>>
    >>> $tenant2 = App\Models\Tenant::create(['id' => 'bar']);
    >>> $tenant2->domains()->create(['domain' => 'bar.localhost']);
```