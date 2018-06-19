---
title: '&lt;fstream&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <fstream>
dev_langs:
- C++
helpviewer_keywords:
- fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3d2fa3ef6113add6bcf72f85f74b8722033cb8d5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846616"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

Dış dosyalarında depolanan sıraları iostreams işlemlerini destekleyen birden fazla sınıf tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <fstream>

```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Bir tür `basic_filebuf` üzerinde özel `char` şablon parametreleri.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Bir tür `basic_fstream` üzerinde özel `char` şablon parametreleri.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Bir tür `basic_ifstream` üzerinde özel `char` şablon parametreleri.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Bir tür `basic_ofstream` üzerinde özel `char` şablon parametreleri.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Bir tür `basic_fstream` üzerinde özel `wchar_t` şablon parametreleri.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Bir tür `basic_ifstream` üzerinde özel `wchar_t` şablon parametreleri.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Bir tür `basic_ofstream` üzerinde özel `wchar_t` şablon parametreleri.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Bir tür `basic_filebuf` üzerinde özel `wchar_t` şablon parametreleri.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Şablon sınıfı türündeki öğeler iletimini denetleyen bir Akış Arabellek açıklar **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir **Tr**, gelen ve giden bir dizi depolanan öğeler Dış dosyası.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Şablon sınıfı ekleme ve çıkarma öğelerinin denetleyen bir nesne sınıfının bir Akış Arabellek kullanarak ve kodlanmış nesneleri tanımlar [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**,  **Tr**>, türündeki öğeler ile **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir **Tr**.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Şablon sınıfı öğelerinin ayıklama denetleyen bir nesne ve akış arabellek sınıfının kodlanmış nesnelerden açıklar [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, türündeki öğeler ile **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir **Tr**.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Şablon sınıfı ve kodlanmış nesneleri öğelerinin ekleme denetimlerini bir nesne sınıfının bir akışı arabelleğe açıklar [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, türündeki öğeler ile **Elem**, olan karakter nitelikler sınıfı tarafından belirlenir **Tr**.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
