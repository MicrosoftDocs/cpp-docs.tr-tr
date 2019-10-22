---
title: '&lt;streambuf &gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: ca5f53d67bb32e59c20d1d440879144f0a617c66
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72686018"
---
# <a name="ltstreambufgt"></a>&lt;streambuf &gt;

İostreams sınıfları için temel olan [basic_streambuf](../standard-library/basic-streambuf-class.md)sınıf şablonunu tanımlamak için, Iostreams standart üst bilgisini \<streambuf > ekleyin. Bu üst bilgi, genellikle Iostreams başlıklarınızdan biri tarafından sizin için eklenmiştir; genellikle doğrudan eklemeniz gerekir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <streambuf>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Şablon parametreleri olarak **char** kullanan `basic_streambuf` özelleştirmesi.|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|Şablon parametreleri olarak **wchar_t** 'yi kullanan `basic_streambuf` özelleştirmesi.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_streambuf Sınıfı](basic-streambuf-class.md)|Sınıf şablonu, akış arabelleği türetmede bir soyut temel sınıf tanımlar. Bu, bir akışın belirli bir gösteriminden ve öğesinden öğelerin aktarılmasını denetler.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[iostream programlama](../standard-library/iostream-programming.md) \
[iostreams Kuralları](../standard-library/iostreams-conventions.md)
