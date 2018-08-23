---
title: ComPtr::Attach yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::Attach
dev_langs:
- C++
helpviewer_keywords:
- Attach method
ms.assetid: 5b911f2d-9830-4dc7-b9e3-527abd55d2c8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f02d8585778dcb10013a5673c7443b0355535555
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42600202"
---
# <a name="comptrattach-method"></a>ComPtr::Attach Yöntemi

Bu ilişkilendirir **ComPtr** geçerli bir şablon türü parametresi tarafından belirtilen arabirim türüne sahip.

## <a name="syntax"></a>Sözdizimi

```cpp
void Attach(
   _In_opt_ InterfaceType* other
);
```

### <a name="parameters"></a>Parametreler

*Diğer*  
Bir arabirim türü.

## <a name="requirements"></a>Gereksinimler

**Başlık:** client.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca Bkz.

[ComPtr Sınıfı](../windows/comptr-class.md)