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
ms.openlocfilehash: 1b50d9ba59ef8aebe4eca388ee30449f4ddd53de
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660674"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Sınıfı](../windows/module-class.md)