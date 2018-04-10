---
title: Başvuru türü işlev bağımsız değişkenleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b94f6b89ec00cc044cbaa93a4f0f914860db71e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="reference-type-function-arguments"></a>Başvuru Türü İşlev Bağımsız Değişkenleri
İşlevlere büyük nesneler yerine başvuruların geçirilmesi, genellikle daha etkili olur. Bu, derleyicinin nesnenin adresini nesneye erişmek için kullanılabilecek sözdizimini koruyarak geçirmesini sağlar. `Date` yapısını kullanan aşağıdaki örneği göz önünde bulundurun:  
  
```  
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
  
 Önceki kod başvuruya göre geçirilen bir yapı üyeleri üye seçimi işleci kullanılarak erişilir gösterir (**.**) yerine işaretçi üye seçimi işleci (**->**).  
  
 Başvuru türleri olarak geçirilen bağımsız değişken olmayan İşaretçi türlerinin sözdizimi gözlemlemek rağmen İşaretçi türlerinin bir önemli özellik korurlar: olarak bildirilir sürece değiştirilebilir **const**. Önceki kodun amacı `GDate` nesnesini değiştirmek olmadığı için daha uygun bir işlev prototipi şöyle olur:  
  
```  
long JulianFromGregorian( const Date& GDate );  
```  
  
 Bu prototip, `JulianFromGregorian` işlevinin bağımsız değişkenini değiştirmeyeceğini garanti eder.  
  
 Standart dönüştürme olduğundan olarak bir başvuru türü alıp örneklenmiş herhangi bir işlev onun yerine aynı türde bir nesne kabul edebilir *typename* için *typename*  **&** .  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Başvuruları](../cpp/references-cpp.md)