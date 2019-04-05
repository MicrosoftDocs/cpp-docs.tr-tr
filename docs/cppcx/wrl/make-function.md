---
title: Make İşlevi
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Make
helpviewer_keywords:
- Make function
ms.assetid: 66704143-df99-4a95-904d-ed99607e1034
ms.openlocfilehash: b45337ef773f93968570f62ab73c02d11fae88ff
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59028253"
---
# <a name="make-function"></a>Make İşlevi

Belirtilen Windows çalışma zamanı sınıf başlatır. Aynı modülde tanımlanmış bir bileşeni oluşturmak için bu işlevi kullanın.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8,
   typename TArg9
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7,
   TArg8 &&arg8,
   TArg9 &&arg9
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7,
   typename TArg8
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7,
   TArg8 &&arg8
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6,
   typename TArg7
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6,
   TArg7 &&arg7
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5,
   typename TArg6
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5,
   TArg6 &&arg6
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4,
   typename TArg5
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4,
   TArg5 &&arg5
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3,
   typename TArg4
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3,
   TArg4 &&arg4
);
template <
   typename T,
   typename TArg1,
   typename TArg2,
   typename TArg3
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2,
   TArg3 &&arg3
);
template <
   typename T,
   typename TArg1,
   typename TArg2
>
ComPtr<T> Make(
   TArg1 &&arg1,
   TArg2 &&arg2
);
template <
   typename T,
   typename TArg1
>
ComPtr<T> Make(
   TArg1 &&arg1
);
template <
   typename T
>
ComPtr<T> Make();
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

A `ComPtr<T>` nesne başarılı; Aksi takdirde `nullptr`.

## <a name="remarks"></a>Açıklamalar

Bkz: [nasıl yapılır: Doğrudan WRL bileşenlerinin örneğini oluşturma](how-to-instantiate-wrl-components-directly.md) bu işlevi arasındaki farkları öğrenin ve [Microsoft::WRL::Details::MakeAndInitialize](makeandinitialize-function.md)ve bir örnek.

## <a name="requirements"></a>Gereksinimler

**Başlık:** implements.h

**Namespace:** Microsoft::WRL

## <a name="see-also"></a>Ayrıca bkz.

[Microsoft::WRL Ad Alanı](microsoft-wrl-namespace.md)