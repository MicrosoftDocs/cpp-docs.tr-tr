---
description: 'Daha fazla bilgi edinin: CAtlAutoThreadModule sınıfı'
title: CAtlAutoThreadModule sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
ms.openlocfilehash: d1742488cca84dccfa53753bec40f9081d77f67d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97165062"
---
# <a name="catlautothreadmodule-class"></a>CAtlAutoThreadModule sınıfı

Bu sınıf, bir iş parçacığı havuza alınmış, Apartman modeli COM sunucusu uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```cpp
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```

## <a name="remarks"></a>Açıklamalar

`CAtlAutoThreadModule`[Catlautothreadmodület](../../atl/reference/catlautothreadmodulet-class.md) öğesinden türetilir ve iş parçacığı havuza alınmış, Apartman modeli com sunucusu uygular. `CAtlAutoThreadModule` modüldeki her iş parçacığı için bir grubu yönetmek üzere [CComApartment](../../atl/reference/ccomapartment-class.md) kullanır.

Sınıf fabrikası olarak [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) belirtmek için, nesnenizin sınıf tanımındaki [declare_classfactory_auto_thread](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) makrosunu kullanmanız gerekir. Daha sonra, gibi türetilmiş bir sınıfın tek bir örneğini eklemeniz gerekir `CAtlAutoThreadModuleT` `CAtlAutoThreadModule` . Örneğin:

`CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`

> [!NOTE]
> Bu sınıf, eski [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) sınıfının yerini alır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlAutoThreadModule`

[Catlautothreadmodület](../../atl/reference/catlautothreadmodulet-class.md)

`CAtlAutoThreadModule`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="see-also"></a>Ayrıca bkz.

[Catlautothreadmodület sınıfı](../../atl/reference/catlautothreadmodulet-class.md)<br/>
[IAtlAutoThreadModule sınıfı](../../atl/reference/iatlautothreadmodule-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[Modül sınıfları](../../atl/atl-module-classes.md)
