---
title: WeakReference::Resolve yöntemi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::Resolve
dev_langs:
- C++
helpviewer_keywords:
- Resolve method
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59e748ef68d78f9cb77eb335f5c5cd44e058f0d4
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601162"
---
# <a name="weakreferenceresolve-method"></a>WeakReference::Resolve Yöntemi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
STDMETHOD(Resolve)  
   (REFIID riid,
   _Deref_out_opt_ IInspectable **ppvObject
);
```

### <a name="parameters"></a>Parametreler

*riid*  
Bir arabirim kimliği.

*ppvObject*  
Bu işlem tamamlandığında bir kopyasını güçlü başvuru sayısı sıfır değilse geçerli güçlü başvuru.

## <a name="return-value"></a>Dönüş Değeri

- Bu işlem başarılı olursa S_OK ve güçlü başvuru sayısı sıfır olan. *PpvObject* parametrenin ayarlanmış **nullptr**.

- Bu işlem başarılı olursa S_OK ve güçlü başvuru sayısı sıfır. *PpvObject* parametre güçlü başvuru.

- Aksi takdirde, nedenini belirten bir HRESULT, bu işlem başarısız oldu.

## <a name="remarks"></a>Açıklamalar

Güçlü Başvuru sayısı sıfır değilse belirtilen işaretçi geçerli güçlü başvuru değerine ayarlar.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[WeakReference Sınıfı1](../windows/weakreference-class1.md)  
[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)