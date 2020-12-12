---
description: 'Daha fazla bilgi edinin: &lt; fstream&gt;'
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: 98fe18306d50a9d6f1f8a360d4d29b6e865f6328
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324271"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

Dış dosyalarda depolanan diziler üzerinde Iostreams işlemlerini destekleyen birkaç sınıfı tanımlar.

## <a name="syntax"></a>Syntax

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
|[basic_fstream](../standard-library/basic-fstream-class.md)|Sınıf şablonu, [](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> `Elem` karakter nitelikleri sınıfı tarafından belirlendiği şekilde, öğe basic_filebuf, öğelerin ve ayıklamanın bir akış arabelleğini kullanarak öğeleri ve ayıklamayı ve kodlanmış nesneleri denetler `Tr` .|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Sınıf şablonu, sınıf [](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> `Elem` nitelikleri sınıfı tarafından belirlendiği şekilde, öğe basic_filebuf bir Stream arabelleğinden öğelerin ve kodlanmış nesnelerin ayıklanmasını denetleyen bir nesne tanımlar `Tr` .|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Sınıf şablonu, öğe ve kodlanmış nesnelerin, [](../standard-library/basic-filebuf-class.md) \<**Elem**, **Tr**> `Elem` karakter nitelikleri sınıfı tarafından belirlenen türdeki öğelerle basic_filebuf bir akış arabelleğine eklenmesini denetleyen bir nesneyi tanımlar `Tr` .|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
