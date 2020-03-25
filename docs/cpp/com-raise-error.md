---
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: 2012ec98d8d40d60a7f12feb68bdc371e1616223
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189799"
---
# <a name="_com_raise_error"></a>_com_raise_error

**Microsoft 'a özgü**

Hataya yanıt olarak bir [_com_error](../cpp/com-error-class.md) oluşturur.

## <a name="syntax"></a>Sözdizimi

```
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>Parametreler

*HR*<br/>
HRESULT bilgileri.

*perrınfo*<br/>
`IErrorInfo` nesnesi.

## <a name="remarks"></a>Açıklamalar

\<Comdef. h > 'de tanımlanan **_com_raise_error**, aynı ad ve prototipin Kullanıcı tarafından yazılmış bir sürümü ile değiştirilebilir. `#import` kullanmak istiyorsanız ancak özel durum işlemeyi kullanmak C++ istemiyorsanız bu işlem yapılabilir. Bu durumda **_com_raise_error** bir Kullanıcı sürümü bir `longjmp` ya da bir ileti kutusu görüntüleyip durdurmak için karar verebilir. Derleyici COM desteği kodu dönmesini beklemediğinden, Kullanıcı sürümü dönmemelidir.

Varsayılan hata işleme işlevini değiştirmek için [_set_com_error_handler](../cpp/set-com-error-handler.md) de kullanabilirsiniz.

Varsayılan olarak, **_com_raise_error** aşağıdaki gibi tanımlanır:

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**SON Microsoft 'a özgü**

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<Comdef. h >

**LIB:** **Wchar_t yerel tür** derleyici seçeneği açık ise comsuppw. lib veya comsuppwd. lib kullanın. **Wchar_t yerel tür** kapalıysa comsupp. lib kullanın. Daha fazla bilgi için bkz. [/Zc: wchar_t (wchar_t yerel tür)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Global COM İşlevleri](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
