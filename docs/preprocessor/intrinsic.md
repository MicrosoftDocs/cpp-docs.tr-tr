---
title: iç pragma
ms.date: 08/29/2019
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
helpviewer_keywords:
- intrinsic pragma
- pragmas, intrinsic
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
ms.openlocfilehash: bb4403abf5e278ed3727af660579e22ab69592c7
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220947"
---
# <a name="intrinsic-pragma"></a>iç pragma

Pragmanın bağımsız değişken listesinde belirtilen işlevlere yapılan çağrıların iç olduğunu belirtir.

## <a name="syntax"></a>Sözdizimi

> **#pragma iç (** *işlev1* [ **,** _function2_ ...] **)**

## <a name="remarks"></a>Açıklamalar

**İçsel** pragma, derleyiciye bir işlevin bilinen davranışı olduğunu söyler. Derleyici, işlevi çağırabilir ve daha iyi performans gösterecekse işlev çağrısını satır içi yönergelerle değiştirmeyebilir.

İç biçimlere sahip kitaplık işlevleri aşağıda listelenmiştir. Bir **iç** pragma görüldüğünde, belirtilen bir iç işlevi içeren ilk işlev tanımında geçerli olur. Etki, kaynak dosyanın sonuna veya aynı iç işlevi belirten bir `function` pragma görünümüne devam eder. **İç** pragma yalnızca bir işlev tanımının dışında, genel düzeyde kullanılabilir.

Aşağıdaki işlevler iç formlara sahiptir ve iç formlar [/Oi](../build/reference/oi-generate-intrinsic-functions.md)belirttiğinizde kullanılır:

|||||
|-|-|-|-|
|[_disable](../intrinsics/disable.md)|[_outp](../c-runtime-library/outp-outpw-outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|
|[_enable](../intrinsics/enable.md)|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|[larda](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|
|[_ınpw](../c-runtime-library/inp-inpw-inpd.md)|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[mutlak](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||

İç işlevleri kullanan programlar, işlev çağrılarının ek yüküne sahip olmadıkları için daha hızlıdır, ancak oluşturulan ek kod nedeniyle daha büyük olabilir.

**x86 özgü**

`_disable` Ve`_enable` iç bilgileri, kesmeleri devre dışı bırakmak veya etkinleştirmek için çekirdek modu yönergeleri oluşturur ve çekirdek modu sürücülerinde yararlı olabilir.

### <a name="example"></a>Örnek

Aşağıdaki kodu komut satırından ile `cl -c -FAs sample.c` derleyin ve Sample. asm ' ye bakarak, x86 yönergelerine CLI ve STI 'nin doğru olduğunu görün:

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

**Son x86 özel**

Aşağıda listelenen kayan nokta işlevleri gerçek iç formlara sahip değildir. Bunun yerine, bağımsız değişkenleri program yığınına döndürmek yerine doğrudan kayan nokta yongasına geçiren sürümleri vardır:

|||||
|-|-|-|-|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[Cosh](../c-runtime-library/reference/cosh-coshf-coshl.md)|[POW](../c-runtime-library/reference/pow-powf-powl.md)|[tanh](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[sinh](../c-runtime-library/reference/sinh-sinhf-sinhl.md)||

Aşağıda listelenen kayan nokta işlevleri, [/Oi](../build/reference/oi-generate-intrinsic-functions.md), [/OG](../build/reference/og-global-optimizations.md)ve [/FP: Fast](../build/reference/fp-specify-floating-point-behavior.md) (ya da/OG içeren herhangi bir seçeneği içeren,/Ox, [/O1](../build/reference/o1-o2-minimize-size-maximize-speed.md)ve [](../build/reference/ox-full-optimization.md) [/O2](../build/reference/o1-o2-minimize-size-maximize-speed.md)) belirttiğinizde gerçek iç formlara sahiptir:

|||||
|-|-|-|-|
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|[Başlangıçtan](../c-runtime-library/reference/tan-tanf-tanl.md)|
|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)||||

Gerçek iç kayan nokta seçeneklerinin oluşturulmasını geçersiz kılmak için [/FP: Strict](../build/reference/fp-specify-floating-point-behavior.md) veya [/za](../build/reference/za-ze-disable-language-extensions.md) kullanabilirsiniz. Bu durumda işlevler, bağımsız değişkenleri program yığınına döndürmek yerine doğrudan kayan nokta yongasına geçiren kitaplık yordamları olarak oluşturulur.

Bilgi için bkz. [#pragma işlevi](../preprocessor/function-c-cpp.md) ve kaynak metin bloğu için iç bilgileri etkinleştirme/devre dışı bırakma hakkında bir örnek.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)
