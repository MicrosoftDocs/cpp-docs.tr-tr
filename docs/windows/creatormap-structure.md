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
ms.openlocfilehash: a6113737d7463354ffa273ced61b190246f63a83
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873290"
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