---
title: GetModuleBase İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: 4d8c8467b7aeb9c21bf5f4ee19c60e6e60880688
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62398400"
---
# <a name="getmodulebase-function"></a>GetModuleBase işlevi

Alır bir [ModuleBase](modulebase-class.md) işaretçi başvuru sayısını artırma ve azaltma için sağlayan bir [RuntimeClass](runtimeclass-class.md) nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>Dönüş değeri

Bir işaretçi bir `ModuleBase` nesne.

## <a name="remarks"></a>Açıklamalar

Bu işlev artırmak ve azaltma için dahili olarak kullanılır Nesne başvurusu sayar.

Bu işlev çağırarak başvuru sayısı denetlemek için kullanabileceğiniz [Modulebase::ıncrementobjectcount](modulebase-class.md#incrementobjectcount) ve [ModuleBase::DecrementObjectCount](modulebase-class.md#decrementobjectcount).

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)