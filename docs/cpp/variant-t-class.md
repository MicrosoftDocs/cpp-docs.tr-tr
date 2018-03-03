---
title: "_variant_t sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 57a4d7e4019e742ff8adc50bb78a926dff34d55a
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/25/2018
---
# <a name="variantt-class"></a>_variant_t Sınıfı
**Microsoft Specific**  
  
 A `_variant_t` nesne yalıtır `VARIANT` veri türü. Sınıf kaynak ayırma ve ayırmayı kaldırma yönetir ve işlev çağrıları yapan **VariantInit** ve **VariantClear** uygun şekilde.  
  
### <a name="construction"></a>Yapı  
  
|||  
|-|-|  
|[_variant_t](../cpp/variant-t-variant-t.md)|Oluşturan bir `_variant_t` nesnesi.|  
  
### <a name="operations"></a>İşlemler  
  
|||  
|-|-|  
|[Attach](../cpp/variant-t-attach.md)|Bağlayan bir **değişken** içine nesne `_variant_t` nesne.|  
|[Temizle](../cpp/variant-t-clear.md)|Kapsüllenmiş temizler **değişken** nesnesi.|  
|[ChangeType](../cpp/variant-t-changetype.md)|Türünü değiştirir `_variant_t` belirtilen nesneye **VARTYPE**.|  
|[Detach](../cpp/variant-t-detach.md)|Kapsüllenmiş ayırır **değişken** bu nesneden `_variant_t` nesnesi.|  
|[SetString](../cpp/variant-t-setstring.md)|Bir dize için atar `_variant_t` nesnesi.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[İşleç =](../cpp/variant-t-operator-equal.md)|Var olan yeni bir değer atar `_variant_t` nesnesi.|  
|[operator ==,! =](../cpp/variant-t-relational-operators.md)|İki karşılaştırmak `_variant_t` nesneleri eşitlik veya eşitsizlik.|  
|[Ayıklayıcıları](../cpp/variant-t-extractors.md)|Veri kapsüllenmiş ayıklamak **değişken** nesnesi.|  
  
**SON Microsoft özel**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<comutil.h >  
  
 **LIB:** comsuppw.lib veya comsuppwd.lib (bkz [/ZC: wchar_t (wchar_t yerel tür olan)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) daha fazla bilgi için)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici COM Desteği Sınıfları](../cpp/compiler-com-support-classes.md)