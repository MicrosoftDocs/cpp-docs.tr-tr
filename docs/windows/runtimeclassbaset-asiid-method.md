---
title: Runtimeclassbaset::asııd yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7092153e49fdb40fc32fb1cbee5bc2376080ff4e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46391884"
---
# <a name="runtimeclassbasetasiid-method"></a>RuntimeClassBaseT::AsIID Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename T>
__forceinline static HRESULT AsIID(
   _In_ T* implements,
   REFIID riid,
   _Deref_out_ void **ppvObject
);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Parametresi tarafından belirtilen arabirim kimliği uygulayan bir tür *riid*.

*Uygulayan*<br/>
Şablon parametresi tarafından belirtilen türde bir değişken *T*.

*riid*<br/>
Alınacak arabirim kimliği.

*ppvObject*<br/>
Bu işlem başarılı olursa, bir işaretçi bir-işaretçiye arabirimi için belirtilen parametre tarafından *riid*.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, hatayı açıklayan bir HRESULT.

## <a name="remarks"></a>Açıklamalar

Belirtilen arabirim kimliği. bir işaretçi alır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[RuntimeClassBaseT Yapısı](../windows/runtimeclassbaset-structure.md)<br/>
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)