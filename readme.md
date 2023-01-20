<p align="center"><img src="https://static.bnewbold.net/tmp/under_construction_bar.gif" /></p>


###################
What is CodeIgniter
###################

CodeIgniter is an Application Development Framework - a toolkit - for people
who build web sites using PHP. Its goal is to enable you to develop projects
much faster than you could if you were writing code from scratch, by providing
a rich set of libraries for commonly needed tasks, as well as a simple
interface and logical structure to access these libraries. CodeIgniter lets
you creatively focus on your project by minimizing the amount of code needed
for a given task.

---

Release Information

---

This repo contains in-development code for future releases. To download the
latest stable release please visit the `CodeIgniter Downloads
<https://codeigniter.com/download>`\_ page.

---

Changelog and New Features

---

You can find a list of all changes for each release in the `user
guide change log <https://github.com/bcit-ci/CodeIgniter/blob/develop/user_guide_src/source/changelog.rst>`\_.

---

Server Requirements

---

PHP version 5.6 or newer is recommended.

It should work on 5.3.7 as well, but we strongly advise you NOT to run
such old versions of PHP, because of potential security and performance
issues, as well as missing features.

---

Installation

---

Please see the `installation section <https://codeigniter.com/userguide3/installation/index.html>`\_
of the CodeIgniter User Guide.

---

License

---

Please see the `license
agreement <https://github.com/bcit-ci/CodeIgniter/blob/develop/user_guide_src/source/license.rst>`\_.

---

Resources

---

- `User Guide <https://codeigniter.com/docs>`\_
- `Contributing Guide <https://github.com/bcit-ci/CodeIgniter/blob/develop/contributing.md>`\_
- `Language File Translations <https://github.com/bcit-ci/codeigniter3-translations>`\_
- `Community Forums <http://forum.codeigniter.com/>`\_
- `Community Wiki <https://github.com/bcit-ci/CodeIgniter/wiki>`\_
- `Community Slack Channel <https://codeigniterchat.slack.com>`\_

Report security issues to our `Security Panel <mailto:security@codeigniter.com>`_
or via our `page on HackerOne <https://hackerone.com/codeigniter>`_, thank you.

---

Acknowledgement

---

The CodeIgniter team would like to thank EllisLab, all the
contributors to the CodeIgniter project and you, the CodeIgniter user.

---

Turn On .ENV

---

Masuk ke directori application melalui command line dan lakukan perintah berikut:

- file `composer.json` Bagi pengguna Mac Os

```
{
	"description": "The CodeIgniter framework",
	"name": "codeigniter/framework",
	"type": "project",
	"homepage": "https://codeigniter.com",
	"license": "MIT",
	"support": {
		"forum": "http://forum.codeigniter.com/",
		"wiki": "https://github.com/bcit-ci/CodeIgniter/wiki",
		"slack": "https://codeigniterchat.slack.com",
		"source": "https://github.com/bcit-ci/CodeIgniter"
	},
	"require": {
		"php": ">=5.3.7",
		"vlucas/phpdotenv": "^3.6"
	},
	"suggest": {
		"paragonie/random_compat": "Provides better randomness in PHP 5.x"
	},
	"scripts": {
		"test:coverage": [
			"@putenv XDEBUG_MODE=coverage",
			"phpunit --color=always --coverage-text --configuration tests/travis/sqlite.phpunit.xml"
		],
		"post-install-cmd": [
			"sed s/name{0}/name[0]/ vendor/mikey179/vfsstream/src/main/php/org/bovigo/vfs/vfsStream.php"
		],
		"post-update-cmd": [
			"sed s/name{0}/name[0]/ vendor/mikey179/vfsstream/src/main/php/org/bovigo/vfs/vfsStream.php"
		]
	},
	"require-dev": {
		"mikey179/vfsstream": "1.6.*",
		"phpunit/phpunit": "4.* || 5.* || 9.*"
	}
}

```

Selanjutnya :

```
  composer require vlucas/phpdotenv ^3.6
```

```
  composer install
```

Selanjutnya, buatlah file .env di dalam direktori application.

Penggunaan .env pada CodeIgniter
Pada bagian ini adalah langkah terakhir dalam integrasi .env pada CodeIgniter, yaitu menggunakan variabel ENVIRONMENT pada konfigurasi bawaan CI. Sebagai contoh saya akan mengubah konfigurasi database menggunakan .env.

```http
# Database Configuration
DB_HOSTNAME="localhost"
DB_USERNAME="...."
DB_PASSWORD="...."
DB_DATABASE="...."
DB_DRIVER="...."
```

\*NB: penggunaan environment variabel bisa menggunakan getenv(), $\_ENV[], $\_SERVER[]
