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
ms.openlocfilehash: aeb68deddd1cdfa9e1e869a08bfb0a1f3bb8d6ca
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33857470"
---
# <a name="activatableclass-macros"></a>ActivatableClass Makroları

Belirtilen sınıfının bir örneğini oluşturabilirsiniz bir Fabrika içeren bir iç önbelleğe doldurur.

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
Oluşturmak için sınıfı adı.  

*Fabrika*  
Belirtilen sınıfının bir örneğini oluşturacak üreteci.

*serverName*  
Modül üreteçleri kümesini belirtir adı.

## <a name="remarks"></a>Açıklamalar

Kullanmadığınız sürece bu makroları klasik COM ile kullanmayın `#undef` emin olmak için yönergesi **&#95; &#95;WRL_WINRT_STRICT&#95; &#95;** makro tanımı kaldırılır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Modül Sınıfı](../windows/module-class.md)