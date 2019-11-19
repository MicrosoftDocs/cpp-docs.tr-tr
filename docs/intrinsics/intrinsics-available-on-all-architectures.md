---
title: Tüm mimarilerde kullanılabilen iç bilgiler
ms.date: 09/02/2019
helpviewer_keywords:
- cl.exe compiler, intrinsics
ms.assetid: 1fe3958e-d2fe-4188-8e34-5896738246eb
ms.openlocfilehash: 0293daacd717b3ae85b993729090fe363f7e0b9b
ms.sourcegitcommit: e805200eaef4fe7a65a00051bbd305273af94fe7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2019
ms.locfileid: "74163475"
---
# <a name="intrinsics-available-on-all-architectures"></a>Tüm mimarilerde kullanılabilen iç bilgiler

Microsoft C/C++ derleyicisini ve evrensel C çalışma zamanı kitaplığı (UCRT) tüm mimarilerde bazı iç bilgileri kullanılabilir hale getirir.

## <a name="compiler-intrinsics"></a>Derleyici iç bilgileri

Aşağıdaki iç bilgiler x86, AMD64, ARM ve ARM64 mimarilerinde kullanılabilir:

|Alanlarla|Üstbilgi|
|---------------|------------|
|[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)|Intrin. h|
|[_BitScanForward](../intrinsics/bitscanforward-bitscanforward64.md)|Intrin. h|
|[_BitScanReverse](../intrinsics/bitscanreverse-bitscanreverse64.md)|Intrin. h|
|[_bittest](../intrinsics/bittest-bittest64.md)|Intrin. h|
|[_bittestandcomplement](../intrinsics/bittestandcomplement-bittestandcomplement64.md)|Intrin. h|
|[_bittestandreset](../intrinsics/bittestandreset-bittestandreset64.md)|Intrin. h|
|[_bittestandset](../intrinsics/bittestandset-bittestandset64.md)|Intrin. h|
|__code_seg|Intrin. h|
|[__debugbreak](../intrinsics/debugbreak.md)|Intrin. h|
|[_disable](../intrinsics/disable.md)|Intrin. h|
|[_enable](../intrinsics/enable.md)|Intrin. h|
|[__fastfail](../intrinsics/fastfail.md)|Intrin. h|
|[_InterlockedAnd](../intrinsics/interlockedand-intrinsic-functions.md)|Intrin. h|
|[_InterlockedAnd16](../intrinsics/interlockedand-intrinsic-functions.md)|Intrin. h|
|[_InterlockedAnd8](../intrinsics/interlockedand-intrinsic-functions.md)|Intrin. h|
|[_interlockedbittestandreset](../intrinsics/interlockedbittestandreset-intrinsic-functions.md)|Intrin. h|
|[_interlockedbittestandset](../intrinsics/interlockedbittestandset-intrinsic-functions.md)|Intrin. h|
|[_InterlockedCompareExchange](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|Intrin. h|
|[_InterlockedCompareExchange16](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|Intrin. h|
|[_InterlockedCompareExchange8](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|Intrin. h|
|[_InterlockedCompareExchangePointer](../intrinsics/interlockedcompareexchangepointer-intrinsic-functions.md)|Intrin. h|
|[_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md)|Intrin. h|
|[_InterlockedDecrement16](../intrinsics/interlockeddecrement-intrinsic-functions.md)|Intrin. h|
|[_InterlockedExchange](../intrinsics/interlockedexchange-intrinsic-functions.md)|Intrin. h|
|[_InterlockedExchange16](../intrinsics/interlockedexchange-intrinsic-functions.md)|Intrin. h|
|[_InterlockedExchange8](../intrinsics/interlockedexchange-intrinsic-functions.md)|Intrin. h|
|[_InterlockedExchangeAdd](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|Intrin. h|
|[_InterlockedExchangeAdd16](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|Intrin. h|
|[_InterlockedExchangeAdd8](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|Intrin. h|
|[_InterlockedExchangePointer](../intrinsics/interlockedexchangepointer-intrinsic-functions.md)|Intrin. h|
|[_InterlockedIncrement](../intrinsics/interlockedincrement-intrinsic-functions.md)|Intrin. h|
|[_InterlockedIncrement16](../intrinsics/interlockedincrement-intrinsic-functions.md)|Intrin. h|
|[_InterlockedOr](../intrinsics/interlockedor-intrinsic-functions.md)|Intrin. h|
|[_InterlockedOr16](../intrinsics/interlockedor-intrinsic-functions.md)|Intrin. h|
|[_InterlockedOr8](../intrinsics/interlockedor-intrinsic-functions.md)|Intrin. h|
|[_InterlockedXor](../intrinsics/interlockedxor-intrinsic-functions.md)|Intrin. h|
|[_InterlockedXor16](../intrinsics/interlockedxor-intrinsic-functions.md)|Intrin. h|
|[_InterlockedXor8](../intrinsics/interlockedxor-intrinsic-functions.md)|Intrin. h|
|[__nop](../intrinsics/nop.md)|Intrin. h|
|[_ReadBarrier](../intrinsics/readbarrier.md)|Intrin. h|
|[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)|Intrin. h|
|[_ReturnAddress](../intrinsics/returnaddress.md)|Intrin. h|
|[_rotl16](../intrinsics/rotl8-rotl16.md)|Intrin. h|
|[_rotl8](../intrinsics/rotl8-rotl16.md)|Intrin. h|
|[_rotr16](../intrinsics/rotr8-rotr16.md)|Intrin. h|
|[_rotr8](../intrinsics/rotr8-rotr16.md)|Intrin. h|
|[_WriteBarrier](../intrinsics/writebarrier.md)|Intrin. h|

## <a name="ucrt-intrinsics"></a>UCRT iç öğeleri

Aşağıdaki UCRT işlevleri tüm mimarilerde iç formlara sahiptir:

|Alanlarla|Üstbilgi|
|---------------|------------|
|[mutlak](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Stdlib. h|
|[_abs64](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Stdlib. h|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|Math. h|
|[acosf](../c-runtime-library/reference/acos-acosf-acosl.md)|Math. h|
|[acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|Math. h|
|[_alloca](../c-runtime-library/reference/alloca.md)|malloc. h|
|[Asin](../c-runtime-library/reference/asin-asinf-asinl.md)|Math. h|
|[asinf](../c-runtime-library/reference/asin-asinf-asinl.md)|Math. h|
|[asinl](../c-runtime-library/reference/asin-asinf-asinl.md)|Math. h|
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math. h|
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math. h|
|[atan2f](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math. h|
|[atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math. h|
|[atanf](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math. h|
|[atanl](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math. h|
|[_byteswap_uint64](../c-runtime-library/reference/byteswap-uint64-byteswap-ulong-byteswap-ushort.md)|Stdlib. h|
|[_byteswap_ulong](../c-runtime-library/reference/byteswap-uint64-byteswap-ulong-byteswap-ushort.md)|Stdlib. h|
|[_byteswap_ushort](../c-runtime-library/reference/byteswap-uint64-byteswap-ulong-byteswap-ushort.md)|Stdlib. h|
|[Ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Math. h|
|[ceilf](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Math. h|
|[ceill](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Math. h|
|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)|Math. h|
|[cosf](../c-runtime-library/reference/cos-cosf-cosl.md)|Math. h|
|[Cosh](../c-runtime-library/reference/cosh-coshf-coshl.md)|Math. h|
|[coshf](../c-runtime-library/reference/cosh-coshf-coshl.md)|Math. h|
|[coshl](../c-runtime-library/reference/cosh-coshf-coshl.md)|Math. h|
|[COSL](../c-runtime-library/reference/cos-cosf-cosl.md)|Math. h|
|[exp](../c-runtime-library/reference/exp-expf.md)|Math. h|
|[expf](../c-runtime-library/reference/exp-expf.md)|Math. h|
|[expl](../c-runtime-library/reference/exp-expf.md)|Math. h|
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Math. h|
|[fabsf](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Math. h|
|[sını](../c-runtime-library/reference/floor-floorf-floorl.md)|Math. h|
|[floorf](../c-runtime-library/reference/floor-floorf-floorl.md)|Math. h|
|[floorl](../c-runtime-library/reference/floor-floorf-floorl.md)|Math. h|
|[FMOD](../c-runtime-library/reference/fmod-fmodf.md)|Math. h|
|[fmodf](../c-runtime-library/reference/fmod-fmodf.md)|Math. h|
|[fmodl](../c-runtime-library/reference/fmod-fmodf.md)|Math. h|
|[larda](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Stdlib. h|
|[LLabs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|Stdlib. h|
|[açmasını](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math. h|
|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math. h|
|[log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math. h|
|[log10l](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math. h|
|[logf](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math. h|
|[günlüğe kaydetme](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math. h|
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|Stdlib. h|
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|Stdlib. h|
|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|String. h|
|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)|String. h|
|[memset](../c-runtime-library/reference/memset-wmemset.md)|String. h|
|[POW](../c-runtime-library/reference/pow-powf-powl.md)|Math. h|
|[powf](../c-runtime-library/reference/pow-powf-powl.md)|Math. h|
|[ptıl](../c-runtime-library/reference/pow-powf-powl.md)|Math. h|
|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Stdlib. h|
|[_rotl64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Stdlib. h|
|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Stdlib. h|
|[_rotr64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|Stdlib. h|
|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|Math. h|
|[sinf](../c-runtime-library/reference/sin-sinf-sinl.md)|Math. h|
|[sinh](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|Math. h|
|[sinhf](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|Math. h|
|[sinhl](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|Math. h|
|[sinl](../c-runtime-library/reference/sin-sinf-sinl.md)|Math. h|
|[k](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Math. h|
|[sqrtf](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Math. h|
|[sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Math. h|
|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)|String. h|
|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|String. h|
|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|String. h|
|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|String. h|
|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|String. h|
|[strset](../c-runtime-library/reference/strset-wcsset.md)|String. h|
|[Başlangıçtan](../c-runtime-library/reference/tan-tanf-tanl.md)|Math. h|
|[tanf](../c-runtime-library/reference/tan-tanf-tanl.md)|Math. h|
|[tanh](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|Math. h|
|[tanhf](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|Math. h|
|[tanhl](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|Math. h|
|[tanl](../c-runtime-library/reference/tan-tanf-tanl.md)|Math. h|
|[wcscat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)|String. h|
|[wcscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|String. h|
|[wcscpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|String. h|
|[wcslen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|String. h|
|[_wcsset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|String. h|

## <a name="see-also"></a>Ayrıca bkz.

[ARM iç](../intrinsics/arm-intrinsics.md) bilgileri\
[ARM64 iç](../intrinsics/arm64-intrinsics.md)\
[x86 iç bilgi listesi](../intrinsics/x86-intrinsics-list.md)\
[x64 (amd64) iç bilgi listesi](../intrinsics/x64-amd64-intrinsics-list.md)
