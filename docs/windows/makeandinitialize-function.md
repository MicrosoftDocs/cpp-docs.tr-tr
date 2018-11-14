---
title: MakeAndInitialize İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAndInitialize
ms.assetid: 71ceeb12-d2a2-4317-b010-3dcde1b39467
ms.openlocfilehash: 4dbcd208acb52522c24f1cc442e2cc1908b51502
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51332289"
---
# <a name="makeandinitialize-function"></a>MakeAndInitialize İşlevi

Belirtilen Windows çalışma zamanı sınıf başlatır. Aynı modülde tanımlanmış bir bileşeni oluşturmak için bu işlevi kullanın.

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
Devralınan bir kullanıcı tarafından belirtilen sınıf `WRL::RuntimeClass`.

*TArg1*<br/>
1 ' belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken türü.

*TArg2*<br/>
2 ' belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken türü.

*TArg3*<br/>
3 ' belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken türü.

*TArg4*<br/>
4 ' belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken türü.

*TArg5*<br/>
5 ' belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken türü.

*TArg6*<br/>
6 ' belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken türü.

*TArg7*<br/>
7 ' belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken türü.

*TArg8*<br/>
8 ' belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken türü.

*TArg9*<br/>
9 ' belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken türü.

*arg1*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 1.

*arg2*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 2.

*Arg3*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 3.

*Arg4*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 4.

*arg5*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 5.

*arg6*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 6.

*arg7*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 7.

*arg8*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 8.

*arg9*<br/>
Belirtilen çalışma zamanı sınıfına geçirilen bağımsız değişken 9.

## <a name="return-value"></a>Dönüş Değeri

HRESULT değerini.

## <a name="remarks"></a>Açıklamalar

Bkz: [nasıl yapılır: doğrudan WRL bileşenlerinin örneğini oluşturma](../windows/how-to-instantiate-wrl-components-directly.md) bu işlevi arasındaki farkları öğrenin ve [Microsoft::wrl:: Make](../windows/make-function.md)ve bir örnek.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::wrl:: details

## <a name="see-also"></a>Ayrıca Bkz.

[Microsoft::WRL::Details Ad Alanı](../windows/microsoft-wrl-details-namespace.md)