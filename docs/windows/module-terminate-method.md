---
title: Module::Terminate yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::Terminate
dev_langs:
- C++
helpviewer_keywords:
- Terminate method
ms.assetid: cf358117-45dc-43c7-ac1e-1e1eedc59e41
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7f89922fb107c1454ec81dfd8a9ac213608da962
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42610849"
---
# <a name="moduleterminate-method"></a>Module::Terminate Yöntemi

Kapatmak için modülü tarafından oluşturulan tüm fabrikaları neden olur.

## <a name="syntax"></a>Sözdizimi

```cpp
void Terminate();
```

## <a name="remarks"></a>Açıklamalar

Önbellek Fabrikalar serbest bırakır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** module.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.
[Modül Sınıfı](../windows/module-class.md)