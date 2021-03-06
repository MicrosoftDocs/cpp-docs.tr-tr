---
description: 'Hakkında daha fazla bilgi edinin: _variant_t sınıfı'
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
ms.openlocfilehash: e720d78e6f7fd22fc369d4b39804260892e235c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116619"
---
# <a name="_variant_t-class"></a>_variant_t Sınıfı

**Microsoft'a Özgü**

**_Variant_t** nesnesi, `VARIANT` veri türünü kapsüller. Sınıfı, kaynak ayırmayı ve ayırmayı yönetir ve uygun şekilde işlev çağrıları `VariantInit` yapar `VariantClear` .

### <a name="construction"></a>İnşaat

| Ad | Açıklama |
|--|--|
| [_variant_t](../cpp/variant-t-variant-t.md) | **_Variant_t** nesnesi oluşturur. |

### <a name="operations"></a>İşlemler

| Ad | Açıklama |
|--|--|
| [İliştir](../cpp/variant-t-attach.md) | `VARIANT` **_Variant_t** nesnesine bir nesne iliştirir. |
| [Temizle](../cpp/variant-t-clear.md) | Encapsulated nesneyi temizler `VARIANT` . |
| [ChangeType](../cpp/variant-t-changetype.md) | **_Variant_t** nesnesinin türünü gösterilen şekilde değiştirir `VARTYPE` . |
| [Ayır](../cpp/variant-t-detach.md) | `VARIANT`Bu **_variant_t** nesnesinden kapsüllenmiş nesneyi ayırır. |
| [SetString](../cpp/variant-t-setstring.md) | Bu **_variant_t** nesnesine bir dize atar. |

### <a name="operators"></a>İşleçler

| Ad | Açıklama |
|--|--|
| [İşleç =](../cpp/variant-t-operator-equal.md) | Varolan bir **_variant_t** nesnesine yeni bir değer atar. |
| [işleç = =,! =](../cpp/variant-t-relational-operators.md) | Eşitlik veya eşitsizlik için iki **_variant_t** nesnesini karşılaştırın. |
| [Ayıklayıcıları](../cpp/variant-t-extractors.md) | Encapsulated nesneden veri ayıklayın `VARIANT` . |

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<comutil.h>

**Lib:** comsuppw. lib veya comsuppwd. lib (daha fazla bilgi için bkz. [/zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) )

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM desteği sınıfları](../cpp/compiler-com-support-classes.md)
