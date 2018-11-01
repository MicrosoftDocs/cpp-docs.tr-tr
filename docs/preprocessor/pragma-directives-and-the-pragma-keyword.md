---
title: Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü
ms.date: 11/04/2016
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
ms.openlocfilehash: 9e79ba7378e28fdea863af010decb7064df415cd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660102"
---
# <a name="pragma-directives-and-the-pragma-keyword"></a>Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü

Pragma yönergeleri makine veya işletim özgü derleyici özelliklerini belirtir. **__Pragma** Microsoft derleyiciye özgü anahtar sözcüğü için kod pragma yönergelerini makro tanımları içinde size sağlar.

## <a name="syntax"></a>Sözdizimi

```
#pragma token-string
__pragma(token-string)
```

## <a name="remarks"></a>Açıklamalar

Her C ve C++ uygulaması, kendi ana makinesine veya işletim sistemi benzersiz bazı özellikler destekler. Örneğin, bazı programların verilerin eklendiği bellek alanları üzerinde veya işlevlerin parametre alma belirli denetlenmesine kesin denetim yollarını denetlemesi gerekir. **#Pragma** yönergeleri her derleyiciye C ve C++ dilleri ile genel uyumluluğu muhafaza ederken, makineye ve işletim sistemine özgü özellikler sunmak için bir yol sunar.

Pragmalar makine veya işletim sistemi-tanımına göre özgüdür ve genelde her derleyici için farklıdır. Pragmalar, yeni önişlemci işlevselliğini sunmak veya derleyiciye uygulama tanımlı bilgileri sağlamak için koşullu ifadelerde kullanılabilir.

`token-string` Belirli bir derleyici yönergesi ve bağımsız değişkenler veren bir karakterler varsa dizisidir. Numara işareti (**#**) ilk boşluk olmayan karakter pragmayı içeren satırda; beyaz boşluk karakterleri numara işaretleri ile "pragma" sözcüğünü ayırabilirsiniz. Aşağıdaki **#pragma**, translator ön işleme belirteci olarak ayrıştırabilirsiniz herhangi bir metni yazın. Bağımsız değişkeni **#pragma** makro genişletmeye tabidir.

Derleyici tanımadığı bir pragma bulursa, bir uyarı verir ve derlemeye devam eder.

Microsoft C and C++ Derleyicileri aşağıdaki pragmaları tanır:

||||
|-|-|-|
|[alloc_text](../preprocessor/alloc-text.md)|[auto_inline](../preprocessor/auto-inline.md)|[bss_seg](../preprocessor/bss-seg.md)|
|[check_stack](../preprocessor/check-stack.md)|[code_seg](../preprocessor/code-seg.md)|[Açıklama](../preprocessor/comment-c-cpp.md)|
|[component](../preprocessor/component.md)|[uygun](../preprocessor/conform.md) <sup>1</sup>|[const_seg](../preprocessor/const-seg.md)|
|[data_seg](../preprocessor/data-seg.md)|[deprecated](../preprocessor/deprecated-c-cpp.md)|[detect_mismatch](../preprocessor/detect-mismatch.md)|
|[fenv_access](../preprocessor/fenv-access.md)|[float_control](../preprocessor/float-control.md)|[fp_contract](../preprocessor/fp-contract.md)|
|[İşlevi](../preprocessor/function-c-cpp.md)|[hdrstop](../preprocessor/hdrstop.md)|[include_alias](../preprocessor/include-alias.md)|
|[init_seg](../preprocessor/init-seg.md) <sup>1</sup>|[inline_depth](../preprocessor/inline-depth.md)|[inline_recursion](../preprocessor/inline-recursion.md)|
|[intrinsic](../preprocessor/intrinsic.md)|[döngü](../preprocessor/loop.md) <sup>1</sup>|[make_public](../preprocessor/make-public.md)|
|[Yönetilen](../preprocessor/managed-unmanaged.md)|[message](../preprocessor/message.md)||
|[omp](../preprocessor/omp.md)|[once](../preprocessor/once.md)||
|[optimize](../preprocessor/optimize.md)|[pack](../preprocessor/pack.md)|[pointers_to_members](../preprocessor/pointers-to-members.md) <sup>1</sup>|
|[pop_macro](../preprocessor/pop-macro.md)|[push_macro](../preprocessor/push-macro.md)|[region, endregion](../preprocessor/region-endregion.md)|
|[runtime_checks](../preprocessor/runtime-checks.md)|[section](../preprocessor/section.md)|[setlocale](../preprocessor/setlocale.md)|
|[strict_gs_check](../preprocessor/strict-gs-check.md)|[Yönetilmeyen](../preprocessor/managed-unmanaged.md)|[vtordisp](../preprocessor/vtordisp.md) <sup>1</sup>|
|[warning](../preprocessor/warning.md)|||

<sup>1</sup> yalnızca C++ Derleyici tarafından desteklenir.

## <a name="pragmas-and-compiler-options"></a>Pragmalar ve derleyici seçenekleri

Bazı pragmalar derleyici seçenekleriyle aynı işlevleri sağlar. Kaynak kodunda bir pragma ile karşılaşıldığında, derleyici seçeneği tarafından belirtilen davranışı geçersiz kılar. Örneğin, belirttiğiniz [/zp8](../build/reference/zp-struct-member-alignment.md), ile kodun belirli bölümleri için bu derleyici ayarını geçersiz kılabilirsiniz [paketi](../preprocessor/pack.md):

```
cl /Zp8 ...

<file> - packing is 8
// ...
#pragma pack(push, 1) - packing is now 1
// ...
#pragma pack(pop) - packing is 8
</file>
```

## <a name="the-pragma-keyword"></a>__Pragma() anahtar sözcüğü

**Microsoft'a özgü**

Derleyici ayrıca destekler **__pragma** anahtar sözcüğü ile aynı işlevlere sahiptir olarak **#pragma** yönergesi, ancak bir Makro tanımında kullanılan satır içi olabilir. **#Pragma** yönergesi çünkü derleyici yönergedeki içinde sayı işareti karakterini ('#') yorumlar bir makro tanımda kullanılamaz [dize haline getirme işleci (#)](../preprocessor/stringizing-operator-hash.md).

Aşağıdaki kod örneğinde nasıl **__pragma** anahtar sözcüğü bir makroda kullanılabilir. Bu kod, "Derleyici COM destek örnekleri" içindeki ACDUAL örneğinde bulunan mfcdual.h başlığından alınmıştır:

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

**End Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)<br/>
[C Pragmaları](../c-language/c-pragmas.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)