---
title: '&lt;strstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <strstream>
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
ms.openlocfilehash: a7df541049aafd191e969eaa392ab3706f171926
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87224610"
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

Ayrılan nesne dizisinde depolanan diziler üzerinde Iostreams işlemlerini destekleyen birkaç sınıfı tanımlar **`char`** . Bu tür diziler kolayca C dizelerine ve bu dizeden dönüştürülür.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<strstream>

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Türündeki nesneler `strstream` **`char`** , C dizeleri olan * ile çalışır. [\<sstream>](../standard-library/sstream.md) [Basic_string](../standard-library/basic-string-class.md)türündeki nesnelerle çalışmak için kullanın.

> [!NOTE]
> İçindeki sınıflar \<strstream> kullanım dışıdır. Bunun yerine sınıfları kullanmayı göz önünde bulundurun \<sstream> .

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[strstreamarabelleğe sınıfı](../standard-library/strstreambuf-class.md)|Sınıfı, bir dizi nesnesinde depolanan bir öğe dizisine ve öğesinden öğelerin aktarılmasını denetleyen bir akış arabelleği tanımlar **`char`** .|
|[istrstream sınıfı](../standard-library/istrstream-class.md)|Sınıfı, [strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının Akış arabelleğindeki öğelerin ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesneyi tanımlar.|
|[ostrstream sınıfı](../standard-library/ostrstream-class.md)|Sınıfı, öğeleri ve kodlanmış nesneleri [strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının Akış arabelleğine eklemeyi denetleyen bir nesneyi tanımlar.|
|[strstream sınıfı](../standard-library/strstream-class.md)|Sınıfı, öğeleri ekleme ve ayıklamayı ve [strstreambuffer](../standard-library/strstreambuf-class.md)sınıfının akış arabelleğini kullanarak kodlanmış nesneleri denetleyen bir nesneyi tanımlar.|

### <a name="functions"></a>İşlevler

```cpp
void freeze(bool freezefl = true);
char* str();
int pcount();
```

## <a name="see-also"></a>Ayrıca bkz.

[\<strstream>](../standard-library/strstream.md)\
[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
