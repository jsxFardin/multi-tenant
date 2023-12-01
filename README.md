## Multi Tenant 

Multi-tenancy is the ability to provide your service to multiple users (tenants) from a single hosted instance of the application. This is contrasted with deploying the application separately for each user.

#### package : [tenancy](https://tenancyforlaravel.com/docs/v3/quickstart)

#### Custom DNS : [Wildcard DNS records ](https://developers.cloudflare.com/dns/manage-dns-records/reference/wildcard-dns-records/)

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

### Trying it out

Now we visit foo.localhost in our browser, replace localhost with one of the values of central_domains in the file config/tenancy.php as modified previously. We should see a dump of the users table where we see some user. If we visit bar.localhost, we should see a different user.

