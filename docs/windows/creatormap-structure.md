---
title: "CreatorMap yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
dev_langs:
- C++
helpviewer_keywords:
- CreatorMap structure
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a941f052527b3617772bcb18b2092fdc35ea3a22
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="creatormap-structure"></a>CreatorMap Yapısı
Windows çalışma zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CreatorMap;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Başlatma, kaydetme ve nesneleri kaydı hakkında bilgi içerir.  
  
 CreatorMap aşağıdaki bilgileri içerir:  
  
-   Nasıl başlatmak, kaydetme ve nesneleri kaydını silin.  
  
-   Klasik COM ya da Windows çalışma zamanı fabrikası bağlı olarak etkinleştirme verileri karşılaştırmak nasıl.  
  
-   Bir arabirim için Fabrika önbellek ve sunucu adı hakkında bilgiler.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CreatorMap::activationId Veri Üyesi](../windows/creatormap-activationid-data-member.md)|Bir klasik COM sınıfı kimliği veya bir Windows çalışma zamanı adı tarafından tanımlanan bir nesne kimliği temsil eder.|  
|[CreatorMap::factoryCache Veri Üyesi](../windows/creatormap-factorycache-data-member.md)|Fabrika önbellek işaretçisine CreatorMap için depolar.|  
|[CreatorMap::factoryCreator Veri Üyesi](../windows/creatormap-factorycreator-data-member.md)|Belirtilen CreatorMap için bir üreteci oluşturur.|  
|[CreatorMap::serverName Veri Üyesi](../windows/creatormap-servername-data-member.md)|CreatorMap için sunucu adını depolar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CreatorMap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)