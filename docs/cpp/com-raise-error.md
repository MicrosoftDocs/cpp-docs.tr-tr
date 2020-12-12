---
description: 'Hakkında daha fazla bilgi edinin: _com_raise_error'
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: 81697b565104971d22da04a7b8b0e33a7f9255ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178218"
---
# <a name="_com_raise_error"></a>_com_raise_error

**Microsoft'a Özgü**

Hataya yanıt olarak bir [_com_error](../cpp/com-error-class.md) oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>Parametreler

*sa*<br/>
HRESULT bilgileri.

*perrınfo*<br/>
`IErrorInfo` nesne.

## <a name="remarks"></a>Açıklamalar

içinde tanımlanan **_com_raise_error**, \<comdef.h> aynı ad ve prototipin Kullanıcı tarafından yazılmış bir sürümü ile değiştirilebilir. Bu işlem, `#import` C++ özel durum işleme kullanmak istemiyorsanız yapılabilir. Bu durumda, **_com_raise_error** bir Kullanıcı sürümü bir `longjmp` ileti kutusu ya da ekran durdurabilir. Derleyici COM desteği kodu dönmesini beklemediğinden, Kullanıcı sürümü dönmemelidir.

Varsayılan hata işleme işlevini değiştirmek için [_set_com_error_handler](../cpp/set-com-error-handler.md) de kullanabilirsiniz.

Varsayılan olarak, **_com_raise_error** aşağıdaki gibi tanımlanır:

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<comdef.h>

**LIB:** **Wchar_t yerel tür** derleyici seçeneği açık ise comsuppw. lib veya comsuppwd. lib kullanın. **Wchar_t yerel tür** kapalıysa comsupp. lib kullanın. Daha fazla bilgi için bkz. [/Zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici COM genel Işlevleri](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
