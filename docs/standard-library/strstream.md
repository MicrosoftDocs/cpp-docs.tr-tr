---
title: '&lt;strstream&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <strstream>
dev_langs:
- C++
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a1695306ddc53a8150917eef8b27f5d3edce2bf3
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961870"
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
