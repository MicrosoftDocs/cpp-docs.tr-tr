---
title: "CreatorMap yapısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
dev_langs: C++
helpviewer_keywords: CreatorMap structure
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c61238a809da49686975acbfb8016996cf5d5c1a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|[Creatormap::activationıd veri üyesi](../windows/creatormap-activationid-data-member.md)|Bir klasik COM sınıfı kimliği veya bir Windows çalışma zamanı adı tarafından tanımlanan bir nesne kimliği temsil eder.|  
|[CreatorMap::factoryCache veri üyesi](../windows/creatormap-factorycache-data-member.md)|Fabrika önbellek işaretçisine CreatorMap için depolar.|  
|[CreatorMap::factoryCreator veri üyesi](../windows/creatormap-factorycreator-data-member.md)|Belirtilen CreatorMap için bir üreteci oluşturur.|  
|[CreatorMap::serverName veri üyesi](../windows/creatormap-servername-data-member.md)|CreatorMap için sunucu adını depolar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CreatorMap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::wrl:: details Namespace](../windows/microsoft-wrl-details-namespace.md)