---
title: '&lt;strstream&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <strstream>
dev_langs:
- C++
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f63ecc2f24431e54042a1b995762806f87c691da
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;

Ayrılmış bir dizi içinde depolanan sıraları iostreams işlemlerini destekleyen birden fazla sınıf tanımlar `char` nesnesi. Bu tür dizileri kolayca C dizeleri gelen ve giden dönüştürülür.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <strstream>

```

## <a name="remarks"></a>Açıklamalar

Nesne türü `strstream` ile çalışmak `char` *, C dizeleri olduğu. Kullanım [ \<sstream >](../standard-library/sstream.md) türü nesneleriyle çalışmak için [basic_string](../standard-library/basic-string-class.md).

> [!NOTE]
> Sınıflarda \<strstream > kullanım dışı bırakılmıştır. Sınıflarda kullanmayı \<sstream > bunun yerine.

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[strstreambuf Sınıfı](../standard-library/strstreambuf-class.md)|Öğeleri depolanan öğe dizisi gelen ve giden iletimini denetleyen bir Akış Arabellek sınıf tanımlar bir `char` dizi nesnesi.|
|[istrstream Sınıfı](../standard-library/istrstream-class.md)|Ayıklama öğelerinin denetleyen bir nesne ve akış arabellek sınıfının kodlanmış nesnelerden sınıfı açıklar [strstreambuf](../standard-library/strstreambuf-class.md).|
|[ostrstream Sınıfı](../standard-library/ostrstream-class.md)|Sınıfı ve kodlanmış nesneleri öğelerinin ekleme denetimlerini bir nesne sınıfının bir akışı arabelleğe açıklar [strstreambuf](../standard-library/strstreambuf-class.md).|
|[strstream Sınıfı](../standard-library/strstream-class.md)|Sınıf ekleme ve çıkarma öğelerinin denetleyen bir nesne sınıfının bir Akış Arabellek kullanarak ve kodlanmış nesneleri tanımlar [strstreambuf](../standard-library/strstreambuf-class.md).|

## <a name="see-also"></a>Ayrıca bkz.

[\<strstream >](../standard-library/strstream.md)<br/>
[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
