---
description: 'Daha fazla bilgi edinin: GetModuleBase İşlevi'
title: GetModuleBase İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: cdedaf905da194400209840b6bd84fa8e626eb0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295204"
---
# <a name="getmodulebase-function"></a>GetModuleBase işlevi

Bir [RuntimeClass](runtimeclass-class.md) nesnesinin başvuru sayısını artırma ve azaltma için izin veren bir [ModuleBase](modulebase-class.md) işaretçisi alır.

## <a name="syntax"></a>Sözdizimi

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>Döndürülen değer

Bir `ModuleBase` nesne işaretçisi.

## <a name="remarks"></a>Açıklamalar

Bu işlev, nesne başvuru sayılarını artırmak ve azaltmak için dahili olarak kullanılır.

Bu işlevi, [ModuleBase:: IncrementObjectCount](modulebase-class.md#incrementobjectcount) ve [modulebase::D ecrementObjectCount](modulebase-class.md#decrementobjectcount)' u çağırarak başvuru sayılarını denetlemek için kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL ad alanı](microsoft-wrl-namespace.md)
