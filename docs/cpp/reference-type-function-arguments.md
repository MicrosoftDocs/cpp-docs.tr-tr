---
title: Başvuru Türü İşlev Bağımsız Değişkenleri
ms.date: 08/27/2018
helpviewer_keywords:
- arguments [C++], function
- functions [C++], parameters
- function parameters [C++], reference-type
- function arguments [C++], reference-type
- passing parameters [C++], reference-type arguments
ms.assetid: 0a70e831-9e76-46c0-821d-aeba13d73cc0
ms.openlocfilehash: 2a0bd21023bd1c6bc14b1f587c85960cf1e8b820
ms.sourcegitcommit: 31a2a9845f5e1d35ab054906d8cdc6582a5220bd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2018
ms.locfileid: "51597722"
---
# <a name="reference-type-function-arguments"></a>Başvuru Türü İşlev Bağımsız Değişkenleri

İşlevlere büyük nesneler yerine başvuruların geçirilmesi, genellikle daha etkili olur. Bu, derleyicinin nesnenin adresini nesneye erişmek için kullanılabilecek sözdizimini koruyarak geçirmesini sağlar. `Date` yapısını kullanan aşağıdaki örneği göz önünde bulundurun:

```cpp
// reference_type_function_arguments.cpp
#include <iostream>

struct Date
{
    short Month;
    short Day;
    short Year;
};

// Create a date of the form DDDYYYY (day of year, year)
// from a Date.
long DateOfYear( Date& date )
{
    static int cDaysInMonth[] = {
        31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31
    };
    long dateOfYear = 0;

    // Add in days for months already elapsed.
    for ( int i = 0; i < date.Month - 1; ++i )
        dateOfYear += cDaysInMonth[i];

    // Add in days for this month.
    dateOfYear += date.Day;

    // Check for leap year.
    if ( date.Month > 2 &&
        (( date.Year % 100 != 0 || date.Year % 400 == 0 ) &&
        date.Year % 4 == 0 ))
        dateOfYear++;

    // Add in year.
    dateOfYear *= 10000;
    dateOfYear += date.Year;

    return dateOfYear;
}

int main()
{
    Date date{ 8, 27, 2018 };
    long dateOfYear = DateOfYear(date);
    std::cout << dateOfYear << std::endl;
}
```

Yukarıdaki kod, başvuru tarafından geçirilen yapının üyelerine üye seçme işleci kullanılarak erişildiğini göstermektedir (**.**) yerine, işaretçi üye seçme işleci (**->**).

Başvuru türleri olarak geçirilen bağımsız değişkenler işaretçi olmayan türlerinin söz dizimi gözlemleyin olsa da, işaretçi türlerinin önemli bir karakteristik korurlar: Bunlar olarak bildirilmedikleri sürece değiştirilebilirler **const**. Önceki kodun amacı `date` nesnesini değiştirmek olmadığı için daha uygun bir işlev prototipi şöyle olur:

```cpp
long DateOfYear( const Date& date );
```

Bu prototip, `DateOfYear` işlevinin bağımsız değişkenini değiştirmeyeceğini garanti eder.

Standart dönüştürme olmadığından herhangi bir başvuru türü alınarak prototipli işlev onun yerine aynı türden bir nesne kabul edebilir *typename* için *typename* <strong>&</strong>.

## <a name="see-also"></a>Ayrıca bkz.

[Başvurular](../cpp/references-cpp.md)<br/>
