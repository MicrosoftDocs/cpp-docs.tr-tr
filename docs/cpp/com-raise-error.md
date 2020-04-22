---
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: f5efbe98a489a380c4e9be5a0e40603be2a409c0
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81745086"
---
# <a name="_com_raise_error"></a>_com_raise_error

**Microsoft'a Özgü**

Bir hataya yanıt olarak [bir _com_error](../cpp/com-error-class.md) atar.

## <a name="syntax"></a>Sözdizimi

```cpp
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>Parametreler

*Hr*<br/>
HRESULT bilgileri.

*perrinfo*<br/>
`IErrorInfo`Nesne.

## <a name="remarks"></a>Açıklamalar

\< **_com_raise_error,** comdef.h> tanımlanan, aynı adı ve prototip kullanıcı yazılı sürümü ile değiştirilebilir. C++ özel durum işlemekullanmak `#import` istiyorsanız ancak kullanmak istemiyorsanız bu yapılabilir. Bu durumda, **_com_raise_error** kullanıcı sürümü bir `longjmp` ileti kutusu yapmaya veya görüntülemeye karar verip durdurmaya karar verebilir. Derleyici COM destek kodu geri dönmesini beklemediği için kullanıcı sürümü geri dönmemelidir.

Varsayılan hata işleme işlevini değiştirmek için [_set_com_error_handler](../cpp/set-com-error-handler.md) de kullanabilirsiniz.

Varsayılan olarak, **_com_raise_error** aşağıdaki gibi tanımlanır:

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**END Microsoft Özel**

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<comdef.h>

**Lib:** wchar_t **Yerli Türü** derleyici seçeneği varsa, comsuppw.lib veya comsuppwd.lib kullanın. **wchar_t Yerel Tür** kapalıysa, comsupp.lib kullanın. Daha fazla bilgi için [bkz: /Zc:wchar_t (wchar_t Yerli Türüdür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
