---
title: Tüm mimarilerde kullanılabilen iç bilgiler
ms.date: 04/11/2018
helpviewer_keywords:
- cl.exe compiler, intrinsics
ms.assetid: 1fe3958e-d2fe-4188-8e34-5896738246eb
ms.openlocfilehash: 0a1331f53cd8b44c8a7bfc903216cbdbaf5fec1f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62396671"
---
# <a name="intrinsics-available-on-all-architectures"></a>Tüm mimarilerde kullanılabilen iç bilgiler

Microsoft C/C++ derleyicisi ve evrensel C Çalışma Zamanı Kitaplığı'nı (UCRT) bazı iç öğeler tüm mimarilerde kullanımına sunun.

## <a name="compiler-intrinsics"></a>Derleyici iç bilgileri

Aşağıdaki yapı içlerini x86, AMD64, kullanılabilir ve ARM mimarileri:

|İç|Üstbilgi|
|---------------|------------|
|[_AddressOfReturnAddress](../intrinsics/addressofreturnaddress.md)|intrin.h|
|[_BitScanForward](../intrinsics/bitscanforward-bitscanforward64.md)|intrin.h|
|[_BitScanForward64](../intrinsics/bitscanforward-bitscanforward64.md)|intrin.h|
|[_BitScanReverse](../intrinsics/bitscanreverse-bitscanreverse64.md)|intrin.h|
|[_BitScanReverse64](../intrinsics/bitscanreverse-bitscanreverse64.md)|intrin.h|
|[_bittest](../intrinsics/bittest-bittest64.md)|intrin.h|
|[_bittest64](../intrinsics/bittest-bittest64.md)|intrin.h|
|[_bittestandcomplement](../intrinsics/bittestandcomplement-bittestandcomplement64.md)|intrin.h|
|[_bittestandcomplement64](../intrinsics/bittestandcomplement-bittestandcomplement64.md)|intrin.h|
|[_bittestandreset](../intrinsics/bittestandreset-bittestandreset64.md)|intrin.h|
|[_bittestandreset64](../intrinsics/bittestandreset-bittestandreset64.md)|intrin.h|
|[_bittestandset](../intrinsics/bittestandset-bittestandset64.md)|intrin.h|
|[_bittestandset64](../intrinsics/bittestandset-bittestandset64.md)|intrin.h|
|[__debugbreak](../intrinsics/debugbreak.md)|intrin.h|
|[_disable](../intrinsics/disable.md)|intrin.h|
|[_enable](../intrinsics/enable.md)|intrin.h|
|[__fastfail](../intrinsics/fastfail.md)|intrin.h|
|[_Interlockedand](../intrinsics/interlockedand-intrinsic-functions.md)|intrin.h|
|[_InterlockedAnd16](../intrinsics/interlockedand-intrinsic-functions.md)|intrin.h|
|[_InterlockedAnd64](../intrinsics/interlockedand-intrinsic-functions.md)|intrin.h|
|[_InterlockedAnd8](../intrinsics/interlockedand-intrinsic-functions.md)|intrin.h|
|[_interlockedbittestandreset](../intrinsics/interlockedbittestandreset-intrinsic-functions.md)|intrin.h|
|[_interlockedbittestandset](../intrinsics/interlockedbittestandset-intrinsic-functions.md)|intrin.h|
|[_InterlockedCompareExchange](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|intrin.h|
|[_InterlockedCompareExchange16](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|intrin.h|
|[_InterlockedCompareExchange64](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|intrin.h|
|[_InterlockedCompareExchange8](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)|intrin.h|
|[_InterlockedCompareExchangePointer](../intrinsics/interlockedcompareexchangepointer-intrinsic-functions.md)|intrin.h|
|[_InterlockedDecrement16](../intrinsics/interlockeddecrement-intrinsic-functions.md)|intrin.h|
|[_InterlockedDecrement64](../intrinsics/interlockeddecrement-intrinsic-functions.md)|intrin.h|
|[_Interlockedexchange](../intrinsics/interlockedexchange-intrinsic-functions.md)|intrin.h|
|[_InterlockedExchange16](../intrinsics/interlockedexchange-intrinsic-functions.md)|intrin.h|
|[_InterlockedExchange64](../intrinsics/interlockedexchange-intrinsic-functions.md)|intrin.h|
|[_InterlockedExchange8](../intrinsics/interlockedexchange-intrinsic-functions.md)|intrin.h|
|[_InterlockedExchangeAdd](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|intrin.h|
|[_InterlockedExchangeAdd16](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|intrin.h|
|[_InterlockedExchangeAdd64](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|intrin.h|
|[_InterlockedExchangeAdd8](../intrinsics/interlockedexchangeadd-intrinsic-functions.md)|intrin.h|
|[_InterlockedExchangePointer](../intrinsics/interlockedexchangepointer-intrinsic-functions.md)|intrin.h|
|[_Interlockedıncrement](../intrinsics/interlockedincrement-intrinsic-functions.md)|intrin.h|
|[_InterlockedIncrement16](../intrinsics/interlockedincrement-intrinsic-functions.md)|intrin.h|
|[_InterlockedIncrement64](../intrinsics/interlockedincrement-intrinsic-functions.md)|intrin.h|
|[_InterlockedOr](../intrinsics/interlockedor-intrinsic-functions.md)|intrin.h|
|[_InterlockedOr16](../intrinsics/interlockedor-intrinsic-functions.md)|intrin.h|
|[_InterlockedOr64](../intrinsics/interlockedor-intrinsic-functions.md)|intrin.h|
|[_InterlockedOr8](../intrinsics/interlockedor-intrinsic-functions.md)|intrin.h|
|[_Interlockedxor](../intrinsics/interlockedxor-intrinsic-functions.md)|intrin.h|
|[_InterlockedXor16](../intrinsics/interlockedxor-intrinsic-functions.md)|intrin.h|
|[_InterlockedXor64](../intrinsics/interlockedxor-intrinsic-functions.md)|intrin.h|
|[_InterlockedXor8](../intrinsics/interlockedxor-intrinsic-functions.md)|intrin.h|
|[_mul128](../intrinsics/mul128.md)|intrin.h|
|[__mulh](../intrinsics/mulh.md)|intrin.h|
|[__nop](../intrinsics/nop.md)|intrin.h|
|[_ReadBarrier](../intrinsics/readbarrier.md)|intrin.h|
|[_ReadWriteBarrier](../intrinsics/readwritebarrier.md)|intrin.h|
|[_ReturnAddress](../intrinsics/returnaddress.md)|intrin.h|
|[_rotl16](../intrinsics/rotl8-rotl16.md)|intrin.h|
|[_rotl8](../intrinsics/rotl8-rotl16.md)|intrin.h|
|[_rotr16](../intrinsics/rotr8-rotr16.md)|intrin.h|
|[_rotr8](../intrinsics/rotr8-rotr16.md)|intrin.h|
|[__shiftleft128](../intrinsics/shiftleft128.md)|intrin.h|
|[__shiftright128](../intrinsics/shiftright128.md)|intrin.h|
|[_umul128](../intrinsics/umul128.md)|intrin.h|
|[__umulh](../intrinsics/umulh.md)|intrin.h|
|[_WriteBarrier](../intrinsics/writebarrier.md)|intrin.h|

## <a name="ucrt-intrinsics"></a>UCRT iç bilgileri

Aşağıdaki UCRT işlevleri tüm mimarilerde iç biçimleri vardır:

|İç|Üstbilgi|
|---------------|------------|
|[Abs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|stdlıb.h|
|[_abs64](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|stdlıb.h|
|[acos](../c-runtime-library/reference/acos-acosf-acosl.md)|Math.h|
|[acosf](../c-runtime-library/reference/acos-acosf-acosl.md)|Math.h|
|[acosl](../c-runtime-library/reference/acos-acosf-acosl.md)|Math.h|
|[_alloca](../c-runtime-library/reference/alloca.md)|malloc.h|
|[asin](../c-runtime-library/reference/asin-asinf-asinl.md)|Math.h|
|[asinf](../c-runtime-library/reference/asin-asinf-asinl.md)|Math.h|
|[asinl](../c-runtime-library/reference/asin-asinf-asinl.md)|Math.h|
|[atan](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math.h|
|[atan2](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math.h|
|[atan2f](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math.h|
|[atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math.h|
|[atanf](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math.h|
|[atanl](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)|Math.h|
|[_byteswap_uint64](../c-runtime-library/reference/byteswap-uint64-byteswap-ulong-byteswap-ushort.md)|stdlıb.h|
|[_byteswap_ulong](../c-runtime-library/reference/byteswap-uint64-byteswap-ulong-byteswap-ushort.md)|stdlıb.h|
|[_byteswap_ushort](../c-runtime-library/reference/byteswap-uint64-byteswap-ulong-byteswap-ushort.md)|stdlıb.h|
|[ceil](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Math.h|
|[ceilf](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Math.h|
|[ceill](../c-runtime-library/reference/ceil-ceilf-ceill.md)|Math.h|
|[cos](../c-runtime-library/reference/cos-cosf-cosl.md)|Math.h|
|[cosf](../c-runtime-library/reference/cos-cosf-cosl.md)|Math.h|
|[COSH](../c-runtime-library/reference/cosh-coshf-coshl.md)|Math.h|
|[coshf](../c-runtime-library/reference/cosh-coshf-coshl.md)|Math.h|
|[coshl](../c-runtime-library/reference/cosh-coshf-coshl.md)|Math.h|
|[cosl](../c-runtime-library/reference/cos-cosf-cosl.md)|Math.h|
|[exp](../c-runtime-library/reference/exp-expf.md)|Math.h|
|[expf](../c-runtime-library/reference/exp-expf.md)|Math.h|
|[expl](../c-runtime-library/reference/exp-expf.md)|Math.h|
|[fabs](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Math.h|
|[fabsf](../c-runtime-library/reference/fabs-fabsf-fabsl.md)|Math.h|
|[Kat](../c-runtime-library/reference/floor-floorf-floorl.md)|Math.h|
|[floorf](../c-runtime-library/reference/floor-floorf-floorl.md)|Math.h|
|[floorl](../c-runtime-library/reference/floor-floorf-floorl.md)|Math.h|
|[fmod](../c-runtime-library/reference/fmod-fmodf.md)|Math.h|
|[fmodf](../c-runtime-library/reference/fmod-fmodf.md)|Math.h|
|[fmodl](../c-runtime-library/reference/fmod-fmodf.md)|Math.h|
|[Laboratuvarları](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|stdlıb.h|
|[llabs](../c-runtime-library/reference/abs-labs-llabs-abs64.md)|stdlıb.h|
|[log](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math.h|
|[log10](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math.h|
|[log10f](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math.h|
|[log10l](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math.h|
|[logf](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math.h|
|[logl](../c-runtime-library/reference/log-logf-log10-log10f.md)|Math.h|
|[_lrotl](../c-runtime-library/reference/lrotl-lrotr.md)|stdlıb.h|
|[_lrotr](../c-runtime-library/reference/lrotl-lrotr.md)|stdlıb.h|
|[memcmp](../c-runtime-library/reference/memcmp-wmemcmp.md)|String.h|
|[memcpy](../c-runtime-library/reference/memcpy-wmemcpy.md)|String.h|
|[memset](../c-runtime-library/reference/memset-wmemset.md)|String.h|
|[POW](../c-runtime-library/reference/pow-powf-powl.md)|Math.h|
|[powf](../c-runtime-library/reference/pow-powf-powl.md)|Math.h|
|[powl](../c-runtime-library/reference/pow-powf-powl.md)|Math.h|
|[_rotl](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|stdlıb.h|
|[_rotl64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|stdlıb.h|
|[_rotr](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|stdlıb.h|
|[_rotr64](../c-runtime-library/reference/rotl-rotl64-rotr-rotr64.md)|stdlıb.h|
|[sin](../c-runtime-library/reference/sin-sinf-sinl.md)|Math.h|
|[sinf](../c-runtime-library/reference/sin-sinf-sinl.md)|Math.h|
|[SİNH](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|Math.h|
|[sinhf](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|Math.h|
|[sinhl](../c-runtime-library/reference/sinh-sinhf-sinhl.md)|Math.h|
|[sinl](../c-runtime-library/reference/sin-sinf-sinl.md)|Math.h|
|[sqrt](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Math.h|
|[sqrtf](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Math.h|
|[sqrtl](../c-runtime-library/reference/sqrt-sqrtf-sqrtl.md)|Math.h|
|[strcat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)|String.h|
|[strcmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|String.h|
|[strcpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|String.h|
|[strlen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|String.h|
|[_strset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|String.h|
|[strset](../c-runtime-library/reference/strset-wcsset.md)|String.h|
|[tan](../c-runtime-library/reference/tan-tanf-tanl.md)|Math.h|
|[tanf](../c-runtime-library/reference/tan-tanf-tanl.md)|Math.h|
|[TANH](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|Math.h|
|[tanhf](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|Math.h|
|[tanhl](../c-runtime-library/reference/tanh-tanhf-tanhl.md)|Math.h|
|[tanl](../c-runtime-library/reference/tan-tanf-tanl.md)|Math.h|
|[wcscat](../c-runtime-library/reference/strcat-wcscat-mbscat.md)|String.h|
|[wcscmp](../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)|String.h|
|[wcscpy](../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)|String.h|
|[wcslen](../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)|String.h|
|[_wcsset](../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)|String.h|

## <a name="see-also"></a>Ayrıca bkz.

[ARM İç Bilgileri](../intrinsics/arm-intrinsics.md)<br/>
[x86 İç Bilgi Listesi](../intrinsics/x86-intrinsics-list.md)<br/>
[x64 (amd64) İç Bilgi Listesi](../intrinsics/x64-amd64-intrinsics-list.md)<br/>
