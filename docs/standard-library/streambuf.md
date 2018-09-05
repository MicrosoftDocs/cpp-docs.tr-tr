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
ms.openlocfilehash: 25ec172fb38fb3b200086c5f9317ccd8e5e54281
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43691486"
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
|[basic_streambuf Sınıfı](basic-streambuf-class.md)|Şablon sınıfı, belirli bir gösterimiyse bir akış, gelen ve giden öğeleri aktarımını denetleyen bir akış arabelleğinin türetmek için Özet temel sınıf tanımlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
