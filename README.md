Hijri Date Time
==================
Hijri Date Time library is a convenient and complete solution for users who want to use Hijri date in their projects and convert Gregorian calendar to Hijri (Islamic) calendar. This library is 100% compatible with "Umm al-Qura" formal calendar in Saudi Arabia and the Muslim world.

It support Arabic, English, France, and Indonesia languages.

The original source [here](https://www.yiiframework.com/extension/hijridatetime)

Extension for Yii2 Framework available [here](https://github.com/biladina/yii2-hijridatetime)

Installation
------------

The preferred way to install this library is through [composer](http://getcomposer.org/download/).

Just run

```
composer require biladina/hijridatetime
```

Usage
-----

Once the library is installed, simply use it in your code by  :

```php
<?php

use biladina\hijridatetime\HijriDateTime;

// Choose Your Format Like 'l ، j F ، Y'
// Y => Hijri Year [1442]
// F => Hijri Month Arabic Name [رمضان]
// j => Hijri Day Number [27]
// l => Arabic Day Name [الجمعة]
// m => Hijri Month Number [09]
// a => 'ص'
// A => 'صباحًا'
// H => Hour
// i => Minutes
// s => Seconds

// set language is available, use 'ar' for Arabic, 'en' for English, 'fr' for France, and 'id' for Indonesia (which is the default language).

$hijri = new HijriDateTime();

$hijri->date("H:i A l, d F Y", time()) // formatting is like date function
// will return in Indonesia language if not set languange
// will return 16:16 PM Jum'at, 01 Ramadhan 1441
//---------------- Or ---------------------
$hijri->date("H:i A l, d F Y", time(), "fr")
// will return in France language
// will return 16:16 PM vendredi, 01 Ramadan 1441

$hijri->GeToHijr(20, 02, 1976)
// will return Array Hijri date[int month, int day, int year, int ln, int ml]

$hijri->strToHijri("24 April 2020")
// will return a Date in Hijri d-m-Y if not formated
//-------- Or -----------
$hijri->strToHijri("24 April 2020 15:00:00", "l, d F Y H:i A")
// will return in Indonesia language if not set languange
// will return a Date in Hijri as formated like Jum'at, 01 Ramadhan 1441 15:00 PM
//-------- Or -----------
$hijri->strToHijri("24 April 2020 15:00:00", "l, d F Y H:i A", "fr")
// will return in France language
// will return a Date in Hijri as formated like vendredi, 01 Ramadan 1441 15:00 PM

```


If you want to add more language :
* open 'language' directory
* copy one of directory in it (I prefer 'en' directory) and rename with initial of your country, like 'ms' for Malaysia, 'de' for Deutch (Germany)
* open 'hijri.php' file in the renamed directory
* translate to your languange
* create PR, I will combine to main project
