---
title: Pragma yönergeleri ve __pragma anahtar sözcüğü
ms.date: 08/29/2019
f1_keywords:
- '#pragma'
helpviewer_keywords:
- '#pragma directives, C/C++'
- __pragma keyword
- pragma directives, C/C++
- pragmas, C/C++
- preprocessor
- pragmas
- preprocessor, pragmas
- pragma directives (#pragma)
ms.assetid: 9867b438-ac64-4e10-973f-c3955209873f
ms.openlocfilehash: 6cfbcd325dc895719bad5dccc9c19bcda90cdaa0
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74858080"
---
# <a name="pragma-directives-and-the-__pragma-keyword"></a>Pragma yönergeleri ve __pragma anahtar sözcüğü

Pragma yönergeleri makine veya işletim sistemine özgü derleyici özelliklerini belirtir. Microsoft derleyicisine özgü **__pragma** anahtar sözcüğü, makro tanımları içinde pragma yönergelerini kodlamanıza olanak sağlar.

## <a name="syntax"></a>Sözdizimi

> **#pragma** *belirteci-dize*\
> **__pragma (** *belirteç-dize* **)**

## <a name="remarks"></a>Açıklamalar

Her bir C ve C++ uygulaması, kendi ana makinesine veya işletim sistemine özgü benzersiz bazı özellikler destekler. Örneğin, bazı programlar, bellekteki verilerin konumu üzerinde tam denetim sağlamalıdır veya belirli işlevlerin parametreleri alma şeklini denetmelidir. **#Pragma** yönergeleri, her bir derleyicinin makine ve işletim sistemine özgü özellikler sunmasına, C ve C++ dillerle genel uyumluluğu sürdürmesinin bir yolunu sunar.

Pragmalar, tanıma göre makine veya işletim sistemine özgüdür ve genellikle her derleyicide farklıdır. Pragmalar, yeni Önişlemci işlevselliği sağlamak ya da derleyiciye uygulama tanımlı bilgiler sağlamak için koşullu yönergeler içinde kullanılabilir.

*Token-string* , varsa belirli bir derleyici yönergesini ve bağımsız değişkenleri veren bir karakter dizisidir. Numara işareti ( **#** ), pragma 'ı içeren satırdaki ilk beyaz boşluk olmayan karakter olmalıdır. Boşluk karakterleri, sayı işaretini ve "pragma" sözcüğünü ayırabilirler. Aşağıdaki **#pragma**, çeviricisinin ön işleme belirteçleri olarak ayrıştırabileceği tüm metinleri yazın. **#Pragma** bağımsız değişkeni makro genişletmeye tabidir.

Derleyici, tanımadığı bir pragma bulduğunda bir uyarı verir ve derlemeyi sürdürür.

Microsoft C ve C++ derleyicileri aşağıdaki pragmaları tanır:

||||
|-|-|-|
|[alloc_text](../preprocessor/alloc-text.md)|[auto_inline](../preprocessor/auto-inline.md)|[bss_seg](../preprocessor/bss-seg.md)|
|[check_stack](../preprocessor/check-stack.md)|[code_seg](../preprocessor/code-seg.md)|[açıklamanın](../preprocessor/comment-c-cpp.md)|
|[component](../preprocessor/component.md)|[uyumlu](../preprocessor/conform.md) <sup>1</sup>|[const_seg](../preprocessor/const-seg.md)|
|[data_seg](../preprocessor/data-seg.md)|[deprecated](../preprocessor/deprecated-c-cpp.md)|[detect_mismatch](../preprocessor/detect-mismatch.md)|
|[fenv_access](../preprocessor/fenv-access.md)|[float_control](../preprocessor/float-control.md)|[fp_contract](../preprocessor/fp-contract.md)|
|[çalışmayacaktır](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include_alias](../preprocessor/include-alias.md)|
|[init_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline_depth](../preprocessor/inline-depth.md)|[inline_recursion](../preprocessor/inline-recursion.md)|
|[intrinsic](../preprocessor/intrinsic.md)|[döngü](../preprocessor/loop.md) <sup>1</sup>|[make_public](../preprocessor/make-public.md)|
|[lebilmesi](../preprocessor/managed-unmanaged.md)|[message](../preprocessor/message.md)|[omp](../preprocessor/omp.md)|
|[once](../preprocessor/once.md)|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|
|[pointers_to_members](../preprocessor/pointers-to-members.md) <sup>1</sup>|[pop_macro](../preprocessor/pop-macro.md)|[push_macro](../preprocessor/push-macro.md)|
|[region, endregion](../preprocessor/region-endregion.md)|[runtime_checks](../preprocessor/runtime-checks.md)|[section](../preprocessor/section.md)|
|[setlocale](../preprocessor/setlocale.md)|[strict_gs_check](../preprocessor/strict-gs-check.md)|[yönetilmeyen](../preprocessor/managed-unmanaged.md)|
|[vtordisp](../preprocessor/vtordisp.md) <sup>1</sup>|[warning](../preprocessor/warning.md)||

<sup>1</sup> yalnızca C++ derleyici tarafından desteklenir.

## <a name="pragmas-and-compiler-options"></a>Pragmalar ve derleyici seçenekleri

Bazı pragmalar derleyici seçenekleriyle aynı işlevleri sağlar. Kaynak kodunda bir pragma ile karşılaşıldığında, derleyici seçeneği tarafından belirtilen davranışı geçersiz kılar. Örneğin, [/ZP8](../build/reference/zp-struct-member-alignment.md)' i belirlediyseniz, [paket](../preprocessor/pack.md)ile kodun belirli bölümleri için bu derleyici ayarını geçersiz kılabilirsiniz:

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

## <a name="the-__pragma-keyword"></a>__Pragma () anahtar sözcüğü

Derleyici Ayrıca, **#pragma** yönergesiyle aynı işlevselliğe sahip olan Microsoft 'a özgü **__pragma** anahtar sözcüğünü de destekler. Farkı, **__pragma** anahtar sözcüğünün bir makro tanımında satır içi kullanılabilir. **#Pragma** yönergesi, bir makro tanımında kullanılamaz, çünkü derleyici yönergede işaret karakteri (' # ') sayısını dize haline getirme [işleci (#)](../preprocessor/stringizing-operator-hash.md)olarak yorumlar.

Aşağıdaki kod örneği, **__pragma** anahtar sözcüğünün bir makroda nasıl kullanılabileceğini gösterir. Bu kod, "Derleyici COM Destek Örnekleri" içindeki ACDUAL örneğinde bulunan mfcdual.h başlığından alınmıştır:

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

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Önişlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)\
[C pragmaları](../c-language/c-pragmas.md)\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
