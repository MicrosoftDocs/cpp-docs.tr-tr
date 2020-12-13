---
description: 'Daha fazla bilgi edinin: &lt; streamarabelleğe&gt;'
title: '&lt;streambuf&gt;'
ms.date: 11/04/2016
f1_keywords:
- <streambuf>
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
ms.openlocfilehash: 417b31b919c95d8aef741b2988c576ff6454ce4a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97183769"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

\<streambuf>İostreams sınıflarının temel aldığı [basic_streambuf](../standard-library/basic-streambuf-class.md)sınıf şablonunu tanımlamak için iostreams standart üstbilgisini ekleyin. Bu üst bilgi, genellikle Iostreams başlıklarınızdan biri tarafından sizin için eklenmiştir; genellikle doğrudan eklemeniz gerekir.

## <a name="syntax"></a>Syntax

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
