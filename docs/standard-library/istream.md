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
ms.openlocfilehash: 1b3e55aaa8cfc659672632a897efc7543effaf26
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33852383"
---
# <a name="ltistreamgt"></a>&lt;istream&gt;

İostreams ayıklamaları aracılık, Şablon sınıfı basic_istream ve eklemeleri ve ayıklamaları aracılık Şablon sınıfı basic_iostream tanımlar. Üstbilgi ayrıca ilgili manipulator tanımlar. Bu üst bilgi dosyası başka bir iostreams üstbilgisi tarafından sizin için genellikle bulunur; nadiren doğrudan eklemek zorunda.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <istream>

```

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[iostream](../standard-library/istream-typedefs.md#iostream)|Bir tür `basic_iostream` üzerinde özel `char`.|
|[istream](../standard-library/istream-typedefs.md#istream)|Bir tür `basic_istream` üzerinde özel `char`.|
|[wiostream](../standard-library/istream-typedefs.md#wiostream)|Bir tür `basic_iostream` üzerinde özel **wchar**.|
|[wistream](../standard-library/istream-typedefs.md#wistream)|Bir tür `basic_istream` üzerinde özel **wchar**.|

### <a name="manipulators"></a>Manipülatörleri

|||
|-|-|
|[ws](../standard-library/istream-functions.md#ws)|Boşluk akışında atlar.|
|[Değiştirme](../standard-library/istream-functions.md#istream_swap)|İki akışı nesneleri değiş tokuş eder.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[İşleç >>](../standard-library/istream-operators.md#op_gt_gt)|Karakterler ve dizeleri akıştan ayıklar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[basic_iostream](../standard-library/basic-iostream-class.md)|Hem giriş ve çıkış yapmak için bir akış sınıfı.|
|[basic_istream](../standard-library/basic-istream-class.md)|Şablon sınıfı öğelerinin ayıklama denetleyen bir nesne ve akış arabellek türündeki öğeler ile kodlanmış nesnelerden açıklar **Elem**, olarak da bilinen [char_type](../standard-library/basic-ios-class.md#char_type), olan karakter nitelikler olan sınıfı tarafından belirlenen **Tr**, olarak da bilinen [traits_type](../standard-library/basic-ios-class.md#traits_type).|

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[iostream Programlaması](../standard-library/iostream-programming.md)<br/>
[iostreams Kuralları](../standard-library/iostreams-conventions.md)<br/>
