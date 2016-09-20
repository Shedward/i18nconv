# i18nconv
XCode/CSV i18n conversation tool

## Usage

```
i18nconv [-h] --from FORMAT PATH [PATH ...] --to
                FORMAT PATH [--verbose]

Localization converter. 
Supported formats (case insensitive): 
- XCode 
- CSV

optional arguments:
  -h, --help            show this help message and exit
  --from FORMAT PATH [PATH ...], -f FORMAT PATH [PATH ...]
                        Importing locale directories with type, ex. --from
                        XCode ./XCodeProj/Resources/
  --to FORMAT PATH, -t FORMAT PATH
                        Directory with type for exported files, ex. --to CSV
                        ./csv
  --verbose, -v         Show verbose output

```

## Formats
### XCode
Folder structure
```
XCodeLocalizationFolder/
├── Base.lproj
│   ├── InfoPlist.strings
│   └── Localizable.strings
└── ru.lproj
    ├── InfoPlist.strings
    └── Localizable.strings
```
Content of Base.lproj/Localizable.strings
```
"test.one" = "One";
"test.two" = "Two";
"test.three" = "Three";
```
### CSV
Folder structure
```
CSVLocalizationFolder/
├── InfoPlist.csv
└── Localizable.csv
```
Content of Localizable.csv
```
String,Base,ru
test.one,One,Раз
test.three,Three,Три
test.two,Two,Два
```
## Examples:
Export localized strings from XCode project to csv file:

`i18nconv -f XCode ./XCodeProject/Resources -t CSV ./LocalizationCSVs/`

Import localized strings from csv file to XCode project:

`i18nconv -f CSV ./LocalizationCSVs -t XCode ./XCodeProject/Resources`
