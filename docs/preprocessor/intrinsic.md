---
title: İç | Microsoft Docs
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- intrinsic_CPP
- vc-pragma.intrinsic
dev_langs:
- C++
helpviewer_keywords:
- intrinsic pragma
- pragmas, intrinsic
ms.assetid: 25c86ac7-ef40-47b7-a2c0-fada9c5dc3c5
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0c26d6eece62a0ae827fc661b92a3adc02d0a6d5
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="intrinsic"></a>içi

Pragmanın bağımsız değişken listesinde belirtilen işlevlere yapılan çağrıların iç olduğunu belirtir.

## <a name="syntax"></a>Sözdizimi

```cpp
#pragma intrinsic( function1 [, function2, ...] )
```

## <a name="remarks"></a>Açıklamalar

**İç** pragma bir işlev davranışı bilinen var. derleyici söyler.  Derleyici, işlevi çağırabilir ve daha iyi performans gösterecekse işlev çağrısını satır içi yönergelerle değiştirmeyebilir.

İç biçimlere sahip kitaplık işlevleri aşağıda listelenmiştir. Bir kez bir **iç** pragma görüldüğü, belirtilen bir iç işlevi içeren ilk işlev tanımı etkili olur. Kaynak dosyanın sonuna veya görünümünü etkisi devam bir **işlevi** pragma aynı iç işlevi belirtme. **İç** pragma yalnızca bir işlev tanımı dışında kullanılabilir — genel düzeyde.

İç forms aşağıdaki işlevlere sahiptir ve iç forms belirttiğinizde kullanılan [/Oi](../build/reference/oi-generate-intrinsic-functions.md):

|||||
|-|-|-|-|
|[_disable](../intrinsics/disable.md)|[_outp](../c-runtime-library/outp-outpw-outpd.md)|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|
|[_enable](../intrinsics/enable.md)|[_outpw](../c-runtime-library/outp-outpw-outpd.md)|[Labs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|
|[_inp](../c-runtime-library/inp-inpw-inpd.md)|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|
|[_inpw](../c-runtime-library/inp-inpw-inpd.md)|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)||
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|[memset](../c-runtime-library/reference/memset-wmemset.md)||
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|[Abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)||

İç işlevler kullanan programlar, işlev çağrılarının ek yükü olmadığı için daha hızlıdır, ancak oluşturulan ek kod nedeniyle daha büyük olabilir.

**x86 belirli**

**_Disable** ve **_tcp** ön tanımlı devre dışı bırak/kesmeler etkinleştirmek için çekirdek modu yönergeleri oluşturur ve çekirdek modu sürücüleri yararlı olabilir.

### <a name="example"></a>Örnek

"cl -c -FAs sample.c" ile komut satırından aşağıdaki kodu derleyin ve x86 yönergeleri CLI ve STI'ya dönüşüp dönüşmediklerini görmek için sample.asm'yi inceleyin.

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

Aşağıda listelenen kayan nokta işlevlerinin, gerçek iç biçimleri yoktur. Bunun yerine, bağımsız değişkenleri program yığınına döndürmek yerine doğrudan kayan nokta yongasına geçiren sürümleri vardır:

|||||
|-|-|-|-|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|[COSH](../c-runtime-library/reference/cosh-coshf-coshl.md)|[POW](../c-runtime-library/reference/pow-powf-powl.md)|[TANH](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|[SİNH](../c-runtime-library/reference/sinh-sinhf-sinhl.md)||

 Belirttiğiniz zaman aşağıda listelenen kayan nokta işlevleri true iç forms sahip [/Oi](../build/reference/oi-generate-intrinsic-functions.md), [/Og](../build/reference/og-global-optimizations.md), ve [/fp:fast](../build/reference/fp-specify-floating-point-behavior.md) (veya /Og içeren herhangi bir seçenek: [/ Ox](../build/reference/ox-full-optimization.md), [/O1](../build/reference/o1-o2-minimize-size-maximize-speed.md)ve O2):

|||||
|-|-|-|-|
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[exp](../c-runtime-library/reference/exp-expf.md)|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|[tan](../c-runtime-library/reference/tan-tanf-tanl.md)|
|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)||||

Kullanabileceğiniz [/fp: katı](../build/reference/fp-specify-floating-point-behavior.md) veya [/Za](../build/reference/za-ze-disable-language-extensions.md) true iç kayan nokta seçenekleri nesil geçersiz kılmak için. Bu durumda işlevler, bağımsız değişkenleri program yığınına döndürmek yerine doğrudan kayan nokta yongasına geçiren kitaplık yordamları olarak oluşturulur.

Bkz: [#pragma işlevi](../preprocessor/function-c-cpp.md) bilgi ve ön tanımlı bir kaynak metin bloğu için etkinleştir/devre dışı bırak konusunda bir örnek için.

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
