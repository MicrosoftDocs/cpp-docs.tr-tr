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
ms.openlocfilehash: 5a409efbe2908954d394656cb989ad6b80a9ce22
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233645"
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

Önceki kod, başvuru tarafından geçirilen bir yapının üyelerine, işaretçi üye seçim işleci () yerine üye seçim işleci (**.**) kullanılarak erişildiğini gösterir **->** .

Başvuru türleri olarak geçirilen bağımsız değişkenler işaretçi olmayan türlerin sözdizimini gözlemlese de, işaretçi türlerinin önemli bir özelliğini korurlar: olarak bildirilmeyen sürece bunlar değiştirilebilir **`const`** . Önceki kodun amacı `date` nesnesini değiştirmek olmadığı için daha uygun bir işlev prototipi şöyle olur:

```cpp
long DateOfYear( const Date& date );
```

Bu prototip, `DateOfYear` işlevinin bağımsız değişkenini değiştirmeyeceğini garanti eder.

Bir başvuru türü alan herhangi bir işlev *prototipten* *TypeName*'e standart bir dönüştürme olduğundan, onun yerine aynı türdeki bir nesneyi kabul edebilir <strong>&</strong> .

## <a name="see-also"></a>Ayrıca bkz.

[Başvurular](../cpp/references-cpp.md)<br/>
