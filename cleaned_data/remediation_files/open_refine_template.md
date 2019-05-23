# Open Refine Template for Volunteer Yearbooks

## Template

#### Prefix

```
<?xml version="1.0" encoding="UTF-8"?>
<modsCollection xmlns="http://www.loc.gov/mods/v3" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xlink="http://www.w3.org/1999/xlink" xsi:schemaLocation="http://www.loc.gov/mods/v3 http://www.loc.gov/standards/mods/v3/mods-3-5.xsd">
```
####Body

```
<mods>
<identifier type="filename">{{cells["identifier"].value}}</identifier>
<identifier type="pid">{{cells['PID'].value}}</identifier>
<titleInfo><title>{{cells["title"].value}}</title></titleInfo>
<titleInfo type="alternative"><title>{{cells['volume'].value}}</title></titleInfo> 
{{if(isBlank(cells["abstract"].value),'', '<abstract>' + cells['abstract'].value + '</abstract>')}}
<physicalDescription><form authority="aat" valueURI="{{cells['form_URI'].value}}">{{cells['form'].value}}</form></physicalDescription>
{{if(isBlank(cells['dateIssued'].value), '', '<originInfo><dateIssued>' + cells['dateIssued'].value + '</dateIssued><dateIssued encoding="edtf" keyDate="yes">' + cells['dateIssued'].value + '</dateIssued><publisher>' + cells['publisher'].value + '</publisher><place><placeTerm valueURI="http://id.loc.gov/authorities/names/n79109786">Knoxville (Tenn.)</placeTerm></place></originInfo>')}}
{{if(isBlank(cells['subject1'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject1_URI'].value) + '"><topic>' + cells['subject1'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject2'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject2_URI'].value) + '"><topic>' + cells['subject2'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject3'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject3_URI'].value) + '"><topic>' + cells['subject3'].value + '</topic></subject>')}}
{{if(isBlank(cells['subject4'].value), '', '<subject authority="lcsh" valueURI="' + cells['subject4_URI'].value) + '"><topic>' + cells['subject4'].value + '</topic></subject>')}}
<classification authority="lcc">{{cells['classification'].value}}</classification>
<typeOfResource>{{cells['item_type'].value}}</typeOfResource>
<typeOfResource>still image</typeOfResource>
<language><languageTerm type="text" authority="iso639-2b">English</languageTerm></language>
<relatedItem displayLabel="Project" type="host"><titleInfo><title>The Volunteer - University of Tennessee Yearbooks</title></titleInfo></relatedItem>
<location><physicalLocation valueURI="http://id.loc.gov/authorities/names/no2014027633">University of Tennessee, Knoxville. Special Collections</physicalLocation></location>
<recordInfo><recordContentSource valueURI="http://id.loc.gov/authorities/names/n87808088">University of Tennessee, Knoxville. Libraries</recordContentSource></recordInfo>
<accessCondition type="use and reproduction" xlink:href="{{cells['rights_URI'].value}}">{{cells['rights'].value}}</accessCondition>
</mods>

```

#### Suffix

```
</modsCollection>
```