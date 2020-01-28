![MIKES DATA WORK GIT REPO](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_01.png "Mikes Data Work")        

# Use SQL To Find The Difference Between Two Dates
**Post Date: September 28, 2015**        



## Contents    
- [About Process](##About-Process)  
- [SQL Logic](#SQL-Logic)  
- [Build Info](#Build-Info)  
- [Author](#Author)  
- [License](#License)       

## About-Process

<p>Ever find yourself needing to find the difference between two dates, but displaying in such a way that makes sense to most people? Here's some quick sql logic to get you the difference.</p>      


## SQL-Logic
```SQL
declare @last_date datetime = '2015-09-26 14:00:01.670'
 
select case
when datediff(second, @last_date, getdate()) / 60 / 60 / 24 / 30 / 12 = 0 then ''
else cast(datediff(second, @last_date, getdate()) / 60 / 60 / 24 / 30 / 12 as nvarchar(50)) + ' Yr ' end +
case
when datediff(second, @last_date, getdate()) / 60 / 60 / 24 / 30 % 12 = 0 then ''
else cast(datediff(second, @last_date, getdate()) / 60 / 60 / 24 / 30 % 12 as nvarchar(50)) + ' Mo ' end +
case
when datediff(second, @last_date, getdate()) / 60 / 60 / 24 % 30 = 0 then ''
else cast(datediff(second, @last_date, getdate()) / 60 / 60 / 24 % 30 as nvarchar(50)) + ' Dy ' end +
case
when datediff(second, @last_date, getdate()) / 60 / 60 % 24 = 0 then ''
else cast(datediff(second, @last_date, getdate()) / 60 / 60 % 24 as nvarchar(50)) + ' Hr ' end +
case
when datediff(second, @last_date, getdate()) / 60 % 60 = 0 then ''
else cast(datediff(second, @last_date, getdate()) / 60 % 60 as nvarchar(50)) + ' mn ' end

```

[![WorksEveryTime](https://forthebadge.com/images/badges/60-percent-of-the-time-works-every-time.svg)](https://shitday.de/)

## Build-Info

| Build Quality | Build History |
|--|--|
|<table><tr><td>[![Build-Status](https://ci.appveyor.com/api/projects/status/pjxh5g91jpbh7t84?svg?style=flat-square)](#)</td></tr><tr><td>[![Coverage](https://coveralls.io/repos/github/tygerbytes/ResourceFitness/badge.svg?style=flat-square)](#)</td></tr><tr><td>[![Nuget](https://img.shields.io/nuget/v/TW.Resfit.Core.svg?style=flat-square)](#)</td></tr></table>|<table><tr><td>[![Build history](https://buildstats.info/appveyor/chart/tygerbytes/resourcefitness)](#)</td></tr></table>|

## Author

[![Gist](https://img.shields.io/badge/Gist-MikesDataWork-<COLOR>.svg)](https://gist.github.com/mikesdatawork)
[![Twitter](https://img.shields.io/badge/Twitter-MikesDataWork-<COLOR>.svg)](https://twitter.com/mikesdatawork)
[![Wordpress](https://img.shields.io/badge/Wordpress-MikesDataWork-<COLOR>.svg)](https://mikesdatawork.wordpress.com/)

   
## License
[![LicenseCCSA](https://img.shields.io/badge/License-CreativeCommonsSA-<COLOR>.svg)](https://creativecommons.org/share-your-work/licensing-types-examples/)

![Mikes Data Work](https://raw.githubusercontent.com/mikesdatawork/images/master/git_mikes_data_work_banner_02.png "Mikes Data Work")

