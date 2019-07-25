---
title: '&lt;streambuf&gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: 87fb74f62abffdd62b8c0179b13f53d96439d6c6
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68449573"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

İostreams sınıfları için temel olan \< [basic_streambuf](../standard-library/basic-streambuf-class.md)şablon sınıfını tanımlamak için iostreams standart üst bilgi streamarabelleğe > ekleyin. Bu üst bilgi, genellikle Iostreams başlıklarınızdan biri tarafından sizin için eklenmiştir; genellikle doğrudan eklemeniz gerekir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <streambuf>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Şablon parametreleri olarak `basic_streambuf` **char** kullanan bir özelleştirmesi.|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|Şablon parametreleri olarak `basic_streambuf` **wchar_t** 'yi kullanan bir özelleştirmesi.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_streambuf Sınıfı](basic-streambuf-class.md)|Şablon sınıfı, akış arabelleği türetmede bir soyut temel sınıf tanımlar. Bu, bir akışın belirli bir gösteriminden ve öğesinden öğelerin aktarılmasını denetler.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ Standart kitaplıkta Iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
