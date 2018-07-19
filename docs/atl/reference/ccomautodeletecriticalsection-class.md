---
title: CComAutoDeleteCriticalSection sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8b90afb9ae47ced33c331aef988489b567b1078b
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/06/2018
ms.locfileid: "37879908"
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection sınıfı
Bu sınıf, alma ve kritik bölüm nesnenin sahipliğini serbest için yöntemler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>Açıklamalar  
 `CComAutoDeleteCriticalSection` sınıfından türetilen [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md). Ancak, `CComAutoDeleteCriticalSection` geçersiz kılmalar [terimi](ccomsafedeletecriticalsection-class.md#term) yönteme **özel** erişim, yalnızca bu sınıfın örneklerinin kapsam dışına çıkmadan veya açıkça silinir gerçekleşmesi için iç bellek temizleme zorlar bellek.  

  
 Bu sınıf, taban sınıfı hiçbir ek yöntemleri tanıtır. Bkz: [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) ve [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) kritik bölüm yardımcı sınıfları hakkında daha fazla bilgi için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComSafeDeleteCriticalSection sınıfı](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 [CComCriticalSection sınıfı](../../atl/reference/ccomcriticalsection-class.md)   
 [Sınıfına genel bakış](../../atl/atl-class-overview.md)
