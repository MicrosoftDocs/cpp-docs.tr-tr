---
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: 46f65f746179740f2d67dd1ada2f96ab3fb6aaf6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87203240"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

Dış dosyalarda depolanan diziler üzerinde Iostreams işlemlerini destekleyen birkaç sınıfı tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <fstream>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|`basic_filebuf`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`char`** .|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|`basic_fstream`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`char`** .|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|`basic_ifstream`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`char`** .|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|`basic_ofstream`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`char`** .|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|`basic_fstream`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`wchar_t`** .|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|`basic_ifstream`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`wchar_t`** .|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|`basic_ofstream`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`wchar_t`** .|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|`basic_filebuf`Şablon parametreleri üzerinde özelleştirilmiş bir tür **`wchar_t`** .|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Sınıf şablonu, türünde öğelerin aktarılmasını denetleyen bir akış arabelleği tanımlar `Elem` . Bu, karakter nitelikleri sınıfı tarafından `Tr` , dış dosyada depolanan öğelerin dizisine ve sonuna kadar belirlenir.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Sınıf şablonu, [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> `Elem` karakter nitelikleri sınıfı tarafından belirlendiği şekilde, öğe basic_filebuf, öğelerin ve ayıklamanın bir akış arabelleğini kullanarak öğeleri ve ayıklamayı ve kodlanmış nesneleri denetler `Tr` .|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Sınıf şablonu, sınıf [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> `Elem` nitelikleri sınıfı tarafından belirlendiği şekilde, öğe basic_filebuf bir Stream arabelleğinden öğelerin ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesne tanımlar `Tr` .|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Sınıf şablonu, öğe ve kodlanmış nesnelerin, [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> `Elem` karakter nitelikleri sınıfı tarafından belirlenen türdeki öğelerle basic_filebuf bir akış arabelleğine eklenmesini denetleyen bir nesneyi tanımlar `Tr` .|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
