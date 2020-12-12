---
description: 'Daha fazla bilgi edinin: ActivatableClass makroları'
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
ms.openlocfilehash: 2b59101373de72ca88338750bb7fe9169376ac65
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287950"
---
# <a name="activatableclass-macros"></a>ActivatableClass Makroları

Belirtilen sınıfın bir örneğini oluşturabileceğiniz bir fabrika içeren bir iç önbelleği doldurur.

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

*Sınıf*<br/>
Oluşturulacak sınıfın adı.

*Çar*<br/>
Belirtilen sınıf örneğini oluşturacak fabrika.

*serverName*<br/>
Modüldeki fabrikaların bir alt kümesini belirten ad.

## <a name="remarks"></a>Açıklamalar

`#undef`Makro tanımının kaldırılmasını sağlamak için yönergesini kullanmadığınız takdirde bu makroları klasık com ile kullanmayın `__WRL_WINRT_STRICT__` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Module sınıfı](module-class.md)
