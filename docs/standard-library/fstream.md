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
ms.openlocfilehash: 6b716248c6fe9d0734cd580800c9254cf01f2a17
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38962880"
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;

Dış dosyalarında depolanan dizileri iostreams işlemleri destekleyen çeşitli sınıfları tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <fstream>

```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|Bir tür `basic_filebuf` üzerinde özelleştirilmiş **char** şablon parametreleri.|
|[fstream](../standard-library/fstream-typedefs.md#fstream)|Bir tür `basic_fstream` üzerinde özelleştirilmiş **char** şablon parametreleri.|
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|Bir tür `basic_ifstream` üzerinde özelleştirilmiş **char** şablon parametreleri.|
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|Bir tür `basic_ofstream` üzerinde özelleştirilmiş **char** şablon parametreleri.|
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|Bir tür `basic_fstream` üzerinde özelleştirilmiş **wchar_t** şablon parametreleri.|
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|Bir tür `basic_ifstream` üzerinde özelleştirilmiş **wchar_t** şablon parametreleri.|
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|Bir tür `basic_ofstream` üzerinde özelleştirilmiş **wchar_t** şablon parametreleri.|
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|Bir tür `basic_filebuf` üzerinde özelleştirilmiş **wchar_t** şablon parametreleri.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|Şablon sınıfı türü öğeler aktarımını denetleyen bir akış arabelleğinin tanımlar `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenir `Tr`, için ve bir dış dosya içinde depolanan öğeleri dizisi.|
|[basic_fstream](../standard-library/basic-fstream-class.md)|Şablon sınıfı, denetimleri ekleme ve çıkarma öğelerin bir nesne ve bir akış arabelleğinin sınıfı kullanarak kodlanmış nesneleri tanımlar [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**,  **Tr**>, türü öğeler ile `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`.|
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|Şablon sınıfı öğelerin ayıklama denetleyen bir nesne ve kodlanmış bir akış arabelleğinin sınıfın nesneleri tanımlar [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, türü öğeler ile `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`.|
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|Şablon sınıfı bir sınıfın akış arabelleğine ekleme öğelerin denetleyen bir nesne ve kodlanmış nesneleri açıklar [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**>, türü öğeler ile `Elem`, olan karakter nitelikleri sınıfı tarafından belirlenen `Tr`.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
