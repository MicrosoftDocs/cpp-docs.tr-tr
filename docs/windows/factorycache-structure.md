---
title: "FactoryCache yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::FactoryCache
dev_langs: C++
helpviewer_keywords: FactoryCache structure
ms.assetid: 624544e6-0989-47f6-a3e9-edb60e1ee6d4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0fc48c9a3651e8c5a6609886862c2f73c5707638
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="factorycache-structure"></a>FactoryCache Yapısı
Windows çalışma zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct FactoryCache;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bir sınıf fabrikası wrt kayıtlı tanımlayan bir değer veya COM sınıf nesnesi konumunu içerir.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[FactoryCache::cookie Veri Üyesi](../windows/factorycache-cookie-data-member.md)|Kayıtlı Windows çalışma zamanı veya COM sınıf nesnesi tanımlar ve daha sonra nesne kaydını silmek için kullanılan bir değer içeriyor.|  
|[FactoryCache::factory Veri Üyesi](../windows/factorycache-factory-data-member.md)|Windows çalışma zamanı veya COM üreteci noktalarına.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `FactoryCache`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)