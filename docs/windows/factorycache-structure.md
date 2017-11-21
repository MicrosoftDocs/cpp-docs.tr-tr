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
ms.openlocfilehash: fbb6b32fbd34794c13d2f4b7dc75e242464bc7b9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[FactoryCache::cookie veri üyesi](../windows/factorycache-cookie-data-member.md)|Kayıtlı Windows çalışma zamanı veya COM sınıf nesnesi tanımlar ve daha sonra nesne kaydını silmek için kullanılan bir değer içeriyor.|  
|[FactoryCache::factory veri üyesi](../windows/factorycache-factory-data-member.md)|Windows çalışma zamanı veya COM üreteci noktalarına.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `FactoryCache`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)