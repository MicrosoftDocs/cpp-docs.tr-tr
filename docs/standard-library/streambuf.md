---
title: '&lt;streambuf&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <streambuf>
dev_langs:
- C++
helpviewer_keywords:
- streambuf header
ms.assetid: 4365b25c-5831-488b-b9c2-867bfe961b89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: db05d1b19a67fc54a148d407fd90992a6d37c4c6
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43213593"
---
# <a name="ltstreambufgt"></a>&lt;streambuf&gt;

İostreams standart üstbilgisini \<streambuf > şablon sınıfını tanımlamak için [basic_streambuf](../standard-library/basic-streambuf-class.md), iostreams sınıfları işlemi için temel olduğu. Bu üst bilgi, genellikle başka iostreams üst bilgi bulunur; nadiren doğrudan eklemeniz gerekir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <streambuf>

```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[streambuf](../standard-library/streambuf-typedefs.md#streambuf)|Bir alt uzmanlaşması `basic_streambuf` kullanan **char** şablon parametreleri olarak.|
|[wstreambuf](../standard-library/streambuf-typedefs.md#wstreambuf)|Bir alt uzmanlaşması `basic_streambuf` kullanan **wchar_t** şablon parametreleri olarak.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_streambuf Sınıfı](https://msdn.microsoft.com/d9c706ba-ce01-43e0-b0b2-a558fc53ea8d)|Şablon sınıfı, belirli bir gösterimiyse bir akış, gelen ve giden öğeleri aktarımını denetleyen bir akış arabelleğinin türetmek için Özet temel sınıf tanımlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
