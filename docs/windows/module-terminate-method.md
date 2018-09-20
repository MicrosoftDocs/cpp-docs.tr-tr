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
ms.openlocfilehash: 76f483c1c57c65c035bcbb0f8c82b4f72cbb06f2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46398736"
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