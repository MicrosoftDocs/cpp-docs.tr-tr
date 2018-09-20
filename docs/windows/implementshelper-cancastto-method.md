---
title: Implementshelper::cancastto yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 9ae6fa17-d0b1-4e31-9ae5-da6ae4026e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9487ba4e05a0094d852b0db0c9c39009c027dc9e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46423747"
---
# <a name="implementshelpercancastto-method"></a>ImplementsHelper::CanCastTo Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
HRESULT CanCastTo(
   REFIID riid,
   _Deref_out_ void **ppv
);

HRESULT CanCastTo(
   _In_ const IID &iid,
   _Deref_out_ void **ppv
);
```

### <a name="parameters"></a>Parametreler

*riid*<br/>
Başvuru için bir arabirim kimliği.

*ppv*<br/>
Bu işlem başarılı olursa, arabirim işaretçisi tarafından belirtilen *riid* veya *IID*.

*IID*<br/>
Başvuru için bir arabirim kimliği.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="remarks"></a>Açıklamalar

Belirtilen arabirim kimliği için bir işaretçi alır

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[ImplementsHelper Yapısı](../windows/implementshelper-structure.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)