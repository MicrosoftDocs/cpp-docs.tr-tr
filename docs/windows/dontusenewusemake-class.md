---
title: "DontUseNewUseMake sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs: C++
helpviewer_keywords: DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 62f8abc151758ac9253698390cbab3e2ba62a4c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake Sınıfı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class DontUseNewUseMake;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 İşleç engel `new` RuntimeClass içinde. Sonuç olarak, kullanmalısınız [olun işlevi](../windows/make-function.md) yerine.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[DontUseNewUseMake::operator new işleci](../windows/dontusenewusemake-operator-new-operator.md)|İşleç aşırı yüklemeler `new` ve RuntimeClass içinde kullanılan engeller.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `DontUseNewUseMake`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)   
 [Make işlevi](../windows/make-function.md)