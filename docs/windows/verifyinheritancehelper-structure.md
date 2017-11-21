---
title: "Verifyınheritancehelper yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::VerifyInheritanceHelper
dev_langs: C++
helpviewer_keywords: VerifyInheritanceHelper structure
ms.assetid: 8a48a702-0f71-4807-935b-8311f0a7a8b6
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 926ed226b67ae510647d2523e4992f6ee3c79a5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="verifyinheritancehelper-structure"></a>VerifyInheritanceHelper Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename I,  
   typename Base  
>  
struct VerifyInheritanceHelper;  
template <  
   typename I  
>  
struct VerifyInheritanceHelper<I, Nil>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `I`  
 Bir tür.  
  
 `Base`  
 Başka bir tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Başka bir arabiriminden bir arabirim türetilmiş olup olmadığını sınar.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Verifyınheritancehelper::Verify yöntemi](../windows/verifyinheritancehelper-verify-method.md)|Geçerli şablon parametrelerle belirtilen iki arabirim sınar ve bir arabirim diğer türetilmiş olup olmadığını belirler.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `VerifyInheritanceHelper`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)