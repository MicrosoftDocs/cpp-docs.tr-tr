---
description: 'Daha fazla bilgi edinin: ATL genel değişkenleri'
title: ATL Genel Değişkenler
ms.date: 12/06/2017
f1_keywords:
- ATLBASE/_pAtlModule
helpviewer_keywords:
- global variables, ATL
- _pAtlModule
ms.assetid: e881a319-99ca-4f5d-8a0b-34b3dcd0f37f
ms.openlocfilehash: 8d0544651e32f5e569973466af8ce04af1433766
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97158783"
---
# <a name="atl-global-variables"></a>ATL Genel Değişkenler

## <a name="_patlmodule"></a>_pAtlModule

Geçerli modüle bir işaretçi depolayan genel bir değişken.

```cpp
__declspec(selectany) CAtlModule * _pAtlModule
```

### <a name="remarks"></a>Açıklamalar

Bu genel değişkende Yöntemler, Visual C++ 6,0 ' de sağlanmış olan CComModule sınıfının işlevlerini sağlamak için kullanılabilir.

### <a name="example"></a>Örnek

```cpp
LONG lLocks = _pAtlModule->GetLockCount();
```

### <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h
