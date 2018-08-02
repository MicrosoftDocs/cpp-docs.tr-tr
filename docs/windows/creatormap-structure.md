---
title: CreatorMap yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreatorMap
- implements/Microsoft::WRL::Details::CreatorMap
dev_langs:
- C++
helpviewer_keywords:
- CreatorMap structure
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fadba5993b7445af2386f6e0669f210e29560c6c
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464262"
---
# <a name="creatormap-structure"></a>CreatorMap Yapısı
Windows çalışma zamanı C++ Şablon kitaplığı altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CreatorMap;  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Nesneleri kaydını başlatmak ve kaydetme hakkında bilgi içerir.  
  
 **CreatorMap** aşağıdaki bilgileri içerir:  
  
-   Başlatma, kaydedin ve nesneleri kaydını nasıl.  
  
-   Klasik COM ya da Windows çalışma zamanı fabrikası bağlı olarak etkinleştirme verileri karşılaştırma yapma.  
  
-   Bir arabirim üreteci önbellek ve sunucu adı hakkında bilgi.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CreatorMap::activationId Veri Üyesi](../windows/creatormap-activationid-data-member.md)|Bir klasik COM sınıfı kimliği veya bir Windows çalışma zamanı adı tanımlanmış bir nesne kimliği temsil eder.|  
|[CreatorMap::factoryCache Veri Üyesi](../windows/creatormap-factorycache-data-member.md)|Üreteci önbellek için yönelik bir işaretçi depolayan **CreatorMap**.|  
|[CreatorMap::factoryCreator Veri Üyesi](../windows/creatormap-factorycreator-data-member.md)|İçin belirtilen bir Üreteç oluşturur **CreatorMap**.|  
|[CreatorMap::serverName Veri Üyesi](../windows/creatormap-servername-data-member.md)|Sunucu adını depolar **CreatorMap**.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CreatorMap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** module.h  
  
 **Namespace:** Microsoft::wrl:: details  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)