---
title: '&lt;yardımcı programı&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <utility>
dev_langs:
- C++
helpviewer_keywords:
- utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 84464f485d39f1146f55fb6b5b1970cf1c9321df
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33858139"
---
# <a name="ltutilitygt"></a>&lt;yardımcı programı&gt;

C++ Standart Kitaplığı türleri, İşlevler ve oluşturmak ve iki nesne bir oldukları gibi kabul gerektiğinde yararlı olan nesneleri çiftlerini yönetmek için yardımcı işleçler tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <utility>

```

## <a name="remarks"></a>Açıklamalar

Çiftleri C++ Standart Kitaplığı'nda yaygın olarak kullanılır. Çeşitli işlevleri için dönüş değerlerini ve bağımsız değişkenler olarak hem olarak öğe türleri gibi kapsayıcıları için gereklidirler [eşleme sınıf](../standard-library/map-class.md) ve [multimap sınıfı](../standard-library/multimap-class.md). \<Yardımcı programı > üstbilgisi tarafından dahil otomatik olarak \<harita > kendi anahtar/değer yönetilmesine yardımcı olmak için çifti öğelerini yazın.

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Türü saran bir sınıf bir `pair` öğesi.|
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Saran bir sınıf `pair` öğe sayısı.|

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[İlet](../standard-library/utility-functions.md#forward)|Başvuru türü korur (ya da `lvalue` veya `rvalue`) tarafından kusursuz iletme getirilmemeli gelen bağımsız değişken.|
|[get](../standard-library/utility-functions.md#get)|Bir öğeyi alır işlevi bir `pair` nesnesi.|
|[make_pair](../standard-library/utility-functions.md#make_pair)|Türündeki nesneleri oluşturmak için kullanılan bir şablon yardımcı işlevini `pair`, bileşen türleri parametre olarak geçirilen veri türleri burada dayanır.|
|[Taşıma](../standard-library/utility-functions.md#move)|Bağımsız değişken olarak geçirilen döndürür bir `rvalue` başvuru.|
|[Değiştirme](../standard-library/utility-functions.md#swap)|İki öğelerini alış verişleri `pair` nesneleri.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](../standard-library/utility-operators.md#op_neq)|Testleri işlecinin sol tarafındaki çifti nesnesi sağ tarafında çifti nesnesi eşit değil.|
|[operator==](../standard-library/utility-operators.md#op_eq_eq)|Sağ taraftaki çifti nesnesi işlecinin sol tarafındaki çifti nesnesi eşitse testleri.|
|[operator <](../standard-library/utility-operators.md#op_lt)|Çift işlecinin sol tarafında nesne sağlayıp sağlamadığını test azdır sağ tarafında çifti nesnesi.|
|[işleci\<=](../standard-library/utility-operators.md#op_gt_eq)|Çift işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında çifti nesnesi eşit veya daha az olur.|
|[operator >](../standard-library/utility-operators.md#op_gt)|Testleri işlecinin sol tarafındaki çifti nesnesi sağ tarafında çifti nesnesi değerinden daha büyük.|
|[operator>=](../standard-library/utility-operators.md#op_gt_eq)|Testleri işlecinin sol tarafındaki çifti nesnesi sağ tarafında çifti nesnesi eşit veya daha büyük.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[Kimlik](../standard-library/identity-structure.md)||
|[çifti](../standard-library/pair-structure.md)|İki nesne tek bir nesne olarak davran olanağı sağlayan bir türü.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
