---
title: GetModuleBase İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: 0d130fffa9fad9ae327d03eaa01d84742094cc67
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213973"
---
# <a name="getmodulebase-function"></a>GetModuleBase işlevi

Bir [RuntimeClass](runtimeclass-class.md) nesnesinin başvuru sayısını artırma ve azaltma için izin veren bir [ModuleBase](modulebase-class.md) işaretçisi alır.

## <a name="syntax"></a>Sözdizimi

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>Dönüş değeri

`ModuleBase` nesnesine yönelik bir işaretçi.

## <a name="remarks"></a>Açıklamalar

Bu işlev, nesne başvuru sayılarını artırmak ve azaltmak için dahili olarak kullanılır.

Bu işlevi, [ModuleBase:: IncrementObjectCount](modulebase-class.md#incrementobjectcount) ve [modulebase::D ecrementObjectCount](modulebase-class.md#decrementobjectcount)' u çağırarak başvuru sayılarını denetlemek için kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)
