---
title: '&lt;strstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <strstream>
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
ms.openlocfilehash: ecf8499a07f03c00588e7b7fd83b8d41a23e8e7a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459092"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

**Char** nesnesinin ayrılmış dizisinde depolanan diziler üzerinde Iostreams işlemlerini destekleyen birkaç sınıfı tanımlar. Bu tür diziler kolayca C dizelerine ve bu dizeden dönüştürülür.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<strstream >

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Türündeki `strstream` nesneler, C dizeleri `char` olan * ile çalışır. [Basic_string](../standard-library/basic-string-class.md)türündeki nesnelerle çalışmak için [ \<sstream >](../standard-library/sstream.md) kullanın.

> [!NOTE]
> \<Strstream > sınıfları kullanım dışıdır. Yerine \<sstream > sınıflarını kullanmayı düşünün.

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[strstreambuf Sınıfı](../standard-library/strstreambuf-class.md)|Sınıfı, bir **char** dizi nesnesinde depolanan bir öğe dizisine ve öğesinden öğelerin aktarılmasını denetleyen bir akış arabelleği tanımlar.|
|[istrstream Sınıfı](../standard-library/istrstream-class.md)|Sınıfı, [strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının Akış arabelleğindeki öğelerin ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesneyi tanımlar.|
|[ostrstream Sınıfı](../standard-library/ostrstream-class.md)|Sınıfı, öğeleri ve kodlanmış nesneleri [strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının Akış arabelleğine eklemeyi denetleyen bir nesneyi tanımlar.|
|[strstream Sınıfı](../standard-library/strstream-class.md)|Sınıfı, öğeleri ekleme ve ayıklamayı ve [strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının akış arabelleğini kullanarak kodlanmış nesneleri denetleyen bir nesneyi tanımlar.|

### <a name="functions"></a>İşlevler

```cpp
void freeze(bool freezefl = true);
char* str();
int pcount();
```

## <a name="see-also"></a>Ayrıca bkz.

[\<strstream >](../standard-library/strstream.md)\
[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
