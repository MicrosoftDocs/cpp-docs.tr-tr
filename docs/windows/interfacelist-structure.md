---
title: "Interfacelist yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceList
dev_langs:
- C++
helpviewer_keywords:
- InterfaceList structure
ms.assetid: 6ec3228d-eb3e-4b7e-aef1-7dcf17bdf61a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: def0a79556d74616d153a97ee5a0cc9f521944ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="interfacelist-structure"></a>InterfaceList Yapısı
WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <  
   typename T,  
   typename U  
>  
struct InterfaceList;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Arabirim adı; özyinelemeli listesindeki ilk arabirimi.  
  
 `U`  
 Arabirim adı; özyinelemeli listesinde kalan arabirimleri.  
  
## <a name="remarks"></a>Açıklamalar  
 Arabirimleri özyinelemeli listesini oluşturmak için kullanılır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`FirstT`|Şablon parametresi için eş anlamlı `T`.|  
|`RestT`|Şablon parametresi için eş anlamlı `U`.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `InterfaceList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** implements.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)