---
title: _variant_t Sınıfı
ms.date: 11/04/2016
f1_keywords:
- _variant_t
helpviewer_keywords:
- _variant_t class [C++], operators
- _variant_t class
- _variant_t class [C++], member functions
- VARIANT object
- VARIANT object [C++], COM encapsulation
ms.assetid: 6a3cbd4e-0ae8-425e-b4cf-ca0df894c93f
ms.openlocfilehash: e11d31904fd8e54049f69ee4f6530d511c8c7f4e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187758"
---
# <a name="_variant_t-class"></a>_variant_t Sınıfı

**Microsoft 'a özgü**

**_Variant_t** nesne `VARIANT` veri türünü kapsüller. Sınıfı, kaynak ayırmayı ve ayırmayı yönetir ve uygun şekilde `VariantInit` ve `VariantClear` işlev çağrıları yapar.

### <a name="construction"></a>İnşaat

|||
|-|-|
|[_variant_t](../cpp/variant-t-variant-t.md)|**_Variant_t** nesnesi oluşturur.|

### <a name="operations"></a>İşlemler

|||
|-|-|
|[Attach](../cpp/variant-t-attach.md)|**_Variant_t** nesnesine bir `VARIANT` nesnesi ekler.|
|[Lediğiniz](../cpp/variant-t-clear.md)|Encapsulated `VARIANT` nesnesini temizler.|
|[ChangeType](../cpp/variant-t-changetype.md)|**_Variant_t** nesnesinin türünü belirtilen `VARTYPE`değiştirir.|
|[Detach](../cpp/variant-t-detach.md)|Bu **_variant_t** nesnesinden kapsüllenmiş `VARIANT` nesnesini ayırır.|
|[SetString](../cpp/variant-t-setstring.md)|Bu **_variant_t** nesnesine bir dize atar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[İşleç =](../cpp/variant-t-operator-equal.md)|Varolan bir **_variant_t** nesnesine yeni bir değer atar.|
|[işleç = =,! =](../cpp/variant-t-relational-operators.md)|Eşitlik veya eşitsizlik için iki **_variant_t** nesnesini karşılaştırın.|
|[Ayıklayıcıları](../cpp/variant-t-extractors.md)|Encapsulated `VARIANT` nesnesinden veri ayıklayın.|

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<comutil. h >

**Lib:** comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)
