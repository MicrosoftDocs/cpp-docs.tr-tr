---
title: Başvuru türü işlev bağımsız değişkenleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- arguments [C++], function
- functions [C++], paramters
- function parameters [C++], reference-type
- function arguments [C++], reference-type
- passing parameters [C++], reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fad8fc85a37aec80d09ed6df9280a78de0540f01
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408607"
---
# <a name="reference-type-function-arguments"></a>Başvuru Türü İşlev Bağımsız Değişkenleri
İşlevlere büyük nesneler yerine başvuruların geçirilmesi, genellikle daha etkili olur. Bu, derleyicinin nesnenin adresini nesneye erişmek için kullanılabilecek sözdizimini koruyarak geçirmesini sağlar. `Date` yapısını kullanan aşağıdaki örneği göz önünde bulundurun:  
  
```cpp 
// reference_type_function_arguments.cpp  
struct Date  
{  
short DayOfWeek;  
short Month;  
short Day;  
short Year;  
};  
  
// Create a Julian date of the form DDDYYYY  
// from a Gregorian date.  
long JulianFromGregorian( Date& GDate )  
{  
static int cDaysInMonth[] = {  
31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31  
   };  
long JDate = 0;  
// Add in days for months already elapsed.  
for ( int i = 0; i < GDate.Month - 1; ++i )  
JDate += cDaysInMonth[i];  
// Add in days for this month.  
JDate += GDate.Day;  
  
// Check for leap year.  
if ( GDate.Year % 100 != 0 && GDate.Year % 4 == 0 )  
JDate++;  
// Add in year.  
JDate *= 10000;  
JDate += GDate.Year;  
  
return JDate;  
}  
  
int main()  
{  
}  
```  
  
 Yukarıdaki kod, başvuru tarafından geçirilen yapının üyelerine üye seçme işleci kullanılarak erişildiğini göstermektedir (**.**) yerine, işaretçi üye seçme işleci (**->**).  
  
 Başvuru türleri olarak geçirilen bağımsız değişkenler işaretçi olmayan türlerinin söz dizimi gözlemleyin olsa da, işaretçi türlerinin önemli bir karakteristik korurlar: Bunlar olarak bildirilmedikleri sürece değiştirilebilirler **const**. Önceki kodun amacı `GDate` nesnesini değiştirmek olmadığı için daha uygun bir işlev prototipi şöyle olur:  
  
```cpp 
long JulianFromGregorian( const Date& GDate );  
```  
  
 Bu prototip, `JulianFromGregorian` işlevinin bağımsız değişkenini değiştirmeyeceğini garanti eder.  
  
 Standart dönüştürme olmadığından herhangi bir başvuru türü alınarak prototipli işlev onun yerine aynı türden bir nesne kabul edebilir *typename* için * typename ***&**.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Başvurular](../cpp/references-cpp.md)