![CLEVER DATA GIT REPO](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/0-clever-data-github.png "李聪明的数据库")

# POST TITLE
#### SECONDARY TITLE
**TIME STAMP**

![#](images/##############?raw=true "#")

## Contents

- [中文](#中文)
- [English](#English)
- [SQL Logic](#Logic)
- [Build Info](#Build-Info)
- [Author](#Author)
- [License](#License) 


## 中文
使用此简单脚本重新组织所有FullText或索引。

## English
Reorganize all the FullText Catalog or Index with this simple script.

---
## Logic
```SQL
use master;
set nocount on
declare @reorganize_all_fti varchar(max)
set @reorganize_all_fti = ''
select @reorganize_all_fti = @reorganize_all_fti + 'use [' + name + ']' + char(10) +
'declare @get_ftc_name varchar(4000)' + char(10) +
'set @get_ftc_name = ''''' + char(10) +
'select @get_ftc_name = @get_ftc_name +
''alter fulltext catalog '' + name + '' reorganize;'' + char(10) from sys.fulltext_catalogs' + char(10) + 'exec (@get_ftc_name);' + char(10) +
'go' + char(10)
from sys.databases where name not in ('master', 'model', 'msdb', 'tempdb') and state_desc = 'online' order by name asc
 
exec (@reorganize_all_fti)


```
希望这对你有所帮助。(Hope this is useful.)



[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

- **李聪明的数据库 Lee's Clever Data**
- **Mike的数据库宝典 Mikes Database Collection**
- **李聪明的数据库** "Lee Songming"

[![Gist](https://img.shields.io/badge/Gist-李聪明的数据库-<COLOR>.svg)](https://gist.github.com/congmingshuju)
[![Twitter](https://img.shields.io/badge/Twitter-mike的数据库宝典-<COLOR>.svg)](https://twitter.com/mikesdatawork?lang=en)
[![Wordpress](https://img.shields.io/badge/Wordpress-mike的数据库宝典-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

---
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Lee Songming](https://raw.githubusercontent.com/LiCongMingDeShujuku/git-resources/master/1-clever-data-github.png "李聪明的数据库")

