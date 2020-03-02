---
title: x86 iç bilgi listesi
ms.date: 02/28/2020
helpviewer_keywords:
- cl.exe compiler, intrinsics
- intrinsics, x86
ms.openlocfilehash: 00d10668b791303d7f5f27cacdb1ab8021470ae3
ms.sourcegitcommit: ab8d7b47b63b62892a1256a09b1324a9a136eccf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/02/2020
ms.locfileid: "78215483"
---
# <a name="x86-intrinsics-list"></a>x86 iç bilgi listesi

Bu belgede, x86 hedeflendiğinde Microsoft C/C++ derleyicisinin desteklediği iç bilgiler listelenir.

Tek tek yapı içleri hakkında daha fazla bilgi için, hedeflediğiniz işlemciye uygun şekilde şu kaynaklara bakabilirsiniz:

- Üst bilgi dosyası. Birçok iç yapı, üstbilgi dosyasındaki açıklamalarda belgelenmiştir.

- [Intel Içiç Kılavuzu](https://software.intel.com/sites/landingpage/IntrinsicsGuide/). Belirli iç bilgileri bulmak için arama kutusunu kullanın.

- [Intel 64 ve IA-32 mimarileri yazılım geliştirici el kitabı](https://software.intel.com/articles/intel-sdm)

- [Intel mimari yönerge kümesi uzantıları programlama başvurusu](https://software.intel.com/isa-extensions)

- [Intel Gelişmiş vektör uzantılarına giriş](https://software.intel.com/articles/introduction-to-intel-advanced-vector-extensions)

- [AMD geliştirici kılavuzları, el kitabı & ISA belgeleri](https://developer.amd.com/resources/developer-guides-manuals/)

## <a name="x86-intrinsics"></a>x86 iç bilgileri

Aşağıdaki tabloda, x86 işlemcilerde kullanılabilen iç bilgiler listelenmektedir. Technology sütununda gerekli yönerge kümesi desteği listelenmektedir. Çalışma zamanında yönerge kümesi desteğini belirleme [__cpuid](cpuid-cpuidex.md) iç öğesini kullanın. İki giriş bir satırdaysa, aynı iç öğe için farklı giriş noktalarını temsil ederler. [1], iç, yalnızca AMD işlemcilerde kullanılabilir olduğunu gösterir. [2], iç, yalnızca Intel işlemcilerde kullanılabilir olduğunu gösterir. [3] prototipi bir makro olduğunu gösterir. İşlev prototipi için gereken üst bilgi, üstbilgi sütununda listelenir. Intrin. h üst bilgisi, basitlik için hem ımmintrin. h hem de ammintrin. h içerir.

|Yapı içi adı|Teknoloji|Üst bilgi|İşlev prototipi|
|--------------------|----------------|------------|------------------------|
|_addcarry_u16||Intrin. h|işaretsiz char _addcarry_u16 (işaretsiz char, işaretsiz kısa, işaretsiz kısa, işaretsiz kısa \*)|
|[_addcarry_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_addcarry_u32)||Intrin. h|işaretsiz char _addcarry_u32 (işaretsiz char, işaretsiz int, işaretsiz int, işaretsiz int \*)|
|_addcarry_u8||Intrin. h|işaretsiz char _addcarry_u8 (işaretsiz char, işaretsiz char, işaretsiz karakter, işaretsiz char \*)|
|[_addcarryx_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_addcarryx_u32)|ADX [2]|ımintrin. h|işaretsiz char _addcarryx_u32 (işaretsiz char, işaretsiz int, işaretsiz int, işaretsiz int \*)|
|[__addfsbyte](addfsbyte-addfsword-addfsdword.md)||Intrin. h|void __addfsbyte (işaretsiz Long, işaretsiz Char)|
|[__addfsdword](addfsbyte-addfsword-addfsdword.md)||Intrin. h|void __addfsdword (işaretsiz Long, unsigned long)|
|[__addfsword](addfsbyte-addfsword-addfsdword.md)||Intrin. h|void __addfsword (işaretsiz Long, işaretsiz Short)|
|[_AddressOfReturnAddress](addressofreturnaddress.md)||Intrin. h|void \* _AddressOfReturnAddress (void)|
|[_andn_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_andn_u32)|BMI [1]|ammintrin. h|işaretsiz int _andn_u32 (işaretsiz int, işaretsiz int)|
|[_bextr_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_bextr_u32)|BMI|ammintrin. h, immintrin. h|işaretsiz int _bextr_u32 (işaretsiz int, işaretsiz int, işaretsiz int)|
|_bextri_u32|ABM [1]|ammintrin. h|işaretsiz int _bextri_u32 (işaretsiz int, işaretsiz int)|
|[_BitScanForward](bitscanforward-bitscanforward64.md)||Intrin. h|işaretsiz karakter _BitScanForward (işaretsiz Long\*, işaretsiz Long)|
|[_BitScanReverse](bitscanreverse-bitscanreverse64.md)||Intrin. h|işaretsiz karakter _BitScanReverse (işaretsiz Long\*, işaretsiz Long)|
|[_bittest](bittest-bittest64.md)||Intrin. h|işaretsiz char _bittest (uzun const \*, Long)|
|[_bittestandcomplement](bittestandcomplement-bittestandcomplement64.md)||Intrin. h|işaretsiz karakter _bittestandcomplement (uzun \*, uzun)|
|[_bittestandreset](bittestandreset-bittestandreset64.md)||Intrin. h|işaretsiz karakter _bittestandreset (uzun \*, uzun)|
|[_bittestandset](bittestandset-bittestandset64.md)||Intrin. h|işaretsiz karakter _bittestandset (uzun \*, uzun)|
|_blcfill_u32|ABM [1]|ammintrin. h|işaretsiz int _blcfill_u32 (işaretsiz int)|
|_blci_u32|ABM [1]|ammintrin. h|işaretsiz int _blci_u32 (işaretsiz int)|
|_blcic_u32|ABM [1]|ammintrin. h|işaretsiz int _blcic_u32 (işaretsiz int)|
|_blcmsk_u32|ABM [1]|ammintrin. h|işaretsiz int _blcmsk_u32 (işaretsiz int)|
|_blcs_u32|ABM [1]|ammintrin. h|işaretsiz int _blcs_u32 (işaretsiz int)|
|_blsfill_u32|ABM [1]|ammintrin. h|işaretsiz int _blsfill_u32 (işaretsiz int)|
|[_blsi_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_blsi_u32)|BMI|ammintrin. h, immintrin. h|işaretsiz int _blsi_u32 (işaretsiz int)|
|_blsic_u32|ABM [1]|ammintrin. h|işaretsiz int _blsic_u32 (işaretsiz int)|
|[_blsmsk_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_blsmsk_u32)|BMI|ammintrin. h, immintrin. h|işaretsiz int _blsmsk_u32 (işaretsiz int)|
|[_blsr_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_blsr_u32)|BMI|ammintrin. h, immintrin. h|işaretsiz int _blsr_u32 (işaretsiz int)|
|[_bzhi_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_bzhi_u32)|BMI [2]|ımintrin. h|işaretsiz int _bzhi_u32 (işaretsiz int, işaretsiz int)|
|_clac|SMAP|Intrin. h|void _clac (void)|
|[__cpuid](cpuid-cpuidex.md)||Intrin. h|void __cpuid (int \*, int)|
|[__cpuidex](cpuid-cpuidex.md)||Intrin. h|void __cpuidex (int \*, int, int)|
|[__debugbreak](debugbreak.md)||Intrin. h|void __debugbreak (void)|
|[_disable](disable.md)||Intrin. h|void _disable (void)|
|[_div64](div64.md)||Intrin. h| int \_div64 (\__int64, int, int \*)|
|[__emul](emul-emulu.md)||Intrin. h|__int64 [Pascal/cdecl] \__emul (int, int)|
|[__emulu](emul-emulu.md)||Intrin. h|işaretsiz __int64 [Pascal/cdecl]\__emulu (işaretsiz int, işaretsiz int)|
|[_enable](enable.md)||Intrin. h|void _enable (void)|
|[__fastfail](fastfail.md)||Intrin. h|void __fastfail (işaretsiz int)|
|[_fxrstor](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_fxrstor)|FXSR [2]|ımintrin. h|void _fxrstor (const\*void)|
|[_fxsave](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_fxsave)|FXSR [2]|ımintrin. h|void _fxsave (void\*)|
|[__getcallerseflags](getcallerseflags.md)||Intrin. h|(işaretsiz int __getcallerseflags ())|
|[__halt](halt.md)||Intrin. h|void __halt (void)|
|[__inbyte](inbyte.md)||Intrin. h|işaretsiz char __inbyte (işaretsiz kısa)|
|[__inbytestring](inbytestring.md)||Intrin. h|void __inbytestring (işaretsiz kısa, işaretsiz char \*, işaretsiz Long)|
|[__incfsbyte](incfsbyte-incfsword-incfsdword.md)||Intrin. h|void __incfsbyte (imzasız Long)|
|[__incfsdword](incfsbyte-incfsword-incfsdword.md)||Intrin. h|void __incfsdword (imzasız Long)|
|[__incfsword](incfsbyte-incfsword-incfsdword.md)||Intrin. h|void __incfsword (imzasız Long)|
|[__indword](indword.md)||Intrin. h|işaretsiz Long __indword (işaretsiz kısa)|
|[__indwordstring](indwordstring.md)||Intrin. h|void __indwordstring (işaretsiz kısa, işaretsiz uzun \*, işaretsiz uzun)|
|[__int2c](int2c.md)||Intrin. h|void __int2c (void)|
|[_InterlockedAddLargeStatistic](interlockedaddlargestatistic.md)||Intrin. h|uzun _InterlockedAddLargeStatistic (\__int64 geçici \*, uzun)|
|[_InterlockedAnd](interlockedand-intrinsic-functions.md)||Intrin. h|uzun _InterlockedAnd (uzun geçici \*, uzun)|
|[_InterlockedAnd_HLEAcquire](interlockedand-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedAnd_HLEAcquire (uzun geçici \*, uzun)|
|[_InterlockedAnd_HLERelease](interlockedand-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedAnd_HLERelease (uzun geçici \*, uzun)|
|[_InterlockedAnd16](interlockedand-intrinsic-functions.md)||Intrin. h|kısa _InterlockedAnd16 (kısa geçici \*, kısa)|
|[_InterlockedAnd8](interlockedand-intrinsic-functions.md)||Intrin. h|Char _InterlockedAnd8 (Char volatile \*, Char)|
|[_interlockedbittestandreset](interlockedbittestandreset-intrinsic-functions.md)||Intrin. h|işaretsiz karakter _interlockedbittestandreset (uzun \*, uzun)|
|[_interlockedbittestandreset_HLEAcquire](interlockedbittestandreset-intrinsic-functions.md)|HLE [2]|ımintrin. h|işaretsiz karakter _interlockedbittestandreset_HLEAcquire (uzun \*, uzun)|
|[_interlockedbittestandreset_HLERelease](interlockedbittestandreset-intrinsic-functions.md)|HLE [2]|ımintrin. h|işaretsiz karakter _interlockedbittestandreset_HLERelease (uzun \*, uzun)|
|[_interlockedbittestandset](interlockedbittestandset-intrinsic-functions.md)||Intrin. h|işaretsiz karakter _interlockedbittestandset (uzun \*, uzun)|
|[_interlockedbittestandset_HLEAcquire](interlockedbittestandset-intrinsic-functions.md)|HLE [2]|ımintrin. h|işaretsiz karakter _interlockedbittestandset_HLEAcquire (uzun \*, uzun)|
|[_interlockedbittestandset_HLERelease](interlockedbittestandset-intrinsic-functions.md)|HLE [2]|ımintrin. h|işaretsiz karakter _interlockedbittestandset_HLERelease (uzun \*, uzun)|
|[_InterlockedCompareExchange](interlockedcompareexchange-intrinsic-functions.md)||Intrin. h|uzun _InterlockedCompareExchange (uzun geçici \*, uzun, uzun)|
|[_InterlockedCompareExchange_HLEAcquire](interlockedcompareexchange-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedCompareExchange_HLEAcquire (uzun geçici \*, uzun, uzun)|
|[_InterlockedCompareExchange_HLERelease](interlockedcompareexchange-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedCompareExchange_HLERelease (uzun geçici \*, uzun, uzun)|
|[_InterlockedCompareExchange16](interlockedcompareexchange-intrinsic-functions.md)||Intrin. h|kısa _InterlockedCompareExchange16 (kısa geçici \*, kısa, kısa)|
|[_InterlockedCompareExchange64](interlockedcompareexchange-intrinsic-functions.md)||Intrin. h|__int64 _InterlockedCompareExchange64 (\__int64 geçici \*, \__int64, \__int64)|
|[_InterlockedCompareExchange64_HLEAcquire](interlockedcompareexchange-intrinsic-functions.md)|HLE [2]|ımintrin. h|__int64 _InterlockedCompareExchange64_HLEAcquire (\__int64 geçici \*, \__int64, \__int64)|
|[_InterlockedCompareExchange64_HLERelease](interlockedcompareexchange-intrinsic-functions.md)|HLE [2]|ımintrin. h|__int64 _InterlockedCompareExchange64_HLERelease (\__int64 geçici \*, \__int64, \__int64)|
|[_InterlockedCompareExchange8](interlockedcompareexchange-intrinsic-functions.md)||Intrin. h|Char _InterlockedCompareExchange8 (Char volatile \*, Char, Char)|
|[_InterlockedCompareExchangePointer](interlockedcompareexchangepointer-intrinsic-functions.md)||Intrin. h|void \*_InterlockedCompareExchangePointer (void \*geçici \*, void \*, void \*)|
|[_InterlockedCompareExchangePointer_HLEAcquire](interlockedcompareexchangepointer-intrinsic-functions.md)|HLE [2]|ımintrin. h|void \*_InterlockedCompareExchangePointer_HLEAcquire (void \*geçici \*, void \*, void \*)|
|[_InterlockedCompareExchangePointer_HLERelease](interlockedcompareexchangepointer-intrinsic-functions.md)|HLE [2]|ımintrin. h|void \*_InterlockedCompareExchangePointer_HLERelease (void \*geçici \*, void \*, void \*)|
|[_InterlockedDecrement](interlockeddecrement-intrinsic-functions.md)||Intrin. h|uzun _InterlockedDecrement (uzun geçici \*)|
|[_InterlockedDecrement16](interlockeddecrement-intrinsic-functions.md)||Intrin. h|Short _InterlockedDecrement16 (kısa geçici \*)|
|[_InterlockedExchange](interlockedexchange-intrinsic-functions.md)||Intrin. h|uzun _InterlockedExchange (uzun geçici \*, uzun)|
|[_InterlockedExchange_HLEAcquire](interlockedexchange-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedExchange_HLEAcquire (uzun geçici \*, uzun)|
|[_InterlockedExchange_HLERelease](interlockedexchange-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedExchange_HLERelease (uzun geçici \*, uzun)|
|[_InterlockedExchange16](interlockedexchange-intrinsic-functions.md)||Intrin. h|kısa _InterlockedExchange16 (kısa geçici \*, kısa)|
|[_InterlockedExchange8](interlockedexchange-intrinsic-functions.md)||Intrin. h|Char _InterlockedExchange8 (Char volatile \*, Char)|
|[_InterlockedExchangeAdd](interlockedexchangeadd-intrinsic-functions.md)||Intrin. h|uzun _InterlockedExchangeAdd (uzun geçici \*, uzun)|
|[_InterlockedExchangeAdd_HLEAcquire](interlockedexchangeadd-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedExchangeAdd_HLEAcquire (uzun geçici \*, uzun)|
|[_InterlockedExchangeAdd_HLERelease](interlockedexchangeadd-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedExchangeAdd_HLERelease (uzun geçici \*, uzun)|
|[_InterlockedExchangeAdd16](interlockedexchangeadd-intrinsic-functions.md)||Intrin. h|Short _InterlockedExchangeAdd16 (kısa geçici *, kısa)|
|[_InterlockedExchangeAdd8](interlockedexchangeadd-intrinsic-functions.md)||Intrin. h|Char _InterlockedExchangeAdd8 (Char volatile \*, Char)|
|[_InterlockedExchangePointer](interlockedexchangepointer-intrinsic-functions.md)||Intrin. h|void \* _InterlockedExchangePointer (void \*volatile \*, void \*)|
|[_InterlockedExchangePointer_HLEAcquire](interlockedexchangepointer-intrinsic-functions.md)|HLE [2]|ımintrin. h|void \* _InterlockedExchangePointer_HLEAcquire (void \*volatile \*, void \*)|
|[_InterlockedExchangePointer_HLERelease](interlockedexchangepointer-intrinsic-functions.md)|HLE [2]|ımintrin. h|void \* _InterlockedExchangePointer_HLERelease (void \*volatile \*, void \*)|
|[_InterlockedIncrement](interlockedincrement-intrinsic-functions.md)||Intrin. h|uzun _InterlockedIncrement (uzun geçici \*)|
|[_InterlockedIncrement16](interlockedincrement-intrinsic-functions.md)||Intrin. h|Short _InterlockedIncrement16 (kısa geçici \*)|
|[_InterlockedOr](interlockedor-intrinsic-functions.md)||Intrin. h|uzun _InterlockedOr (uzun geçici \*, uzun)|
|[_InterlockedOr_HLEAcquire](interlockedor-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedOr_HLEAcquire (uzun geçici \*, uzun)|
|[_InterlockedOr_HLERelease](interlockedor-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedOr_HLERelease (uzun geçici \*, uzun)|
|[_InterlockedOr16](interlockedor-intrinsic-functions.md)||Intrin. h|kısa _InterlockedOr16 (kısa geçici \*, kısa)|
|[_InterlockedOr8](interlockedor-intrinsic-functions.md)||Intrin. h|Char _InterlockedOr8 (Char volatile \*, Char)|
|[_InterlockedXor](interlockedxor-intrinsic-functions.md)||Intrin. h|uzun _InterlockedXor (uzun geçici \*, uzun)|
|[_InterlockedXor_HLEAcquire](interlockedxor-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedXor_HLEAcquire (uzun geçici \*, uzun)|
|[_InterlockedXor_HLERelease](interlockedxor-intrinsic-functions.md)|HLE [2]|ımintrin. h|uzun _InterlockedXor_HLERelease (uzun geçici \*, uzun)|
|[_InterlockedXor16](interlockedxor-intrinsic-functions.md)||Intrin. h|kısa _InterlockedXor16 (kısa geçici \*, kısa)|
|[_InterlockedXor8](interlockedxor-intrinsic-functions.md)||Intrin. h|Char _InterlockedXor8 (Char volatile \*, Char)|
|[__invlpg](invlpg.md)||Intrin. h|void __invlpg (void\*)|
|[_invpcid](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_invpcid)|INVPCıD [2]|ımintrin. h|void _invpcid (işaretsiz int, void \*)|
|[__inword](inword.md)||Intrin. h|işaretsiz kısa __inword (işaretsiz kısa)|
|[__inwordstring](inwordstring.md)||Intrin. h|void __inwordstring (işaretsiz kısa, işaretsiz kısa \*, işaretsiz uzun)|
|_lgdt||Intrin. h|void _lgdt (void\*)|
|[__lidt](lidt.md)||Intrin. h|void __lidt (void\*)|
|[__ll_lshift](ll-lshift.md)||Intrin. h|işaretsiz __int64 [Pascal/cdecl] \__ll_lshift (imzasız \__int64, int)|
|[__ll_rshift](ll-rshift.md)||Intrin. h|__int64 [Pascal/cdecl] \__ll_rshift (\__int64, int)|
|_load_be_u16<br /><br /> [_loadbe_i16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_loadbe_i16&expand=3071)|MOVBE|ımintrin. h|işaretsiz kısa _load_be_u16 (void const\*);<br /><br /> Short _loadbe_i16 (void const\*); 03|
|_load_be_u32<br /><br /> [_loadbe_i32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_loadbe_i32&expand=3072)|MOVBE|ımintrin. h|işaretsiz int _load_be_u32 (void const\*);<br /><br /> int _loadbe_i32 (void const\*); 03|
|__llwpcb|LWP [1]|ammintrin. h|void __llwpcb (void \*)|
|__lwpins32|LWP [1]|ammintrin. h|işaretsiz char __lwpins32 (işaretsiz int, işaretsiz int, işaretsiz int)|
|__lwpval32|LWP [1]|ammintrin. h|void __lwpval32 (işaretsiz int, işaretsiz int, işaretsiz int)|
|[__lzcnt](lzcnt16-lzcnt-lzcnt64.md)|LZCNT|Intrin. h|işaretsiz int __lzcnt (işaretsiz int)|
|[_lzcnt_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_lzcnt_u32)|BMI|ammintrin. h, immintrin. h|işaretsiz int _lzcnt_u32 (işaretsiz int)|
|[__lzcnt16](lzcnt16-lzcnt-lzcnt64.md)|LZCNT|Intrin. h|işaretsiz kısa __lzcnt16 (işaretsiz kısa)|
|[_m_empty](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_empty)|MMX|Intrin. h|void _m_empty (void)|
|_m_femms|Şimdi 3D|Intrin. h|void _m_femms (void)|
|_m_from_float|Şimdi 3D|Intrin. h|__m64 _m_from_float (float)|
|[_m_from_int](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_from_int)|MMX|Intrin. h|__m64 _m_from_int (int)|
|[_m_maskmovq](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_maskmovq)|SSE|Intrin. h|void _m_maskmovq (\__m64, \__m64, Char\*)|
|[_m_packssdw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_packssdw)|MMX|Intrin. h|__m64 _m_packssdw (\__m64, \__m64)|
|[_m_packsswb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_packsswb)|MMX|Intrin. h|__m64 _m_packsswb (\__m64, \__m64)|
|[_m_packuswb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_packuswb)|MMX|Intrin. h|__m64 _m_packuswb (\__m64, \__m64)|
|[_m_paddb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_paddb)|MMX|Intrin. h|__m64 _m_paddb (\__m64, \__m64)|
|[_m_paddd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_paddd)|MMX|Intrin. h|__m64 _m_paddd (\__m64, \__m64)|
|[_m_paddsb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_paddsb)|MMX|Intrin. h|__m64 _m_paddsb (\__m64, \__m64)|
|[_m_paddsw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_paddsw)|MMX|Intrin. h|__m64 _m_paddsw (\__m64, \__m64)|
|[_m_paddusb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_paddusb)|MMX|Intrin. h|__m64 _m_paddusb (\__m64, \__m64)|
|[_m_paddusw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_paddusw)|MMX|Intrin. h|__m64 _m_paddusw (\__m64, \__m64)|
|[_m_paddw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_paddw)|MMX|Intrin. h|__m64 _m_paddw (\__m64, \__m64)|
|[_m_pand](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pand)|MMX|Intrin. h|__m64 _m_pand (\__m64, \__m64)|
|[_m_pandn](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pandn)|MMX|Intrin. h|__m64 _m_pandn (\__m64, \__m64)|
|[_m_pavgb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pavgb)|SSE|Intrin. h|__m64 _m_pavgb (\__m64, \__m64)|
|_m_pavgusb|Şimdi 3D|Intrin. h|__m64 _m_pavgusb (\__m64, \__m64)|
|[_m_pavgw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pavgw)|SSE|Intrin. h|__m64 _m_pavgw (\__m64, \__m64)|
|[_m_pcmpeqb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pcmpeqb)|MMX|Intrin. h|__m64 _m_pcmpeqb (\__m64, \__m64)|
|[_m_pcmpeqd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pcmpeqd)|MMX|Intrin. h|__m64 _m_pcmpeqd (\__m64, \__m64)|
|[_m_pcmpeqw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pcmpeqw)|MMX|Intrin. h|__m64 _m_pcmpeqw (\__m64, \__m64)|
|[_m_pcmpgtb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pcmpgtb)|MMX|Intrin. h|__m64 _m_pcmpgtb (\__m64, \__m64)|
|[_m_pcmpgtd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pcmpgtd)|MMX|Intrin. h|__m64 _m_pcmpgtd (\__m64, \__m64)|
|[_m_pcmpgtw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pcmpgtw)|MMX|Intrin. h|__m64 _m_pcmpgtw (\__m64, \__m64)|
|[_m_pextrw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pextrw)|SSE|Intrin. h|int _m_pextrw (\__m64, int)|
|_m_pf2id|Şimdi 3D|Intrin. h|__m64 _m_pf2id (\__m64)|
|_m_pf2iw|3DŞIMDI ext|Intrin. h|__m64 _m_pf2iw (\__m64)|
|_m_pfacc|Şimdi 3D|Intrin. h|__m64 _m_pfacc (\__m64, \__m64)|
|_m_pfadd|Şimdi 3D|Intrin. h|__m64 _m_pfadd (\__m64, \__m64)|
|_m_pfcmpeq|Şimdi 3D|Intrin. h|__m64 _m_pfcmpeq (\__m64, \__m64)|
|_m_pfcmpge|Şimdi 3D|Intrin. h|__m64 _m_pfcmpge (\__m64, \__m64)|
|_m_pfcmpgt|Şimdi 3D|Intrin. h|__m64 _m_pfcmpgt (\__m64, \__m64)|
|_m_pfmax|Şimdi 3D|Intrin. h|__m64 _m_pfmax (\__m64, \__m64)|
|_m_pfmin|Şimdi 3D|Intrin. h|__m64 _m_pfmin (\__m64, \__m64)|
|_m_pfmul|Şimdi 3D|Intrin. h|__m64 _m_pfmul (\__m64, \__m64)|
|_m_pfnacc|3DŞIMDI ext|Intrin. h|__m64 _m_pfnacc (\__m64, \__m64)|
|_m_pfpnacc|3DŞIMDI ext|Intrin. h|__m64 _m_pfpnacc (\__m64, \__m64)|
|_m_pfrcp|Şimdi 3D|Intrin. h|__m64 _m_pfrcp (\__m64)|
|_m_pfrcpit1|Şimdi 3D|Intrin. h|__m64 _m_pfrcpit1 (\__m64, \__m64)|
|_m_pfrcpit2|Şimdi 3D|Intrin. h|__m64 _m_pfrcpit2 (\__m64, \__m64)|
|_m_pfrsqit1|Şimdi 3D|Intrin. h|__m64 _m_pfrsqit1 (\__m64, \__m64)|
|_m_pfrsqrt|Şimdi 3D|Intrin. h|__m64 _m_pfrsqrt (\__m64)|
|_m_pfsub|Şimdi 3D|Intrin. h|__m64 _m_pfsub (\__m64, \__m64)|
|_m_pfsubr|Şimdi 3D|Intrin. h|__m64 _m_pfsubr (\__m64, \__m64)|
|_m_pi2fd|Şimdi 3D|Intrin. h|__m64 _m_pi2fd (\__m64)|
|_m_pi2fw|3DŞIMDI ext|Intrin. h|__m64 _m_pi2fw (\__m64)|
|[_m_pinsrw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pinsrw)|SSE|Intrin. h|__m64 _m_pinsrw (\__m64, int, int)|
|[_m_pmaddwd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pmaddwd)|MMX|Intrin. h|__m64 _m_pmaddwd (\__m64, \__m64)|
|[_m_pmaxsw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pmaxsw)|SSE|Intrin. h|__m64 _m_pmaxsw (\__m64, \__m64)|
|[_m_pmaxub](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pmaxub)|SSE|Intrin. h|__m64 _m_pmaxub (\__m64, \__m64)|
|[_m_pminsw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pminsw)|SSE|Intrin. h|__m64 _m_pminsw (\__m64, \__m64)|
|[_m_pminub](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pminub)|SSE|Intrin. h|__m64 _m_pminub (\__m64, \__m64)|
|[_m_pmovmskb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pmovmskb)|SSE|Intrin. h|int _m_pmovmskb (\__m64)|
|_m_pmulhrw|Şimdi 3D|Intrin. h|__m64 _m_pmulhrw (\__m64, \__m64)|
|[_m_pmulhuw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pmulhuw)|SSE|Intrin. h|__m64 _m_pmulhuw (\__m64, \__m64)|
|[_m_pmulhw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pmulhw)|MMX|Intrin. h|__m64 _m_pmulhw (\__m64, \__m64)|
|[_m_pmullw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pmullw)|MMX|Intrin. h|__m64 _m_pmullw (\__m64, \__m64)|
|[_m_por](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_por)|MMX|Intrin. h|__m64 _m_por (\__m64, \__m64)|
|_m_prefetch|Şimdi 3D|Intrin. h|void _m_prefetch (void\*)|
|_m_prefetchw|Şimdi 3D|Intrin. h|void _m_prefetchw (void\*)|
|[_m_psadbw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psadbw)|SSE|Intrin. h|__m64 _m_psadbw (\__m64, \__m64)|
|[_m_pshufw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pshufw)|SSE|Intrin. h|__m64 _m_pshufw (\__m64, int)|
|[_m_pslld](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pslld)|MMX|Intrin. h|__m64 _m_pslld (\__m64, \__m64)|
|[_m_pslldi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pslldi)|MMX|Intrin. h|__m64 _m_pslldi (\__m64, int)|
|[_m_psllq](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psllq)|MMX|Intrin. h|__m64 _m_psllq (\__m64, \__m64)|
|[_m_psllqi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psllqi)|MMX|Intrin. h|__m64 _m_psllqi (\__m64, int)|
|[_m_psllw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psllw)|MMX|Intrin. h|__m64 _m_psllw (\__m64, \__m64)|
|[_m_psllwi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psllwi)|MMX|Intrin. h|__m64 _m_psllwi (\__m64, int)|
|[_m_psrad](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psrad)|MMX|Intrin. h|__m64 _m_psrad (\__m64, \__m64)|
|[_m_psradi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psradi)|MMX|Intrin. h|__m64 _m_psradi (\__m64, int)|
|[_m_psraw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psraw)|MMX|Intrin. h|__m64 _m_psraw (\__m64, \__m64)|
|[_m_psrawi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psrawi)|MMX|Intrin. h|__m64 _m_psrawi (\__m64, int)|
|[_m_psrld](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psrld)|MMX|Intrin. h|__m64 _m_psrld (\__m64, \__m64)|
|[_m_psrldi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psrldi)|MMX|Intrin. h|__m64 _m_psrldi (\__m64, int)|
|[_m_psrlq](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psrlq)|MMX|Intrin. h|__m64 _m_psrlq (\__m64, \__m64)|
|[_m_psrlqi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psrlqi)|MMX|Intrin. h|__m64 _m_psrlqi (\__m64, int)|
|[_m_psrlw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psrlw)|MMX|Intrin. h|__m64 _m_psrlw (\__m64, \__m64)|
|[_m_psrlwi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psrlwi)|MMX|Intrin. h|__m64 _m_psrlwi (\__m64, int)|
|[_m_psubb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psubb)|MMX|Intrin. h|__m64 _m_psubb (\__m64, \__m64)|
|[_m_psubd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psubd)|MMX|Intrin. h|__m64 _m_psubd (\__m64, \__m64)|
|[_m_psubsb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psubsb)|MMX|Intrin. h|__m64 _m_psubsb (\__m64, \__m64)|
|[_m_psubsw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psubsw)|MMX|Intrin. h|__m64 _m_psubsw (\__m64, \__m64)|
|[_m_psubusb](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psubusb)|MMX|Intrin. h|__m64 _m_psubusb (\__m64, \__m64)|
|[_m_psubusw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psubusw)|MMX|Intrin. h|__m64 _m_psubusw (\__m64, \__m64)|
|[_m_psubw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_psubw)|MMX|Intrin. h|__m64 _m_psubw (\__m64, \__m64)|
|_m_pswapd|3DŞIMDI ext|Intrin. h|__m64 _m_pswapd (\__m64)|
|[_m_punpckhbw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_punpckhbw)|MMX|Intrin. h|__m64 _m_punpckhbw (\__m64, \__m64)|
|[_m_punpckhdq](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_punpckhdq)|MMX|Intrin. h|__m64 _m_punpckhdq (\__m64, \__m64)|
|[_m_punpckhwd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_punpckhwd)|MMX|Intrin. h|__m64 _m_punpckhwd (\__m64, \__m64)|
|[_m_punpcklbw](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_punpcklbw)|MMX|Intrin. h|__m64 _m_punpcklbw (\__m64, \__m64)|
|[_m_punpckldq](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_punpckldq)|MMX|Intrin. h|__m64 _m_punpckldq (\__m64, \__m64)|
|[_m_punpcklwd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_punpcklwd)|MMX|Intrin. h|__m64 _m_punpcklwd (\__m64, \__m64)|
|[_m_pxor](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_pxor)|MMX|Intrin. h|__m64 _m_pxor (\__m64, \__m64)|
|_m_to_float|Şimdi 3D|Intrin. h|kayan _m_to_float (\__m64)|
|[_m_to_int](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_m_to_int)|MMX|Intrin. h|int _m_to_int (\__m64)|
|[_mm_abs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_abs_epi16)|SSSE3|Intrin. h|__m128i _mm_abs_epi16 (\__m128i)|
|[_mm_abs_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_abs_epi32)|SSSE3|Intrin. h|__m128i _mm_abs_epi32 (\__m128i)|
|[_mm_abs_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_abs_epi8)|SSSE3|Intrin. h|__m128i _mm_abs_epi8 (\__m128i)|
|[_mm_abs_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_abs_pi16)|SSSE3|Intrin. h|__m64 _mm_abs_pi16 (\__m64)|
|[_mm_abs_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_abs_pi32)|SSSE3|Intrin. h|__m64 _mm_abs_pi32 (\__m64)|
|[_mm_abs_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_abs_pi8)|SSSE3|Intrin. h|__m64 _mm_abs_pi8 (\__m64)|
|[_mm_add_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_epi16)|SSE2|Intrin. h|__m128i _mm_add_epi16 (\__m128i, \__m128i)|
|[_mm_add_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_epi32)|SSE2|Intrin. h|__m128i _mm_add_epi32 (\__m128i, \__m128i)|
|[_mm_add_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_epi64)|SSE2|Intrin. h|__m128i _mm_add_epi64 (\__m128i, \__m128i)|
|[_mm_add_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_epi8)|SSE2|Intrin. h|__m128i _mm_add_epi8 (\__m128i, \__m128i)|
|[_mm_add_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_pd)|SSE2|Intrin. h|__m128d _mm_add_pd (\__m128d, \__m128d)|
|[_mm_add_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_pi8)|MMX|mmintrin. h|__m64 _mm_add_pi8 (\__m64, \__m64) [3]|
|[_mm_add_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_pi16)|MMX|mmintrin. h|__m64 _mm_add_pi16 (\__m64, \__m64) [3]|
|[_mm_add_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_pi32)|MMX|mmintrin. h|__m64 _mm_add_pi32 (\__m64, \__m64) [3]|
|[_mm_add_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_ps)|SSE|Intrin. h|__m128 _mm_add_ps (\__m128, \__m128)|
|[_mm_add_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_sd)|SSE2|Intrin. h|__m128d _mm_add_sd (\__m128d, \__m128d)|
|[_mm_add_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_si64)|SSE2|Intrin. h|__m64 _mm_add_si64 (\__m64, \__m64)|
|[_mm_add_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_add_ss)|SSE|Intrin. h|__m128 _mm_add_ss (\__m128, \__m128)|
|[_mm_adds_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_epi16)|SSE2|Intrin. h|__m128i _mm_adds_epi16 (\__m128i, \__m128i)|
|[_mm_adds_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_epi8)|SSE2|Intrin. h|__m128i _mm_adds_epi8 (\__m128i, \__m128i)|
|[_mm_adds_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_epu16)|SSE2|Intrin. h|__m128i _mm_adds_epu16 (\__m128i, \__m128i)|
|[_mm_adds_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_epu8)|SSE2|Intrin. h|__m128i _mm_adds_epu8 (\__m128i, \__m128i)|
|[_mm_adds_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_pi8)|MMX|mmintrin. h|__m64 _mm_adds_pi8 (\__m64, \__m64) [3]|
|[_mm_adds_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_pi16)|MMX|mmintrin. h|__m64 _mm_adds_pi16 (\__m64, \__m64) [3]|
|[_mm_adds_pu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_pu8)|MMX|mmintrin. h|__m64 _mm_adds_pu8 (\__m64, \__m64) [3]|
|[_mm_adds_pu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_adds_pu16)|MMX|mmintrin. h|__m64 _mm_adds_pu16 (\__m64, \__m64) [3]|
|[_mm_addsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_addsub_pd)|SSE3|Intrin. h|__m128d _mm_addsub_pd (\__m128d, \__m128d)|
|[_mm_addsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_addsub_ps)|SSE3|Intrin. h|__m128 _mm_addsub_ps (\__m128, \__m128)|
|[_mm_aesdec_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aesdec_si128)|AESNI [2]|ımintrin. h|__m128i _mm_aesdec_si128 (\__m128i, \__m128i)|
|[_mm_aesdeclast_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aesdeclast_si128)|AESNI [2]|ımintrin. h|__m128i _mm_aesdeclast_si128 (\__m128i, \__m128i)|
|[_mm_aesenc_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aesenc_si128)|AESNI [2]|ımintrin. h|__m128i _mm_aesenc_si128 (\__m128i, \__m128i)|
|[_mm_aesenclast_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aesenclast_si128)|AESNI [2]|ımintrin. h|__m128i _mm_aesenclast_si128 (\__m128i, \__m128i)|
|[_mm_aesimc_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aesimc_si128)|AESNI [2]|ımintrin. h|__m128i _mm_aesimc_si128 (\__m128i)|
|[_mm_aeskeygenassist_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_aeskeygenassist_si128)|AESNI [2]|ımintrin. h|__m128i _mm_aeskeygenassist_si128 (\__m128i, const int)|
|[_mm_alignr_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_alignr_epi8)|SSSE3|Intrin. h|__m128i _mm_alignr_epi8 (\__m128i, \__m128i, int)|
|[_mm_alignr_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_alignr_pi8)|SSSE3|Intrin. h|__m64 _mm_alignr_pi8 (\__m64, \__m64, int)|
|[_mm_and_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_and_pd)|SSE2|Intrin. h|__m128d _mm_and_pd (\__m128d, \__m128d)|
|[_mm_and_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_and_ps)|SSE|Intrin. h|__m128 _mm_and_ps (\__m128, \__m128)|
|[_mm_and_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_and_si64)|MMX|mmintrin. h|__m64 _mm_and_si64 (\__m64, \__m64) [3]|
|[_mm_and_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_and_si128)|SSE2|Intrin. h|__m128i _mm_and_si128 (\__m128i, \__m128i)|
|[_mm_andnot_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_andnot_pd)|SSE2|Intrin. h|__m128d _mm_andnot_pd (\__m128d, \__m128d)|
|[_mm_andnot_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_andnot_ps)|SSE|Intrin. h|__m128 _mm_andnot_ps (\__m128, \__m128)|
|[_mm_andnot_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_andnot_si64)|MMX|mmintrin. h|__m64 _mm_andnot_si64 (\__m64, \__m64) [3]|
|[_mm_andnot_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_andnot_si128)|SSE2|Intrin. h|__m128i _mm_andnot_si128 (\__m128i, \__m128i)|
|[_mm_avg_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_avg_epu16)|SSE2|Intrin. h|__m128i _mm_avg_epu16 (\__m128i, \__m128i)|
|[_mm_avg_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_avg_epu8)|SSE2|Intrin. h|__m128i _mm_avg_epu8 (\__m128i, \__m128i)|
|[_mm_blend_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blend_epi16)|SSE41|Intrin. h|__m128i _mm_blend_epi16 (\__m128i, \__m128i, const int)|
|[_mm_blend_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blend_epi32)|AVX2 [2]|ımintrin. h|__m128i _mm_blend_epi32 (\__m128i, \__m128i, const int)|
|[_mm_blend_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blend_pd)|SSE41|Intrin. h|__m128d _mm_blend_pd (\__m128d, \__m128d, const int)|
|[_mm_blend_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blend_ps)|SSE41|Intrin. h|__m128 _mm_blend_ps (\__m128, \__m128, const int)|
|[_mm_blendv_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blendv_epi8)|SSE41|Intrin. h|__m128i _mm_blendv_epi8 (\__m128i, \__m128i, \__m128i)|
|[_mm_blendv_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blendv_pd)|SSE41|Intrin. h|__m128d _mm_blendv_pd (\__m128d, \__m128d, \__m128d)|
|[_mm_blendv_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_blendv_ps)|SSE41|Intrin. h|__m128 _mm_blendv_ps (\__m128, \__m128, \__m128)|
|[_mm_broadcast_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcast_ss)|AVX [2]|ımintrin. h|__m128 _mm_broadcast_ss (float const *)|
|[_mm_broadcastb_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastb_epi8)|AVX2 [2]|ımintrin. h|__m128i _mm_broadcastb_epi8 (\__m128i)|
|[_mm_broadcastd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastd_epi32)|AVX2 [2]|ımintrin. h|__m128i _mm_broadcastd_epi32 (\__m128i)|
|[_mm_broadcastq_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastq_epi64)|AVX2 [2]|ımintrin. h|__m128i _mm_broadcastq_epi64 (\__m128i)|
|[_mm_broadcastsd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastsd_pd)|AVX2 [2]|ımintrin. h|__m128d _mm_broadcastsd_pd (\__m128d)|
|[_mm_broadcastss_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastss_ps)|AVX2 [2]|ımintrin. h|__m128 _mm_broadcastss_ps (\__m128)|
|[_mm_broadcastw_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_broadcastw_epi16)|AVX2 [2]|ımintrin. h|__m128i _mm_broadcastw_epi16 (\__m128i)|
|[_mm_castpd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castpd_ps)|SSSE3|Intrin. h|__m128 _mm_castpd_ps (\__m128d)|
|[_mm_castpd_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castpd_si128)|SSSE3|Intrin. h|__m128i _mm_castpd_si128 (\__m128d)|
|[_mm_castps_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castps_pd)|SSSE3|Intrin. h|__m128d _mm_castps_pd (\__m128)|
|[_mm_castps_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castps_si128)|SSSE3|Intrin. h|__m128i _mm_castps_si128 (\__m128)|
|[_mm_castsi128_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castsi128_pd)|SSSE3|Intrin. h|__m128d _mm_castsi128_pd (\__m128i)|
|[_mm_castsi128_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_castsi128_ps)|SSSE3|Intrin. h|__m128 _mm_castsi128_ps (\__m128i)|
|[_mm_clflush](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_clflush)|SSE2|Intrin. h|void _mm_clflush (const \*void)|
|[_mm_clmulepi64_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_clmulepi64_si128)|PCLMULQDQ [2]|ımintrin. h|__m128i _mm_clmulepi64_si128 (\__m128i, \__m128i, const int)|
|_mm_cmov_si128|XOP [1]|ammintrin. h|__m128i _mm_cmov_si128 (\__m128i, \__m128i, \__m128i)|
|[_mm_cmp_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmp_pd)|AVX [2]|ımintrin. h|__m128d _mm_cmp_pd (\__m128d, \__m128d, const int)|
|[_mm_cmp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmp_ps)|AVX [2]|ımintrin. h|__m128 _mm_cmp_ps (\__m128, \__m128, const int)|
|[_mm_cmp_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmp_sd)|AVX [2]|ımintrin. h|__m128d _mm_cmp_sd (\__m128d, \__m128d, const int)|
|[_mm_cmp_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmp_ss)|AVX [2]|ımintrin. h|__m128 _mm_cmp_ss (\__m128, \__m128, const int)|
|[_mm_cmpeq_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_epi16)|SSE2|Intrin. h|__m128i _mm_cmpeq_epi16 (\__m128i, \__m128i)|
|[_mm_cmpeq_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_epi32)|SSE2|Intrin. h|__m128i _mm_cmpeq_epi32 (\__m128i, \__m128i)|
|[_mm_cmpeq_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_epi64)|SSE41|Intrin. h|__m128i _mm_cmpeq_epi64 (\__m128i, \__m128i)|
|[_mm_cmpeq_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_epi8)|SSE2|Intrin. h|__m128i _mm_cmpeq_epi8 (\__m128i, \__m128i)|
|[_mm_cmpeq_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_pd)|SSE2|Intrin. h|__m128d _mm_cmpeq_pd (\__m128d, \__m128d)|
|[_mm_cmpeq_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_pi8)|MMX|mmintrin. h|__m64 _mm_cmpeq_pi8 (\__m64, \__m64) [3]|
|[_mm_cmpeq_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_pi16)|MMX|mmintrin. h|__m64 _mm_cmpeq_pi16 (\__m64, \__m64) [3]|
|[_mm_cmpeq_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_pi32)|MMX|mmintrin. h|__m64 _mm_cmpeq_pi32 (\__m64, \__m64) [3]|
|[_mm_cmpeq_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_ps)|SSE|Intrin. h|__m128 _mm_cmpeq_ps (\__m128, \__m128)|
|[_mm_cmpeq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_sd)|SSE2|Intrin. h|__m128d _mm_cmpeq_sd (\__m128d, \__m128d)|
|[_mm_cmpeq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpeq_ss)|SSE|Intrin. h|__m128 _mm_cmpeq_ss (\__m128, \__m128)|
|[_mm_cmpestra](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestra)|SSE42|Intrin. h|int _mm_cmpestra (\__m128i, int, \__m128i, int, const int)|
|[_mm_cmpestrc](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestrc)|SSE42|Intrin. h|int _mm_cmpestrc (\__m128i, int, \__m128i, int, const int)|
|[_mm_cmpestri](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestri)|SSE42|Intrin. h|int _mm_cmpestri (\__m128i, int, \__m128i, int, const int)|
|[_mm_cmpestrm](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestrm)|SSE42|Intrin. h|__m128i _mm_cmpestrm (\__m128i, int, \__m128i, int, const int)|
|[_mm_cmpestro](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestro)|SSE42|Intrin. h|int _mm_cmpestro (\__m128i, int, \__m128i, int, const int)|
|[_mm_cmpestrs](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestrs)|SSE42|Intrin. h|int _mm_cmpestrs (\__m128i, int, \__m128i, int, const int)|
|[_mm_cmpestrz](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpestrz)|SSE42|Intrin. h|int _mm_cmpestrz (\__m128i, int, \__m128i, int, const int)|
|[_mm_cmpge_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpge_pd)|SSE2|Intrin. h|__m128d _mm_cmpge_pd (\__m128d, \__m128d)|
|[_mm_cmpge_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpge_ps)|SSE|Intrin. h|__m128 _mm_cmpge_ps (\__m128, \__m128)|
|[_mm_cmpge_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpge_sd)|SSE2|Intrin. h|__m128d _mm_cmpge_sd (\__m128d, \__m128d)|
|[_mm_cmpge_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpge_ss)|SSE|Intrin. h|__m128 _mm_cmpge_ss (\__m128, \__m128)|
|[_mm_cmpgt_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_epi16)|SSE2|Intrin. h|__m128i _mm_cmpgt_epi16 (\__m128i, \__m128i)|
|[_mm_cmpgt_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_epi32)|SSE2|Intrin. h|__m128i _mm_cmpgt_epi32 (\__m128i, \__m128i)|
|[_mm_cmpgt_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_epi64)|SSE42|Intrin. h|__m128i _mm_cmpgt_epi64 (\__m128i, \__m128i)|
|[_mm_cmpgt_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_epi8)|SSE2|Intrin. h|__m128i _mm_cmpgt_epi8 (\__m128i, \__m128i)|
|[_mm_cmpgt_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_pi8)|MMX|mmintrin. h|__m64 _mm_cmpgt_pi8 (\__m64, \__m64) [3]|
|[_mm_cmpgt_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_pi16)|MMX|mmintrin. h|__m64 _mm_cmpgt_pi16 (\__m64, \__m64) [3]|
|[_mm_cmpgt_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_pi32)|MMX|mmintrin. h|__m64 _mm_cmpgt_pi32 (\__m64, \__m64) [3]|
|[_mm_cmpgt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_pd)|SSE2|Intrin. h|__m128d _mm_cmpgt_pd (\__m128d, \__m128d)|
|[_mm_cmpgt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_ps)|SSE|Intrin. h|__m128 _mm_cmpgt_ps (\__m128, \__m128)|
|[_mm_cmpgt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_sd)|SSE2|Intrin. h|__m128d _mm_cmpgt_sd (\__m128d, \__m128d)|
|[_mm_cmpgt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpgt_ss)|SSE|Intrin. h|__m128 _mm_cmpgt_ss (\__m128, \__m128)|
|[_mm_cmpistra](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistra)|SSE42|Intrin. h|int _mm_cmpistra (\__m128i, \__m128i, const int)|
|[_mm_cmpistrc](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistrc)|SSE42|Intrin. h|int _mm_cmpistrc (\__m128i, \__m128i, const int)|
|[_mm_cmpistri](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistri)|SSE42|Intrin. h|int _mm_cmpistri (\__m128i, \__m128i, const int)|
|[_mm_cmpistrm](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistrm)|SSE42|Intrin. h|__m128i _mm_cmpistrm (\__m128i, \__m128i, const int)|
|[_mm_cmpistro](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistro)|SSE42|Intrin. h|int _mm_cmpistro (\__m128i, \__m128i, const int)|
|[_mm_cmpistrs](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistrs)|SSE42|Intrin. h|int _mm_cmpistrs (\__m128i, \__m128i, const int)|
|[_mm_cmpistrz](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpistrz)|SSE42|Intrin. h|int _mm_cmpistrz (\__m128i, \__m128i, const int)|
|[_mm_cmple_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmple_pd)|SSE2|Intrin. h|__m128d _mm_cmple_pd (\__m128d, \__m128d)|
|[_mm_cmple_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmple_ps)|SSE|Intrin. h|__m128 _mm_cmple_ps (\__m128, \__m128)|
|[_mm_cmple_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmple_sd)|SSE2|Intrin. h|__m128d _mm_cmple_sd (\__m128d, \__m128d)|
|[_mm_cmple_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmple_ss)|SSE|Intrin. h|__m128 _mm_cmple_ss (\__m128, \__m128)|
|[_mm_cmplt_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_epi16)|SSE2|Intrin. h|__m128i _mm_cmplt_epi16 (\__m128i, \__m128i)|
|[_mm_cmplt_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_epi32)|SSE2|Intrin. h|__m128i _mm_cmplt_epi32 (\__m128i, \__m128i)|
|[_mm_cmplt_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_epi8)|SSE2|Intrin. h|__m128i _mm_cmplt_epi8 (\__m128i, \__m128i)|
|[_mm_cmplt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_pd)|SSE2|Intrin. h|__m128d _mm_cmplt_pd (\__m128d, \__m128d)|
|[_mm_cmplt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_ps)|SSE|Intrin. h|__m128 _mm_cmplt_ps (\__m128, \__m128)|
|[_mm_cmplt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_sd)|SSE2|Intrin. h|__m128d _mm_cmplt_sd (\__m128d, \__m128d)|
|[_mm_cmplt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmplt_ss)|SSE|Intrin. h|__m128 _mm_cmplt_ss (\__m128, \__m128)|
|[_mm_cmpneq_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpneq_pd)|SSE2|Intrin. h|__m128d _mm_cmpneq_pd (\__m128d, \__m128d)|
|[_mm_cmpneq_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpneq_ps)|SSE|Intrin. h|__m128 _mm_cmpneq_ps (\__m128, \__m128)|
|[_mm_cmpneq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpneq_sd)|SSE2|Intrin. h|__m128d _mm_cmpneq_sd (\__m128d, \__m128d)|
|[_mm_cmpneq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpneq_ss)|SSE|Intrin. h|__m128 _mm_cmpneq_ss (\__m128, \__m128)|
|[_mm_cmpnge_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnge_pd)|SSE2|Intrin. h|__m128d _mm_cmpnge_pd (\__m128d, \__m128d)|
|[_mm_cmpnge_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnge_ps)|SSE|Intrin. h|__m128 _mm_cmpnge_ps (\__m128, \__m128)|
|[_mm_cmpnge_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnge_sd)|SSE2|Intrin. h|__m128d _mm_cmpnge_sd (\__m128d, \__m128d)|
|[_mm_cmpnge_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnge_ss)|SSE|Intrin. h|__m128 _mm_cmpnge_ss (\__m128, \__m128)|
|[_mm_cmpngt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpngt_pd)|SSE2|Intrin. h|__m128d _mm_cmpngt_pd (\__m128d, \__m128d)|
|[_mm_cmpngt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpngt_ps)|SSE|Intrin. h|__m128 _mm_cmpngt_ps (\__m128, \__m128)|
|[_mm_cmpngt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpngt_sd)|SSE2|Intrin. h|__m128d _mm_cmpngt_sd (\__m128d, \__m128d)|
|[_mm_cmpngt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpngt_ss)|SSE|Intrin. h|__m128 _mm_cmpngt_ss (\__m128, \__m128)|
|[_mm_cmpnle_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnle_pd)|SSE2|Intrin. h|__m128d _mm_cmpnle_pd (\__m128d, \__m128d)|
|[_mm_cmpnle_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnle_ps)|SSE|Intrin. h|__m128 _mm_cmpnle_ps (\__m128, \__m128)|
|[_mm_cmpnle_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnle_sd)|SSE2|Intrin. h|__m128d _mm_cmpnle_sd (\__m128d, \__m128d)|
|[_mm_cmpnle_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnle_ss)|SSE|Intrin. h|__m128 _mm_cmpnle_ss (\__m128, \__m128)|
|[_mm_cmpnlt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnlt_pd)|SSE2|Intrin. h|__m128d _mm_cmpnlt_pd (\__m128d, \__m128d)|
|[_mm_cmpnlt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnlt_ps)|SSE|Intrin. h|__m128 _mm_cmpnlt_ps (\__m128, \__m128)|
|[_mm_cmpnlt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnlt_sd)|SSE2|Intrin. h|__m128d _mm_cmpnlt_sd (\__m128d, \__m128d)|
|[_mm_cmpnlt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpnlt_ss)|SSE|Intrin. h|__m128 _mm_cmpnlt_ss (\__m128, \__m128)|
|[_mm_cmpord_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpord_pd)|SSE2|Intrin. h|__m128d _mm_cmpord_pd (\__m128d, \__m128d)|
|[_mm_cmpord_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpord_ps)|SSE|Intrin. h|__m128 _mm_cmpord_ps (\__m128, \__m128)|
|[_mm_cmpord_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpord_sd)|SSE2|Intrin. h|__m128d _mm_cmpord_sd (\__m128d, \__m128d)|
|[_mm_cmpord_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpord_ss)|SSE|Intrin. h|__m128 _mm_cmpord_ss (\__m128, \__m128)|
|[_mm_cmpunord_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpunord_pd)|SSE2|Intrin. h|__m128d _mm_cmpunord_pd (\__m128d, \__m128d)|
|[_mm_cmpunord_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpunord_ps)|SSE|Intrin. h|__m128 _mm_cmpunord_ps (\__m128, \__m128)|
|[_mm_cmpunord_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpunord_sd)|SSE2|Intrin. h|__m128d _mm_cmpunord_sd (\__m128d, \__m128d)|
|[_mm_cmpunord_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cmpunord_ss)|SSE|Intrin. h|__m128 _mm_cmpunord_ss (\__m128, \__m128)|
|_mm_com_epi16|XOP [1]|ammintrin. h|__m128i _mm_com_epi16 (\__m128i, \__m128i, int)|
|_mm_com_epi32|XOP [1]|ammintrin. h|__m128i _mm_com_epi32 (\__m128i, \__m128i, int)|
|_mm_com_epi64|XOP [1]|ammintrin. h|__m128i _mm_com_epi32 (\__m128i, \__m128i, int)|
|_mm_com_epi8|XOP [1]|ammintrin. h|__m128i _mm_com_epi8 (\__m128i, \__m128i, int)|
|_mm_com_epu16|XOP [1]|ammintrin. h|__m128i _mm_com_epu16 (\__m128i, \__m128i, int)|
|_mm_com_epu32|XOP [1]|ammintrin. h|__m128i _mm_com_epu32 (\__m128i, \__m128i, int)|
|_mm_com_epu64|XOP [1]|ammintrin. h|__m128i _mm_com_epu32 (\__m128i, \__m128i, int)|
|_mm_com_epu8|XOP [1]|ammintrin. h|__m128i _mm_com_epu8 (\__m128i, \__m128i, int)|
|[_mm_comieq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comieq_sd)|SSE2|Intrin. h|int _mm_comieq_sd (\__m128d, \__m128d)|
|[_mm_comieq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comieq_ss)|SSE|Intrin. h|int _mm_comieq_ss (\__m128, \__m128)|
|[_mm_comige_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comige_sd)|SSE2|Intrin. h|int _mm_comige_sd (\__m128d, \__m128d)|
|[_mm_comige_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comige_ss)|SSE|Intrin. h|int _mm_comige_ss (\__m128, \__m128)|
|[_mm_comigt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comigt_sd)|SSE2|Intrin. h|int _mm_comigt_sd (\__m128d, \__m128d)|
|[_mm_comigt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comigt_ss)|SSE|Intrin. h|int _mm_comigt_ss (\__m128, \__m128)|
|[_mm_comile_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comile_sd)|SSE2|Intrin. h|int _mm_comile_sd (\__m128d, \__m128d)|
|[_mm_comile_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comile_ss)|SSE|Intrin. h|int _mm_comile_ss (\__m128, \__m128)|
|[_mm_comilt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comilt_sd)|SSE2|Intrin. h|int _mm_comilt_sd (\__m128d, \__m128d)|
|[_mm_comilt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comilt_ss)|SSE|Intrin. h|int _mm_comilt_ss (\__m128, \__m128)|
|[_mm_comineq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comineq_sd)|SSE2|Intrin. h|int _mm_comineq_sd (\__m128d, \__m128d)|
|[_mm_comineq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_comineq_ss)|SSE|Intrin. h|int _mm_comineq_ss (\__m128, \__m128)|
|[_mm_crc32_u16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_crc32_u16)|SSE42|Intrin. h|işaretsiz int _mm_crc32_u16 (işaretsiz int, işaretsiz kısa)|
|[_mm_crc32_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_crc32_u32)|SSE42|Intrin. h|işaretsiz int _mm_crc32_u32 (işaretsiz int, işaretsiz int)|
|[_mm_crc32_u8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_crc32_u8)|SSE42|Intrin. h|işaretsiz int _mm_crc32_u8 (işaretsiz int, işaretsiz karakter)|
|[_mm_cvt_pi2ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvt_pi2ps)|SSE|Intrin. h|__m128 _mm_cvt_pi2ps (\__m128, \__m64)|
|[_mm_cvt_ps2pi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvt_ps2pi)|SSE|Intrin. h|__m64 _mm_cvt_ps2pi (\__m128)|
|[_mm_cvt_si2ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvt_si2ss)|SSE|Intrin. h|__m128 _mm_cvt_si2ss (\__m128, int)|
|[_mm_cvt_ss2si](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvt_ss2si)|SSE|Intrin. h|int _mm_cvt_ss2si (\__m128)|
|[_mm_cvtepi16_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi16_epi32)|SSE41|Intrin. h|__m128i _mm_cvtepi16_epi32 (\__m128i)|
|[_mm_cvtepi16_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi16_epi64)|SSE41|Intrin. h|__m128i _mm_cvtepi16_epi64 (\__m128i)|
|[_mm_cvtepi32_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi32_epi64)|SSE41|Intrin. h|__m128i _mm_cvtepi32_epi64 (\__m128i)|
|[_mm_cvtepi32_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi32_pd)|SSE2|Intrin. h|__m128d _mm_cvtepi32_pd (\__m128i)|
|[_mm_cvtepi32_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi32_ps)|SSE2|Intrin. h|__m128 _mm_cvtepi32_ps (\__m128i)|
|[_mm_cvtepi8_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi8_epi16)|SSE41|Intrin. h|__m128i _mm_cvtepi8_epi16 (\__m128i)|
|[_mm_cvtepi8_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi8_epi32)|SSE41|Intrin. h|__m128i _mm_cvtepi8_epi32 (\__m128i)|
|[_mm_cvtepi8_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepi8_epi64)|SSE41|Intrin. h|__m128i _mm_cvtepi8_epi64 (\__m128i)|
|[_mm_cvtepu16_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu16_epi32)|SSE41|Intrin. h|__m128i _mm_cvtepu16_epi32 (\__m128i)|
|[_mm_cvtepu16_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu16_epi64)|SSE41|Intrin. h|__m128i _mm_cvtepu16_epi64 (\__m128i)|
|[_mm_cvtepu32_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu32_epi64)|SSE41|Intrin. h|__m128i _mm_cvtepu32_epi64 (\__m128i)|
|[_mm_cvtepu8_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu8_epi16)|SSE41|Intrin. h|__m128i _mm_cvtepu8_epi16 (\__m128i)|
|[_mm_cvtepu8_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu8_epi32)|SSE41|Intrin. h|__m128i _mm_cvtepu8_epi32 (\__m128i)|
|[_mm_cvtepu8_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtepu8_epi64)|SSE41|Intrin. h|__m128i _mm_cvtepu8_epi64 (\__m128i)|
|[_mm_cvtpd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtpd_epi32)|SSE2|Intrin. h|__m128i _mm_cvtpd_epi32 (\__m128d)|
|[_mm_cvtpd_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtpd_pi32)|SSE2|Intrin. h|__m64 _mm_cvtpd_pi32 (\__m128d)|
|[_mm_cvtpd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtpd_ps)|SSE2|Intrin. h|__m128 _mm_cvtpd_ps (\__m128d)|
|[_mm_cvtph_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtph_ps)|F16C [2]|ımintrin. h|__m128 _mm_cvtph_ps (\__m128i)|
|[_mm_cvtpi32_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtpi32_pd)|SSE2|Intrin. h|__m128d _mm_cvtpi32_pd (\__m64)|
|[_mm_cvtps_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtps_epi32)|SSE2|Intrin. h|__m128i _mm_cvtps_epi32 (\__m128)|
|[_mm_cvtps_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtps_pd)|SSE2|Intrin. h|__m128d _mm_cvtps_pd (\__m128)|
|[_mm_cvtps_ph](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtps_ph)|F16C [2]|ımintrin. h|__m128i _mm_cvtps_ph (\__m128, const int)|
|[_mm_cvtsd_f64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsd_f64)|SSSE3|Intrin. h|Double _mm_cvtsd_f64 (\__m128d)|
|[_mm_cvtsd_si32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsd_si32)|SSE2|Intrin. h|int _mm_cvtsd_si32 (\__m128d)|
|[_mm_cvtsd_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsd_ss)|SSE2|Intrin. h|__m128 _mm_cvtsd_ss (\__m128, \__m128d)|
|[_mm_cvtsi128_si32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi128_si32)|SSE2|Intrin. h|int _mm_cvtsi128_si32 (\__m128i)|
|[_mm_cvtsi32_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi32_sd)|SSE2|Intrin. h|__m128d _mm_cvtsi32_sd (\__m128d, int)|
|[_mm_cvtsi32_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi32_si128)|SSE2|Intrin. h|__m128i _mm_cvtsi32_si128 (int)|
|[_mm_cvtsi32_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi32_si64)|MMX|mmintrin. h|__m64 _mm_cvtsi32_si64 (int) [3]|
|[_mm_cvtsi64_si32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtsi64_si32)|MMX|mmintrin. h|int _mm_cvtsi64_si32 (__m64) [3]|
|[_mm_cvtss_f32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtss_f32)|SSSE3|Intrin. h|kayan _mm_cvtss_f32 (\__m128)|
|[_mm_cvtss_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtss_sd)|SSE2|Intrin. h|__m128d _mm_cvtss_sd (\__m128d, \__m128)|
|[_mm_cvtt_ps2pi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtt_ps2pi)|SSE|Intrin. h|__m64 _mm_cvtt_ps2pi (\__m128)|
|[_mm_cvtt_ss2si](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvtt_ss2si)|SSE|Intrin. h|int _mm_cvtt_ss2si (\__m128)|
|[_mm_cvttpd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvttpd_epi32)|SSE2|Intrin. h|__m128i _mm_cvttpd_epi32 (\__m128d)|
|[_mm_cvttpd_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvttpd_pi32)|SSE2|Intrin. h|__m64 _mm_cvttpd_pi32 (\__m128d)|
|[_mm_cvttps_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvttps_epi32)|SSE2|Intrin. h|__m128i _mm_cvttps_epi32 (\__m128)|
|[_mm_cvttsd_si32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_cvttsd_si32)|SSE2|Intrin. h|int _mm_cvttsd_si32 (\__m128d)|
|[_mm_div_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_div_pd)|SSE2|Intrin. h|__m128d _mm_div_pd (\__m128d, \__m128d)|
|[_mm_div_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_div_ps)|SSE|Intrin. h|__m128 _mm_div_ps (\__m128, \__m128)|
|[_mm_div_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_div_sd)|SSE2|Intrin. h|__m128d _mm_div_sd (\__m128d, \__m128d)|
|[_mm_div_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_div_ss)|SSE|Intrin. h|__m128 _mm_div_ss (\__m128, \__m128)|
|[_mm_dp_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_dp_pd)|SSE41|Intrin. h|__m128d _mm_dp_pd (\__m128d, \__m128d, const int)|
|[_mm_dp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_dp_ps)|SSE41|Intrin. h|__m128 _mm_dp_ps (\__m128, \__m128, const int)|
|[_mm_empty](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_empty)|MMX|mmintrin. h|void _mm_empty (void) [3]|
|[_mm_extract_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_extract_epi16)|SSE2|Intrin. h|int _mm_extract_epi16 (\__m128i, int)|
|[_mm_extract_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_extract_epi32)|SSE41|Intrin. h|int _mm_extract_epi32 (\__m128i, const int)|
|[_mm_extract_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_extract_epi8)|SSE41|Intrin. h|int _mm_extract_epi8 (\__m128i, const int)|
|[_mm_extract_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_extract_ps)|SSE41|Intrin. h|int _mm_extract_ps (\__m128, const int)|
|[_mm_extract_si64](mm-extract-si64-mm-extracti-si64.md)|SSE4a|Intrin. h|__m128i _mm_extract_si64 (\__m128i, \__m128i)|
|[_mm_extracti_si64](mm-extract-si64-mm-extracti-si64.md)|SSE4a|Intrin. h|__m128i _mm_extracti_si64 (\__m128i, int, int)|
|[_mm_fmadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmadd_pd)|FMA [2]|ımintrin. h|__m128d _mm_fmadd_pd (\__m128d, \__m128d, \__m128d)|
|[_mm_fmadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmadd_ps)|FMA [2]|ımintrin. h|__m128 _mm_fmadd_ps (\__m128, \__m128, \__m128)|
|[_mm_fmadd_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmadd_sd)|FMA [2]|ımintrin. h|__m128d _mm_fmadd_sd (\__m128d, \__m128d, \__m128d)|
|[_mm_fmadd_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmadd_ss)|FMA [2]|ımintrin. h|__m128 _mm_fmadd_ss (\__m128, \__m128, \__m128)|
|[_mm_fmaddsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmaddsub_pd)|FMA [2]|ımintrin. h|__m128d _mm_fmaddsub_pd (\__m128d, \__m128d, \__m128d)|
|[_mm_fmaddsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmaddsub_ps)|FMA [2]|ımintrin. h|__m128 _mm_fmaddsub_ps (\__m128, \__m128, \__m128)|
|[_mm_fmsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsub_pd)|FMA [2]|ımintrin. h|__m128d _mm_fmsub_pd (\__m128d, \__m128d, \__m128d)|
|[_mm_fmsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsub_ps)|FMA [2]|ımintrin. h|__m128 _mm_fmsub_ps (\__m128, \__m128, \__m128)|
|[_mm_fmsub_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsub_sd)|FMA [2]|ımintrin. h|__m128d _mm_fmsub_sd (\__m128d, \__m128d, \__m128d)|
|[_mm_fmsub_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsub_ss)|FMA [2]|ımintrin. h|__m128 _mm_fmsub_ss (\__m128, \__m128, \__m128)|
|[_mm_fmsubadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsubadd_pd)|FMA [2]|ımintrin. h|__m128d _mm_fmsubadd_pd (\__m128d, \__m128d, \__m128d)|
|[_mm_fmsubadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fmsubadd_ps)|FMA [2]|ımintrin. h|__m128 _mm_fmsubadd_ps (\__m128, \__m128, \__m128)|
|[_mm_fnmadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmadd_pd)|FMA [2]|ımintrin. h|__m128d _mm_fnmadd_pd (\__m128d, \__m128d, \__m128d)|
|[_mm_fnmadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmadd_ps)|FMA [2]|ımintrin. h|__m128 _mm_fnmadd_ps (\__m128, \__m128, \__m128)|
|[_mm_fnmadd_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmadd_sd)|FMA [2]|ımintrin. h|__m128d _mm_fnmadd_sd (\__m128d, \__m128d, \__m128d)|
|[_mm_fnmadd_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmadd_ss)|FMA [2]|ımintrin. h|__m128 _mm_fnmadd_ss (\__m128, \__m128, \__m128)|
|[_mm_fnmsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmsub_pd)|FMA [2]|ımintrin. h|__m128d _mm_fnmsub_pd (\__m128d, \__m128d, \__m128d)|
|[_mm_fnmsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmsub_ps)|FMA [2]|ımintrin. h|__m128 _mm_fnmsub_ps (\__m128, \__m128, \__m128)|
|[_mm_fnmsub_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmsub_sd)|FMA [2]|ımintrin. h|__m128d _mm_fnmsub_sd (\__m128d, \__m128d, \__m128d)|
|[_mm_fnmsub_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_fnmsub_ss)|FMA [2]|ımintrin. h|__m128 _mm_fnmsub_ss (\__m128, \__m128, \__m128)|
|_mm_frcz_pd|XOP [1]|ammintrin. h|__m128d _mm_frcz_pd (\__m128d)|
|_mm_frcz_ps|XOP [1]|ammintrin. h|__m128 _mm_frcz_ps (\__m128)|
|_mm_frcz_sd|XOP [1]|ammintrin. h|__m128d _mm_frcz_sd (\__m128d, \__m128d)|
|_mm_frcz_ss|XOP [1]|ammintrin. h|__m128 _mm_frcz_ss (\__m128, \__m128)|
|[_mm_getcsr](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_getcsr)|SSE|Intrin. h|işaretsiz int _mm_getcsr (void)|
|[_mm_hadd_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadd_epi16)|SSSE3|Intrin. h|__m128i _mm_hadd_epi16 (\__m128i, \__m128i)|
|[_mm_hadd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadd_epi32)|SSSE3|Intrin. h|__m128i _mm_hadd_epi32 (\__m128i, \__m128i)|
|[_mm_hadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadd_pd)|SSE3|Intrin. h|__m128d _mm_hadd_pd (\__m128d, \__m128d)|
|[_mm_hadd_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadd_pi16)|SSSE3|Intrin. h|__m64 _mm_hadd_pi16 (\__m64, \__m64)|
|[_mm_hadd_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadd_pi32)|SSSE3|Intrin. h|__m64 _mm_hadd_pi32 (\__m64, \__m64)|
|[_mm_hadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadd_ps)|SSE3|Intrin. h|__m128 _mm_hadd_ps (\__m128, \__m128)|
|_mm_haddd_epi16|XOP [1]|ammintrin. h|__m128i _mm_haddd_epi16 (\__m128i)|
|_mm_haddd_epi8|XOP [1]|ammintrin. h|__m128i _mm_haddd_epi8 (\__m128i)|
|_mm_haddd_epu16|XOP [1]|ammintrin. h|__m128i _mm_haddd_epu16 (\__m128i)|
|_mm_haddd_epu8|XOP [1]|ammintrin. h|__m128i _mm_haddd_epu8 (\__m128i)|
|_mm_haddq_epi16|XOP [1]|ammintrin. h|__m128i _mm_haddq_epi16 (\__m128i)|
|_mm_haddq_epi32|XOP [1]|ammintrin. h|__m128i _mm_haddq_epi32 (\__m128i)|
|_mm_haddq_epi8|XOP [1]|ammintrin. h|__m128i _mm_haddq_epi8 (\__m128i)|
|_mm_haddq_epu16|XOP [1]|ammintrin. h|__m128i _mm_haddq_epu16 (\__m128i)|
|_mm_haddq_epu32|XOP [1]|ammintrin. h|__m128i _mm_haddq_epu32 (\__m128i)|
|_mm_haddq_epu8|XOP [1]|ammintrin. h|__m128i _mm_haddq_epu8 (\__m128i)|
|[_mm_hadds_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadds_epi16)|SSSE3|Intrin. h|__m128i _mm_hadds_epi16 (\__m128i, \__m128i)|
|[_mm_hadds_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hadds_pi16)|SSSE3|Intrin. h|__m64 _mm_hadds_pi16 (\__m64, \__m64)|
|_mm_haddw_epi8|XOP [1]|ammintrin. h|__m128i _mm_haddw_epi8 (\__m128i)|
|_mm_haddw_epu8|XOP [1]|ammintrin. h|__m128i _mm_haddw_epu8 (\__m128i)|
|[_mm_hsub_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsub_epi16)|SSSE3|Intrin. h|__m128i _mm_hsub_epi16 (\__m128i, \__m128i)|
|[_mm_hsub_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsub_epi32)|SSSE3|Intrin. h|__m128i _mm_hsub_epi32 (\__m128i, \__m128i)|
|[_mm_hsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsub_pd)|SSE3|Intrin. h|__m128d _mm_hsub_pd (\__m128d, \__m128d)|
|[_mm_hsub_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsub_pi16)|SSSE3|Intrin. h|__m64 _mm_hsub_pi16 (\__m64, \__m64)|
|[_mm_hsub_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsub_pi32)|SSSE3|Intrin. h|__m64 _mm_hsub_pi32 (\__m64, \__m64)|
|[_mm_hsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsub_ps)|SSE3|Intrin. h|__m128 _mm_hsub_ps (\__m128, \__m128)|
|_mm_hsubd_epi16|XOP [1]|ammintrin. h|__m128i _mm_hsubd_epi16 (\__m128i)|
|_mm_hsubq_epi32|XOP [1]|ammintrin. h|__m128i _mm_hsubq_epi32 (\__m128i)|
|[_mm_hsubs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsubs_epi16)|SSSE3|Intrin. h|__m128i _mm_hsubs_epi16 (\__m128i, \__m128i)|
|[_mm_hsubs_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_hsubs_pi16)|SSSE3|Intrin. h|__m64 _mm_hsubs_pi16 (\__m64, \__m64)|
|_mm_hsubw_epi8|XOP [1]|ammintrin. h|__m128i _mm_hsubw_epi8 (\__m128i)|
|[_mm_i32gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i32gather_epi32)|AVX2 [2]|ımintrin. h|__m128i _mm_i32gather_epi32 (int const \*, \__m128i, const int)|
|[_mm_i32gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i32gather_epi64)|AVX2 [2]|ımintrin. h|__m128i _mm_i32gather_epi64 (\__int64 const \*, \__m128i, const int)|
|[_mm_i32gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i32gather_pd)|AVX2 [2]|ımintrin. h|__m128d _mm_i32gather_pd (çift const \*, \__m128i, const int)|
|[_mm_i32gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i32gather_ps)|AVX2 [2]|ımintrin. h|__m128 _mm_i32gather_ps (float const \*, \__m128i, const int)|
|[_mm_i64gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i64gather_epi32)|AVX2 [2]|ımintrin. h|__m128i _mm_i64gather_epi32 (int const \*, \__m128i, const int)|
|[_mm_i64gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i64gather_epi64)|AVX2 [2]|ımintrin. h|__m128i _mm_i64gather_epi64 (\__int64 const \*, \__m128i, const int)|
|[_mm_i64gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i64gather_pd)|AVX2 [2]|ımintrin. h|__m128d _mm_i64gather_pd (çift const \*, \__m128i, const int)|
|[_mm_i64gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_i64gather_ps)|AVX2 [2]|ımintrin. h|__m128 _mm_i64gather_ps (float const \*, \__m128i, const int)|
|[_mm_insert_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_insert_epi16)|SSE2|Intrin. h|__m128i _mm_insert_epi16 (\__m128i, int, int)|
|[_mm_insert_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_insert_epi32)|SSE41|Intrin. h|__m128i _mm_insert_epi32 (\__m128i, int, const int)|
|[_mm_insert_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_insert_epi8)|SSE41|Intrin. h|__m128i _mm_insert_epi8 (\__m128i, int, const int)|
|[_mm_insert_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_insert_ps)|SSE41|Intrin. h|__m128 _mm_insert_ps (\__m128, \__m128, const int)|
|[_mm_insert_si64](mm-insert-si64-mm-inserti-si64.md)|SSE4a|Intrin. h|__m128i _mm_insert_si64 (\__m128i, \__m128i)|
|[_mm_inserti_si64](mm-insert-si64-mm-inserti-si64.md)|SSE4a|Intrin. h|__m128i _mm_inserti_si64 (\__m128i, \__m128i, int, int)|
|[_mm_lddqu_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_lddqu_si128)|SSE3|Intrin. h|__m128i _mm_lddqu_si128 (\__m128i const\*)|
|[_mm_lfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_lfence)|SSE2|Intrin. h|void _mm_lfence (void)|
|[_mm_load_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_pd)|SSE2|Intrin. h|__m128d _mm_load_pd (çift\*)|
|[_mm_load_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_ps)|SSE|Intrin. h|__m128 _mm_load_ps (float\*)|
|[_mm_load_ps1](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_ps1)|SSE|Intrin. h|__m128 _mm_load_ps1 (float\*)|
|[_mm_load_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_sd)|SSE2|Intrin. h|__m128d _mm_load_sd (çift\*)|
|[_mm_load_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_si128)|SSE2|Intrin. h|__m128i _mm_load_si128 (\__m128i\*)|
|[_mm_load_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load_ss)|SSE|Intrin. h|__m128 _mm_load_ss (float\*)|
|[_mm_load1_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_load1_pd)|SSE2|Intrin. h|__m128d _mm_load1_pd (çift\*)|
|[_mm_loaddup_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loaddup_pd)|SSE3|Intrin. h|__m128d _mm_loaddup_pd (çift const\*)|
|[_mm_loadh_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadh_pd)|SSE2|Intrin. h|__m128d _mm_loadh_pd (\__m128d, Çift\*)|
|[_mm_loadh_pi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadh_pi)|SSE|Intrin. h|__m128 _mm_loadh_pi (\__m128, \__m64\*)|
|[_mm_loadl_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadl_epi64)|SSE2|Intrin. h|__m128i _mm_loadl_epi64 (\__m128i\*)|
|[_mm_loadl_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadl_pd)|SSE2|Intrin. h|__m128d _mm_loadl_pd (\__m128d, Çift\*)|
|[_mm_loadl_pi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadl_pi)|SSE|Intrin. h|__m128 _mm_loadl_pi (\__m128, \__m64\*)|
|[_mm_loadr_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadr_pd)|SSE2|Intrin. h|__m128d _mm_loadr_pd (çift\*)|
|[_mm_loadr_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadr_ps)|SSE|Intrin. h|__m128 _mm_loadr_ps (float\*)|
|[_mm_loadu_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadu_pd)|SSE2|Intrin. h|__m128d _mm_loadu_pd (çift\*)|
|[_mm_loadu_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadu_ps)|SSE|Intrin. h|__m128 _mm_loadu_ps (float\*)|
|[_mm_loadu_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_loadu_si128)|SSE2|Intrin. h|__m128i _mm_loadu_si128 (\__m128i\*)|
|_mm_macc_epi16|XOP [1]|ammintrin. h|__m128i _mm_macc_epi16 (\__m128i, \__m128i, \__m128i)|
|_mm_macc_epi32|XOP [1]|ammintrin. h|__m128i _mm_macc_epi32 (\__m128i, \__m128i, \__m128i)|
|_mm_macc_pd|FMA4 [1]|ammintrin. h|__m128d _mm_macc_pd (\__m128d, \__m128d, \__m128d)|
|_mm_macc_ps|FMA4 [1]|ammintrin. h|__m128 _mm_macc_ps (\__m128, \__m128, \__m128)|
|_mm_macc_sd|FMA4 [1]|ammintrin. h|__m128d _mm_macc_sd (\__m128d, \__m128d, \__m128d)|
|_mm_macc_ss|FMA4 [1]|ammintrin. h|__m128 _mm_macc_ss (\__m128, \__m128, \__m128)|
|_mm_maccd_epi16|XOP [1]|ammintrin. h|__m128i _mm_maccd_epi16 (\__m128i, \__m128i, \__m128i)|
|_mm_macchi_epi32|XOP [1]|ammintrin. h|__m128i _mm_macchi_epi32 (\__m128i, \__m128i, \__m128i)|
|_mm_macclo_epi32|XOP [1]|ammintrin. h|__m128i _mm_macclo_epi32 (\__m128i, \__m128i, \__m128i)|
|_mm_maccs_epi16|XOP [1]|ammintrin. h|__m128i _mm_maccs_epi16 (\__m128i, \__m128i, \__m128i)|
|_mm_maccs_epi32|XOP [1]|ammintrin. h|__m128i _mm_maccs_epi32 (\__m128i, \__m128i, \__m128i)|
|_mm_maccsd_epi16|XOP [1]|ammintrin. h|__m128i _mm_maccsd_epi16 (\__m128i, \__m128i, \__m128i)|
|_mm_maccshi_epi32|XOP [1]|ammintrin. h|__m128i _mm_maccshi_epi32 (\__m128i, \__m128i, \__m128i)|
|_mm_maccslo_epi32|XOP [1]|ammintrin. h|__m128i _mm_maccslo_epi32 (\__m128i, \__m128i, \__m128i)|
|[_mm_madd_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_madd_epi16)|SSE2|Intrin. h|__m128i _mm_madd_epi16 (\__m128i, \__m128i)|
|[_mm_madd_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_madd_pi16)|MMX|mmintrin. h|__m64 _mm_madd_pi16 (\__m64, \__m64) [3]|
|_mm_maddd_epi16|XOP [1]|ammintrin. h|__m128i _mm_maddd_epi16 (\__m128i, \__m128i, \__m128i)|
|_mm_maddsd_epi16|XOP [1]|ammintrin. h|__m128i _mm_maddsd_epi16 (\__m128i, \__m128i, \__m128i)|
|_mm_maddsub_pd|FMA4 [1]|ammintrin. h|__m128d _mm_maddsub_pd (\__m128d, \__m128d, \__m128d)|
|_mm_maddsub_ps|FMA4 [1]|ammintrin. h|__m128 _mm_maddsub_ps (\__m128, \__m128, \__m128)|
|[_mm_maddubs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maddubs_epi16)|SSSE3|Intrin. h|__m128i _mm_maddubs_epi16 (\__m128i, \__m128i)|
|[_mm_maddubs_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maddubs_pi16)|SSSE3|Intrin. h|__m64 _mm_maddubs_pi16 (\__m64, \__m64)|
|[_mm_mask_i32gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i32gather_epi32)|AVX2 [2]|ımintrin. h|__m128i _mm_mask_i32gather_epi32 (\__m128i, int const \*, \__m128i, \__m128i, const int)|
|[_mm_mask_i32gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i32gather_epi64)|AVX2 [2]|ımintrin. h|__m128i _mm_mask_i32gather_epi64 (\__m128i, \__int64 const \*, \__m128i, \__m128i, const int)|
|[_mm_mask_i32gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i32gather_pd)|AVX2 [2]|ımintrin. h|__m128d _mm_mask_i32gather_pd (\__m128d, Double const \*, \__m128i, \__m128d, const int)|
|[_mm_mask_i32gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i32gather_ps)|AVX2 [2]|ımintrin. h|__m128 _mm_mask_i32gather_ps (\__m128, float const \*, \__m128i, \__m128, const int)|
|[_mm_mask_i64gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i64gather_epi32)|AVX2 [2]|ımintrin. h|__m128i _mm_mask_i64gather_epi32 (\__m128i, int const \*, \__m128i, \__m128i, const int)|
|[_mm_mask_i64gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i64gather_epi64)|AVX2 [2]|ımintrin. h|__m128i _mm_mask_i64gather_epi64 (\__m128i, \__int64 const \*, \__m128i, \__m128i, const int)|
|[_mm_mask_i64gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i64gather_pd)|AVX2 [2]|ımintrin. h|__m128d _mm_mask_i64gather_pd (\__m128d, Double const \*, \__m128i, \__m128d, const int)|
|[_mm_mask_i64gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mask_i64gather_ps)|AVX2 [2]|ımintrin. h|__m128 _mm_mask_i64gather_ps (\__m128, float const \*, \__m128i, \__m128, const int)|
|[_mm_maskload_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskload_epi32)|AVX2 [2]|ımintrin. h|__m128i _mm_maskload_epi32 (int const \*, \__m128i)|
|[_mm_maskload_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskload_epi64)|AVX2 [2]|ımintrin. h|__m128i _mm_maskload_epi64 (\__int64 const \*, \__m128i)|
|[_mm_maskload_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskload_pd)|AVX [2]|ımintrin. h|__m128d _mm_maskload_pd (çift const \*, \__m128i)|
|[_mm_maskload_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskload_ps)|AVX [2]|ımintrin. h|__m128 _mm_maskload_ps (float const \*, \__m128i)|
|[_mm_maskmoveu_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskmoveu_si128)|SSE2|Intrin. h|void _mm_maskmoveu_si128 (\__m128i, \__m128i, Char\*)|
|[_mm_maskstore_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskstore_epi32)|AVX2 [2]|ımintrin. h|void _mm_maskstore_epi32 (int \*, \__m128i, \__m128i)|
|[_mm_maskstore_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskstore_epi64)|AVX2 [2]|ımintrin. h|void _mm_maskstore_epi64 (\__int64 \*, \__m128i, \__m128i)|
|[_mm_maskstore_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskstore_pd)|AVX [2]|ımintrin. h|void _mm_maskstore_pd (çift \*, \__m128i, \__m128d)|
|[_mm_maskstore_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_maskstore_ps)|AVX [2]|ımintrin. h|void _mm_maskstore_ps (float \*, \__m128i, \__m128)|
|[_mm_max_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epi16)|SSE2|Intrin. h|__m128i _mm_max_epi16 (\__m128i, \__m128i)|
|[_mm_max_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epi32)|SSE41|Intrin. h|__m128i _mm_max_epi32 (\__m128i, \__m128i)|
|[_mm_max_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epi8)|SSE41|Intrin. h|__m128i _mm_max_epi8 (\__m128i, \__m128i)|
|[_mm_max_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epu16)|SSE41|Intrin. h|__m128i _mm_max_epu16 (\__m128i, \__m128i)|
|[_mm_max_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epu32)|SSE41|Intrin. h|__m128i _mm_max_epu32 (\__m128i, \__m128i)|
|[_mm_max_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_epu8)|SSE2|Intrin. h|__m128i _mm_max_epu8 (\__m128i, \__m128i)|
|[_mm_max_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_pd)|SSE2|Intrin. h|__m128d _mm_max_pd (\__m128d, \__m128d)|
|[_mm_max_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_ps)|SSE|Intrin. h|__m128 _mm_max_ps (\__m128, \__m128)|
|[_mm_max_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_sd)|SSE2|Intrin. h|__m128d _mm_max_sd (\__m128d, \__m128d)|
|[_mm_max_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_max_ss)|SSE|Intrin. h|__m128 _mm_max_ss (\__m128, \__m128)|
|[_mm_mfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mfence)|SSE2|Intrin. h|void _mm_mfence (void)|
|[_mm_min_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epi16)|SSE2|Intrin. h|__m128i _mm_min_epi16 (\__m128i, \__m128i)|
|[_mm_min_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epi32)|SSE41|Intrin. h|__m128i _mm_min_epi32 (\__m128i, \__m128i)|
|[_mm_min_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epi8)|SSE41|Intrin. h|__m128i _mm_min_epi8 (\__m128i, \__m128i)|
|[_mm_min_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epu16)|SSE41|Intrin. h|__m128i _mm_min_epu16 (\__m128i, \__m128i)|
|[_mm_min_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epu32)|SSE41|Intrin. h|__m128i _mm_min_epu32 (\__m128i, \__m128i)|
|[_mm_min_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_epu8)|SSE2|Intrin. h|__m128i _mm_min_epu8 (\__m128i, \__m128i)|
|[_mm_min_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_pd)|SSE2|Intrin. h|__m128d _mm_min_pd (\__m128d, \__m128d)|
|[_mm_min_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_ps)|SSE|Intrin. h|__m128 _mm_min_ps (\__m128, \__m128)|
|[_mm_min_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_sd)|SSE2|Intrin. h|__m128d _mm_min_sd (\__m128d, \__m128d)|
|[_mm_min_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_min_ss)|SSE|Intrin. h|__m128 _mm_min_ss (\__m128, \__m128)|
|[_mm_minpos_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_minpos_epu16)|SSE41|Intrin. h|__m128i _mm_minpos_epu16 (\__m128i)|
|[_mm_monitor](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_monitor)|SSE3|Intrin. h|void _mm_monitor (void const *, işaretsiz int, işaretsiz int)|
|[_mm_move_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_move_epi64)|SSE2|Intrin. h|__m128i _mm_move_epi64 (\__m128i)|
|[_mm_move_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_move_sd)|SSE2|Intrin. h|__m128d _mm_move_sd (\__m128d, \__m128d)|
|[_mm_move_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_move_ss)|SSE|Intrin. h|__m128 _mm_move_ss (\__m128, \__m128)|
|[_mm_movedup_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movedup_pd)|SSE3|Intrin. h|__m128d _mm_movedup_pd (\__m128d)|
|[_mm_movehdup_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movehdup_ps)|SSE3|Intrin. h|__m128 _mm_movehdup_ps (\__m128)|
|[_mm_movehl_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movehl_ps)|SSE|Intrin. h|__m128 _mm_movehl_ps (\__m128, \__m128)|
|[_mm_moveldup_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_moveldup_ps)|SSE3|Intrin. h|__m128 _mm_moveldup_ps (\__m128)|
|[_mm_movelh_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movelh_ps)|SSE|Intrin. h|__m128 _mm_movelh_ps (\__m128, \__m128)|
|[_mm_movemask_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movemask_epi8)|SSE2|Intrin. h|int _mm_movemask_epi8 (\__m128i)|
|[_mm_movemask_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movemask_pd)|SSE2|Intrin. h|int _mm_movemask_pd (\__m128d)|
|[_mm_movemask_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movemask_ps)|SSE|Intrin. h|int _mm_movemask_ps (\__m128)|
|[_mm_movepi64_pi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movepi64_pi64)|SSE2|Intrin. h|__m64 _mm_movepi64_pi64 (\__m128i)|
|[_mm_movpi64_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_movpi64_epi64)|SSE2|Intrin. h|__m128i _mm_movpi64_epi64 (\__m64)|
|[_mm_mpsadbw_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mpsadbw_epu8)|SSE41|Intrin. h|__m128i _mm_mpsadbw_epu8 (\__m128i, \__m128i, const int)|
|_mm_msub_pd|FMA4 [1]|ammintrin. h|__m128d _mm_msub_pd (\__m128d, \__m128d, \__m128d)|
|_mm_msub_ps|FMA4 [1]|ammintrin. h|__m128 _mm_msub_ps (\__m128, \__m128, \__m128)|
|_mm_msub_sd|FMA4 [1]|ammintrin. h|__m128d _mm_msub_sd (\__m128d, \__m128d, \__m128d)|
|_mm_msub_ss|FMA4 [1]|ammintrin. h|__m128 _mm_msub_ss (\__m128, \__m128, \__m128)|
|_mm_msubadd_pd|FMA4 [1]|ammintrin. h|__m128d _mm_msubadd_pd (\__m128d, \__m128d, \__m128d)|
|_mm_msubadd_ps|FMA4 [1]|ammintrin. h|__m128 _mm_msubadd_ps (\__m128, \__m128, \__m128)|
|[_mm_mul_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_epi32)|SSE41|Intrin. h|__m128i _mm_mul_epi32 (\__m128i, \__m128i)|
|[_mm_mul_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_epu32)|SSE2|Intrin. h|__m128i _mm_mul_epu32 (\__m128i, \__m128i)|
|[_mm_mul_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_pd)|SSE2|Intrin. h|__m128d _mm_mul_pd (\__m128d, \__m128d)|
|[_mm_mul_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_ps)|SSE|Intrin. h|__m128 _mm_mul_ps (\__m128, \__m128)|
|[_mm_mul_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_sd)|SSE2|Intrin. h|__m128d _mm_mul_sd (\__m128d, \__m128d)|
|[_mm_mul_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_ss)|SSE|Intrin. h|__m128 _mm_mul_ss (\__m128, \__m128)|
|[_mm_mul_su32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mul_su32)|SSE2|Intrin. h|__m64 _mm_mul_su32 (\__m64, \__m64)|
|[_mm_mulhi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mulhi_epi16)|SSE2|Intrin. h|__m128i _mm_mulhi_epi16 (\__m128i, \__m128i)|
|[_mm_mulhi_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mulhi_epu16)|SSE2|Intrin. h|__m128i _mm_mulhi_epu16 (\__m128i, \__m128i)|
|[_mm_mulhi_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mulhi_pi16)|MMX|mmintrin. h|__m64 _mm_mulhi_pi16 (\__m64, \__m64) [3]|
|[_mm_mulhrs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mulhrs_epi16)|SSSE3|Intrin. h|__m128i _mm_mulhrs_epi16 (\__m128i, \__m128i)|
|[_mm_mulhrs_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mulhrs_pi16)|SSSE3|Intrin. h|__m64 _mm_mulhrs_pi16 (\__m64, \__m64)|
|[_mm_mullo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mullo_epi16)|SSE2|Intrin. h|__m128i _mm_mullo_epi16 (\__m128i, \__m128i)|
|[_mm_mullo_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mullo_epi32)|SSE41|Intrin. h|__m128i _mm_mullo_epi32 (\__m128i, \__m128i)|
|[_mm_mullo_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mullo_pi16)|MMX|mmintrin. h|__m64 _mm_mullo_pi16 (\__m64, \__m64) [3]|
|[_mm_mwait](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_mwait)|SSE3|Intrin. h|void _mm_mwait (işaretsiz int, işaretsiz int)|
|_mm_nmacc_pd|FMA4 [1]|ammintrin. h|__m128d _mm_nmacc_pd (\__m128d, \__m128d, \__m128d)|
|_mm_nmacc_ps|FMA4 [1]|ammintrin. h|__m128 _mm_nmacc_ps (\__m128, \__m128, \__m128)|
|_mm_nmacc_sd|FMA4 [1]|ammintrin. h|__m128d _mm_nmacc_sd (\__m128d, \__m128d, \__m128d)|
|_mm_nmacc_ss|FMA4 [1]|ammintrin. h|__m128 _mm_nmacc_ss (\__m128, \__m128, \__m128)|
|_mm_nmsub_pd|FMA4 [1]|ammintrin. h|__m128d _mm_nmsub_pd (\__m128d, \__m128d, \__m128d)|
|_mm_nmsub_ps|FMA4 [1]|ammintrin. h|__m128 _mm_nmsub_ps (\__m128, \__m128, \__m128)|
|_mm_nmsub_sd|FMA4 [1]|ammintrin. h|__m128d _mm_nmsub_sd (\__m128d, \__m128d, \__m128d)|
|_mm_nmsub_ss|FMA4 [1]|ammintrin. h|__m128 _mm_nmsub_ss (\__m128, \__m128, \__m128)|
|[_mm_or_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_or_pd)|SSE2|Intrin. h|__m128d _mm_or_pd (\__m128d, \__m128d)|
|[_mm_or_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_or_ps)|SSE|Intrin. h|__m128 _mm_or_ps (\__m128, \__m128)|
|[_mm_or_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_or_si64)|MMX|mmintrin. h|__m64 _mm_or_si64 (\__m64, \__m64) [3]|
|[_mm_or_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_or_si128)|SSE2|Intrin. h|__m128i _mm_or_si128 (\__m128i, \__m128i)|
|[_mm_packs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_packs_epi16)|SSE2|Intrin. h|__m128i _mm_packs_epi16 (\__m128i, \__m128i)|
|[_mm_packs_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_packs_epi32)|SSE2|Intrin. h|__m128i _mm_packs_epi32 (\__m128i, \__m128i)|
|[_mm_packs_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_packs_pi16)|MMX|mmintrin. h|__m64 _mm_packs_pi16 (__m64, __m64) [3]|
|[_mm_packs_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_packs_pi32)|MMX|mmintrin. h|__m64 _mm_packs_pi32 (__m64, __m64) [3]|
|[_mm_packs_pu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_packs_pu16)|MMX|mmintrin. h|__m64 _mm_packs_pu16 (__m64, __m64) [3]|
|[_mm_packus_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_packus_epi16)|SSE2|Intrin. h|__m128i _mm_packus_epi16 (\__m128i, \__m128i)|
|[_mm_packus_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_packus_epi32)|SSE41|Intrin. h|__m128i _mm_packus_epi32 (\__m128i, \__m128i)|
|[_mm_pause](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_pause)|SSE2|Intrin. h|void _mm_pause (void)|
|_mm_perm_epi8|XOP [1]|ammintrin. h|__m128i _mm_perm_epi8 (\__m128i, \__m128i, \__m128i)|
|[_mm_permute_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_permute_pd)|AVX [2]|ımintrin. h|__m128d _mm_permute_pd (\__m128d, int)|
|[_mm_permute_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_permute_ps)|AVX [2]|ımintrin. h|__m128 _mm_permute_ps (\__m128, int)|
|_mm_permute2_pd|XOP [1]|ammintrin. h|__m128d _mm_permute2_pd (\__m128d, \__m128d, \__m128i, int)|
|_mm_permute2_ps|XOP [1]|ammintrin. h|__m128 _mm_permute2_ps (\__m128, \__m128, \__m128i, int)|
|[_mm_permutevar_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_permutevar_pd)|AVX [2]|ımintrin. h|__m128d _mm_permutevar_pd (\__m128d, \__m128i)|
|[_mm_permutevar_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_permutevar_ps)|AVX [2]|ımintrin. h|__m128 _mm_permutevar_ps (\__m128, \__m128i)|
|[_mm_popcnt_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_popcnt_u32)|POPCNT|Intrin. h|int _mm_popcnt_u32 (işaretsiz int)|
|[_mm_prefetch](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_prefetch)|SSE|Intrin. h|void _mm_prefetch (Char *, int)|
|[_mm_rcp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_rcp_ps)|SSE|Intrin. h|__m128 _mm_rcp_ps (\__m128)|
|[_mm_rcp_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_rcp_ss)|SSE|Intrin. h|__m128 _mm_rcp_ss (\__m128)|
|_mm_rot_epi16|XOP [1]|ammintrin. h|__m128i _mm_rot_epi16 (\__m128i, \__m128i)|
|_mm_rot_epi32|XOP [1]|ammintrin. h|__m128i _mm_rot_epi32 (\__m128i, \__m128i)|
|_mm_rot_epi64|XOP [1]|ammintrin. h|__m128i _mm_rot_epi64 (\__m128i, \__m128i)|
|_mm_rot_epi8|XOP [1]|ammintrin. h|__m128i _mm_rot_epi8 (\__m128i, \__m128i)|
|_mm_roti_epi16|XOP [1]|ammintrin. h|__m128i _mm_rot_epi16 (\__m128i, int)|
|_mm_roti_epi32|XOP [1]|ammintrin. h|__m128i _mm_rot_epi32 (\__m128i, int)|
|_mm_roti_epi64|XOP [1]|ammintrin. h|__m128i _mm_rot_epi64 (\__m128i, int)|
|_mm_roti_epi8|XOP [1]|ammintrin. h|__m128i _mm_rot_epi8 (\__m128i, int)|
|[_mm_round_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_round_pd)|SSE41|Intrin. h|__m128d _mm_round_pd (\__m128d, const int)|
|[_mm_round_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_round_ps)|SSE41|Intrin. h|__m128 _mm_round_ps (\__m128, const int)|
|[_mm_round_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_round_sd)|SSE41|Intrin. h|__m128d _mm_round_sd (\__m128d, \__m128d, const int)|
|[_mm_round_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_round_ss)|SSE41|Intrin. h|__m128 _mm_round_ss (\__m128, \__m128, const int)|
|[_mm_rsqrt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_rsqrt_ps)|SSE|Intrin. h|__m128 _mm_rsqrt_ps (\__m128)|
|[_mm_rsqrt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_rsqrt_ss)|SSE|Intrin. h|__m128 _mm_rsqrt_ss (\__m128)|
|[_mm_sad_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sad_epu8)|SSE2|Intrin. h|__m128i _mm_sad_epu8 (\__m128i, \__m128i)|
|[_mm_set_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_epi16)|SSE2|Intrin. h|__m128i _mm_set_epi16 (kısa, kısa, kısa, kısa, kısa, kısa, kısa, kısa)|
|[_mm_set_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_epi32)|SSE2|Intrin. h|__m128i _mm_set_epi32 (int, int, int, int)|
|[_mm_set_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_epi64)|SSE2|Intrin. h|__m128i _mm_set_epi64 (\__m64, \__m64)|
|[_mm_set_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_epi8)|SSE2|Intrin. h|__m128i _mm_set_epi8 (Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char)|
|[_mm_set_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_pd)|SSE2|Intrin. h|__m128d _mm_set_pd (Double, Double)|
|[_mm_set_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_pi16)|MMX|Intrin. h|__m64 _mm_set_pi16 (kısa, kısa, kısa, kısa)|
|[_mm_set_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_pi32)|MMX|Intrin. h|__m64 _mm_set_pi32 (int, int)|
|[_mm_set_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_pi8)|MMX|Intrin. h|__m64 _mm_set_pi8 (Char, Char, Char, Char, Char, Char, Char, Char)|
|[_mm_set_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_ps)|SSE|Intrin. h|__m128 _mm_set_ps (float, float, float, float)|
|[_mm_set_ps1](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_ps1)|SSE|Intrin. h|__m128 _mm_set_ps1 (float)|
|[_mm_set_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_sd)|SSE2|Intrin. h|__m128d _mm_set_sd (çift)|
|[_mm_set_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set_ss)|SSE|Intrin. h|__m128 _mm_set_ss (float)|
|[_mm_set1_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_epi16)|SSE2|Intrin. h|__m128i _mm_set1_epi16 (kısa)|
|[_mm_set1_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_epi32)|SSE2|Intrin. h|__m128i _mm_set1_epi32 (int)|
|[_mm_set1_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_epi64)|SSE2|Intrin. h|__m128i _mm_set1_epi64 (\__m64)|
|[_mm_set1_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_epi8)|SSE2|Intrin. h|__m128i _mm_set1_epi8 (Char)|
|[_mm_set1_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_pd)|SSE2|Intrin. h|__m128d _mm_set1_pd (çift)|
|[_mm_set1_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_pi16)|MMX|Intrin. h|__m64 _mm_set1_pi16 (kısa)|
|[_mm_set1_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_pi32)|MMX|Intrin. h|__m64 _mm_set1_pi32 (int)|
|[_mm_set1_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_set1_pi8)|MMX|Intrin. h|__m64 _mm_set1_pi8 (Char)|
|[_mm_setcsr](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setcsr)|SSE|Intrin. h|void _mm_setcsr (işaretsiz int)|
|_mm_setl_epi64|SSE2|Intrin. h|__m128i _mm_setl_epi64 (\__m128i)|
|[_mm_setr_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_epi16)|SSE2|Intrin. h|__m128i _mm_setr_epi16 (kısa, kısa, kısa, kısa, kısa, kısa, kısa, kısa)|
|[_mm_setr_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_epi32)|SSE2|Intrin. h|__m128i _mm_setr_epi32 (int, int, int, int)|
|[_mm_setr_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_epi64)|SSE2|Intrin. h|__m128i _mm_setr_epi64 (\__m64, \__m64)|
|[_mm_setr_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_epi8)|SSE2|Intrin. h|__m128i _mm_setr_epi8 (Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char)|
|[_mm_setr_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_pd)|SSE2|Intrin. h|__m128d _mm_setr_pd (Double, Double)|
|[_mm_setr_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_pi16)|MMX|Intrin. h|__m64 _mm_setr_pi16 (kısa, kısa, kısa, kısa)|
|[_mm_setr_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_pi32)|MMX|Intrin. h|__m64 _mm_setr_pi32 (int, int)|
|[_mm_setr_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_pi8)|MMX|Intrin. h|__m64 _mm_setr_pi8 (Char, Char, Char, Char, Char, Char, Char, Char)|
|[_mm_setr_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setr_ps)|SSE|Intrin. h|__m128 _mm_setr_ps (float, float, float, float)|
|[_mm_setzero_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setzero_pd)|SSE2|Intrin. h|__m128d _mm_setzero_pd (void)|
|[_mm_setzero_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setzero_ps)|SSE|Intrin. h|__m128 _mm_setzero_ps (void)|
|[_mm_setzero_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setzero_si128)|SSE2|Intrin. h|__m128i _mm_setzero_si128 (void)|
|[_mm_setzero_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_setzero_si64)|MMX|Intrin. h|__m64 _mm_setzero_si64 (void)|
|[_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)|SSE|Intrin. h|void _mm_sfence (void)|
|_mm_sha_epi16|XOP [1]|ammintrin. h|__m128i _mm_sha_epi16 (\__m128i, \__m128i)|
|_mm_sha_epi32|XOP [1]|ammintrin. h|__m128i _mm_sha_epi32 (\__m128i, \__m128i)|
|_mm_sha_epi64|XOP [1]|ammintrin. h|__m128i _mm_sha_epi64 (\__m128i, \__m128i)|
|_mm_sha_epi8|XOP [1]|ammintrin. h|__m128i _mm_sha_epi8 (\__m128i, \__m128i)|
|_mm_shl_epi16|XOP [1]|ammintrin. h|__m128i _mm_shl_epi16 (\__m128i, \__m128i)|
|_mm_shl_epi32|XOP [1]|ammintrin. h|__m128i _mm_shl_epi32 (\__m128i, \__m128i)|
|_mm_shl_epi64|XOP [1]|ammintrin. h|__m128i _mm_shl_epi64 (\__m128i, \__m128i)|
|_mm_shl_epi8|XOP [1]|ammintrin. h|__m128i _mm_shl_epi8 (\__m128i, \__m128i)|
|[_mm_shuffle_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shuffle_epi32)|SSE2|Intrin. h|__m128i _mm_shuffle_epi32 (\__m128i, int)|
|[_mm_shuffle_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shuffle_epi8)|SSSE3|Intrin. h|__m128i _mm_shuffle_epi8 (\__m128i, \__m128i)|
|[_mm_shuffle_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shuffle_pd)|SSE2|Intrin. h|__m128d _mm_shuffle_pd (\__m128d, \__m128d, int)|
|[_mm_shuffle_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shuffle_pi8)|SSSE3|Intrin. h|__m64 _mm_shuffle_pi8 (\__m64, \__m64)|
|[_mm_shuffle_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shuffle_ps)|SSE|Intrin. h|__m128 _mm_shuffle_ps (\__m128, \__m128, işaretsiz int)|
|[_mm_shufflehi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shufflehi_epi16)|SSE2|Intrin. h|__m128i _mm_shufflehi_epi16 (\__m128i, int)|
|[_mm_shufflelo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_shufflelo_epi16)|SSE2|Intrin. h|__m128i _mm_shufflelo_epi16 (\__m128i, int)|
|[_mm_sign_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sign_epi16)|SSSE3|Intrin. h|__m128i _mm_sign_epi16 (\__m128i, \__m128i)|
|[_mm_sign_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sign_epi32)|SSSE3|Intrin. h|__m128i _mm_sign_epi32 (\__m128i, \__m128i)|
|[_mm_sign_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sign_epi8)|SSSE3|Intrin. h|__m128i _mm_sign_epi8 (\__m128i, \__m128i)|
|[_mm_sign_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sign_pi16)|SSSE3|Intrin. h|__m64 _mm_sign_pi16 (\__m64, \__m64)|
|[_mm_sign_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sign_pi32)|SSSE3|Intrin. h|__m64 _mm_sign_pi32 (\__m64, \__m64)|
|[_mm_sign_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sign_pi8)|SSSE3|Intrin. h|__m64 _mm_sign_pi8 (\__m64, \__m64)|
|[_mm_sll_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sll_epi16)|SSE2|Intrin. h|__m128i _mm_sll_epi16 (\__m128i, \__m128i)|
|[_mm_sll_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sll_epi32)|SSE2|Intrin. h|__m128i _mm_sll_epi32 (\__m128i, \__m128i)|
|[_mm_sll_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sll_epi64)|SSE2|Intrin. h|__m128i _mm_sll_epi64 (\__m128i, \__m128i)|
|[_mm_sll_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sll_pi16)|MMX|mmintrin. h|__m64 _mm_sll_pi16 (\__m64, \__m64) [3]|
|[_mm_sll_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sll_pi32)|MMX|mmintrin. h|__m64 _mm_sll_pi32 (\__m64, \__m64) [3]|
|[_mm_sll_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sll_si64)|MMX|mmintrin. h|__m64 _mm_sll_si64 (\__m64, \__m64) [3]|
|[_mm_slli_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_slli_epi16)|SSE2|Intrin. h|__m128i _mm_slli_epi16 (\__m128i, int)|
|[_mm_slli_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_slli_epi32)|SSE2|Intrin. h|__m128i _mm_slli_epi32 (\__m128i, int)|
|[_mm_slli_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_slli_epi64)|SSE2|Intrin. h|__m128i _mm_slli_epi64 (\__m128i, int)|
|[_mm_slli_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_slli_pi16)|MMX|mmintrin. h|__m64 _mm_slli_pi16 (\__m64, int) [3]|
|[_mm_slli_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_slli_pi32)|MMX|mmintrin. h|__m64 _mm_slli_pi32 (\__m64, int) [3]|
|[_mm_slli_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_slli_si64)|MMX|mmintrin. h|__m64 _mm_slli_si64 (\__m64, int) [3]|
|[_mm_slli_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_slli_si128)|SSE2|Intrin. h|__m128i _mm_slli_si128 (\__m128i, int)|
|[_mm_sllv_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sllv_epi32)|AVX2 [2]|ımintrin. h|__m128i _mm_sllv_epi32 (\__m128i, \__m128i)|
|[_mm_sllv_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sllv_epi64)|AVX2 [2]|ımintrin. h|__m128i _mm_sllv_epi64 (\__m128i, \__m128i)|
|[_mm_sqrt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sqrt_pd)|SSE2|Intrin. h|__m128d _mm_sqrt_pd (\__m128d)|
|[_mm_sqrt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sqrt_ps)|SSE|Intrin. h|__m128 _mm_sqrt_ps (\__m128)|
|[_mm_sqrt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sqrt_sd)|SSE2|Intrin. h|__m128d _mm_sqrt_sd (\__m128d, \__m128d)|
|[_mm_sqrt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sqrt_ss)|SSE|Intrin. h|__m128 _mm_sqrt_ss (\__m128)|
|[_mm_sra_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sra_epi16)|SSE2|Intrin. h|__m128i _mm_sra_epi16 (\__m128i, \__m128i)|
|[_mm_sra_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sra_epi32)|SSE2|Intrin. h|__m128i _mm_sra_epi32 (\__m128i, \__m128i)|
|[_mm_sra_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sra_pi16)|MMX|mmintrin. h|__m64 _mm_sra_pi16 (\__m64, \__m64) [3]|
|[_mm_sra_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sra_pi32)|MMX|mmintrin. h|__m64 _mm_sra_pi32 (\__m64, \__m64) [3]|
|[_mm_srai_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srai_epi16)|SSE2|Intrin. h|__m128i _mm_srai_epi16 (\__m128i, int)|
|[_mm_srai_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srai_epi32)|SSE2|Intrin. h|__m128i _mm_srai_epi32 (\__m128i, int)|
|[_mm_srai_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srai_pi16)|MMX|mmintrin. h|__m64 _mm_srai_pi16 (\__m64, int) [3]|
|[_mm_srai_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srai_pi32)|MMX|mmintrin. h|__m64 _mm_srai_pi32 (\__m64, int) [3]|
|[_mm_srav_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srav_epi32)|AVX2 [2]|ımintrin. h|__m128i _mm_srav_epi32 (\__m128i, \__m128i)|
|[_mm_srl_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srl_epi16)|SSE2|Intrin. h|__m128i _mm_srl_epi16 (\__m128i, \__m128i)|
|[_mm_srl_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srl_epi32)|SSE2|Intrin. h|__m128i _mm_srl_epi32 (\__m128i, \__m128i)|
|[_mm_srl_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srl_epi64)|SSE2|Intrin. h|__m128i _mm_srl_epi64 (\__m128i, \__m128i)|
|[_mm_srl_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srl_pi16)|MMX|mmintrin. h|__m64 _mm_srl_pi16 (\__m64, \__m64) [3]|
|[_mm_srl_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srl_pi32)|MMX|mmintrin. h|__m64 _mm_srl_pi32 (\__m64, \__m64) [3]|
|[_mm_srl_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srl_si64)|MMX|mmintrin. h|__m64 _mm_srl_si64 (\__m64, \__m64) [3]|
|[_mm_srli_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srli_epi16)|SSE2|Intrin. h|__m128i _mm_srli_epi16 (\__m128i, int)|
|[_mm_srli_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srli_epi32)|SSE2|Intrin. h|__m128i _mm_srli_epi32 (\__m128i, int)|
|[_mm_srli_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srli_epi64)|SSE2|Intrin. h|__m128i _mm_srli_epi64 (\__m128i, int)|
|[_mm_srli_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srli_pi16)|MMX|mmintrin. h|__m64 _mm_srli_pi16 (\__m64, int) [3]|
|[_mm_srli_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srli_pi32)|MMX|mmintrin. h|__m64 _mm_srli_pi32 (\__m64, int) [3]|
|[_mm_srli_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srli_si64)|MMX|mmintrin. h|__m64 _mm_srli_si64 (\__m64, int) [3]|
|[_mm_srli_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srli_si128)|SSE2|Intrin. h|__m128i _mm_srli_si128 (\__m128i, int)|
|[_mm_srlv_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srlv_epi32)|AVX2 [2]|ımintrin. h|__m128i _mm_srlv_epi32 (\__m128i, \__m128i)|
|[_mm_srlv_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_srlv_epi64)|AVX2 [2]|ımintrin. h|__m128i _mm_srlv_epi64 (\__m128i, \__m128i)|
|[_mm_store_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_pd)|SSE2|Intrin. h|void _mm_store_pd (çift\*, \__m128d)|
|[_mm_store_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ps)|SSE|Intrin. h|void _mm_store_ps (float\*, \__m128)|
|[_mm_store_ps1](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ps1)|SSE|Intrin. h|void _mm_store_ps1 (float\*, \__m128)|
|[_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)|SSE2|Intrin. h|void _mm_store_sd (çift\*, \__m128d)|
|[_mm_store_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_si128)|SSE2|Intrin. h|void _mm_store_si128 (\__m128i\*, \__m128i)|
|[_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)|SSE|Intrin. h|void _mm_store_ss (float\*, \__m128)|
|[_mm_store1_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store1_pd)|SSE2|Intrin. h|void _mm_store1_pd (çift\*, \__m128d)|
|[_mm_storeh_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storeh_pd)|SSE2|Intrin. h|void _mm_storeh_pd (çift\*, \__m128d)|
|[_mm_storeh_pi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storeh_pi)|SSE|Intrin. h|void _mm_storeh_pi (\__m64\*, \__m128)|
|[_mm_storel_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storel_epi64)|SSE2|Intrin. h|void _mm_storel_epi64 (\__m128i\*, \__m128i)|
|[_mm_storel_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storel_pd)|SSE2|Intrin. h|void _mm_storel_pd (çift\*, \__m128d)|
|[_mm_storel_pi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storel_pi)|SSE|Intrin. h|void _mm_storel_pi (\__m64\*, \__m128)|
|[_mm_storer_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storer_pd)|SSE2|Intrin. h|void _mm_storer_pd (çift\*, \__m128d)|
|[_mm_storer_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storer_ps)|SSE|Intrin. h|void _mm_storer_ps (float\*, \__m128)|
|[_mm_storeu_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storeu_pd)|SSE2|Intrin. h|void _mm_storeu_pd (çift\*, \__m128d)|
|[_mm_storeu_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storeu_ps)|SSE|Intrin. h|void _mm_storeu_ps (float\*, \__m128)|
|[_mm_storeu_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_storeu_si128)|SSE2|Intrin. h|void _mm_storeu_si128 (\__m128i\*, \__m128i)|
|[_mm_stream_load_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_load_si128)|SSE41|Intrin. h|__m128i _mm_stream_load_si128 (\__m128i\*)|
|[_mm_stream_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_pd)|SSE2|Intrin. h|void _mm_stream_pd (çift\*, \__m128d)|
|[_mm_stream_pi](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_pi)|SSE|Intrin. h|void _mm_stream_pi (\__m64\*, \__m64)|
|[_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)|SSE|Intrin. h|void _mm_stream_ps (float\*, \__m128)|
|[_mm_stream_sd](mm-stream-sd.md)|SSE4a|Intrin. h|void _mm_stream_sd (çift\*, \__m128d)|
|[_mm_stream_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_si128)|SSE2|Intrin. h|void _mm_stream_si128 (\__m128i\*, \__m128i)|
|[_mm_stream_si32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_si32)|SSE2|Intrin. h|void _mm_stream_si32 (int\*, int)|
|[_mm_stream_ss](mm-stream-ss.md)|SSE4a|Intrin. h|void _mm_stream_ss (float\*, \__m128)|
|[_mm_sub_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_epi16)|SSE2|Intrin. h|__m128i _mm_sub_epi16 (\__m128i, \__m128i)|
|[_mm_sub_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_epi32)|SSE2|Intrin. h|__m128i _mm_sub_epi32 (\__m128i, \__m128i)|
|[_mm_sub_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_epi64)|SSE2|Intrin. h|__m128i _mm_sub_epi64 (\__m128i, \__m128i)|
|[_mm_sub_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_epi8)|SSE2|Intrin. h|__m128i _mm_sub_epi8 (\__m128i, \__m128i)|
|[_mm_sub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_pd)|SSE2|Intrin. h|__m128d _mm_sub_pd (\__m128d, \__m128d)|
|[_mm_sub_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_pi8)|MMX|mmintrin. h|__m64 _mm_sub_pi8 (\__m64, \__m64) [3]|
|[_mm_sub_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_pi16)|MMX|mmintrin. h|__m64 _mm_sub_pi16 (\__m64, \__m64) [3]|
|[_mm_sub_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_pi32)|MMX|mmintrin. h|__m64 _mm_sub_pi32 (\__m64, \__m64) [3]|
|[_mm_sub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_ps)|SSE|Intrin. h|__m128 _mm_sub_ps (\__m128, \__m128)|
|[_mm_sub_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_sd)|SSE2|Intrin. h|__m128d _mm_sub_sd (\__m128d, \__m128d)|
|[_mm_sub_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_si64)|SSE2|Intrin. h|__m64 _mm_sub_si64 (\__m64, \__m64)|
|[_mm_sub_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sub_ss)|SSE|Intrin. h|__m128 _mm_sub_ss (\__m128, \__m128)|
|[_mm_subs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_epi16)|SSE2|Intrin. h|__m128i _mm_subs_epi16 (\__m128i, \__m128i)|
|[_mm_subs_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_epi8)|SSE2|Intrin. h|__m128i _mm_subs_epi8 (\__m128i, \__m128i)|
|[_mm_subs_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_epu16)|SSE2|Intrin. h|__m128i _mm_subs_epu16 (\__m128i, \__m128i)|
|[_mm_subs_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_epu8)|SSE2|Intrin. h|__m128i _mm_subs_epu8 (\__m128i, \__m128i)|
|[_mm_subs_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_pi8)|MMX|mmintrin. h|__m64 _mm_subs_pi8 (\__m64, \__m64) [3]|
|[_mm_subs_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_pi16)|MMX|mmintrin. h|__m64 _mm_subs_pi16 (\__m64, \__m64) [3]|
|[_mm_subs_pu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_pu8)|MMX|mmintrin. h|__m64 _mm_subs_pu8 (\__m64, \__m64) [3]|
|[_mm_subs_pu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_subs_pu16)|MMX|mmintrin. h|__m64 _mm_subs_pu16 (\__m64, \__m64) [3]|
|[_mm_testc_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testc_pd)|AVX [2]|ımintrin. h|int _mm_testc_pd (\__m128d, \__m128d)|
|[_mm_testc_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testc_ps)|AVX [2]|ımintrin. h|int _mm_testc_ps (\__m128, \__m128)|
|[_mm_testc_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testc_si128)|SSE41|Intrin. h|int _mm_testc_si128 (\__m128i, \__m128i)|
|[_mm_testnzc_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testnzc_pd)|AVX [2]|ımintrin. h|int _mm_testnzc_pd (\__m128d, \__m128d)|
|[_mm_testnzc_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testnzc_ps)|AVX [2]|ımintrin. h|int _mm_testnzc_ps (\__m128, \__m128)|
|[_mm_testnzc_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testnzc_si128)|SSE41|Intrin. h|int _mm_testnzc_si128 (\__m128i, \__m128i)|
|[_mm_testz_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testz_pd)|AVX [2]|ımintrin. h|int _mm_testz_pd (\__m128d, \__m128d)|
|[_mm_testz_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testz_ps)|AVX [2]|ımintrin. h|int _mm_testz_ps (\__m128, \__m128)|
|[_mm_testz_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_testz_si128)|SSE41|Intrin. h|int _mm_testz_si128 (\__m128i, \__m128i)|
|[_mm_ucomieq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomieq_sd)|SSE2|Intrin. h|int _mm_ucomieq_sd (\__m128d, \__m128d)|
|[_mm_ucomieq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomieq_ss)|SSE|Intrin. h|int _mm_ucomieq_ss (\__m128, \__m128)|
|[_mm_ucomige_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomige_sd)|SSE2|Intrin. h|int _mm_ucomige_sd (\__m128d, \__m128d)|
|[_mm_ucomige_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomige_ss)|SSE|Intrin. h|int _mm_ucomige_ss (\__m128, \__m128)|
|[_mm_ucomigt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomigt_sd)|SSE2|Intrin. h|int _mm_ucomigt_sd (\__m128d, \__m128d)|
|[_mm_ucomigt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomigt_ss)|SSE|Intrin. h|int _mm_ucomigt_ss (\__m128, \__m128)|
|[_mm_ucomile_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomile_sd)|SSE2|Intrin. h|int _mm_ucomile_sd (\__m128d, \__m128d)|
|[_mm_ucomile_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomile_ss)|SSE|Intrin. h|int _mm_ucomile_ss (\__m128, \__m128)|
|[_mm_ucomilt_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomilt_sd)|SSE2|Intrin. h|int _mm_ucomilt_sd (\__m128d, \__m128d)|
|[_mm_ucomilt_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomilt_ss)|SSE|Intrin. h|int _mm_ucomilt_ss (\__m128, \__m128)|
|[_mm_ucomineq_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomineq_sd)|SSE2|Intrin. h|int _mm_ucomineq_sd (\__m128d, \__m128d)|
|[_mm_ucomineq_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_ucomineq_ss)|SSE|Intrin. h|int _mm_ucomineq_ss (\__m128, \__m128)|
|[_mm_unpackhi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_epi16)|SSE2|Intrin. h|__m128i _mm_unpackhi_epi16 (\__m128i, \__m128i)|
|[_mm_unpackhi_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_epi32)|SSE2|Intrin. h|__m128i _mm_unpackhi_epi32 (\__m128i, \__m128i)|
|[_mm_unpackhi_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_epi64)|SSE2|Intrin. h|__m128i _mm_unpackhi_epi64 (\__m128i, \__m128i)|
|[_mm_unpackhi_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_epi8)|SSE2|Intrin. h|__m128i _mm_unpackhi_epi8 (\__m128i, \__m128i)|
|[_mm_unpackhi_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_pd)|SSE2|Intrin. h|__m128d _mm_unpackhi_pd (\__m128d, \__m128d)|
|[_mm_unpackhi_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_pi8)|MMX|mmintrin. h|__m64 _mm_unpackhi_pi8 (__m64, __m64) [3]|
|[_mm_unpackhi_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_pi16)|MMX|mmintrin. h|__m64 _mm_unpackhi_pi16 (__m64, __m64) [3]|
|[_mm_unpackhi_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_pi32)|MMX|mmintrin. h|__m64 _mm_unpackhi_pi32 (__m64, __m64) [3]|
|[_mm_unpackhi_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpackhi_ps)|SSE|Intrin. h|__m128 _mm_unpackhi_ps (\__m128, \__m128)|
|[_mm_unpacklo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_epi16)|SSE2|Intrin. h|__m128i _mm_unpacklo_epi16 (\__m128i, \__m128i)|
|[_mm_unpacklo_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_epi32)|SSE2|Intrin. h|__m128i _mm_unpacklo_epi32 (\__m128i, \__m128i)|
|[_mm_unpacklo_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_epi64)|SSE2|Intrin. h|__m128i _mm_unpacklo_epi64 (\__m128i, \__m128i)|
|[_mm_unpacklo_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_epi8)|SSE2|Intrin. h|__m128i _mm_unpacklo_epi8 (\__m128i, \__m128i)|
|[_mm_unpacklo_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_pd)|SSE2|Intrin. h|__m128d _mm_unpacklo_pd (\__m128d, \__m128d)|
|[_mm_unpacklo_pi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_pi8)|MMX|mmintrin. h|__m64 _mm_unpacklo_pi8 (__m64, __m64) [3]|
|[_mm_unpacklo_pi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_pi16)|MMX|mmintrin. h|__m64 _mm_unpacklo_pi16 (__m64, __m64) [3]|
|[_mm_unpacklo_pi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_pi32)|MMX|mmintrin. h|__m64 _mm_unpacklo_pi32 (__m64, __m64) [3]|
|[_mm_unpacklo_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_unpacklo_ps)|SSE|Intrin. h|__m128 _mm_unpacklo_ps (\__m128, \__m128)|
|[_mm_xor_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_xor_pd)|SSE2|Intrin. h|__m128d _mm_xor_pd (\__m128d, \__m128d)|
|[_mm_xor_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_xor_ps)|SSE|Intrin. h|__m128 _mm_xor_ps (\__m128, \__m128)|
|[_mm_xor_si64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_xor_si64)|MMX|mmintrin. h|__m64 _mm_xor_si64 (\__m64, \__m64) [3]|
|[_mm_xor_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_xor_si128)|SSE2|Intrin. h|__m128i _mm_xor_si128 (\__m128i, \__m128i)|
|[_mm256_abs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_abs_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_abs_epi16 (\__m256i)|
|[_mm256_abs_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_abs_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_abs_epi32 (\__m256i)|
|[_mm256_abs_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_abs_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_abs_epi8 (\__m256i)|
|[_mm256_add_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_add_epi16 (\__m256i, \__m256i)|
|[_mm256_add_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_add_epi32 (\__m256i, \__m256i)|
|[_mm256_add_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_add_epi64 (\__m256i, \__m256i)|
|[_mm256_add_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_add_epi8 (\__m256i, \__m256i)|
|[_mm256_add_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_pd)|AVX [2]|ımintrin. h|__m256d _mm256_add_pd (\__m256d, \__m256d)|
|[_mm256_add_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_add_ps)|AVX [2]|ımintrin. h|__m256 _mm256_add_ps (\__m256, \__m256)|
|[_mm256_adds_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_adds_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_adds_epi16 (\__m256i, \__m256i)|
|[_mm256_adds_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_adds_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_adds_epi8 (\__m256i, \__m256i)|
|[_mm256_adds_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_adds_epu16)|AVX2 [2]|ımintrin. h|__m256i _mm256_adds_epu16 (\__m256i, \__m256i)|
|[_mm256_adds_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_adds_epu8)|AVX2 [2]|ımintrin. h|__m256i _mm256_adds_epu8 (\__m256i, \__m256i)|
|[_mm256_addsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_addsub_pd)|AVX [2]|ımintrin. h|__m256d _mm256_addsub_pd (\__m256d, \__m256d)|
|[_mm256_addsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_addsub_ps)|AVX [2]|ımintrin. h|__m256 _mm256_addsub_ps (\__m256, \__m256)|
|[_mm256_alignr_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_alignr_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_alignr_epi8 (\__m256i, \__m256i, const int)|
|[_mm256_and_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_and_pd)|AVX [2]|ımintrin. h|__m256d _mm256_and_pd (\__m256d, \__m256d)|
|[_mm256_and_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_and_ps)|AVX [2]|ımintrin. h|__m256 _mm256_and_ps (\__m256, \__m256)|
|[_mm256_and_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_and_si256)|AVX2 [2]|ımintrin. h|__m256i _mm256_and_si256 (\__m256i, \__m256i)|
|[_mm256_andnot_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_andnot_pd)|AVX [2]|ımintrin. h|__m256d _mm256_andnot_pd (\__m256d, \__m256d)|
|[_mm256_andnot_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_andnot_ps)|AVX [2]|ımintrin. h|__m256 _mm256_andnot_ps (\__m256, \__m256)|
|[_mm256_andnot_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_andnot_si256)|AVX2 [2]|ımintrin. h|__m256i _mm256_andnot_si256 (\__m256i, \__m256i)|
|[_mm256_avg_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_avg_epu16)|AVX2 [2]|ımintrin. h|__m256i _mm256_avg_epu16 (\__m256i, \__m256i)|
|[_mm256_avg_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_avg_epu8)|AVX2 [2]|ımintrin. h|__m256i _mm256_avg_epu8 (\__m256i, \__m256i)|
|[_mm256_blend_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blend_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_blend_epi16 (\__m256i, \__m256i, const int)|
|[_mm256_blend_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blend_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_blend_epi32 (\__m256i, \__m256i, const int)|
|[_mm256_blend_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blend_pd)|AVX [2]|ımintrin. h|__m256d _mm256_blend_pd (\__m256d, \__m256d, const int)|
|[_mm256_blend_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blend_ps)|AVX [2]|ımintrin. h|__m256 _mm256_blend_ps (\__m256, \__m256, const int)|
|[_mm256_blendv_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blendv_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_blendv_epi8 (\__m256i, \__m256i, \__m256i)|
|[_mm256_blendv_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blendv_pd)|AVX [2]|ımintrin. h|__m256d _mm256_blendv_pd (\__m256d, \__m256d, \__m256d)|
|[_mm256_blendv_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_blendv_ps)|AVX [2]|ımintrin. h|__m256 _mm256_blendv_ps (\__m256, \__m256, \__m256)|
|[_mm256_broadcast_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcast_pd)|AVX [2]|ımintrin. h|__m256d _mm256_broadcast_pd (\__m128d const \*)|
|[_mm256_broadcast_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcast_ps)|AVX [2]|ımintrin. h|__m256 _mm256_broadcast_ps (\__m128 const \*)|
|[_mm256_broadcast_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcast_sd)|AVX [2]|ımintrin. h|__m256d _mm256_broadcast_sd (çift const \*)|
|[_mm256_broadcast_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcast_ss)|AVX [2]|ımintrin. h|__m256 _mm256_broadcast_ss (float const \*)|
|[_mm256_broadcastb_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastb_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_broadcastb_epi8 (\__m128i)|
|[_mm256_broadcastd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastd_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_broadcastd_epi32 (\__m128i)|
|[_mm256_broadcastq_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastq_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_broadcastq_epi64 (\__m128i)|
|[_mm256_broadcastsd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastsd_pd)|AVX2 [2]|ımintrin. h|__m256d _mm256_broadcastsd_pd (\__m128d)|
|[_mm256_broadcastsi128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastsi128_si256)|AVX2 [2]|ımintrin. h|__m256i _mm256_broadcastsi128_si256 (\__m128i)|
|[_mm256_broadcastss_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastss_ps)|AVX2 [2]|ımintrin. h|__m256 _mm256_broadcastss_ps (\__m128)|
|[_mm256_broadcastw_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_broadcastw_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_broadcastw_epi16 (\__m128i)|
|[_mm256_castpd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castpd_ps)|AVX [2]|ımintrin. h|__m256 _mm256_castpd_ps (\__m256d)|
|[_mm256_castpd_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castpd_si256)|AVX [2]|ımintrin. h|__m256i _mm256_castpd_si256 (\__m256d)|
|[_mm256_castpd128_pd256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castpd128_pd256)|AVX [2]|ımintrin. h|__m256d _mm256_castpd128_pd256 (\__m128d)|
|[_mm256_castpd256_pd128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castpd256_pd128)|AVX [2]|ımintrin. h|__m128d _mm256_castpd256_pd128 (\__m256d)|
|[_mm256_castps_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castps_pd)|AVX [2]|ımintrin. h|__m256d _mm256_castps_pd (\__m256)|
|[_mm256_castps_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castps_si256)|AVX [2]|ımintrin. h|__m256i _mm256_castps_si256 (\__m256)|
|[_mm256_castps128_ps256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castps128_ps256)|AVX [2]|ımintrin. h|__m256 _mm256_castps128_ps256 (\__m128)|
|[_mm256_castps256_ps128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castps256_ps128)|AVX [2]|ımintrin. h|__m128 _mm256_castps256_ps128 (\__m256)|
|[_mm256_castsi128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castsi128_si256)|AVX [2]|ımintrin. h|__m256i _mm256_castsi128_si256 (\__m128i)|
|[_mm256_castsi256_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castsi256_pd)|AVX [2]|ımintrin. h|__m256d _mm256_castsi256_pd (\__m256i)|
|[_mm256_castsi256_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castsi256_ps)|AVX [2]|ımintrin. h|__m256 _mm256_castsi256_ps (\__m256i)|
|[_mm256_castsi256_si128](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_castsi256_si128)|AVX [2]|ımintrin. h|__m128i _mm256_castsi256_si128 (\__m256i)|
|_mm256_cmov_si256|XOP [1]|ammintrin. h|__m256i _mm256_cmov_si256 (\__m256i, \__m256i, \__m256i)|
|[_mm256_cmp_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmp_pd)|AVX [2]|ımintrin. h|__m256d _mm256_cmp_pd (\__m256d, \__m256d, const int)|
|[_mm256_cmp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmp_ps)|AVX [2]|ımintrin. h|__m256 _mm256_cmp_ps (\__m256, \__m256, const int)|
|[_mm256_cmpeq_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpeq_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_cmpeq_epi16 (\__m256i, \__m256i)|
|[_mm256_cmpeq_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpeq_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_cmpeq_epi32 (\__m256i, \__m256i)|
|[_mm256_cmpeq_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpeq_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_cmpeq_epi64 (\__m256i, \__m256i)|
|[_mm256_cmpeq_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpeq_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_cmpeq_epi8 (\__m256i, \__m256i)|
|[_mm256_cmpgt_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpgt_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_cmpgt_epi16 (\__m256i, \__m256i)|
|[_mm256_cmpgt_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpgt_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_cmpgt_epi32 (\__m256i, \__m256i)|
|[_mm256_cmpgt_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpgt_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_cmpgt_epi64 (\__m256i, \__m256i)|
|[_mm256_cmpgt_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cmpgt_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_cmpgt_epi8 (\__m256i, \__m256i)|
|[_mm256_cvtepi16_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi16_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepi16_epi32 (\__m128i)|
|[_mm256_cvtepi16_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi16_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepi16_epi64 (\__m128i)|
|[_mm256_cvtepi32_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi32_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepi32_epi64 (\__m128i)|
|[_mm256_cvtepi32_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi32_pd)|AVX [2]|ımintrin. h|__m256d _mm256_cvtepi32_pd (\__m128i)|
|[_mm256_cvtepi32_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi32_ps)|AVX [2]|ımintrin. h|__m256 _mm256_cvtepi32_ps (\__m256i)|
|[_mm256_cvtepi8_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi8_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepi8_epi16 (\__m128i)|
|[_mm256_cvtepi8_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi8_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepi8_epi32 (\__m128i)|
|[_mm256_cvtepi8_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepi8_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepi8_epi64 (\__m128i)|
|[_mm256_cvtepu16_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu16_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepu16_epi32 (\__m128i)|
|[_mm256_cvtepu16_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu16_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepu16_epi64 (\__m128i)|
|[_mm256_cvtepu32_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu32_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepu32_epi64 (\__m128i)|
|[_mm256_cvtepu8_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu8_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepu8_epi16 (\__m128i)|
|[_mm256_cvtepu8_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu8_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepu8_epi32 (\__m128i)|
|[_mm256_cvtepu8_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtepu8_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_cvtepu8_epi64 (\__m128i)|
|[_mm256_cvtpd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtpd_epi32)|AVX [2]|ımintrin. h|__m128i _mm256_cvtpd_epi32 (\__m256d)|
|[_mm256_cvtpd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtpd_ps)|AVX [2]|ımintrin. h|__m128 _mm256_cvtpd_ps (\__m256d)|
|[_mm256_cvtph_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtph_ps)|F16C [2]|ımintrin. h|__m256 _mm256_cvtph_ps (\__m128i)|
|[_mm256_cvtps_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtps_epi32)|AVX [2]|ımintrin. h|__m256i _mm256_cvtps_epi32 (\__m256)|
|[_mm256_cvtps_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtps_pd)|AVX [2]|ımintrin. h|__m256d _mm256_cvtps_pd (\__m128)|
|[_mm256_cvtps_ph](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvtps_ph)|F16C [2]|ımintrin. h|__m128i _mm256_cvtps_ph (\__m256, const int)|
|[_mm256_cvttpd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvttpd_epi32)|AVX [2]|ımintrin. h|__m128i _mm256_cvttpd_epi32 (\__m256d)|
|[_mm256_cvttps_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_cvttps_epi32)|AVX [2]|ımintrin. h|__m256i _mm256_cvttps_epi32 (\__m256)|
|[_mm256_div_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_div_pd)|AVX [2]|ımintrin. h|__m256d _mm256_div_pd (\__m256d, \__m256d)|
|[_mm256_div_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_div_ps)|AVX [2]|ımintrin. h|__m256 _mm256_div_ps (\__m256, \__m256)|
|[_mm256_dp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_dp_ps)|AVX [2]|ımintrin. h|__m256 _mm256_dp_ps (\__m256, \__m256, const int)|
|[_mm256_extractf128_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_extractf128_pd)|AVX [2]|ımintrin. h|__m128d _mm256_extractf128_pd (\__m256d, const int)|
|[_mm256_extractf128_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_extractf128_ps)|AVX [2]|ımintrin. h|__m128 _mm256_extractf128_ps (\__m256, const int)|
|[_mm256_extractf128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_extractf128_si256)|AVX [2]|ımintrin. h|__m128i _mm256_extractf128_si256 (\__m256i, const int)|
|[_mm256_extracti128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_extracti128_si256)|AVX2 [2]|ımintrin. h|__m128i _mm256_extracti128_si256 (\__m256i, int)|
|[_mm256_fmadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmadd_pd)|FMA [2]|ımintrin. h|__m256d _mm256_fmadd_pd (\__m256d, \__m256d, \__m256d)|
|[_mm256_fmadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmadd_ps)|FMA [2]|ımintrin. h|__m256 _mm256_fmadd_ps (\__m256, \__m256, \__m256)|
|[_mm256_fmaddsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmaddsub_pd)|FMA [2]|ımintrin. h|__m256d _mm256_fmaddsub_pd (\__m256d, \__m256d, \__m256d)|
|[_mm256_fmaddsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmaddsub_ps)|FMA [2]|ımintrin. h|__m256 _mm256_fmaddsub_ps (\__m256, \__m256, \__m256)|
|[_mm256_fmsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmsub_pd)|FMA [2]|ımintrin. h|__m256d _mm256_fmsub_pd (\__m256d, \__m256d, \__m256d)|
|[_mm256_fmsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmsub_ps)|FMA [2]|ımintrin. h|__m256 _mm256_fmsub_ps (\__m256, \__m256, \__m256)|
|[_mm256_fmsubadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmsubadd_pd)|FMA [2]|ımintrin. h|__m256d _mm256_fmsubadd_pd (\__m256d, \__m256d, \__m256d)|
|[_mm256_fmsubadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fmsubadd_ps)|FMA [2]|ımintrin. h|__m256 _mm256_fmsubadd_ps (\__m256, \__m256, \__m256)|
|[_mm256_fnmadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fnmadd_pd)|FMA [2]|ımintrin. h|__m256d _mm256_fnmadd_pd (\__m256d, \__m256d, \__m256d)|
|[_mm256_fnmadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fnmadd_ps)|FMA [2]|ımintrin. h|__m256 _mm256_fnmadd_ps (\__m256, \__m256, \__m256)|
|[_mm256_fnmsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fnmsub_pd)|FMA [2]|ımintrin. h|__m256d _mm256_fnmsub_pd (\__m256d, \__m256d, \__m256d)|
|[_mm256_fnmsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_fnmsub_ps)|FMA [2]|ımintrin. h|__m256 _mm256_fnmsub_ps (\__m256, \__m256, \__m256)|
|_mm256_frcz_pd|XOP [1]|ammintrin. h|__m256d _mm256_frcz_pd (\__m256d)|
|_mm256_frcz_ps|XOP [1]|ammintrin. h|__m256 _mm256_frcz_ps (\__m256)|
|[_mm256_hadd_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hadd_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_hadd_epi16 (\__m256i, \__m256i)|
|[_mm256_hadd_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hadd_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_hadd_epi32 (\__m256i, \__m256i)|
|[_mm256_hadd_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hadd_pd)|AVX [2]|ımintrin. h|__m256d _mm256_hadd_pd (\__m256d, \__m256d)|
|[_mm256_hadd_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hadd_ps)|AVX [2]|ımintrin. h|__m256 _mm256_hadd_ps (\__m256, \__m256)|
|[_mm256_hadds_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hadds_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_hadds_epi16 (\__m256i, \__m256i)|
|[_mm256_hsub_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hsub_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_hsub_epi16 (\__m256i, \__m256i)|
|[_mm256_hsub_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hsub_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_hsub_epi32 (\__m256i, \__m256i)|
|[_mm256_hsub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hsub_pd)|AVX [2]|ımintrin. h|__m256d _mm256_hsub_pd (\__m256d, \__m256d)|
|[_mm256_hsub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hsub_ps)|AVX [2]|ımintrin. h|__m256 _mm256_hsub_ps (\__m256, \__m256)|
|[_mm256_hsubs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_hsubs_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_hsubs_epi16 (\__m256i, \__m256i)|
|[_mm256_i32gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i32gather_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_i32gather_epi32 (int const \*, \__m256i, const int)|
|[_mm256_i32gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i32gather_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_i32gather_epi64 (\__int64 const \*, \__m128i, const int)|
|[_mm256_i32gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i32gather_pd)|AVX2 [2]|ımintrin. h|__m256d _mm256_i32gather_pd (çift const \*, \__m128i, const int)|
|[_mm256_i32gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i32gather_ps)|AVX2 [2]|ımintrin. h|__m256 _mm256_i32gather_ps (float const \*, \__m256i, const int)|
|[_mm256_i64gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i64gather_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_i64gather_epi32 (int const \*, \__m256i, const int)|
|[_mm256_i64gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i64gather_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_i64gather_epi64 (\__int64 const \*, \__m256i, const int)|
|[_mm256_i64gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i64gather_pd)|AVX2 [2]|ımintrin. h|__m256d _mm256_i64gather_pd (çift const \*, \__m256i, const int)|
|[_mm256_i64gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_i64gather_ps)|AVX2 [2]|ımintrin. h|__m128 _mm256_i64gather_ps (float const \*, \__m256i, const int)|
|[_mm256_insertf128_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_insertf128_pd)|AVX [2]|ımintrin. h|__m256d _mm256_insertf128_pd (\__m256d, \__m128d, int)|
|[_mm256_insertf128_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_insertf128_ps)|AVX [2]|ımintrin. h|__m256 _mm256_insertf128_ps (\__m256, \__m128, int)|
|[_mm256_insertf128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_insertf128_si256)|AVX [2]|ımintrin. h|__m256i _mm256_insertf128_si256 (\__m256i, \__m128i, int)|
|[_mm256_inserti128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_inserti128_si256)|AVX2 [2]|ımintrin. h|__m256i _mm256_inserti128_si256 (\__m256i, \__m128i, int)|
|[_mm256_lddqu_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_lddqu_si256)|AVX [2]|ımintrin. h|__m256i _mm256_lddqu_si256 (\__m256i \*)|
|[_mm256_load_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_load_pd)|AVX [2]|ımintrin. h|__m256d _mm256_load_pd (çift const \*)|
|[_mm256_load_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_load_ps)|AVX [2]|ımintrin. h|__m256 _mm256_load_ps (float const \*)|
|[_mm256_load_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_load_si256)|AVX [2]|ımintrin. h|__m256i _mm256_load_si256 (\__m256i \*)|
|[_mm256_loadu_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_loadu_pd)|AVX [2]|ımintrin. h|__m256d _mm256_loadu_pd (çift const \*)|
|[_mm256_loadu_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_loadu_ps)|AVX [2]|ımintrin. h|__m256 _mm256_loadu_ps (float const \*)|
|[_mm256_loadu_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_loadu_si256)|AVX [2]|ımintrin. h|__m256i _mm256_loadu_si256 (\__m256i \*)|
|_mm256_macc_pd|FMA4 [1]|ammintrin. h|__m256d _mm_macc_pd (\__m256d, \__m256d, \__m256d)|
|_mm256_macc_ps|FMA4 [1]|ammintrin. h|__m256 _mm_macc_ps (\__m256, \__m256, \__m256)|
|[_mm256_madd_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_madd_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_madd_epi16 (\__m256i, \__m256i)|
|_mm256_maddsub_pd|FMA4 [1]|ammintrin. h|__m256d _mm_maddsub_pd (\__m256d, \__m256d, \__m256d)|
|_mm256_maddsub_ps|FMA4 [1]|ammintrin. h|__m256 _mm_maddsub_ps (\__m256, \__m256, \__m256)|
|[_mm256_maddubs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maddubs_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_maddubs_epi16 (\__m256i, \__m256i)|
|[_mm256_mask_i32gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i32gather_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_mask_i32gather_epi32 (\__m256i, int const \*, \__m256i, \__m256i, const int)|
|[_mm256_mask_i32gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i32gather_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_mask_i32gather_epi64 (\__m256i, \__int64 const \*, \__m128i, \__m256i, const int)|
|[_mm256_mask_i32gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i32gather_pd)|AVX2 [2]|ımintrin. h|__m256d _mm256_mask_i32gather_pd (\__m256d, Double const \*, \__m128i, \__m256d, const int)|
|[_mm256_mask_i32gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i32gather_ps)|AVX2 [2]|ımintrin. h|__m256 _mm256_mask_i32gather_ps (\__m256, float const \*, \__m256i, \__m256, const int)|
|[_mm256_mask_i64gather_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i64gather_epi32)|AVX2 [2]|ımintrin. h|__m128i _mm256_mask_i64gather_epi32 (\__m128i, int const \*, \__m256i, \__m128i, const int)|
|[_mm256_mask_i64gather_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i64gather_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_mask_i64gather_epi64 (\__m256i, \__int64 const \*, \__m256i, \__m256i, const int)|
|[_mm256_mask_i64gather_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i64gather_pd)|AVX2 [2]|ımintrin. h|__m256d _mm256_mask_i64gather_pd (\__m256d, Double const \*, \__m256i, \__m256d, const int)|
|[_mm256_mask_i64gather_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mask_i64gather_ps)|AVX2 [2]|ımintrin. h|__m128 _mm256_mask_i64gather_ps (\__m128, float const \*, \__m256i, \__m128, const int)|
|[_mm256_maskload_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskload_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_maskload_epi32 (int const \*, \__m256i)|
|[_mm256_maskload_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskload_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_maskload_epi64 (\__int64 const \*, \__m256i)|
|[_mm256_maskload_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskload_pd)|AVX [2]|ımintrin. h|__m256d _mm256_maskload_pd (çift const \*, \__m256i)|
|[_mm256_maskload_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskload_ps)|AVX [2]|ımintrin. h|__m256 _mm256_maskload_ps (float const \*, \__m256i)|
|[_mm256_maskstore_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskstore_epi32)|AVX2 [2]|ımintrin. h|void _mm256_maskstore_epi32 (int \*, \__m256i, \__m256i)|
|[_mm256_maskstore_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskstore_epi64)|AVX2 [2]|ımintrin. h|void _mm256_maskstore_epi64 (\__int64 \*, \__m256i, \__m256i)|
|[_mm256_maskstore_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskstore_pd)|AVX [2]|ımintrin. h|void _mm256_maskstore_pd (çift \*, \__m256i, \__m256d)|
|[_mm256_maskstore_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_maskstore_ps)|AVX [2]|ımintrin. h|void _mm256_maskstore_ps (float \*, \__m256i, \__m256)|
|[_mm256_max_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_max_epi16 (\__m256i, \__m256i)|
|[_mm256_max_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_max_epi32 (\__m256i, \__m256i)|
|[_mm256_max_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_max_epi8 (\__m256i, \__m256i)|
|[_mm256_max_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epu16)|AVX2 [2]|ımintrin. h|__m256i _mm256_max_epu16 (\__m256i, \__m256i)|
|[_mm256_max_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epu32)|AVX2 [2]|ımintrin. h|__m256i _mm256_max_epu32 (\__m256i, \__m256i)|
|[_mm256_max_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_epu8)|AVX2 [2]|ımintrin. h|__m256i _mm256_max_epu8 (\__m256i, \__m256i)|
|[_mm256_max_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_pd)|AVX [2]|ımintrin. h|__m256d _mm256_max_pd (\__m256d, \__m256d)|
|[_mm256_max_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_max_ps)|AVX [2]|ımintrin. h|__m256 _mm256_max_ps (\__m256, \__m256)|
|[_mm256_min_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_min_epi16 (\__m256i, \__m256i)|
|[_mm256_min_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_min_epi32 (\__m256i, \__m256i)|
|[_mm256_min_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_min_epi8 (\__m256i, \__m256i)|
|[_mm256_min_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epu16)|AVX2 [2]|ımintrin. h|__m256i _mm256_min_epu16 (\__m256i, \__m256i)|
|[_mm256_min_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epu32)|AVX2 [2]|ımintrin. h|__m256i _mm256_min_epu32 (\__m256i, \__m256i)|
|[_mm256_min_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_epu8)|AVX2 [2]|ımintrin. h|__m256i _mm256_min_epu8 (\__m256i, \__m256i)|
|[_mm256_min_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_pd)|AVX [2]|ımintrin. h|__m256d _mm256_min_pd (\__m256d, \__m256d)|
|[_mm256_min_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_min_ps)|AVX [2]|ımintrin. h|__m256 _mm256_min_ps (\__m256, \__m256)|
|[_mm256_movedup_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_movedup_pd)|AVX [2]|ımintrin. h|__m256d _mm256_movedup_pd (\__m256d)|
|[_mm256_movehdup_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_movehdup_ps)|AVX [2]|ımintrin. h|__m256 _mm256_movehdup_ps (\__m256)|
|[_mm256_moveldup_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_moveldup_ps)|AVX [2]|ımintrin. h|__m256 _mm256_moveldup_ps (\__m256)|
|[_mm256_movemask_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_movemask_epi8)|AVX2 [2]|ımintrin. h|int _mm256_movemask_epi8 (\__m256i)|
|[_mm256_movemask_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_movemask_pd)|AVX [2]|ımintrin. h|int _mm256_movemask_pd (\__m256d)|
|[_mm256_movemask_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_movemask_ps)|AVX [2]|ımintrin. h|int _mm256_movemask_ps (\__m256)|
|[_mm256_mpsadbw_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mpsadbw_epu8)|AVX2 [2]|ımintrin. h|__m256i _mm256_mpsadbw_epu8 (\__m256i, \__m256i, const int)|
|_mm256_msub_pd|FMA4 [1]|ammintrin. h|__m256d _mm_msub_pd (\__m256d, \__m256d, \__m256d)|
|_mm256_msub_ps|FMA4 [1]|ammintrin. h|__m256 _mm_msub_ps (\__m256, \__m256, \__m256)|
|_mm256_msubadd_pd|FMA4 [1]|ammintrin. h|__m256d _mm_msubadd_pd (\__m256d, \__m256d, \__m256d)|
|_mm256_msubadd_ps|FMA4 [1]|ammintrin. h|__m256 _mm_msubadd_ps (\__m256, \__m256, \__m256)|
|[_mm256_mul_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mul_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_mul_epi32 (\__m256i, \__m256i)|
|[_mm256_mul_epu32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mul_epu32)|AVX2 [2]|ımintrin. h|__m256i _mm256_mul_epu32 (\__m256i, \__m256i)|
|[_mm256_mul_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mul_pd)|AVX [2]|ımintrin. h|__m256d _mm256_mul_pd (\__m256d, \__m256d)|
|[_mm256_mul_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mul_ps)|AVX [2]|ımintrin. h|__m256 _mm256_mul_ps (\__m256, \__m256)|
|[_mm256_mulhi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mulhi_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_mulhi_epi16 (\__m256i, \__m256i)|
|[_mm256_mulhi_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mulhi_epu16)|AVX2 [2]|ımintrin. h|__m256i _mm256_mulhi_epu16 (\__m256i, \__m256i)|
|[_mm256_mulhrs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mulhrs_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_mulhrs_epi16 (\__m256i, \__m256i)|
|[_mm256_mullo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mullo_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_mullo_epi16 (\__m256i, \__m256i)|
|[_mm256_mullo_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_mullo_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_mullo_epi32 (\__m256i, \__m256i)|
|_mm256_nmacc_pd|FMA4 [1]|ammintrin. h|__m256d _mm_nmacc_pd (\__m256d, \__m256d, \__m256d)|
|_mm256_nmacc_ps|FMA4 [1]|ammintrin. h|__m256 _mm_nmacc_ps (\__m256, \__m256, \__m256)|
|_mm256_nmsub_pd|FMA4 [1]|ammintrin. h|__m256d _mm_nmsub_pd (\__m256d, \__m256d, \__m256d)|
|_mm256_nmsub_ps|FMA4 [1]|ammintrin. h|__m256 _mm_nmsub_ps (\__m256, \__m256, \__m256)|
|[_mm256_or_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_or_pd)|AVX [2]|ımintrin. h|__m256d _mm256_or_pd (\__m256d, \__m256d)|
|[_mm256_or_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_or_ps)|AVX [2]|ımintrin. h|__m256 _mm256_or_ps (\__m256, \__m256)|
|[_mm256_or_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_or_si256)|AVX2 [2]|ımintrin. h|__m256i _mm256_or_si256 (\__m256i, \__m256i)|
|[_mm256_packs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_packs_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_packs_epi16 (\__m256i, \__m256i)|
|[_mm256_packs_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_packs_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_packs_epi32 (\__m256i, \__m256i)|
|[_mm256_packus_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_packus_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_packus_epi16 (\__m256i, \__m256i)|
|[_mm256_packus_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_packus_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_packus_epi32 (\__m256i, \__m256i)|
|[_mm256_permute_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute_pd)|AVX [2]|ımintrin. h|__m256d _mm256_permute_pd (\__m256d, int)|
|[_mm256_permute_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute_ps)|AVX [2]|ımintrin. h|__m256 _mm256_permute_ps (\__m256, int)|
|_mm256_permute2_pd|XOP [1]|ammintrin. h|__m256d _mm256_permute2_pd (\__m256d, \__m256d, \__m256i, int)|
|_mm256_permute2_ps|XOP [1]|ammintrin. h|__m256 _mm256_permute2_ps (\__m256, \__m256, \__m256i, int)|
|[_mm256_permute2f128_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute2f128_pd)|AVX [2]|ımintrin. h|__m256d _mm256_permute2f128_pd (\__m256d, \__m256d, int)|
|[_mm256_permute2f128_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute2f128_ps)|AVX [2]|ımintrin. h|__m256 _mm256_permute2f128_ps (\__m256, \__m256, int)|
|[_mm256_permute2f128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute2f128_si256)|AVX [2]|ımintrin. h|__m256i _mm256_permute2f128_si256 (\__m256i, \__m256i, int)|
|[_mm256_permute2x128_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute2x128_si256)|AVX2 [2]|ımintrin. h|__m256i _mm256_permute2x128_si256 (\__m256i, \__m256i, const int)|
|[_mm256_permute4x64_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute4x64_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_permute4x64_epi64 (\__m256i, const int)|
|[_mm256_permute4x64_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permute4x64_pd)|AVX2 [2]|ımintrin. h|__m256d _mm256_permute4x64_pd (\__m256d, const int)|
|[_mm256_permutevar_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permutevar_pd)|AVX [2]|ımintrin. h|__m256d _mm256_permutevar_pd (\__m256d, \__m256i)|
|[_mm256_permutevar_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permutevar_ps)|AVX [2]|ımintrin. h|__m256 _mm256_permutevar_ps (\__m256, \__m256i)|
|[_mm256_permutevar8x32_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permutevar8x32_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_permutevar8x32_epi32 (\__m256i, \__m256i)|
|[_mm256_permutevar8x32_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_permutevar8x32_ps)|AVX2 [2]|ımintrin. h|__m256 _mm256_permutevar8x32_ps (\__m256, \__m256i)|
|[_mm256_rcp_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_rcp_ps)|AVX [2]|ımintrin. h|__m256 _mm256_rcp_ps (\__m256)|
|[_mm256_round_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_round_pd)|AVX [2]|ımintrin. h|__m256d _mm256_round_pd (\__m256d, int)|
|[_mm256_round_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_round_ps)|AVX [2]|ımintrin. h|__m256 _mm256_round_ps (\__m256, int)|
|[_mm256_rsqrt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_rsqrt_ps)|AVX [2]|ımintrin. h|__m256 _mm256_rsqrt_ps (\__m256)|
|[_mm256_sad_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sad_epu8)|AVX2 [2]|ımintrin. h|__m256i _mm256_sad_epu8 (\__m256i, \__m256i)|
|[_mm256_set_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set_epi16)|AVX [2]|ımintrin. h|(__m256i _mm256_set_epi16 (kısa|
|[_mm256_set_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set_epi32)|AVX [2]|ımintrin. h|__m256i _mm256_set_epi32 (int, int, int, int, int, int, int, int)|
|[_mm256_set_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set_epi8)|AVX [2]|ımintrin. h|__m256i _mm256_set_epi8 (Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char, Char)|
|[_mm256_set_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set_pd)|AVX [2]|ımintrin. h|__m256d _mm256_set_pd (Double, Double, Double, Double)|
|[_mm256_set_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set_ps)|AVX [2]|ımintrin. h|__m256 _mm256_set_ps (float, float, float, float, float, float, float, float)|
|[_mm256_set1_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set1_epi16)|AVX [2]|ımintrin. h|__m256i _mm256_set1_epi16 (kısa)|
|[_mm256_set1_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set1_epi32)|AVX [2]|ımintrin. h|__m256i _mm256_set1_epi32 (int)|
|[_mm256_set1_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set1_epi8)|AVX [2]|ımintrin. h|__m256i _mm256_set1_epi8 (Char)|
|[_mm256_set1_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set1_pd)|AVX [2]|ımintrin. h|__m256d _mm256_set1_pd (çift)|
|[_mm256_set1_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_set1_ps)|AVX [2]|ımintrin. h|__m256 _mm256_set1_ps (float)|
|[_mm256_setr_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setr_epi16)|AVX [2]|ımintrin. h|(__m256i _mm256_setr_epi16 (kısa|
|[_mm256_setr_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setr_epi32)|AVX [2]|ımintrin. h|__m256i _mm256_setr_epi32 (int, int, int, int, int, int, int, int)|
|[_mm256_setr_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setr_epi8)|AVX [2]|ımintrin. h|(__m256i _mm256_setr_epi8 (Char|
|[_mm256_setr_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setr_pd)|AVX [2]|ımintrin. h|__m256d _mm256_setr_pd (Double, Double, Double, Double)|
|[_mm256_setr_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setr_ps)|AVX [2]|ımintrin. h|__m256 _mm256_setr_ps (float, float, float, float, float, float, float, float)|
|[_mm256_setzero_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setzero_pd)|AVX [2]|ımintrin. h|__m256d _mm256_setzero_pd (void)|
|[_mm256_setzero_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setzero_ps)|AVX [2]|ımintrin. h|__m256 _mm256_setzero_ps (void)|
|[_mm256_setzero_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_setzero_si256)|AVX [2]|ımintrin. h|__m256i _mm256_setzero_si256 (void)|
|[_mm256_shuffle_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shuffle_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_shuffle_epi32 (\__m256i, const int)|
|[_mm256_shuffle_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shuffle_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_shuffle_epi8 (\__m256i, \__m256i)|
|[_mm256_shuffle_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shuffle_pd)|AVX [2]|ımintrin. h|__m256d _mm256_shuffle_pd (\__m256d, \__m256d, const int)|
|[_mm256_shuffle_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shuffle_ps)|AVX [2]|ımintrin. h|__m256 _mm256_shuffle_ps (\__m256, \__m256, const int)|
|[_mm256_shufflehi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shufflehi_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_shufflehi_epi16 (\__m256i, const int)|
|[_mm256_shufflelo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_shufflelo_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_shufflelo_epi16 (\__m256i, const int)|
|[_mm256_sign_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sign_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_sign_epi16 (\__m256i, \__m256i)|
|[_mm256_sign_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sign_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_sign_epi32 (\__m256i, \__m256i)|
|[_mm256_sign_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sign_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_sign_epi8 (\__m256i, \__m256i)|
|[_mm256_sll_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sll_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_sll_epi16 (\__m256i, \__m128i)|
|[_mm256_sll_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sll_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_sll_epi32 (\__m256i, \__m128i)|
|[_mm256_sll_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sll_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_sll_epi64 (\__m256i, \__m128i)|
|[_mm256_slli_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_slli_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_slli_epi16 (\__m256i, int)|
|[_mm256_slli_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_slli_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_slli_epi32 (\__m256i, int)|
|[_mm256_slli_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_slli_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_slli_epi64 (\__m256i, int)|
|[_mm256_slli_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_slli_si256)|AVX2 [2]|ımintrin. h|__m256i _mm256_slli_si256 (\__m256i, int)|
|[_mm256_sllv_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sllv_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_sllv_epi32 (\__m256i, \__m256i)|
|[_mm256_sllv_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sllv_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_sllv_epi64 (\__m256i, \__m256i)|
|[_mm256_sqrt_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sqrt_pd)|AVX [2]|ımintrin. h|__m256d _mm256_sqrt_pd (\__m256d)|
|[_mm256_sqrt_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sqrt_ps)|AVX [2]|ımintrin. h|__m256 _mm256_sqrt_ps (\__m256)|
|[_mm256_sra_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sra_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_sra_epi16 (\__m256i, \__m128i)|
|[_mm256_sra_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sra_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_sra_epi32 (\__m256i, \__m128i)|
|[_mm256_srai_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srai_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_srai_epi16 (\__m256i, int)|
|[_mm256_srai_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srai_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_srai_epi32 (\__m256i, int)|
|[_mm256_srav_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srav_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_srav_epi32 (\__m256i, \__m256i)|
|[_mm256_srl_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srl_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_srl_epi16 (\__m256i, \__m128i)|
|[_mm256_srl_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srl_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_srl_epi32 (\__m256i, \__m128i)|
|[_mm256_srl_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srl_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_srl_epi64 (\__m256i, \__m128i)|
|[_mm256_srli_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srli_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_srli_epi16 (\__m256i, int)|
|[_mm256_srli_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srli_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_srli_epi32 (\__m256i, int)|
|[_mm256_srli_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srli_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_srli_epi64 (\__m256i, int)|
|[_mm256_srli_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srli_si256)|AVX2 [2]|ımintrin. h|__m256i _mm256_srli_si256 (\__m256i, int)|
|[_mm256_srlv_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srlv_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_srlv_epi32 (\__m256i, \__m256i)|
|[_mm256_srlv_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_srlv_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_srlv_epi64 (\__m256i, \__m256i)|
|[_mm256_store_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_store_pd)|AVX [2]|ımintrin. h|void _mm256_store_pd (çift \*, \__m256d)|
|[_mm256_store_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_store_ps)|AVX [2]|ımintrin. h|void _mm256_store_ps (float \*, \__m256)|
|[_mm256_store_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_store_si256)|AVX [2]|ımintrin. h|void _mm256_store_si256 (\__m256i \*, \__m256i)|
|[_mm256_storeu_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_storeu_pd)|AVX [2]|ımintrin. h|void _mm256_storeu_pd (çift \*, \__m256d)|
|[_mm256_storeu_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_storeu_ps)|AVX [2]|ımintrin. h|void _mm256_storeu_ps (float \*, \__m256)|
|[_mm256_storeu_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_storeu_si256)|AVX [2]|ımintrin. h|void _mm256_storeu_si256 (\__m256i \*, \__m256i)|
|[_mm256_stream_load_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_stream_load_si256)|AVX2 [2]|ımintrin. h|__m256i _mm256_stream_load_si256 (\__m256i const \*)|
|[_mm256_stream_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_stream_pd)|AVX [2]|ımintrin. h|void __mm256_stream_pd (çift \*, \__m256d)|
|[_mm256_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_stream_ps)|AVX [2]|ımintrin. h|void _mm256_stream_ps (float \*, \__m256)|
|[_mm256_stream_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_stream_si256)|AVX [2]|ımintrin. h|void __mm256_stream_si256 (\__m256i \*, \__m256i)|
|[_mm256_sub_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_sub_epi16 (\__m256i, \__m256i)|
|[_mm256_sub_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_sub_epi32 (\__m256i, \__m256i)|
|[_mm256_sub_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_sub_epi64 (\__m256i, \__m256i)|
|[_mm256_sub_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_sub_epi8 (\__m256i, \__m256i)|
|[_mm256_sub_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_pd)|AVX [2]|ımintrin. h|__m256d _mm256_sub_pd (\__m256d, \__m256d)|
|[_mm256_sub_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_sub_ps)|AVX [2]|ımintrin. h|__m256 _mm256_sub_ps (\__m256, \__m256)|
|[_mm256_subs_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_subs_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_subs_epi16 (\__m256i, \__m256i)|
|[_mm256_subs_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_subs_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_subs_epi8 (\__m256i, \__m256i)|
|[_mm256_subs_epu16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_subs_epu16)|AVX2 [2]|ımintrin. h|__m256i _mm256_subs_epu16 (\__m256i, \__m256i)|
|[_mm256_subs_epu8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_subs_epu8)|AVX2 [2]|ımintrin. h|__m256i _mm256_subs_epu8 (\__m256i, \__m256i)|
|[_mm256_testc_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testc_pd)|AVX [2]|ımintrin. h|int _mm256_testc_pd (\__m256d, \__m256d)|
|[_mm256_testc_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testc_ps)|AVX [2]|ımintrin. h|int _mm256_testc_ps (\__m256, \__m256)|
|[_mm256_testc_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testc_si256)|AVX [2]|ımintrin. h|int _mm256_testc_si256 (\__m256i, \__m256i)|
|[_mm256_testnzc_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testnzc_pd)|AVX [2]|ımintrin. h|int _mm256_testnzc_pd (\__m256d, \__m256d)|
|[_mm256_testnzc_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testnzc_ps)|AVX [2]|ımintrin. h|int _mm256_testnzc_ps (\__m256, \__m256)|
|[_mm256_testnzc_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testnzc_si256)|AVX [2]|ımintrin. h|int _mm256_testnzc_si256 (\__m256i, \__m256i)|
|[_mm256_testz_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testz_pd)|AVX [2]|ımintrin. h|int _mm256_testz_pd (\__m256d, \__m256d)|
|[_mm256_testz_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testz_ps)|AVX [2]|ımintrin. h|int _mm256_testz_ps (\__m256, \__m256)|
|[_mm256_testz_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_testz_si256)|AVX [2]|ımintrin. h|int _mm256_testz_si256 (\__m256i, \__m256i)|
|[_mm256_unpackhi_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_unpackhi_epi16 (\__m256i, \__m256i)|
|[_mm256_unpackhi_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_unpackhi_epi32 (\__m256i, \__m256i)|
|[_mm256_unpackhi_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_unpackhi_epi64 (\__m256i, \__m256i)|
|[_mm256_unpackhi_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_unpackhi_epi8 (\__m256i, \__m256i)|
|[_mm256_unpackhi_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_pd)|AVX [2]|ımintrin. h|__m256d _mm256_unpackhi_pd (\__m256d, \__m256d)|
|[_mm256_unpackhi_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpackhi_ps)|AVX [2]|ımintrin. h|__m256 _mm256_unpackhi_ps (\__m256, \__m256)|
|[_mm256_unpacklo_epi16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_epi16)|AVX2 [2]|ımintrin. h|__m256i _mm256_unpacklo_epi16 (\__m256i, \__m256i)|
|[_mm256_unpacklo_epi32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_epi32)|AVX2 [2]|ımintrin. h|__m256i _mm256_unpacklo_epi32 (\__m256i, \__m256i)|
|[_mm256_unpacklo_epi64](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_epi64)|AVX2 [2]|ımintrin. h|__m256i _mm256_unpacklo_epi64 (\__m256i, \__m256i)|
|[_mm256_unpacklo_epi8](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_epi8)|AVX2 [2]|ımintrin. h|__m256i _mm256_unpacklo_epi8 (\__m256i, \__m256i)|
|[_mm256_unpacklo_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_pd)|AVX [2]|ımintrin. h|__m256d _mm256_unpacklo_pd (\__m256d, \__m256d)|
|[_mm256_unpacklo_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_unpacklo_ps)|AVX [2]|ımintrin. h|__m256 _mm256_unpacklo_ps (\__m256, \__m256)|
|[_mm256_xor_pd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_xor_pd)|AVX [2]|ımintrin. h|__m256d _mm256_xor_pd (\__m256d, \__m256d)|
|[_mm256_xor_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_xor_ps)|AVX [2]|ımintrin. h|__m256 _mm256_xor_ps (\__m256, \__m256)|
|[_mm256_xor_si256](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_xor_si256)|AVX2 [2]|ımintrin. h|__m256i _mm256_xor_si256 (\__m256i, \__m256i)|
|[_mm256_zeroall](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_zeroall)|AVX [2]|ımintrin. h|void _mm256_zeroall (void)|
|[_mm256_zeroupper](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm256_zeroupper)|AVX [2]|ımintrin. h|void _mm256_zeroupper (void)|
|[__movsb](movsb.md)||Intrin. h|void __movsb (işaretsiz char \*, işaretsiz char const \*, size_t)|
|[__movsd](movsd.md)||Intrin. h|void __movsd (işaretsiz Long \*, imzasız Long const \*, size_t)|
|[__movsw](movsw.md)||Intrin. h|void __movsw (işaretsiz kısa \*, işaretsiz kısa const \*, size_t)|
|_mulx_u32|BMI [2]|ımintrin. h|işaretsiz int _mulx_u32 (işaretsiz int, işaretsiz int, işaretsiz int\*)|
|[__nop](nop.md)||Intrin. h|void __nop (void)|
|__nvreg_restore_fence||Intrin. h|void __nvreg_restore_fence (void)|
|__nvreg_save_fence||Intrin. h|void __nvreg_save_fence (void)|
|[__outbyte](outbyte.md)||Intrin. h|void __outbyte (işaretsiz kısa, işaretsiz karakter)|
|[__outbytestring](outbytestring.md)||Intrin. h|void __outbytestring (işaretsiz kısa, işaretsiz char \*, işaretsiz Long)|
|[__outdword](outdword.md)||Intrin. h|void __outdword (işaretsiz kısa, işaretsiz uzun)|
|[__outdwordstring](outdwordstring.md)||Intrin. h|void __outdwordstring (işaretsiz kısa, işaretsiz uzun \*, işaretsiz uzun)|
|[__outword](outword.md)||Intrin. h|void __outword (işaretsiz kısa, işaretsiz kısa)|
|[__outwordstring](outwordstring.md)||Intrin. h|void __outwordstring (işaretsiz kısa, işaretsiz kısa \*, işaretsiz uzun)|
|[_pdep_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_pdep_u32)|BMI [2]|ımintrin. h|işaretsiz int _pdep_u32 (işaretsiz int, işaretsiz int)|
|[_pext_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_pext_u32)|BMI [2]|ımintrin. h|işaretsiz int _pext_u32 (işaretsiz int, işaretsiz int)|
|[__popcnt](popcnt16-popcnt-popcnt64.md)|POPCNT|Intrin. h|işaretsiz int __popcnt (işaretsiz int)|
|[__popcnt16](popcnt16-popcnt-popcnt64.md)|POPCNT|Intrin. h|işaretsiz kısa __popcnt16 (işaretsiz kısa)|
|[_rdrand16_step](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_rdrand16_step)|RDRAND [2]|ımintrin. h|int _rdrand16_step (işaretsiz kısa \*)|
|[_rdrand32_step](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_rdrand32_step)|RDRAND [2]|ımintrin. h|int _rdrand32_step (işaretsiz int \*)|
|[_rdseed16_step](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_rdseed16_step)|RDSEED [2]|ımintrin. h|int _rdseed16_step (işaretsiz kısa \*)|
|[_rdseed32_step](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_rdseed32_step)|RDSEED [2]|ımintrin. h|int _rdseed32_step (işaretsiz int \*)|
|[__rdtsc](rdtsc.md)||Intrin. h|imzasız __int64 \__rdtsc (void)|
|[__rdtscp](rdtscp.md)|RDTSCP|Intrin. h|imzasız __int64 \__rdtscp (işaretsiz int\*)|
|[_ReadBarrier](readbarrier.md)||Intrin. h|void _ReadBarrier (void)|
|[__readcr0](readcr0.md)||Intrin. h|işaretsiz Long __readcr0 (void)|
|[__readcr2](readcr2.md)||Intrin. h|işaretsiz Long __readcr2 (void)|
|[__readcr3](readcr3.md)||Intrin. h|işaretsiz Long __readcr3 (void)|
|[__readcr4](readcr4.md)||Intrin. h|işaretsiz Long __readcr4 (void)|
|[__readcr8](readcr8.md)||Intrin. h|işaretsiz Long __readcr8 (void)|
|[__readdr](readdr.md)||Intrin. h|imzasız __readdr (işaretsiz)|
|[__readeflags](readeflags.md)||Intrin. h|işaretsiz __readeflags (void)|
|[__readfsbyte](readfsbyte-readfsdword-readfsqword-readfsword.md)||Intrin. h|işaretsiz karakter __readfsbyte (işaretsiz Long)|
|[__readfsdword](readfsbyte-readfsdword-readfsqword-readfsword.md)||Intrin. h|işaretsiz Long __readfsdword (imzasız Long)|
|[__readfsword](readfsbyte-readfsdword-readfsqword-readfsword.md)||Intrin. h|işaretsiz kısa __readfsword (imzasız Long)|
|[__readmsr](readmsr.md)||Intrin. h|imzasız __int64 \__readmsr (işaretsiz Long)|
|[__readpmc](readpmc.md)||Intrin. h|imzasız __int64 \__readpmc (işaretsiz Long)|
|[_ReadWriteBarrier](readwritebarrier.md)||Intrin. h|void _ReadWriteBarrier (void)|
|[_ReturnAddress](returnaddress.md)||Intrin. h|void \* _ReturnAddress (void)|
|_rorx_u32|BMI [2]|ımintrin. h|işaretsiz int _rorx_u32 (işaretsiz int, const işaretsiz int)|
|[_rotl16](rotl8-rotl16.md)||Intrin. h|işaretsiz kısa _rotl16 (işaretsiz kısa, işaretsiz karakter)|
|[_rotl8](rotl8-rotl16.md)||Intrin. h|işaretsiz karakter _rotl8 (işaretsiz char, işaretsiz karakter)|
|[_rotr16](rotr8-rotr16.md)||Intrin. h|işaretsiz kısa _rotr16 (işaretsiz kısa, işaretsiz karakter)|
|[_rotr8](rotr8-rotr16.md)||Intrin. h|işaretsiz karakter _rotr8 (işaretsiz char, işaretsiz karakter)|
|_rsm||Intrin. h|void _rsm (void)|
|_sarx_i32|BMI [2]|ımintrin. h|int _sarx_i32 (int, işaretsiz int)|
|[__segmentlimit](segmentlimit.md)||Intrin. h|işaretsiz Long __segmentlimit (imzasız Long)|
|_sgdt||Intrin. h|void _sgdt (void\*)|
|_shlx_u32|BMI [2]|ımintrin. h|işaretsiz int _shlx_u32 (işaretsiz int, işaretsiz int)|
|_shrx_u32|BMI [2]|ımintrin. h|işaretsiz int _shrx_u32 (işaretsiz int, işaretsiz int)|
|[__sidt](sidt.md)||Intrin. h|void __sidt (void\*)|
|__slwpcb|LWP [1]|ammintrin. h|void \*__slwpcb (void)|
|_stac|SMAP|Intrin. h|void _stac (void)|
|_store_be_u16<br /><br /> [_storebe_i16](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_storebe_i16&expand=5141)|MOVBE|ımintrin. h|void _store_be_u16 (void \*, işaretsiz Short);<br /><br /> void _storebe_i16 (void \*, short); 03|
|_store_be_u32<br /><br /> [_storebe_i32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_storebe_i32&expand=5142)|MOVBE|ımintrin. h|void _store_be_u32 (void \*, işaretsiz int);<br /><br /> void _storebe_i32 (void \*, int); 03|
|_Store_HLERelease|HLE [2]|ımintrin. h|void _Store_HLERelease (uzun geçici \*, uzun)|
|_StorePointer_HLERelease|HLE [2]|ımintrin. h|void _StorePointer_HLERelease (void \* volatile \*, void \*)|
|[__stosb](stosb.md)||Intrin. h|void __stosb (işaretsiz char \*, işaretsiz char, size_t)|
|[__stosd](stosd.md)||Intrin. h|void __stosd (imzasız Long \*, işaretsiz Long, size_t)|
|[__stosw](stosw.md)||Intrin. h|void __stosw (işaretsiz kısa \*, işaretsiz kısa, size_t)|
|_subborrow_u16||Intrin. h|işaretsiz char _subborrow_u16 (işaretsiz char, işaretsiz kısa, işaretsiz kısa, işaretsiz kısa \*)|
|[_subborrow_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_subborrow_u32)||Intrin. h|işaretsiz char _subborrow_u32 (işaretsiz char, işaretsiz int, işaretsiz int, işaretsiz int \*)|
|_subborrow_u8||Intrin. h|işaretsiz char _subborrow_u8 (işaretsiz char, işaretsiz char, işaretsiz karakter, işaretsiz char \*)|
|[__svm_clgi](svm-clgi.md)||Intrin. h|void __svm_clgi (void)|
|[__svm_invlpga](svm-invlpga.md)||Intrin. h|void __svm_invlpga (void\*, int)|
|[__svm_skinit](svm-skinit.md)||Intrin. h|void __svm_skinit (int)|
|[__svm_stgi](svm-stgi.md)||Intrin. h|void __svm_stgi (void)|
|[__svm_vmload](svm-vmload.md)||Intrin. h|void __svm_vmload(size_t)|
|[__svm_vmrun](svm-vmrun.md)||Intrin. h|void __svm_vmrun(size_t)|
|[__svm_vmsave](svm-vmsave.md)||Intrin. h|void __svm_vmsave (size_t)|
|_t1mskc_u32|ABM [1]|ammintrin. h|işaretsiz int _t1mskc_u32 (işaretsiz int)|
|[_tzcnt_u32](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_tzcnt_u32)|BMI|ammintrin. h, immintrin. h|işaretsiz int _tzcnt_u32 (işaretsiz int)|
|_tzmsk_u32|ABM [1]|ammintrin. h|işaretsiz int _tzmsk_u32 (işaretsiz int)|
|[__ud2](ud2.md)||Intrin. h|void __ud2 (void)|
|[_udiv64](udiv64.md)||Intrin. h|işaretsiz int \_udiv64 (imzasız \__int64, işaretsiz int, işaretsiz int \*)|
|[__ull_rshift](ull-rshift.md)||Intrin. h|işaretsiz __int64 [Pascal/cdecl] \__ull_rshift (imzasız \__int64, int)|
|[__vmx_off](vmx-off.md)||Intrin. h|void __vmx_off (void)|
|[__vmx_vmptrst](vmx-vmptrst.md)||Intrin. h|void __vmx_vmptrst (imzasız \__int64 \*)|
|[__wbinvd](wbinvd.md)||Intrin. h|void __wbinvd (void)|
|[_WriteBarrier](writebarrier.md)||Intrin. h|void _WriteBarrier (void)|
|[__writecr0](writecr0.md)||Intrin. h|void __writecr0 (imzasız Long)|
|[__writecr3](writecr3.md)||Intrin. h|void __writecr3 (imzasız Long)|
|[__writecr4](writecr4.md)||Intrin. h|void __writecr4 (imzasız Long)|
|[__writecr8](writecr8.md)||Intrin. h|void __writecr8 (imzasız Long)|
|[__writedr](writedr.md)||Intrin. h|void __writedr (işaretsiz, işaretsiz)|
|[__writeeflags](writeeflags.md)||Intrin. h|void __writeeflags (işaretsiz)|
|[__writefsbyte](writefsbyte-writefsdword-writefsqword-writefsword.md)||Intrin. h|void __writefsbyte (işaretsiz Long, işaretsiz Char)|
|[__writefsdword](writefsbyte-writefsdword-writefsqword-writefsword.md)||Intrin. h|void __writefsdword (işaretsiz Long, unsigned long)|
|[__writefsword](writefsbyte-writefsdword-writefsqword-writefsword.md)||Intrin. h|void __writefsword (işaretsiz Long, işaretsiz Short)|
|[__writemsr](writemsr.md)||Intrin. h|void __writemsr (işaretsiz Long, işaretsiz \__int64)|
|[_xabort](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xabort)|RTM [2]|ımintrin. h|void _xabort (işaretsiz int)|
|[_xbegin](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xbegin)|RTM [2]|ımintrin. h|işaretsiz _xbegin (void)|
|[_xend](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xend)|RTM [2]|ımintrin. h|void _xend (void)|
|[_xgetbv](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xgetbv)|XSAVE [2]|ımintrin. h|imzasız __int64 _xgetbv (işaretsiz int)|
|[_xrstor](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xrstor)|XSAVE [2]|ımintrin. h|void _xrstor (void const\*, imzasız \__int64)|
|[_xsave](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xsave)|XSAVE [2]|ımintrin. h|void _xsave (void\*, imzasız \__int64)|
|[_xsaveopt](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xsaveopt)|XSAVEOPT [2]|ımintrin. h|void _xsaveopt (void\*, imzasız \__int64)|
|[_xsetbv](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xsetbv)|XSAVE [2]|ımintrin. h|void _xsetbv (işaretsiz int, imzasız \__int64)|
|[_xtest](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_xtest)|XTEST [2]|ımintrin. h|işaretsiz karakter _xtest (void)|

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç](compiler-intrinsics.md) bilgileri\
[ARM iç](arm-intrinsics.md) bilgileri\
[ARM64 iç](arm64-intrinsics.md)\
[x64 (amd64) iç bilgileri](x64-amd64-intrinsics-list.md)
