---
title: RaiseException İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
ms.openlocfilehash: 3270057bf5b1b27a98bef1ab236291eab15d27ab
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213635"
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

*HR*<br/>
Yükseltilen özel durumun özel durum kodu; diğer bir deyişle, başarısız bir işlemin HRESULT.

*dwExceptionFlags*<br/>
Sürekliliği olmayan bir özel durumu (bayrak değeri sıfır) veya kalıcı olmayan özel durum (bayrak değeri sıfır dışında) gösteren bayrak. Varsayılan olarak, özel durum devam ettirilebilir.

## <a name="remarks"></a>Açıklamalar

Çağıran iş parçacığında bir özel durum oluşturur.

Daha fazla bilgi için bkz. Windows `RaiseException` işlevi.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** iç. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL::Details Ad Alanı](microsoft-wrl-details-namespace.md)
