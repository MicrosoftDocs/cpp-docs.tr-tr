---
title: '&lt;CTime&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ctime>
- std::<ctime>
helpviewer_keywords:
- ctime header
ms.assetid: c1f7d4a4-4bfe-4e35-92cb-f63dbd3c39a8
ms.openlocfilehash: f4bdb8fa30c44a6eaa83f53624c5bd43bd235261
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449381"
---
# <a name="ltctimegt"></a>&lt;CTime&gt;

Standart C Kitaplığı üstbilgisi \<saati. h > içerir ve ilişkili adları `std` ad alanına ekler.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <ctime>
```

## <a name="remarks"></a>Açıklamalar

Bu üstbilginin dahil edilmesi, standart C Kitaplığı üstbilgisinde harici bağlantı kullanılarak belirtilen adların `std` ad alanında bildirilmesini sağlar.

## <a name="constants"></a>Sabitler

```cpp
#define NULL
#define CLOCKS_PER_SEC
#define TIME_UTC

namespace std {
    using size_t = see below;
    using clock_t = see below ;
    using time_t = see below ;
}
```
    
## <a name="structures"></a>Yapılar
    
```cpp
struct timespec;
struct tm;
```
    
## <a name="functions"></a>İşlevler

```cpp
clock_t clock();
double difftime(time_t time1, time_t time0);
time_t mktime(struct tm* timeptr);
time_t time(time_t* timer);
int timespec_get(timespec* ts, int base);
char* asctime(const struct tm* timeptr);
char* ctime(const time_t* timer);
struct tm* gmtime(const time_t* timer);
struct tm* localtime(const time_t* timer);
size_t strftime(char* s, size_t maxsize, const char* format, const struct tm* timeptr);
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++Standart kitaplığa genel bakış](../standard-library/cpp-standard-library-overview.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
