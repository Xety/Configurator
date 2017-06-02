# Xety\Configurator\Configurator  

Configurator class.

## Implements:
Xety\Configurator\Interfaces\ConfiguratorInterface, Xety\Configurator\Interfaces\ConfiguratorOptionInterface



## Methods

| Name | Description |
|------|-------------|
|[clear](#configuratorclear)|Clear all options stored.|
|[consumeOption](#configuratorconsumeoption)|Read then flush an option.|
|[flush](#configuratorflush)|Flush a list of options from the config array.|
|[flushOption](#configuratorflushoption)|Flush an option.|
|[get](#configuratorget)|Get all the options.|
|[getOption](#configuratorgetoption)|Get an option value.|
|[hasOption](#configuratorhasoption)|Check if the option exist.|
|[merge](#configuratormerge)|Merge the values to the options array, or the current options in
the values if the param `invert` is true.|
|[pushOption](#configuratorpushoption)|Push the listed args to the named option.|
|[set](#configuratorset)|Set the values to the options array. Will replace all the configuration options.|
|[setOption](#configuratorsetoption)|Set a value to the given option.|
|[transientOption](#configuratortransientoption)|Adds a transient configuration key/value.|




### Configurator::clear  

**Description**

```php
public clear (void)
```

Clear all options stored. 

 

**Parameters**

`This function has no parameters.`

**Return Values**

`\Xety\Configurator\Configurator`





### Configurator::consumeOption  

**Description**

```php
public consumeOption (string $name)
```

Read then flush an option. 

Exemple:  
  
Config:  
```  
$config = [  
    'key1' => 'value1'  
]  
```  
Usage:  
```  
$result = $this->consumeOption('key1');  
```  
Result:  
```  
echo $result; // value1  
var_dump($config); // []  
``` 

**Parameters**

* `(string) $name`
: The name of the option to read then flush.  

**Return Values**

`mixed`





### Configurator::flush  

**Description**

```php
public flush (string $filter)
```

Flush a list of options from the config array. 

Usage:  
```  
$this->flush('key1', 'key2');  
``` 

**Parameters**

* `(string) $filter`
: All the options to remove from the config.  

**Return Values**

`\Xety\Configurator\Configurator`





### Configurator::flushOption  

**Description**

```php
public flushOption (string $name)
```

Flush an option. 

 

**Parameters**

* `(string) $name`
: The name of the option to flush.  

**Return Values**

`\Xety\Configurator\Configurator`





### Configurator::get  

**Description**

```php
public get (void)
```

Get all the options. 

 

**Parameters**

`This function has no parameters.`

**Return Values**

`array`





### Configurator::getOption  

**Description**

```php
public getOption (string $name)
```

Get an option value. 

Usage:  
```  
$this->getOption('key');  
``` 

**Parameters**

* `(string) $name`
: The option name to to get.  

**Return Values**

`mixed`





### Configurator::hasOption  

**Description**

```php
public hasOption (string $name)
```

Check if the option exist. 

 

**Parameters**

* `(string) $name`
: The option name to check.  

**Return Values**

`bool`





### Configurator::merge  

**Description**

```php
public merge (array $values, bool $invert)
```

Merge the values to the options array, or the current options in
the values if the param `invert` is true. 

 

**Parameters**

* `(array) $values`
: The values to merge in the config.  
* `(bool) $invert`
: Invert the merge by merging the actual config into the values.  

**Return Values**

`\Xety\Configurator\Configurator`





### Configurator::pushOption  

**Description**

```php
public pushOption (string $name, array $args)
```

Push the listed args to the named option. 

Usage:  
```  
$this->pushOption('key', ['key1' => 'value1'], ['key2' => ['value2' => 'value3']]);  
```  
Result:  
```  
'key' => [  
    'key1' => 'value1',  
    'key2' => [  
        value2 => value3  
    ]  
]  
``` 

**Parameters**

* `(string) $name`
: The name of the option.  
* `(array) $args`
: A list of values to push into the option key.  

**Return Values**

`\Xety\Configurator\Configurator`





### Configurator::set  

**Description**

```php
public set (array $values)
```

Set the values to the options array. Will replace all the configuration options. 

 

**Parameters**

* `(array) $values`
: The values to push into the config.  

**Return Values**

`\Xety\Configurator\Configurator`





### Configurator::setOption  

**Description**

```php
public setOption (string $name, mixed $value)
```

Set a value to the given option. 

Usage:  
```  
$this->setOption('key', 'value');  
$this->setOption('key', ['key2' => ['value2']]);  
``` 

**Parameters**

* `(string) $name`
: The option name.  
* `(mixed) $value`
: The option value.  

**Return Values**

`\Xety\Configurator\Configurator`





### Configurator::transientOption  

**Description**

```php
public transientOption (string $name, mixed $value)
```

Adds a transient configuration key/value. 

Usage:  
```  
// Will update the value of the key `key` if it exist,  
// or it will create it with the value `value`.  
 $this->transientOption('key', 'value');  
``` 

**Parameters**

* `(string) $name`
: The name of the option.  
* `(mixed) $value`
: The value to set.  

**Return Values**

`\Xety\Configurator\Configurator`




