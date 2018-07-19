---
title: '&lt;istream&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- istream/std::<istream>
- <istream>
- std::<istream>
dev_langs:
- C++
helpviewer_keywords:
- istream header
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7000bd30e34836466e9f662f9b6b0dd8f2ecde4c
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956560"
---
# <a name="ltistreamgt"></a>&lt;istream&gt;

İostreams için ayıklamalar aracılık, Şablon sınıfı basic_istream ve hem ekleme hem de ayıklamalar aracılık Şablon sınıfı basic_iostream tanımlar. Üst bilgi, ayrıca ilgili işleyici tanımlar. Bu başlık dosyasının başka bir iostreams üstbilgisi tarafından sizin için genellikle bulunur; nadiren doğrudan dahil etmek zorunda.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <istream>

```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[iostream](../standard-library/istream-typedefs.md#iostream)|Bir tür `basic_iostream` üzerinde özelleştirilmiş **char**.|
|[istream](../standard-library/istream-typedefs.md#istream)|Bir tür `basic_istream` üzerinde özelleştirilmiş **char**.|
|[wiostream](../standard-library/istream-typedefs.md#wiostream)|Bir tür `basic_iostream` üzerinde özelleştirilmiş **wchar**.|
|[wistream](../standard-library/istream-typedefs.md#wistream)|Bir tür `basic_istream` üzerinde özelleştirilmiş **wchar**.|

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[ws](../standard-library/istream-functions.md#ws)|Boşluk stream'de atlar.|
|[değiştirme](../standard-library/istream-functions.md#istream_swap)|İki akışı nesneleri birbiriyle değiştirir.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[İşleç >>](../standard-library/istream-operators.md#op_gt_gt)|Karakterlerin ve dizelerin akıştan ayıklar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_iostream](../standard-library/basic-iostream-class.md)|Hem giriş ve çıkış yapabileceği bir akışı sınıfı.|
|[basic_istream](../standard-library/basic-istream-class.md)|Şablon sınıfı öğelerin ayıklama denetleyen bir nesne ve bir Akış Arabellek türü öğeler ile kodlanmış nesneleri tanımlar `Elem`olarak da bilinen [char_type](../standard-library/basic-ios-class.md#char_type), olan karakter nitelikleri sınıfı tarafından belirlenir `Tr`olarak da bilinen [traits_type](../standard-library/basic-ios-class.md#traits_type).|

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
