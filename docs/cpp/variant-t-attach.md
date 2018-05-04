---
title: _variant_t::Attach | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93c4ec0b4d25f1ca0ec03d9aae1dd9e1c16b79a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="varianttattach"></a>_variant_t::Attach
**Microsoft özel**  
  
 Bağlayan bir **değişken** içine nesne `_variant_t` nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *varSrc*  
 A **değişken** için eklenecek nesne `_variant_t` nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 Sahipliğini **değişken** , şifrelenmiş olarak. Bu üye işlevi kapsüllenmiş var olan serbest **değişken**, sağlanan kopyalar **değişken**ve ayarlar kendi **VARTYPE** için `VT_EMPTY` emin olmak için kaynaklar yalnızca değiştirilerek serbest bırakılabilir `_variant_t` yıkıcı.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_variant_t Sınıfı](../cpp/variant-t-class.md)