---
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: 5790fceef26d6de4edff604270cc7108f764aced
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627571"
---
# <a name="comraiseerror"></a>_com_raise_error

**Microsoft'a özgü**

Oluşturur bir [_com_error](../cpp/com-error-class.md) yanıt olarak bir hata.

## <a name="syntax"></a>Sözdizimi

```
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>Parametreler

*İK*<br/>
HRESULT bilgileri.

*perrinfo*<br/>
`IErrorInfo` nesne.

## <a name="remarks"></a>Açıklamalar

**_com_raise_error**, tanımlanan \<comdef.h >, bir kullanıcı tarafından yazılan sürümü aynı ada ve prototip tarafından değiştirilebilir. Kullanmak istiyorsanız bu yapılabilir `#import` ancak C++ özel durum işleme kullanmak istemiyorsanız. Bu durumda, kullanıcı sürümünde **_com_raise_error** yapmak karar verebilirsiniz bir `longjmp` veya bir ileti kutusu görüntüleme ve durdur. Derleyici COM destek kodunu döndürmek için bunu beklemiyor çünkü kullanıcı sürümüdür, ancak döndürmemelidir.

Ayrıca [_set_com_error_handler](../cpp/set-com-error-handler.md) varsayılan hata işleme işlevinizi değiştirilecek.

Varsayılan olarak, **_com_raise_error** şu şekilde tanımlanır:

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**END Microsoft özgü**

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<comdef.h >

**Lib:** varsa **wchar_t yerel tür olan** derleyici seçeneği açıktır, comsuppw.lib veya comsuppwd.lib kullanın. Varsa **wchar_t yerel tür olan** kapalıysa, comsupp.lib kullanın. Daha fazla bilgi için [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)