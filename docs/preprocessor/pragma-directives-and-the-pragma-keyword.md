---
title: Pragma yönergeleri ve __ pragma ve _Pragma anahtar sözcükleri
description: pragmaMicrosoft Visual C ve C++ ' da kullanılabilen yönergeleri açıklar (MSVC)
ms.date: 01/19/2021
f1_keywords:
- '#pragma'
- _Pragma
- __pragma
helpviewer_keywords:
- '#pragma directives, C/C++'
- __pragma keyword
- _Pragma keyword
- pragma directives, C/C++
- pragmas, C/C++
- preprocessor
- pragmas
- preprocessor, pragmas
- pragma directives (#pragma)
no-loc:
- pragma
ms.openlocfilehash: fb6daf4c2912ea2168c38bfe2d1ae2650aaecc20
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713356"
---
# <a name="pragma-directives-and-the-__no-locpragma-and-_pragma-keywords"></a>Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri

Pragma yönergeleri makineye özel veya işletim sistemine özgü derleyici özelliklerini belirtir. **`__pragma`** Microsoft derleyicisine özgü anahtar sözcük, pragma makro tanımları içindeki yönergeleri kodlamanıza olanak sağlar. Standart **`_Pragma`** Önişlemci Işleci C99 içinde tanıtılmıştı ve c++ 11 tarafından benimsenmiştir.

## <a name="syntax"></a>Syntax

> **`#pragma`***belirteç-dize*\
> **`__pragma(`***belirteç-dize* **`)`** iki önde gelen alt çizgi-Microsoft 'a özgü uzantı \
> **`_Pragma(`***dize sabit değeri* **`)`** C99

## <a name="remarks"></a>Açıklamalar

Her C ve C++ uygulamasının, ana makinesi veya işletim sistemine özgü bazı özellikleri destekler. Örneğin, bazı programlar, bellekteki verilerin konumu üzerinde tam denetim sağlamalıdır veya belirli işlevlerin parametreleri alma şeklini denetmelidir. **`#pragma`** Yönergeler, her derleyicinin makine ve işletim sistemine özgü özellikler sunmasına, C ve C++ dilleriyle genel uyumluluğu sürdürmesinin bir yolunu sunar.

Pragma yönergeleri, belirli bir tanıma göre makineye özgü veya işletim sistemine özgüdür ve genellikle her derleyicide farklıdır. Bir pragma koşullu yönergede yeni Önişlemci işlevselliği sağlamak için kullanılabilir. Veya, derleyicisine uygulama tanımlı bilgiler sağlamak için bir tane kullanın.

*Belirteç dizesi* , varsa belirli bir derleyici yönergesini ve bağımsız değişkenleri temsil eden bir karakter dizisidir. Numara işareti ( **`#`** ), içeren satırdaki ilk beyaz boşluk olmayan karakter olmalıdır pragma . Boşluk karakterleri, sayı işaretini ve "" sözcüğünü ayırabilirler pragma . Aşağıda **`#pragma`** , çeviricisinin ön işleme belirteçleri olarak ayrıştırılacak tüm metinleri yazın. Bağımsız değişkeni **`#pragma`** makro genişletmeye tabidir.

*Dize sabit değeri* , giriştir `_Pragma` . Dış tırnaklar ve baştaki/sondaki boşluklar kaldırılır. `\"` ile değiştirilmiştir `"` ve `\\` ile değiştirilmiştir `\` .

Derleyici, pragma tanımadığı ve derlemeyi devam eden bir hata bulduğunda bir uyarı verir.

Microsoft C ve C++ derleyicileri aşağıdaki yönergeleri tanır pragma :

:::row:::
   :::column span="":::
      [`alloc_text`](../preprocessor/alloc-text.md)\
      [`auto_inline`](../preprocessor/auto-inline.md)\
      [`bss_seg`](../preprocessor/bss-seg.md)\
      [`check_stack`](../preprocessor/check-stack.md)\
      [`code_seg`](../preprocessor/code-seg.md)\
      [`comment`](../preprocessor/comment-c-cpp.md)\
      [`component`](../preprocessor/component.md)\
      [`conform`](../preprocessor/conform.md)<sup>1</sup>\
      [`const_seg`](../preprocessor/const-seg.md)\
      [`data_seg`](../preprocessor/data-seg.md)\
      [`deprecated`](../preprocessor/deprecated-c-cpp.md)
   :::column-end:::
   :::column span="":::
      [`detect_mismatch`](../preprocessor/detect-mismatch.md)\
      [`endregion`](../preprocessor/region-endregion.md)\
      [`fenv_access`](../preprocessor/fenv-access.md)\
      [`float_control`](../preprocessor/float-control.md)\
      [`fp_contract`](../preprocessor/fp-contract.md)\
      [`function`](../preprocessor/function-c-cpp.md)\
      [`hdrstop`](../preprocessor/hdrstop.md)\
      [`include_alias`](../preprocessor/include-alias.md)\
      [`init_seg`](../preprocessor/init-seg.md)<sup>1</sup>\
      [`inline_depth`](../preprocessor/inline-depth.md)\
      [`inline_recursion`](../preprocessor/inline-recursion.md)
   :::column-end:::
   :::column span="":::
      [`intrinsic`](../preprocessor/intrinsic.md)\
      [`loop`](../preprocessor/loop.md)<sup>1</sup>\
      [`make_public`](../preprocessor/make-public.md)\
      [`managed`](../preprocessor/managed-unmanaged.md)\
      [`message`](../preprocessor/message.md)\
      [`omp`](../preprocessor/omp.md)\
      [`once`](../preprocessor/once.md)\
      [`optimize`](../preprocessor/optimize.md)\
      [`pack`](../preprocessor/pack.md)\
      [`pointers_to_members`](../preprocessor/pointers-to-members.md)<sup>1</sup>
   :::column-end:::
   :::column span="":::
      [`pop_macro`](../preprocessor/pop-macro.md)\
      [`push_macro`](../preprocessor/push-macro.md)\
      [`region`](../preprocessor/region-endregion.md)\
      [`runtime_checks`](../preprocessor/runtime-checks.md)\
      [`section`](../preprocessor/section.md)\
      [`setlocale`](../preprocessor/setlocale.md)\
      [`strict_gs_check`](../preprocessor/strict-gs-check.md)\
      [`unmanaged`](../preprocessor/managed-unmanaged.md)\
      [`vtordisp`](../preprocessor/vtordisp.md)<sup>1</sup>\
      [`warning`](../preprocessor/warning.md)
   :::column-end:::
:::row-end:::

<sup>1</sup> yalnızca C++ derleyicisi tarafından desteklenir.

## <a name="pragma-directives-and-compiler-options"></a>Pragma yönergeleri ve derleyici seçenekleri

Bazı pragma yönergeler derleyici seçenekleriyle aynı işlevleri sağlar. pragmaKaynak kodunda bir ulaşıldığında, derleyici seçeneği tarafından belirtilen davranışı geçersiz kılar. Örneğin, belirttiyseniz [`/Zp8`](../build/reference/zp-struct-member-alignment.md) , kodun belirli bölümleri için bu derleyici ayarını geçersiz kılabilirsiniz [`pack`](../preprocessor/pack.md) :

```cmd
cl /Zp8 some_file.cpp
```

```cpp
// some_file.cpp - packing is 8
// ...
#pragma pack(push, 1) - packing is now 1
// ...
#pragma pack(pop) - packing is 8 again
// ...
```

## <a name="the-__no-locpragma-keyword"></a>`__pragma()` anahtar sözcüğü

Derleyici Ayrıca, **`__pragma`** yönergeyle aynı işlevselliğe sahip olan Microsoft 'a özgü anahtar sözcüğünü de destekler **`#pragma`** . Fark, **`__pragma`** anahtar sözcüğünün satır içi olarak bir makro tanımında kullanılabilir olması. **`#pragma`** Bir makro tanımında yönerge kullanılamaz, çünkü derleyici yönergedeki işaret karakteri (' # ') sayısını dize haline getirme [işleci (#)](../preprocessor/stringizing-operator-hash.md)olarak yorumlar.

Aşağıdaki kod örneği, **`__pragma`** anahtar sözcüğünün bir makroda nasıl kullanılabileceğini gösterir. Bu kod, "derleyici COM desteği örnekleri" içinde ACDUAL örneğindeki *mfcdual. h* üst bilgisinden ayıklanalınmıştır:

```cpp
#define CATCH_ALL_DUAL \
CATCH(COleException, e) \
{ \
_hr = e->m_sc; \
} \
AND_CATCH_ALL(e) \
{ \
__pragma(warning(push)) \
__pragma(warning(disable:6246)) /*disable _ctlState prefast warning*/ \
AFX_MANAGE_STATE(pThis->m_pModuleState); \
__pragma(warning(pop)) \
_hr = DualHandleException(_riidSource, e); \
} \
END_CATCH_ALL \
return _hr; \
```

## <a name="the-_pragma-preprocessing-operator-c99-c11"></a>`_Pragma`Ön işleme işleci (C99, c++ 11)

`_Pragma`[`__pragma`](#the-__pragma-keyword), standart bir parçası dışında, Microsoft 'a özgü anahtar sözcüğe benzerdir. C99 içinde C için sunulmuştur. C++ için C++ 11 ' de kullanıma sunulmuştur.

 pragmaBir makro tanımına yönergeler eklemenizi sağlar. `_`Microsoft 'a özgü anahtar sözcüğünün sahip olduğu iki önde gelen alt çizgi yerine bir önde gelen alt çizgi `__` ve ilk harf büyük harfli olur.

Dize değişmez değeri, daha önce bir deyimin ardından yerleştirilecek şekilde olmalıdır *`#pragma`* . Örneğin:

```c
#pragma message("the #pragma way")
_Pragma ("message( \"the _Pragma way\")") 
```

Yukarıda gösterildiği gibi, tırnak işaretleri ve ters eğik çizgiler kaçmalıdır. pragmaTanınmayan bir dize yok sayılır.

Aşağıdaki kod örneği, **`_Pragma`** koşul ifadesi sabit olduğunda bir uyarı almak istemediğinizde anahtar sözcüğünün onay benzeri bir makroda nasıl kullanılabileceğini gösterir. 

Makro tanımı, `do` - `while(0)` çok deyimli makrolar için IOM kullanır, böylece bir deyim olarak kullanılabilir. Daha fazla bilgi için bkz. Stack Overflow [çok satırlı makro](https://stackoverflow.com/questions/1067226/c-multi-line-macro-do-while0-vs-scope-block) . **`_Pragma`** İfade yalnızca, izleyen kod satırı için geçerlidir.

```C
// Compile with /W4

#include <stdio.h>
#include <stdlib.h>

#define MY_ASSERT(BOOL_EXPRESSION) \
    do { \
        _Pragma("warning(suppress: 4127)") /* C4127 conditional expression is constant */  \
        if (!(BOOL_EXPRESSION)) {   \
            printf("MY_ASSERT FAILED: \"" #BOOL_EXPRESSION "\" on %s(%d)", __FILE__, __LINE__); \
            exit(-1); \
        } \
    } while (0)

int main()
{
    MY_ASSERT(0 && "Note that there is no warning: C4127 conditional expression is constant");

    return 0;
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Önişlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)\
[C pragma yönergeleri](../c-language/c-pragmas.md)\
[Anahtar sözcükler](../cpp/keywords-cpp.md)
