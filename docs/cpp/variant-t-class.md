---
title: _variant_t sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t
dev_langs:
- C++
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dd9e7347b1ba85f34587b3ce9e94963efb23efd8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110633"
---
# <a name="variantt-class"></a>_variant_t Sınıfı

**Microsoft'a özgü**

A **_variant_t** kapsülleyen nesne `VARIANT` veri türü. Sınıf kaynak ayırmayı ve ayırmayı yönetir ve işlev çağrıları yapan `VariantInit` ve `VariantClear` uygun şekilde.

### <a name="construction"></a>Oluşturma

|||
|-|-|
|[_variant_t](../cpp/variant-t-variant-t.md)|Oluşturur bir **_variant_t** nesne.|

### <a name="operations"></a>İşlemler

|||
|-|-|
|[Attach](../cpp/variant-t-attach.md)|Bağlanan bir `VARIANT` içine nesne **_variant_t** nesne.|
|[Temizle](../cpp/variant-t-clear.md)|Kapsüllenmiş temizler `VARIANT` nesne.|
|[ChangeType](../cpp/variant-t-changetype.md)|Değişiklikleri türde **_variant_t** belirtilen nesneye `VARTYPE`.|
|[Detach](../cpp/variant-t-detach.md)|Kapsüllenmiş ayırır `VARIANT` bu nesneden **_variant_t** nesne.|
|[SetString](../cpp/variant-t-setstring.md)|Bir dize için atar **_variant_t** nesne.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleç =](../cpp/variant-t-operator-equal.md)|Mevcut bir yeni bir değer atar **_variant_t** nesne.|
|[işleç ==,! =](../cpp/variant-t-relational-operators.md)|Karşılaştırabilirsiniz **_variant_t** eşitlik ve eşitsizlik için nesneleri.|
|[Ayıklayıcıları](../cpp/variant-t-extractors.md)|Kapsüllenmiş verileri ayıklamak `VARIANT` nesne.|

**END Microsoft özgü**

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<comutil.h >

**Lib:** comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)