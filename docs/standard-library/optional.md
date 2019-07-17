---
title: '&lt;optional&gt;'
ms.date: 11/04/2016
f1_keywords:
- <optional>
helpviewer_keywords:
- <optional>
ms.assetid: 8b4ab09e-1475-434a-b4e0-fdbc07a08b5b
ms.openlocfilehash: c73ad2ad94a5de29bc2c457fdf6ca8b9c783615c
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68267900"
---
# <a name="ltoptionalgt"></a>&lt;optional&gt;

İsteğe bağlı kapsayıcı Şablon sınıfı ve çeşitli destek şablonları tanımlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<isteğe bağlı >

**Namespace:** std

## <a name="members"></a>Üyeler

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator==](../standard-library/optional-operators.md#op_eq_eq)|Olmadığını test eder `optional` işlecin sol tarafındaki nesnesinin eşit olup `optional` işlecin sağ tarafındaki nesne.|
|[operator!=](../standard-library/optional-operators.md#op_neq)|Olmadığını test eder `optional` işlecinin sol tarafındaki nesnesi eşit değil `optional` işlecin sağ tarafındaki nesne.|
|[işleç <](../standard-library/optional-operators.md#op_lt)|Olmadığını test eder `optional` nesne işlecinin sol tarafındaki küçüktür `optional` işlecin sağ tarafındaki nesne.|
|[operator < =](../standard-library/optional-operators.md#op_lt_eq)|Olmadığını test eder `optional` işlecin sol tarafındaki nesnesinin değerinden küçük veya buna eşit olup `optional` işlecin sağ tarafındaki nesne.|
|[operator >](../standard-library/optional-operators.md#op_gt)|Olmadığını test eder `optional` nesne işlecinin sol tarafındaki büyük `optional` işlecin sağ tarafındaki nesne.|
|[operator>=](../standard-library/optional-operators.md#op_lt_eq)|Olmadığını test eder `optional` işlecin sol tarafındaki nesnesinin değerinden büyük veya ona eşit olup `optional` işlecin sağ tarafındaki nesne.|

> [!NOTE]
> İlişkisel karşılaştırır yanı sıra \<isteğe bağlı > işleçleri de destekler karşılaştırma **nullopt** ve `T`.

### <a name="functions"></a>İşlevler

|||
|-|-|
|[make_optional](../standard-library/optional-functions.md#make_optional)|Bir nesnenin isteğe bağlı hale getirir.|
|[değiştirme](../standard-library/optional-functions.md#swap)||

### <a name="classes-and-structs"></a>Sınıflar ve Yapılar

|||
|-|-|
|[Karma]()||
|[İsteğe bağlı sınıfı](../standard-library/optional-class.md)|Değer tutan değil veya bir nesneyi tanımlar.|
|[nullopt_t yapısı](../standard-library/nullopt-t-structure.md)|Bir değer değil basılı tutarak bir nesneyi tanımlar.|
|[bad_optional_access sınıfı](../standard-library/bad-optional-access-class.md)|Bir değer var. erişemezler girişimi bildirmek için bir özel durum bir nesneyi tanımlar.|

### <a name="objects"></a>Nesneler

|||
|-|-|
|[nullopt](../standard-library/optional-functions.md#nullopt)||

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
