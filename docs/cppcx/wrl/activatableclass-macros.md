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
ms.openlocfilehash: 7bc3d789d6c0d304aa170d59dff23a97a67061d7
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80214297"
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

`__WRL_WINRT_STRICT__` makro tanımının kaldırıldığından emin olmak için `#undef` yönergesini kullanmadığınız durumlar dışında bu makroları klasik COM ile kullanmayın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Module. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Modül Sınıfı](module-class.md)
