---
title: "CAtlAutoThreadModule sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
dev_langs: C++
helpviewer_keywords: CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ceff548fe53ff317eaca432a5e0c223cdc0a4e6d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="catlautothreadmodule-class"></a>CAtlAutoThreadModule sınıfı
Bu sınıf, bir iş parçacığı havuza, modeli COM sunucusu uygular.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```  
  
## <a name="remarks"></a>Açıklamalar  
 `CAtlAutoThreadModule`türetilen [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) ve iş parçacığı havuza, modeli bir COM sunucusu uygular. `CAtlAutoThreadModule`kullanan [CComApartment](../../atl/reference/ccomapartment-class.md) modüldeki her bir iş parçacığı için bir grup yönetmek için.  
  
 Kullanmalısınız [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) belirtmek için nesnenin sınıf tanımında makrosu [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) üreteci olarak. Türetilmiş bir sınıf tek bir örneğini sonra eklemelisiniz `CAtlAutoThreadModuleT` gibi `CAtlAutoThreadModule`. Örneğin:  
  
 `CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`  
  
> [!NOTE]
>  Bu sınıf artık kullanılmıyor değiştirir [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) sınıfı.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IAtlAutoThreadModule`  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 `CAtlAutoThreadModule`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlbase.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CAtlAutoThreadModuleT sınıfı](../../atl/reference/catlautothreadmodulet-class.md)   
 [IAtlAutoThreadModule sınıfı](../../atl/reference/iatlautothreadmodule-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Modül sınıfları](../../atl/atl-module-classes.md)
