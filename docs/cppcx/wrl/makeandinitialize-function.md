---
description: 'Daha fazla bilgi edinin: Makeanınvoınitialize Işlevi'
title: MakeAndInitialize İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAndInitialize
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
ms.openlocfilehash: 108da1f19d6956527f06e5239f5ce2e14716d664
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317928"
---
# <a name="makeandinitialize-function"></a>MakeAndInitialize İşlevi

Belirtilen Windows Çalışma Zamanı sınıfını başlatır. Aynı modülde tanımlanmış bir bileşeni örneklemek için bu işlevi kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename T,
    typename I,
    typename TArg1,
    typename TArg2,
    typename TArg3,
    typename TArg4,
    typename TArg5,
    typename TArg6,
    typename TArg7,
    typename TArg8,
    typename TArg9>
HRESULT MakeAndInitialize(
    _Outptr_result_nullonfailure_ I** ppvObject,
    TArg1 &&arg1,
    TArg2 &&arg2,
    TArg3 &&arg3,
    TArg4 &&arg4,
    TArg5 &&arg5,
    TArg6 &&arg6,
    TArg7 &&arg7,
    TArg8 &&arg8,
    TArg9 &&arg9) throw()
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Öğesinden devralan Kullanıcı tarafından belirtilen bir sınıf `WRL::RuntimeClass` .

*TArg1*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 1 türü.

*TArg2*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 2 türü.

*TArg3*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen 3 bağımsız değişkeninin türü.

*TArg4*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen 4 bağımsız değişkeninin türü.

*TArg5*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen 5 bağımsız değişkeninin türü.

*TArg6*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen 6 bağımsız değişkeninin türü.

*TArg7*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen 7 bağımsız değişkeninin türü.

*TArg8*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen 8 bağımsız değişkeninin türü.

*TArg9*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen 9 bağımsız değişkeninin türü.

*arg1*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 1.

*arg2*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 2.

*arg3*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 3.

*arg4*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen 4 bağımsız değişkeni.

*arg5*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 5.

*arg6*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen 6 bağımsız değişkeni.

*arg7*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 7.

*arg8*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 8.

*arg9*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 9.

## <a name="return-value"></a>Dönüş Değeri

HRESULT değeri.

## <a name="remarks"></a>Açıklamalar

Bu işlev ile [Microsoft:: WRL:: Make](make-function.md)arasındaki farklılıkları öğrenmek için bkz. [nasıl yapılır: WRL bileşenlerini doğrudan örnek oluşturma](how-to-instantiate-wrl-components-directly.md) .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** uygular. h

**Ad alanı:** Microsoft:: WRL::D euçlar

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft:: WRL::D euçlar ad alanı](microsoft-wrl-details-namespace.md)
