---
title: '&lt;strstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <strstream>
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
ms.openlocfilehash: 72b96c300aba1729823462ce6671e2f9a5285761
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523721"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

Ayrılmış bir dizi içinde depolanan dizileri iostreams işlemleri destekleyen çeşitli sınıfları tanımlar **char** nesne. Tür dizilerini kolayca C dizeleri gelen ve giden dönüştürülür.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <strstream>
```

## <a name="remarks"></a>Açıklamalar

Türündeki nesneler `strstream` ile çalışmak `char` *, C dizeleri olan. Kullanım [ \<sstream >](../standard-library/sstream.md) türü nesnelerle çalışmayı [basic_string](../standard-library/basic-string-class.md).

> [!NOTE]
> Sınıflarda \<strstream > kullanım dışı bırakılmıştır. Sınıflarda kullanmayı \<sstream > bunun yerine.

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[strstreambuf Sınıfı](../standard-library/strstreambuf-class.md)|Sınıfı bir dizi öğe depolanan gelen ve giden öğeleri iletimini denetleyen bir akış arabelleğinin açıklar bir **char** dizi nesnesi.|
|[istrstream Sınıfı](../standard-library/istrstream-class.md)|Öğelerin ayıklama denetleyen bir nesne ve bir akış arabelleğinin sınıfın kodlanmış nesnelerden sınıfı tanımlar [strstreambuf](../standard-library/strstreambuf-class.md).|
|[ostrstream Sınıfı](../standard-library/ostrstream-class.md)|Sınıfı bir akış arabelleğine ekleme öğelerin denetleyen bir nesne ve kodlanmış nesneleri sınıfı tanımlar [strstreambuf](../standard-library/strstreambuf-class.md).|
|[strstream Sınıfı](../standard-library/strstream-class.md)|Ekleme ve çıkarma öğelerin denetleyen bir nesne ve bir akış arabelleğinin sınıfı kullanarak kodlanmış nesne sınıfı tanımlar [strstreambuf](../standard-library/strstreambuf-class.md).|

## <a name="see-also"></a>Ayrıca bkz.

[\<strstream >](../standard-library/strstream.md)<br/>
[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
