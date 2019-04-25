---
title: ActivatableClass Makroları
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
ms.openlocfilehash: 7d38db9e7d3fa94c89195b6379e14692f26f7ee5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62304143"
---
# <a name="activatableclass-macros"></a>ActivatableClass Makroları

Belirtilen sınıfın bir örneğini oluşturan bir üreteci içeren bir iç önbelleğe doldurur.

## <a name="syntax"></a>Sözdizimi

```cpp
ActivatableClass(
   className
);

ActivatableClassWithFactory(
   className,
   factory
);

ActivatableClassWithFactoryEx(
   className,
   factory,
   serverName
);
```

### <a name="parameters"></a>Parametreler

*className*<br/>
Oluşturma sınıfı adı.

*Fabrika*<br/>
Belirtilen sınıfın bir örneğini oluşturan üreteci.

*SunucuAdı*<br/>
Modülde üreteçleri kümesini belirten bir ad.

## <a name="remarks"></a>Açıklamalar

Kullandığınız sürece bu makrolar ile klasik COM kullanmayın `#undef` emin olmak için yönergesi `__WRL_WINRT_STRICT__` Makro tanımında kaldırılır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca bkz.

[Modül Sınıfı](module-class.md)