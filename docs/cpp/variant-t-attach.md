---
title: _variant_t::Attach | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _variant_t::Attach
- _variant_t.Attach
dev_langs: C++
helpviewer_keywords:
- Attach method [C++]
- VARIANT object [C++], attach
- VARIANT object
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 893cf8c10fce70645fa42373f08e6b4636e41d11
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [_variant_t sınıfı](../cpp/variant-t-class.md)