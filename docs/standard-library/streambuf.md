---
title: '&lt;streambuf&gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: 1121bd4e782fca57588d05fb29b5b9b6cdec18e9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215614"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

\<streambuf>İostreams sınıflarının temel aldığı [basic_streambuf](../standard-library/basic-streambuf-class.md)sınıf şablonunu tanımlamak için iostreams standart üstbilgisini ekleyin. Bu üst bilgi, genellikle Iostreams başlıklarınızdan biri tarafından sizin için eklenmiştir; genellikle doğrudan eklemeniz gerekir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <streambuf>
```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|`basic_streambuf` **`char`** Şablon parametreleri olarak kullanılan özelleştirmesi.|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|`basic_streambuf` **`wchar_t`** Şablon parametreleri olarak kullanılan özelleştirmesi.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[basic_streambuf sınıfı](basic-streambuf-class.md)|Sınıf şablonu, akış arabelleği türetmede bir soyut temel sınıf tanımlar. Bu, bir akışın belirli bir gösteriminden ve öğesinden öğelerin aktarılmasını denetler.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[iostream programlama](../standard-library/iostream-programming.md)\
[iostreams kuralları](../standard-library/iostreams-conventions.md)
