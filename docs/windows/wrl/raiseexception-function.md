---
title: RaiseException İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
ms.openlocfilehash: 0a1c661378c4b71378456f2813159b7415cf3fad
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2019
ms.locfileid: "54335223"
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

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)