---
title: RaiseException İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
ms.openlocfilehash: 08305c5d59d7e272aac87ad9aa183c8e82588632
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62231359"
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

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)