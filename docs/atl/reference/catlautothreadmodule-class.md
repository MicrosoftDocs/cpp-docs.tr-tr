---
title: CAtlAutoThreadModule sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
ms.openlocfilehash: 1ec66bf77d8dd705cb2e1e93f70a885ab96420a6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247304"
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

## <a name="see-also"></a>Ayrıca bkz.

[CAtlAutoThreadModuleT Sınıfı](../../atl/reference/catlautothreadmodulet-class.md)<br/>
[IAtlAutoThreadModule Sınıfı](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
