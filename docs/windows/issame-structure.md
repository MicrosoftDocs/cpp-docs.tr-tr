---
title: "Issame yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::IsSame
dev_langs: C++
helpviewer_keywords: IsSame structure
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bae4ecb6f03b7b1cdb0fae02f211dd613e7c39d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="issame-structure"></a>IsSame Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename T1,  
   typename T2  
>  
struct IsSame;  
template <  
   typename T1  
>  
struct IsSame<T1, T1>;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T1`  
 Bir tür.  
  
 `T2`  
 Başka bir tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Belirtilen türü testleri bir türü belirtilmiş olup olmadığını başka aynıdır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[IsSame::value Sabiti](../windows/issame-value-constant.md)|Bir tür başka ile aynı olup olmadığını gösterir.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IsSame`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** internal.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)