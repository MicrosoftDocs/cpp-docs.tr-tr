---
title: RaiseException işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
dev_langs:
- C++
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 12032318f898b2986b64d5cd8a1e611a31d1fc8c
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372398"
---
# <a name="raiseexception-function"></a>RaiseException İşlevi

WRL altyapısını destekler ve doğrudan kodunuzdan kullanılmaya yönelik değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
inline void __declspec(noreturn)   RaiseException(
      HRESULT hr,
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);
```

### <a name="parameters"></a>Parametreler

*İK*<br/>
Özel durum kodu gerçekleştirilen özel durum; diğer bir deyişle, başarısız bir işlemin HRESULT.

*dwExceptionFlags*<br/>
(Bayrak değeri sıfırdır) devam ettirilebilir özel durum ya da (bayrak değeri sıfır dışında) noncontinuable özel durumu gösteren bir bayrak. Varsayılan olarak, özel durum oluştuktan ' dir.

## <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığında bir özel durum oluşturur.

Daha fazla bilgi için bkz. Windows `RaiseException` işlevi.

## <a name="requirements"></a>Gereksinimler

**Başlık:** internal.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)