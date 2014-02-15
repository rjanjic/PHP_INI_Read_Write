PHP_INI_Read_Write
==================

This class can read and write configuration values in INI files.

It can parse a given INI file and extract the contained configuration values into class array variables.

The class can also do the opposite, i.e., write the configuration values in the array variable back to a INI file.


Examples:


`````php
// Parse config.ini
$ini = new INI('config.ini');

// Content of: config.ini
print_r($ini->data);

// Udate settings
$ini->data['first_section']['animal'] = 'COW';

// Save settings to file
$ini->write();

// Update settings
$ini->data['first_section']['animal'] = 'HORSE';

// Add new setting to section third_section
$ini->data['third_section']['phpversion'][] = 5.4;

// Add new section third_section and new item something
$ini->data['fourth_section']['something'] = 'some data';

// Save settings to new file
$ini->write('config-2.ini');

// INI obj is now using ini 2 file
// Content of: config-2.ini
print_r($ini->data);

// Parse config.ini
$ini->read('config.ini');

// Remove item from second_section
unset($ini->data['second_section']['URL']);

// Remove third_section from second ini file and save to third file
unset($ini->data['third_section']);

// Save settings to new file
$ini->write('config-3.ini');

// INI obj is now using ini 3 file
// Content of: config-3.ini
print_r($ini->data);
`````
