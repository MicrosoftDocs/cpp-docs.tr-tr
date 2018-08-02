---
title: ActivatableClass makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
dev_langs:
- C++
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e46063bc94fae25d414d25ae67b5418ee5aa8c27
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465863"
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

*className*  
Oluşturma sınıfı adı.  

*Fabrika*  
Belirtilen sınıfın bir örneğini oluşturan üreteci.

*SunucuAdı*  
Modülde üreteçleri kümesini belirten bir ad.

## <a name="remarks"></a>Açıklamalar

Kullandığınız sürece bu makrolar ile klasik COM kullanmayın `#undef` emin olmak için yönergesi **&#95; &#95;WRL_WINRT_STRICT&#95; &#95;** Makro tanımında kaldırılır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.
[Modül Sınıfı](../windows/module-class.md)