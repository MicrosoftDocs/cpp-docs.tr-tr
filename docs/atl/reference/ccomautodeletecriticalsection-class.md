---
title: "CComAutoDeleteCriticalSection sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d0a0c5fdd45e819105a3f47e98c02bb5ad3d51be
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection sınıfı
Bu sınıf, alma ve kritik bölüm nesnenin sahipliğini serbest bırakma için yöntemleri sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>Açıklamalar  
 `CComAutoDeleteCriticalSection`sınıfından türetilen [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md). Ancak, `CComAutoDeleteCriticalSection` geçersiz kılmaları [terim](ccomsafedeletecriticalsection-class.md#term) yönteme `private` yalnızca bu sınıfın örnekleri, kapsam dışı gidin veya bellekten açıkça silinir gerçekleşmesi için iç bellek temizleme zorlar erişim.  

  
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
