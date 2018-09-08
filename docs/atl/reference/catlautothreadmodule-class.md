---
title: CAtlAutoThreadModule sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b534190a4e7243f5192e6d703b056d8bcb327ca
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110649"
---
# <a name="catlautothreadmodule-class"></a>CAtlAutoThreadModule sınıfı

Bu sınıf, apartman modeli iş parçacığı havuza, COM sunucu uygular.

> [!IMPORTANT]
> Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```

## <a name="remarks"></a>Açıklamalar

`CAtlAutoThreadModule` öğesinden türetilen [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) ve apartman modeli iş parçacığı havuza, COM sunucu uygular. `CAtlAutoThreadModule` kullanan [CComApartment](../../atl/reference/ccomapartment-class.md) modüldeki her bir iş parçacığı için bir grup yönetmek için.

Kullanmalısınız [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) makrosu belirtmek için nesnenin sınıf tanımında [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) sınıf üreteci olarak. Ardından tek bir türetilen bir sınıf örneği eklemelisiniz `CAtlAutoThreadModuleT` gibi `CAtlAutoThreadModule`. Örneğin:

`CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`

> [!NOTE]
> Bu sınıf artık kullanılmıyor değiştirir [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) sınıfı.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlAutoThreadModule`

[CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)

`CAtlAutoThreadModule`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

## <a name="see-also"></a>Ayrıca Bkz.

[CAtlAutoThreadModuleT sınıfı](../../atl/reference/catlautothreadmodulet-class.md)   
[Iatlautothreadmodule sınıfı](../../atl/reference/iatlautothreadmodule-class.md)   
[Sınıfına genel bakış](../../atl/atl-class-overview.md)   
[Modül sınıfları](../../atl/atl-module-classes.md)
