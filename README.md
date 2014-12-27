# Robo Phinx Extension
[![Build Status](https://travis-ci.org/robertboloc/robo-phinx.svg?branch=master)](https://travis-ci.org/robertboloc/robo-phinx)

Integrates Phinx tool with the Robo task runner.


## Table of contents
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)

## Installation
Add `"robertboloc/robo-phinx": "1.0.*"` to your composer.json.
```json
    {
        "require": {
            "robertboloc/robo-phinx": "1.0.*"
        }
    }
```

Execute `composer update`

## Usage

Use the `Phinx` trait in your `RoboFile.php`
```php
<?php

class Robofile extends \Robo\Tasks
{
    use \Rb\Robo\Task\Phinx;
    
    //...
}
```

Build your tasks using the `Phinx` commands:

### Init
```php
<?php

$this->taskPhinx()
     ->init($path = '.')
     ->run();
```
### Create
```php
<?php

$this->taskPhinx()
     ->create($migration)
     ->run();
```
### Migrate
```php
<?php

$this->taskPhinx()
     ->migrate($target = null)
     ->run();
```
### Rollback
```php
<?php

$this->taskPhinx()
     ->rollback($target = null)
     ->run();
```
### Status
```php
<?php

$this->taskPhinx()
     ->status()
     ->run();
```

## Configuration

You can apply configuration parameters to all the commands using the configuration modifiers:

### Config
```php
<?php

$this->taskPhinx()
     ->config($file = 'phinx.yml')
     ->status()
     ->run();
```

### Parser 
```php
<?php

$this->taskPhinx()
     ->parser($format = 'yaml')
     ->status()
     ->run();
```

### Environment
```php
<?php

$this->taskPhinx()
     ->environment($environment = 'development')
     ->status()
     ->run();
```

Note that all the commands have their default arguments in parenthesis. If no argument is specified the command takes no argument.
