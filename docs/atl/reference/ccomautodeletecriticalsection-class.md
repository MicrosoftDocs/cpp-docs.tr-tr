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
ms.openlocfilehash: c5153520b5a5648f8352465031264c223ffd97c4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection sınıfı
Bu sınıf, alma ve kritik bölüm nesnenin sahipliğini serbest bırakma için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>Açıklamalar  
 `CComAutoDeleteCriticalSection` sınıfından türetilen [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md). Ancak, `CComAutoDeleteCriticalSection` geçersiz kılmaları [terim](ccomsafedeletecriticalsection-class.md#term) yönteme `private` yalnızca bu sınıfın örnekleri, kapsam dışı gidin veya bellekten açıkça silinir gerçekleşmesi için iç bellek temizleme zorlar erişim.  

  
 Bu sınıf kendi temel sınıfının hiçbir ek yöntemleri sunar. Bkz: [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) ve [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) kritik bölüm yardımcı sınıfları hakkında daha fazla bilgi için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcore.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CComSafeDeleteCriticalSection sınıfı](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 [CComCriticalSection sınıfı](../../atl/reference/ccomcriticalsection-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
