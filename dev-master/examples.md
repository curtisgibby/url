---
layout: default
title: Examples
---

# Simple example

Let's say you have a document that can be downloaded in different format (CSV, XML, JSON) and you quickly want to generate each format URL. This example illustrates how easy it is to generate theses different URLs from an original URL whithout losing its information.

~~~php
use League\Url\Services\Builder as UrlBuilder;

$urlBuilder  = new UrlBuilder("http://download.example.com/path/to/my/file.csv");
$csv_output  = $urlBuilder->getUrl();
$xml_output  = $urlBuilder->withExtension('xml')->getUrl();
$json_output = $urlBuilder->withExtension('json')->getUrl();

echo $csv_output;  //display "http://download.example.com/path/to/my/file.csv"
echo $xml_output;  //display "http://download.example.com/path/to/my/file.xml"
echo $json_output; //display "http://download.example.com/path/to/my/file.json"
~~~