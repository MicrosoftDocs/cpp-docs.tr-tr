---
title: GetModuleBase İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: 40289903eba2ce7ac35d4d0b208c3b609efb09f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650820"
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