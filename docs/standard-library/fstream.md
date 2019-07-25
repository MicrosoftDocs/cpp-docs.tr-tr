---
title: '&lt;fstream&gt;'
ms.date: 11/04/2016
f1_keywords:
- <fstream>
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
ms.openlocfilehash: ba6a4152b8d37f5b0186f9d05c6ba850e8c2e54c
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454014"
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
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Char şablon `basic_filebuf` parametreleri üzerinde  özelleştirilmiş bir tür.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Char şablon `basic_fstream` parametreleri üzerinde  özelleştirilmiş bir tür.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Char şablon `basic_ifstream` parametreleri üzerinde  özelleştirilmiş bir tür.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Char şablon `basic_ofstream` parametreleri üzerinde  özelleştirilmiş bir tür.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Wchar_t şablon `basic_fstream` parametrelerine özel  bir tür.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Wchar_t şablon `basic_ifstream` parametrelerine özel  bir tür.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Wchar_t şablon `basic_ofstream` parametrelerine özel  bir tür.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Wchar_t şablon `basic_filebuf` parametrelerine özel  bir tür.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Şablon sınıfı, türünde `Elem`öğelerin aktarılmasını denetleyen bir akış arabelleğini tanımlar. Bu, karakter nitelikleri sınıfı `Tr`tarafından, dış dosyada depolanan bir öğe dizisine ve bu diziye göre belirlenir.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Şablon sınıfı, [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**eled**, `Elem` **tr**> sınıfının bir akış arabelleğini kullanarak öğeleri ve ayıklamayı ve kodlanmış nesneleri içeren bir nesneyi tanımlar, karakter nitelikleri sınıfı `Tr`tarafından belirlenir.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Şablon sınıfı, öğe ve kodlanmış nesneleri [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**eled**, `Elem` **tr**> sınıfının bir akış arabelleğinden, karakter nitelikleri olan bir nesne sınıfı `Tr`tarafından belirlenir.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Şablon sınıfı, öğelerin ve kodlanmış nesnelerin [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**eled**, `Elem` **tr**> sınıfının bir akış arabelleğine eklenmesini denetleyen, karakter nitelikleri olan bir nesneyi tanımlar. sınıfı `Tr`tarafından belirlenir.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
