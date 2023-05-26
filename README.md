## Running it locally

Please note: The example env file assumes that host.docker.internal resolves to 127.0.0.1 from your terminal. If not, change the env file accordingly or add host.docker.internal to your /etc/hosts file.

-   composer i
-   cp .env.example .env
-   php artisan key:generate
-   ./vendor/bin/sail up -d
-   php artisan scout:delete-all-indexes
-   php artisan migrate:fresh --seed

Visit http://localhost:8080/nova

Username: test@example.com
Password: 12345

## Reproduction of pagination bug in Laravel Nova with Laravel Scout

1. Go to the users index
2. Put 'example' in the user search field
3. Set the 'Create at - To' filter to yesterday

At this point, no results should be in the list.

4. Change the page size from 25 to 50

Now the 'Test user' should appear in the list.
