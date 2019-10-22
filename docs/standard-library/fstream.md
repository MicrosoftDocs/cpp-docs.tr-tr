---
title: '&lt;fstream &gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: 1f85367b9ae527c9387d085acc1496bfbbf7cc9e
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688031"
---
# <a name="ltfstreamgt"></a>&lt;fstream &gt;

Dış dosyalarda depolanan diziler üzerinde Iostreams işlemlerini destekleyen birkaç sınıfı tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <fstream>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Bir tür, **char** şablonu parametrelerinde özelleştirilmiş `basic_filebuf`.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Bir tür, **char** şablonu parametrelerinde özelleştirilmiş `basic_fstream`.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Bir tür, **char** şablonu parametrelerinde özelleştirilmiş `basic_ifstream`.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Bir tür, **char** şablonu parametrelerinde özelleştirilmiş `basic_ofstream`.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|**Wchar_t** Şablon parametrelerinde özelleştirilmiş bir tür `basic_fstream`.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|**Wchar_t** Şablon parametrelerinde özelleştirilmiş bir tür `basic_ifstream`.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|**Wchar_t** Şablon parametrelerinde özelleştirilmiş bir tür `basic_ofstream`.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|**Wchar_t** Şablon parametrelerinde özelleştirilmiş bir tür `basic_filebuf`.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Sınıf şablonu, `Elem` türünde öğelerin aktarımını denetleyen bir akış arabelleği tanımlar. Bu, karakter nitelikleri, bir dış dosyada depolanan öğelerin dizisine ve sonuna kadar olan `Tr`.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Sınıf şablonu, [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**eled**, **tr**> sınıfının bir akış arabelleğini kullanarak öğe ekleme ve ayıklamanın yanı sıra, karakter olan `Elem` türündeki öğeleri tanımlar nitelikler `Tr` sınıf tarafından belirlenir.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Sınıf şablonu, [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**eled**, **tr**> sınıfının bir akış arabelleğinden, karakter nitelikleri olan `Elem` türündeki öğelerle öğelerin ayıklanmasını denetleyen bir nesne tanımlar. `Tr` sınıfı tarafından belirlenir.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Sınıf şablonu, [basic_filebuf](../standard-library/basic-filebuf-class.md) \<**eled**, **tr**> sınıfının, karakter nitelikleri belirlenen `Elem` türündeki öğelerle birlikte öğelerin ve kodlanmış nesnelerin bir akış arabelleğine eklenmesini denetleyen bir nesne tanımlar `Tr` sınıfı.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md) \
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
