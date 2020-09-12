---
title: iç pragma
description: MSVC Intrinsic pragma, iç yapı olarak kullanılacak desteklenen iç işlevleri belirtmek için kullanılır.
ms.date: 07/08/2020
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
helpviewer_keywords:
- intrinsic pragma
- pragmas, intrinsic
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
ms.openlocfilehash: 45a5a13f3bda3657b93e1a89e7a842a4465b01d5
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90041113"
---
# <a name="intrinsic-pragma"></a>`intrinsic` Prag

Pragmanın bağımsız değişken listesinde belirtilen işlevlere yapılan çağrıların iç olduğunu belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma intrinsic(`** *`function1`* [**`,`** _`function2`_ ... ] **`)`**

## <a name="remarks"></a>Açıklamalar

**`intrinsic`** Pragma derleyiciye bir işlevin bilinen davranışı olduğunu söyler. Derleyici, işlevi çağırabilir ve daha iyi performans gösterecekse işlev çağrısını satır içi yönergelerle değiştirmeyebilir.

İç biçimlere sahip kitaplık işlevleri aşağıda listelenmiştir. Bir **`intrinsic`** pragma görüldüğünde, belirtilen bir iç işlevi içeren ilk işlev tanımında geçerli olur. Etki, kaynak dosyanın sonuna veya `function` aynı iç işlevi belirten bir pragma görünümüne devam eder. **`intrinsic`** Pragma, genel düzeyde yalnızca bir işlev tanımının dışında kullanılabilir.

Aşağıdaki işlevlerin iç formları vardır ve belirttiğiniz sırada iç formlar kullanılır [`/Oi`](../build/reference/oi-generate-intrinsic-functions.md) :

:::row:::
   :::column span="":::
      [`abs`](../c-runtime-library/reference/abs-labs-llabs-abs64.md)\
      [`_disable`](../intrinsics/disable.md)\
      [`_enable`](../intrinsics/enable.md)\
      [`fabs`](../c-runtime-library/reference/fabs-fabsf-fabsl.md)\
      [`_inp`](../c-runtime-library/inp-inpw-inpd.md)\
      [`_inpw`](../c-runtime-library/inp-inpw-inpd.md)\
   :::column-end:::
   :::column span="":::
      [`labs`](../c-runtime-library/reference/abs-labs-llabs-abs64.md)\
      [`_lrotl`](../c-runtime-library/reference/lrotl-lrotr.md)\
      [`_lrotr`](../c-runtime-library/reference/lrotl-lrotr.md)\
      [`memcmp`](../c-runtime-library/reference/memcmp-wmemcmp.md)\
      [`memcpy`](../c-runtime-library/reference/memcpy-wmemcpy.md)\
   :::column-end:::
   :::column span="":::
      [`memset`](../c-runtime-library/reference/memset-wmemset.md)\
      [`_outp`](../c-runtime-library/outp-outpw-outpd.md)\
      [`_outpw`](../c-runtime-library/outp-outpw-outpd.md)\
      [`_rotl`](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)\
      [`_rotr`](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)\
   :::column-end:::
   :::column span="":::
      [`strcat`](../c-runtime-library/reference/strcat-wcscat-mbscat.md)\
      [`strcmp`](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)\
      [`strcpy`](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)\
      [`strlen`](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)\
      [`_strset`](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)\
   :::column-end:::
:::row-end:::

İç işlevleri kullanan programlar, işlev çağrılarının ek yüküne sahip olmadıkları için daha hızlıdır. Ancak, oluşturulan ek kod nedeniyle daha büyük olabilirler.

### <a name="x86-specific-example"></a>x86 özgü örnek

`_disable`Ve `_enable` iç bilgileri, kesmeleri devre dışı bırakmak veya etkinleştirmek için çekirdek modu yönergeleri oluşturur ve çekirdek modu sürücülerinde yararlı olabilir.

İle komut satırından aşağıdaki kodu derleyin `cl -c -FAs sample.c` ve *`sample.asm`* x86 yönergelerine CLı ve STI 'nin nasıl görüneceğine bakmak için bölümüne bakın:

```cpp
// pragma_directive_intrinsic.cpp
// processor: x86
#include <dos.h>   // definitions for _disable, _enable
#pragma intrinsic(_disable)
#pragma intrinsic(_enable)
void f1(void) {
   _disable();
   // do some work here that should not be interrupted
   _enable();
}
int main() {
}
```

### <a name="intrinsic-floating-point-functions"></a>İç kayan nokta işlevleri

Bu kayan nokta işlevleri gerçek iç formlara sahip değildir. Bunun yerine, bağımsız değişkenleri yığına göndermek yerine doğrudan kayan nokta yongasına geçiren sürümlere sahiptir:

:::row:::
   :::column span="":::
      [`acos`](../c-runtime-library/reference/acos-acosf-acosl.md)\
      [`asin`](../c-runtime-library/reference/asin-asinf-asinl.md)\
   :::column-end:::
   :::column span="":::
      [`cosh`](../c-runtime-library/reference/cosh-coshf-coshl.md)\
      [`fmod`](../c-runtime-library/reference/fmod-fmodf.md)\
   :::column-end:::
   :::column span="":::
      [`pow`](../c-runtime-library/reference/pow-powf-powl.md)\
      [`sinh`](../c-runtime-library/reference/sinh-sinhf-sinhl.md)\
   :::column-end:::
   :::column span="":::
      [`tanh`](../c-runtime-library/reference/tanh-tanhf-tanhl.md)\
   :::column-end:::
:::row-end:::

Bu kayan nokta işlevleri, [`/Oi`](../build/reference/oi-generate-intrinsic-functions.md) ve [`/fp:fast`](../build/reference/fp-specify-floating-point-behavior.md) (ya da içeren herhangi bir seçeneği **`/Oi`** ,, [`/Ox`](../build/reference/ox-full-optimization.md) [`/O1`](../build/reference/o1-o2-minimize-size-maximize-speed.md) ve [`/O2`](../build/reference/o1-o2-minimize-size-maximize-speed.md) ) belirttiğinizde gerçek iç formlara sahiptir:

:::row:::
   :::column span="":::
      [`atan`](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)\
      [`atan2`](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)\
      [`cos`](../c-runtime-library/reference/cos-cosf-cosl.md)\
   :::column-end:::
   :::column span="":::
      [`exp`](../c-runtime-library/reference/exp-expf.md)\
      [`log`](../c-runtime-library/reference/log-logf-log10-log10f.md)\
   :::column-end:::
   :::column span="":::
      [`log10`](../c-runtime-library/reference/log-logf-log10-log10f.md)\
      [`sin`](../c-runtime-library/reference/sin-sinf-sinl.md)\
   :::column-end:::
   :::column span="":::
      [`sqrt`](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)\
      [`tan`](../c-runtime-library/reference/tan-tanf-tanl.md)\
   :::column-end:::
:::row-end:::

[`/fp:strict`](../build/reference/fp-specify-floating-point-behavior.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) Gerçek iç kayan nokta seçeneklerinin oluşturulmasını geçersiz kılmak için ya da kullanabilirsiniz. Bu durumda işlevler, bağımsız değişkenleri program yığınına döndürmek yerine doğrudan kayan nokta yongasına geçiren kitaplık yordamları olarak oluşturulur.

[`#pragma function`](../preprocessor/function-c-cpp.md)Kaynak metin bloğu için iç bilgileri etkinleştirme ve devre dışı bırakma hakkında bilgi ve örnek için bkz..

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)
