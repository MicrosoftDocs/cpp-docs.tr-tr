---
title: "ActivatableClass makroları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ActivatableClass
- ActivatableClassWithFactory
- ActivatableClassWithFactoryEx
dev_langs: C++
helpviewer_keywords:
- ActivatableClassWithFactory
- ActivatableClass
- ActivatableClassWithFactoryEx
ms.assetid: 9bd64709-ec2c-4678-8c96-ea5982622bdd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6cd75d4075cfe590151f7746281640febb334ce9
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
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

Kullanmadığınız sürece bu makroları klasik COM ile kullanmayın `#undef` emin olmak için yönergesi **&#95; &#95; WRL_WINRT_STRICT &#95; &#95;**  makro tanımı kaldırılır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[Modül sınıfı](../windows/module-class.md)