---
title: GetModuleBase işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
dev_langs:
- C++
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4d460b006d2d17df308a62c0433621aac7008f4d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411423"
---
# <a name="getmodulebase-function"></a>GetModuleBase İşlevi
Alır bir [ModuleBase](../windows/modulebase-class.md) işaretçi başvuru sayısını artırma ve azaltma için sağlayan bir [RuntimeClass](../windows/runtimeclass-class.md) nesne.
  
## <a name="syntax"></a>Sözdizimi
  
```cpp
inline Details::ModuleBase* GetModuleBase() throw()  
```
  
## <a name="return-value"></a>Dönüş Değeri

Bir işaretçi bir `ModuleBase` nesne.
  
## <a name="remarks"></a>Açıklamalar

Bu işlev artırmak ve azaltma için dahili olarak kullanılır Nesne başvurusu sayar.
  
Bu işlev çağırarak başvuru sayısı denetlemek için kullanabileceğiniz [Modulebase::ıncrementobjectcount](../windows/modulebase-incrementobjectcount-method.md) ve [ModuleBase::DecrementObjectCount](../windows/modulebase-decrementobjectcount-method.md).
  
## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h
  
**Namespace:** Microsoft::WRL
  
## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL Ad Alanı](../windows/microsoft-wrl-namespace.md)