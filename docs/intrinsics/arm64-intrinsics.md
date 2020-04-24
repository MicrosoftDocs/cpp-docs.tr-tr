---
title: ARM64 iç bilgileri
description: Visual Studio'daki Microsoft C++ derleyicisi tarafından desteklenen ARM64 içsellerinin başvuru listesi.
f1_keywords:
- __break
- __addx18byte
- __addx18word
- __addx18dword
- __addx18qword
- __cas8
- __cas16
- __cas32
- __cas64
- __casa8
- __casa16
- __casa32
- __casa64
- __casl8
- __casl16
- __casl32
- __casl64
- __casal8
- __casal16
- __casal32
- __casal64
- __crc32b
- __crc32h
- __crc32w
- __crc32d
- __crc32cb
- __crc32ch
- __crc32cw
- __crc32cd
- __getReg
- __getRegFp
- __getCallerReg
- __getCallerRegFp
- __hlt
- __incx18byte
- __incx18word
- __incx18dword
- __incx18qword
- __ldar8
- __ldar16
- __ldar32
- __ldar64
- __ldapr8
- __ldapr16
- __ldapr32
- __ldapr64
- __prefetch2
- __readx18byte
- __readx18word
- __readx18dword
- __readx18qword
- __setReg
- __setRegFp
- __setCallerReg
- __setCallerRegFp
- __stlr8
- __stlr16
- __stlr32
- __stlr64
- __swp8
- __swp16
- __swp32
- __swp64
- __swpa8
- __swpa16
- __swpa32
- __swpa64
- __swpl8
- __swpl16
- __swpl32
- __swpl64
- __swpal8
- __swpal16
- __swpal32
- __swpal64
- __sys
- __svc
- __writex18byte
- __writex18word
- __writex18dword
- __writex18qword
helpviewer_keywords:
- __break ARM64 intrinsic
- __addx18byte ARM64 intrinsic
- __addx18word ARM64 intrinsic
- __addx18dword ARM64 intrinsic
- __addx18qword ARM64 intrinsic
- __cas8 ARM64 intrinsic
- __cas16 ARM64 intrinsic
- __cas32 ARM64 intrinsic
- __cas64 ARM64 intrinsic
- __casa8 ARM64 intrinsic
- __casa16 ARM64 intrinsic
- __casa32 ARM64 intrinsic
- __casa64 ARM64 intrinsic
- __casl8 ARM64 intrinsic
- __casl16 ARM64 intrinsic
- __casl32 ARM64 intrinsic
- __casl64 ARM64 intrinsic
- __casal8 ARM64 intrinsic
- __casal16 ARM64 intrinsic
- __casal32 ARM64 intrinsic
- __casal64 ARM64 intrinsic
- __crc32b ARM64 intrinsic
- __crc32h ARM64 intrinsic
- __crc32w ARM64 intrinsic
- __crc32d ARM64 intrinsic
- __crc32cb ARM64 intrinsic
- __crc32ch ARM64 intrinsic
- __crc32cw ARM64 intrinsic
- __crc32cd ARM64 intrinsic
- __getReg ARM64 intrinsic
- __getRegFp ARM64 intrinsic
- __getCallerReg ARM64 intrinsic
- __getCallerRegFp ARM64 intrinsic
- __hlt ARM64 intrinsic
- __incx18byte ARM64 intrinsic
- __incx18word ARM64 intrinsic
- __incx18dword ARM64 intrinsic
- __incx18qword ARM64 intrinsic
- __ldar8 ARM64 intrinsic
- __ldar16 ARM64 intrinsic
- __ldar32 ARM64 intrinsic
- __ldar64 ARM64 intrinsic
- __ldapr8 ARM64 intrinsic
- __ldapr16 ARM64 intrinsic
- __ldapr32 ARM64 intrinsic
- __ldapr64 ARM64 intrinsic
- __prefetch2 ARM64 intrinsic
- __readx18byte ARM64 intrinsic
- __readx18word ARM64 intrinsic
- __readx18dword ARM64 intrinsic
- __readx18qword ARM64 intrinsic
- __setReg ARM64 intrinsic
- __setRegFp ARM64 intrinsic
- __setCallerReg ARM64 intrinsic
- __setCallerRegFp ARM64 intrinsic
- __stlr8 ARM64 intrinsic
- __stlr16 ARM64 intrinsic
- __stlr32 ARM64 intrinsic
- __stlr64 ARM64 intrinsic
- __swp8 ARM64 intrinsic
- __swp16 ARM64 intrinsic
- __swp32 ARM64 intrinsic
- __swp64 ARM64 intrinsic
- __swpa8 ARM64 intrinsic
- __swpa16 ARM64 intrinsic
- __swpa32 ARM64 intrinsic
- __swpa64 ARM64 intrinsic
- __swpl8 ARM64 intrinsic
- __swpl16 ARM64 intrinsic
- __swpl32 ARM64 intrinsic
- __swpl64 ARM64 intrinsic
- __swpal8 ARM64 intrinsic
- __swpal16 ARM64 intrinsic
- __swpal32 ARM64 intrinsic
- __swpal64 ARM64 intrinsic
- __sys ARM64 intrinsic
- __svc ARM64 intrinsic
- __writex18byte ARM64 intrinsic
- __writex18word ARM64 intrinsic
- __writex18dword ARM64 intrinsic
- __writex18qword ARM64 intrinsic
author: sigatrev
ms.author: magardn
ms.date: 11/14/2019
ms.openlocfilehash: 27325df55d128337a45e76bbf5387508a523f57c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754525"
---
# <a name="arm64-intrinsics"></a>ARM64 iç bilgileri

Microsoft C++ derleyicisi (MSVC), ARM64 mimarisinde aşağıdaki içselleri kullanılabilir hale getirir. ARM hakkında daha fazla bilgi için ARM Geliştirici [Belgeleri](https://developer.arm.com/docs) web sitesinin Mimari ve Yazılım Geliştirme Araçları bölümlerine bakın.

## <a name="neon"></a><a name="top"></a>Neon

ARM64 için NEON vektör talimat seti uzantıları, Tek Öğretimli Çoklu Veri (SIMD) özellikleri sağlar. MMX ve SSE vektör talimat kümelerinde x86 ve x64 mimari işlemcilerde yaygın olan ait olanlara benzerler.

NEON içselleri, *arm64_neon.h*. NEON içselleri için MSVC desteği ARM Infocenter web sitesinde [ARM NEON Intrinsic Referans](https://static.docs.arm.com/ihi0073/c/IHI0073C_arm_neon_intrinsics_ref.pdf) belgelenmiştir ARM64 derleyici, benzer.

## <a name="arm64-specific-intrinsics-listing"></a><a name="A"></a>ARM64'e özgü içsel liste

|İşlev Adı|Yönerge|Fonksiyon Prototipi|
|-------------------|-----------------|------------------------|
|__break|Brk|void __break(int)|
|__addx18byte||void __addx18byte (imzasız uzun, imzasız char)|
|__addx18word||void __addx18word (imzasız uzun, imzasız kısa)|
|__addx18dword||void __addx18dword (imzasız uzun, imzasız uzun)|
|__addx18qword||void __addx18qword (imzasız uzun, imzasız __int64)|
|__cas8|CASB|imzasız __int8 __cas8 (imzasız __int8 geçici* _Target, imzasız __int8 _Comp, imzasız __int8 _Value)|
|__cas16|Nakit|imzasız __int16 __cas16 (imzasız __int16 uçucu* _Target, imzasız __int16 _Comp, imzasız __int16 _Value)|
|__cas32|CAS|imzasız __int32 __cas32 (imzasız __int32 geçici* _Target, imzasız __int32 _Comp, imzasız __int32 _Value)|
|__cas64|CAS|imzasız __int64 __cas64 (imzasız __int64 uçucu* _Target, imzasız __int64 _Comp, imzasız __int64 _Value)|
|__casa8|CASAB|imzasız __int8 __casa8 (imzasız __int8 geçici* _Target, imzasız __int8 _Comp, imzasız __int8 _Value)|
|__casa16|CASAH|imzasız __int16 __casa16 (imzasız __int16 geçici* _Target, imzasız __int16 _Comp, imzasız __int16 _Value)|
|__casa32|Casa|imzasız __int32 __casa32 (imzasız __int32 geçici* _Target, imzasız __int32 _Comp, imzasız __int32 _Value)|
|__casa64|Casa|imzasız __int64 __casa64 (imzasız __int64 geçici* _Target, imzasız __int64 _Comp, imzasız __int64 _Value)|
|__casl8|CASLB|imzasız __int8 __casl8 (imzasız __int8 uçucu* _Target, imzasız __int8 _Comp, imzasız __int8 _Value)|
|__casl16|CASLH|imzasız __int16 __casl16 (imzasız __int16 geçici* _Target, imzasız __int16 _Comp, imzasız __int16 _Value)|
|__casl32|CASL|imzasız __int32 __casl32 (imzasız __int32 geçici* _Target, imzasız __int32 _Comp, imzasız __int32 _Value)|
|__casl64|CASL|imzasız __int64 __casl64 (imzasız __int64 geçici* _Target, imzasız __int64 _Comp, imzasız __int64 _Value)|
|__casal8|CASALB|imzasız __int8 __casal8 (imzasız __int8 geçici* _Target, imzasız __int8 _Comp, imzasız __int8 _Value)|
|__casal16|CASALH|imzasız __int16 __casal16 (imzasız __int16 geçici* _Target, imzasız __int16 _Comp, imzasız __int16 _Value)|
|__casal32|Casal|imzasız __int32 __casal32 (imzasız __int32 geçici* _Target, imzasız __int32 _Comp, imzasız __int32 _Value)|
|__casal64|Casal|imzasız __int64 __casal64 (imzasız __int64 geçici* _Target, imzasız __int64 _Comp, imzasız __int64 _Value)|
|__crc32b|CRC32B|imzasız __int32 __crc32b (imzasız __int32, imzasız __int32)|
|__crc32h|CRC32H|imzasız __int32 __crc32h (imzasız __int32, imzasız __int32)|
|__crc32w|CRC32W|imzasız __int32 __crc32w (imzasız __int32, imzasız __int32)|
|__crc32d|CRC32X|imzasız __int32 __crc32d (imzasız __int32, imzasız __int64)|
|__crc32cb|CRC32CB|imzasız __int32 __crc32cb (imzasız __int32, imzasız __int32)|
|__crc32ch|CRC32CH|imzasız __int32 __crc32ch (imzasız __int32, imzasız __int32)|
|__crc32cw|CRC32CW|imzasız __int32 __crc32cw (imzasız __int32, imzasız __int32)|
|__crc32cd|CRC32CX|imzasız __int32 __crc32cd (imzasız __int32, imzasız __int64)|
|__dmb|Dmb|void __dmb(imzasız `_Type`int)<br /><br /> Talimat akışına bir bellek engeli işlemi ekler. Parametre, `_Type` bariyerin uyguladığı kısıtlama türünü belirtir.<br /><br /> Uygulanabilecek kısıtlama türleri hakkında daha fazla bilgi için [bellek engeli kısıtlamalarına](#BarrierRestrictions)bakın.|
|__dsb|Dsb|void __dsb (imzasız int _Type)<br /><br /> Talimat akışına bir bellek engeli işlemi ekler. Parametre, `_Type` bariyerin uyguladığı kısıtlama türünü belirtir.<br /><br /> Uygulanabilecek kısıtlama türleri hakkında daha fazla bilgi için [bellek engeli kısıtlamalarına](#BarrierRestrictions)bakın.|
|__isb|ısb|void __isb (imzasız int _Type)<br /><br /> Talimat akışına bir bellek engeli işlemi ekler. Parametre, `_Type` bariyerin uyguladığı kısıtlama türünü belirtir.<br /><br /> Uygulanabilecek kısıtlama türleri hakkında daha fazla bilgi için [bellek engeli kısıtlamalarına](#BarrierRestrictions)bakın.|
|__getReg||imzasız __int64 __getReg(int)|
|__getRegFp||çift __getRegFp(int)|
|__getCallerReg||imzasız __int64 __getCallerReg(int)|
|__getCallerRegFp||çift __getCallerRegFp(int)|
|__hvc|HVC|imzasız int __hvc(imzasız int, ...)|
|__hlt|Hlt|int __hlt(imzasız int, ...)|
|__incx18byte||void __incx18byte (imzasız uzun)|
|__incx18word||void __incx18word (imzasız uzun)|
|__incx18dword||void __incx18dword (imzasız uzun)|
|__incx18qword||void __incx18qword (imzasız uzun)|
|__iso_volatile_load16||__int16 \__iso_volatile_load16 (const uçucu \__int16) \*<br /><br /> Daha fazla bilgi için [__iso_volatile_load/mağaza içlerine](#IsoVolatileLoadStore)bakın.|
|__iso_volatile_load32||__int32 \__iso_volatile_load32 (const uçucu \__int32) \*<br /><br /> Daha fazla bilgi için [__iso_volatile_load/mağaza içlerine](#IsoVolatileLoadStore)bakın.|
|__iso_volatile_load64||__int64 \__iso_volatile_load64(const \_ \*uçucu _int64)<br /><br /> Daha fazla bilgi için [__iso_volatile_load/mağaza içlerine](#IsoVolatileLoadStore)bakın.|
|__iso_volatile_load8||__int8 \__iso_volatile_load8 (const uçucu \__int8 \*)<br /><br /> Daha fazla bilgi için [__iso_volatile_load/mağaza içlerine](#IsoVolatileLoadStore)bakın.|
|__iso_volatile_store16||void __iso_volatile_store16 \_(uçucu _int16 \*, \__int16)<br /><br /> Daha fazla bilgi için [__iso_volatile_load/mağaza içlerine](#IsoVolatileLoadStore)bakın.|
|__iso_volatile_store32||void __iso_volatile_store32 \_(uçucu _int32 \*, \__int32)<br /><br /> Daha fazla bilgi için [__iso_volatile_load/mağaza içlerine](#IsoVolatileLoadStore)bakın.|
|__iso_volatile_store64||void __iso_volatile_store64 \_(uçucu _int64 \*, \__int64)<br /><br /> Daha fazla bilgi için [__iso_volatile_load/mağaza içlerine](#IsoVolatileLoadStore)bakın.|
|__iso_volatile_store8||void __iso_volatile_store8 \_(uçucu _int8 \*, \__int8)<br /><br /> Daha fazla bilgi için [__iso_volatile_load/mağaza içlerine](#IsoVolatileLoadStore)bakın.|
|__ldar8|LDARB|imzasız __int8 __ldar8 (imzasız __int8 uçucu* _Target)|
|__ldar16|LDARH|imzasız __int16 __ldar16 (imzasız __int16 geçici* _Target)|
|__ldar32|LDAR|imzasız __int32 __ldar32 (imzasız __int32 geçici* _Target)|
|__ldar64|LDAR|imzasız __int64 __ldar64 (imzasız __int64 geçici* _Target)|
|__ldapr8|LDAPRB|imzasız __int8 __ldapr8 (imzasız __int8 uçucu* _Target)|
|__ldapr16|LDAPRH|imzasız __int16 __ldapr16 (imzasız __int16 uçucu* _Target)|
|__ldapr32|LDAPR|imzasız __int32 __ldapr32 (imzasız __int32 uçucu* _Target)|
|__ldapr64|LDAPR|imzasız __int64 __ldapr64 (imzasız __int64 geçici* _Target)|
|__mulh||\__int64 __mulh(\_ \__int64, _int64)|
|__prefetch|PRFM|void \___cdecl _prefetch(const void) \*<br /><br /> Belirtilen `PRFM` adresteki veya yakınında `PLDL1KEEP` olan belleğe yakında erişilebilen sisteme ön getirme işlemi yle birlikte bir bellek ipucu sağlar. Bazı sistemler, çalışma zamanı performansını artırmak için bu bellek erişim deseni için en iyi duruma getirmeyi seçebilir. Ancak, C++ dil açısından bakıldığında, işlevin gözlemlenebilir bir etkisi yoktur ve hiçbir şey yapmayabilir.|
|__prefetch2|PRFM|void \___cdecl _prefetch(const void \*, uint8_t prfop)<br /><br /> Sisteme `PRFM` sağlanan ön getirme işlemiyle birlikte, belirtilen adresteki veya yakınında olan belleğe yakında erişilebilen bir bellek ipucu sağlar. Bazı sistemler, çalışma zamanı performansını artırmak için bu bellek erişim deseni için en iyi duruma getirmeyi seçebilir. Ancak, C++ dil açısından bakıldığında, işlevin gözlemlenebilir bir etkisi yoktur ve hiçbir şey yapmayabilir.|
|__readx18byte||imzasız char __readx18byte (imzasız uzun)|
|__readx18word||imzasız kısa __readx18word (imzasız uzun)|
|__readx18dword||imzasız uzun __readx18dword (imzasız uzun)|
|__readx18qword||imzasız __int64 __readx18qword (imzasız uzun)|
|__setReg||void __setReg (int, imzasız __int64)|
|__setRegFp||void __setRegFp(int, çift)|
|__setCallerReg||void __setCallerReg (int, imzasız __int64)|
|__setCallerRegFp||void __setCallerRegFp (int, çift)|
|__sev|SEV|void __sev(void)|
|__static_assert||void __static_assert(int, const char \*)|
|__stlr8|STLRB|void __stlr8 (imzasız __int8 uçucu* _Target, imzasız __int8 _Value)|
|__stlr16|STLRH|void __stlr16 (imzasız __int16 geçici* _Target, imzasız __int16 _Value)|
|__stlr32|STLR|void __stlr32 (imzasız __int32 geçici* _Target, imzasız __int32 _Value)|
|__stlr64|STLR|void __stlr64 (imzasız __int64 uçucu* _Target, imzasız __int64 _Value)|
|__swp8|SWPB|imzasız __int8 __swp8 (imzasız __int8 geçici* _Target, imzasız __int8 _Value)|
|__swp16|SWPH|imzasız __int16 __swp16 (imzasız __int16 geçici* _Target, imzasız __int16 _Value)|
|__swp32|Swp|imzasız __int32 __swp32 (imzasız __int32 uçucu* _Target, imzasız __int32 _Value)|
|__swp64|Swp|imzasız __int64 __swp64 (imzasız __int64 geçici* _Target, imzasız __int64 _Value)|
|__swpa8|SWPAB|imzasız __int8 __swpa8 (imzasız __int8 uçucu* _Target, imzasız __int8 _Value)|
|__swpa16|SWPAH|imzasız __int16 __swpa16 (imzasız __int16 geçici* _Target, imzasız __int16 _Value)|
|__swpa32|SWPA|imzasız __int32 __swpa32 (imzasız __int32 geçici* _Target, imzasız __int32 _Value)|
|__swpa64|SWPA|imzasız __int64 __swpa64 (imzasız __int64 uçucu* _Target, imzasız __int64 _Value)|
|__swpl8|SWPLB|imzasız __int8 __swpl8 (imzasız __int8 geçici* _Target, imzasız __int8 _Value)|
|__swpl16|SWPLH|imzasız __int16 __swpl16 (imzasız __int16 uçucu* _Target, imzasız __int16 _Value)|
|__swpl32|SWPL|imzasız __int32 __swpl32 (imzasız __int32 uçucu* _Target, imzasız __int32 _Value)|
|__swpl64|SWPL|imzasız __int64 __swpl64 (imzasız __int64 geçici* _Target, imzasız __int64 _Value)|
|__swpal8|SWPALB|imzasız __int8 __swpal8 (imzasız __int8 uçucu* _Target, imzasız __int8 _Value)|
|__swpal16|SWPALH|imzasız __int16 __swpal16 (imzasız __int16 uçucu* _Target, imzasız __int16 _Value)|
|__swpal32|SWPAL|imzasız __int32 __swpal32 (imzasız __int32 geçici* _Target, imzasız __int32 _Value)|
|__swpal64|SWPAL|imzasız __int64 __swpal64 (imzasız __int64 geçici* _Target, imzasız __int64 _Value)|
|__sys|SYS|imzasız int __sys(int, __int64)|
|__svc|Svc|imzasız int __svc (imzasız int, ...)|
|__wfe|WFE|void __wfe(void)|
|__wfi|WFI|void __wfi(void)|
|__writex18byte||void __writex18byte (imzasız uzun, imzasız char)|
|__writex18word||void __writex18word (imzasız uzun, imzasız kısa)|
|__writex18dword||void __writex18dword (imzasız uzun, imzasız uzun)|
|__writex18qword||void __writex18qword (imzasız uzun, imzasız __int64)|
|__umulh||imzasız \__int64 __umulh \_(imzasız \__int64, imzasız _int64)|
|_CopyDoubleFromInt64||çift _CopyDoubleFromInt64\_(_int64)|
|_CopyFloatFromInt32||float _CopyFloatFromInt32\_(_int32)|
|_CopyInt32FromFloat||__int32 _CopyInt32FromFloat(float)|
|_CopyInt64FromDouble||__int64 _CopyInt64FromDouble(çift)|
|_CountLeadingOnes||imzasız int _CountLeadingOnes (imzasız uzun)|
|_CountLeadingOnes64||imzasız int _CountLeadingOnes64 \_(imzasız _int64)|
|_CountLeadingSigns||imzasız int _CountLeadingSigns(uzun)|
|_CountLeadingSigns64||imzasız int\__CountLeadingSigns64 (_int64)|
|_CountLeadingZeros||imzasız int _CountLeadingZeros (imzasız uzun)|
|_CountLeadingZeros64||imzasız int _CountLeadingZeros64 \_(imzasız _int64)|
|_ReadStatusReg|Bayan|\__int64 _ReadStatusReg(int)|
|_WriteStatusReg|Msr|void _WriteStatusReg(int, \__int64)|

[[En tepeye dön](#top)]

### <a name="memory-barrier-restrictions"></a><a name="BarrierRestrictions"></a>Bellek bariyeri kısıtlamaları

İçsel işlevler `__dmb` (veri belleği `__dsb` bariyeri), (veri `__isb` eşitleme bariyeri) ve (yönerge eşitleme engeli) paylaşım etki alanı ve işlemden etkilenen erişim türü açısından bellek bariyeri kısıtlamasını belirtmek için aşağıdaki önceden tanımlanmış değerleri kullanır.

|Kısıtlama Değeri|Açıklama|
|-----------------------|-----------------|
|_ARM64_BARRIER_SY|Tam sistem, okur ve yazıyor.|
|_ARM64_BARRIER_ST|Tam sistem, sadece yazıyor.|
|_ARM64_BARRIER_LD|Tam sistem, sadece okuyun.|
|_ARM64_BARRIER_ISH|İç sharable, okur ve yazıyor.|
|_ARM64_BARRIER_ISHST|İç sharable, sadece yazıyor.|
|_ARM64_BARRIER_ISHLD|İç sharable, sadece okuyun.|
|_ARM64_BARRIER_NSH|Sharable olmayan, okur ve yazıyor.|
|_ARM64_BARRIER_NSHST|Sharable olmayan, sadece yazıyor.|
|_ARM64_BARRIER_NSHLD|Sharable olmayan, sadece okuyun.|
|_ARM64_BARRIER_OSH|Dış sharable, okur ve yazıyor.|
|_ARM64_BARRIER_OSHST|Dış sharable, sadece yazıyor.|
|_ARM64_BARRIER_OSHLD|Dış sharable, sadece okuyun.|

`__isb` İçsel olarak, şu anda geçerli olan tek kısıtlama _ARM64_BARRIER_SY; diğer tüm değerler mimari tarafından ayrılmıştır.

### <a name="__iso_volatile_loadstore-intrinsics"></a><a name="IsoVolatileLoadStore"></a>__iso_volatile_load/mağaza içsel

Bu içsel işlevler, derleyici optimizasyonlarına tabi olmayan yükleri ve depoları açıkça gerçekleştirir.

```C
__int16 __iso_volatile_load16(const volatile __int16 * Location);
__int32 __iso_volatile_load32(const volatile __int32 * Location);
__int64 __iso_volatile_load64(const volatile __int64 * Location);
__int8 __iso_volatile_load8(const volatile __int8 * Location);

void __iso_volatile_store16(volatile __int16 * Location, __int16 Value);
void __iso_volatile_store32(volatile __int32 * Location, __int32 Value);
void __iso_volatile_store64(volatile __int64 * Location, __int64 Value);
void __iso_volatile_store8(volatile __int8 * Location, __int8 Value);
```

#### <a name="parameters"></a>Parametreler

*Konum*\
Okunacak veya yazılmak için bir bellek konumunun adresi.

*Değer*\
Belirtilen bellek konumuna yazılması gereken değer (yalnızca içsel leri saklayın).

#### <a name="return-value-load-intrinsics-only"></a>İade değeri (yalnızca yük içselleri)

*Konum*tarafından belirtilen bellek konumunun değeri.

#### <a name="remarks"></a>Açıklamalar

Derleyici optimizasyonlarına tabi olmayan bellek erişimlerini açıkça gerçekleştirmek için `__iso_volatile_load8/16/32/64` ve `__iso_volatile_store8/16/32/64` içsel olarak kullanabilirsiniz. Derleyici bu işlemlerin göreli sırasını kaldıramaz, sentezleyebilir veya değiştiremez. Ancak, örtülü donanım bellek engelleri oluşturmaz. Bu nedenle, donanım yine de birden çok iş parçacığı arasında gözlemlenebilir bellek erişimleri yeniden sıralayabilir. Daha doğrusu, bu içseller **/volatile:iso**altında derlenen aşağıdaki ifadelere eşdeğerdir.

```cpp
int a = __iso_volatile_load32(p);    // equivalent to: int a = *(const volatile __int32*)p;
__iso_volatile_store32(p, a);        // equivalent to: *(volatile __int32*)p = a;
```

Içsel değişkenlerin uçucu değişkenleri yerleştirmek için uçucu işaretçiler ilerler. Ancak, bağımsız değişken olarak geçici işaretçiler kullanmak için bir gereklilik veya öneri yoktur. Düzenli, uçucu olmayan bir tür kullanılıyorsa, bu işlemlerin anlambilimi tamamen aynıdır.

**/volatile:iso** komut satırı bağımsız değişkeni hakkında daha fazla bilgi için [bkz.](../build/reference/volatile-volatile-keyword-interpretation.md)

## <a name="arm64-support-for-intrinsics-from-other-architectures"></a><a name="I"></a>Diğer mimarilerden içseller için ARM64 desteği

Aşağıdaki tabloda ARM64 platformlarında desteklenen diğer mimarilerin içsel leri listelenmiştir. ARM64'teki bir içsel davranışının diğer donanım mimarileri üzerindeki davranışından farklı olduğu durumlarda, ek ayrıntılar belirtilir.

|İşlev Adı|Fonksiyon Prototipi|
|-------------------|------------------------|
|__assume|void __assume(int)|
|__code_seg|void __code_seg(const \*char)|
|__debugbreak|void \___cdecl _debugbreak(void)|
|__fastfail|__declspec(noreturn) \_void _fastfail (imzasız int)|
|__nop|void __nop(void)|
|__yield|void __yield(void) **Not:** ARM64 platformlarında bu fonksiyon YIELD talimatını oluşturur. Bu yönerge, iş parçacığının programı olumsuz etkilemeden geçici olarak yürütmeden (örneğin, bir spinlock) askıya alınabilecek bir görev gerçekleştirdiğini gösterir. CPU aksi takdirde boşa olurdu yürütme döngüleri sırasında diğer görevleri yürütmek için sağlar.|
|_AddressOfReturnAddress|void \* _AddressOfReturnAddress(void)|
|_BitScanForward|imzasız char _BitScanForward (imzasız uzun \* _Index, imzasız uzun _Mask)|
|_BitScanForward64|imzasız char _BitScanForward64 (imzasız uzun \* _Index, imzasız __int64 _Mask)|
|_BitScanReverse|imzasız char _BitScanReverse (imzasız uzun \* _Index, imzasız uzun _Mask)|
|_BitScanReverse64|imzasız char _BitScanReverse64 (imzasız uzun \* _Index, imzasız __int64 _Mask)|
|_bittest|imzasız char _bittest(uzun \*const, uzun)|
|_bittest64|imzasız char _bittest64(__int64 \*const , __int64)|
|_bittestandcomplement|imzasız char _bittestandcomplement(uzun, \*uzun)|
|_bittestandcomplement64|imzasız char _bittestandcomplement64(__int64 \*, __int64)|
|_bittestandreset|imzasız char _bittestandreset(uzun, \*uzun)|
|_bittestandreset64|imzasız char _bittestandreset64(__int64 \*, __int64)|
|_bittestandset|imzasız char _bittestandset(uzun, \*uzun)|
|_bittestandset64|imzasız char _bittestandset64(__int64 \*, __int64)|
|_byteswap_uint64|imzasız \___int64 _cdecl _byteswap_uint64 \_(imzasız _int64)|
|_byteswap_ulong|imzasız uzun __cdecl _byteswap_ulong (imzasız uzun)|
|_byteswap_ushort|imzasız kısa __cdecl _byteswap_ushort (imzasız kısa)|
|_disable|void __cdecl _disable(void) **Not:** ARM64 platformlarında bu `MSR DAIFCLR,#2`işlev yönergeyi oluşturur; sadece içsel olarak kullanılabilir.|
|_enable|void __cdecl _enable(void) **Not:** ARM64 platformlarında bu `MSR DAIFSET,#2`işlev yönergeyi oluşturur; sadece içsel olarak kullanılabilir.|
|_lrotl|imzasız uzun __cdecl _lrotl (imzasız uzun, int)|
|_lrotr|imzasız uzun __cdecl _lrotr (imzasız uzun, int)|
|_ReadBarrier|void _ReadBarrier(void)|
|_ReadWriteBarrier|void _ReadWriteBarrier(void)|
|_ReturnAddress|void \* _ReturnAddress(void)|
|_rotl|imzasız int __cdecl _rotl (imzasız int _Value, int _Shift)|
|_rotl16|imzasız kısa _rotl16 (imzasız kısa _Value, imzasız char _Shift)|
|_rotl64|imzasız \___int64 _cdecl _rotl64 \_(imzasız _int64 _Value, int _Shift)|
|_rotl8|imzasız char _rotl8 (imzasız char _Value, imzasız char _Shift)|
|_rotr|imzasız int __cdecl _rotr (imzasız int _Value, int _Shift)|
|_rotr16|imzasız kısa _rotr16 (imzasız kısa _Value, imzasız char _Shift)|
|_rotr64|imzasız \___int64 _cdecl _rotr64 \_(imzasız _int64 _Value, int _Shift)|
|_rotr8|imzasız char _rotr8 (imzasız char _Value, imzasız char _Shift)|
|_setjmpex|int __cdecl _setjmpex(jmp_buf)|
|_WriteBarrier|void _WriteBarrier(void)|

[[En tepeye dön](#top)]

## <a name="interlocked-intrinsics"></a>Birbirine kenetlenmiş içsellikler

Birbirine kenetlenmiş içseller, atomik okuma-değiştirme-yazma işlemlerini gerçekleştirmek için kullanılan bir içsel kümedir. Bazıları tüm platformlarda yaygındır. Burada ayrı ayrı listelenmişler çünkü çok sayıda var. Tanımları çoğunlukla gereksiz olduğundan, genel olarak onları düşünmek daha kolaydır. İsimleri tam davranışları türetmek için kullanılabilir.

Aşağıdaki tablo, bittest olmayan birbirine kenetlenmiş içsellerin ARM64 desteğini özetleyin. Tablodaki her hücre, satırın sol daki en çok hücreye işlem adı ve sütunun en üstteki hücresindeki tür adı `_Interlocked`ekleyerek türetilen bir ada karşılık gelir. Örneğin, `Xor` satır ın kesiştiği hücre `8` ve sütun `_InterlockedXor8` karşılık gelir ve tam olarak desteklenir. Desteklenen işlevlerin çoğu bu isteğe bağlı `_acq`sonekleri sunar: , , `_rel`ve `_nf`. Sonek `_acq` bir "edinme" semantik gösterir `_rel` ve sonek bir "sürüm" semantik gösterir. `_nf` Veya "hiçbir çit" soneki ARM ve ARM64 benzersizdir ve sonraki bölümde ele alınmıştır.

||8|16|32|64|128|P|
|-|-------|--------|--------|--------|-------|-------|
|Ekle|Hiçbiri|Hiçbiri|Tam|Tam|Hiçbiri|Hiçbiri|
|And|Tam|Tam|Tam|Tam|Hiçbiri|Hiçbiri|
|Compareexchange|Tam|Tam|Tam|Tam|Tam|Tam|
|Azaltma|Hiçbiri|Tam|Tam|Tam|Hiçbiri|Hiçbiri|
|Exchange|Tam|Tam|Tam|Tam|Hiçbiri|Tam|
|ExchangeAdd|Tam|Tam|Tam|Tam|Hiçbiri|Hiçbiri|
|Artış|Hiçbiri|Tam|Tam|Tam|Hiçbiri|Hiçbiri|
|Veya|Tam|Tam|Tam|Tam|Hiçbiri|Hiçbiri|
|Xor|Tam|Tam|Tam|Tam|Hiçbiri|Hiçbiri|

Anahtar:

- **Full**: `_acq`düz, `_rel`, `_nf` , ve formları destekler.

- **Yok**: Desteklenmiyor

### <a name="_nf-no-fence-suffix"></a><a name="nf_suffix"></a>_nf (çit yok) soneki

Veya `_nf` "çit yok" soneki, işlemin, diğer üç formun (düz, `_acq`ve), `_rel`aksine, herhangi bir tür bariyer olarak davranmasının herhangi bir bellek engeli olarak davranmadığını gösterir. `_nf` Formların olası bir kullanımı, aynı anda birden çok iş parçacığı tarafından güncelleştirilen ancak birden çok iş parçacığı yürütülerken değeri başka şekilde kullanılmayan bir istatistik sayacı korumaktır.

### <a name="list-of-interlocked-intrinsics"></a>Birbirine kenetlenmiş içseller listesi

|İşlev Adı|Fonksiyon Prototipi|
|-------------------|------------------------|
|_InterlockedAdd|uzun _InterlockedAdd (uzun _volatile, \*uzun)|
|_InterlockedAdd64|__int64 _InterlockedAdd64\_(_int64 uçucu \*, \__int64)|
|_InterlockedAdd64_acq|__int64 _InterlockedAdd64_acq\_(_int64 uçucu \*, \__int64)|
|_InterlockedAdd64_nf|__int64 _InterlockedAdd64_nf\_( \* \__int64 uçucu , _int64)|
|_InterlockedAdd64_rel|__int64 _InterlockedAdd64_rel(\_ \*_int64 \_uçucu , _int64)|
|_InterlockedAdd_acq|uzun _InterlockedAdd_acq (uzun uçucu, \*uzun)|
|_InterlockedAdd_nf|uzun _InterlockedAdd_nf (uzun uçucu, \*uzun)|
|_InterlockedAdd_rel|uzun _InterlockedAdd_rel (uzun uçucu, \*uzun)|
|_InterlockedAnd|uzun _InterlockedAnd (uzun uçucu, \*uzun)|
|_InterlockedAnd16|kısa _InterlockedAnd16 (kısa uçucu, \*kısa)|
|_InterlockedAnd16_acq|kısa _InterlockedAnd16_acq (kısa uçucu, \*kısa)|
|_InterlockedAnd16_nf|kısa _InterlockedAnd16_nf (kısa uçucu, \*kısa)|
|_InterlockedAnd16_rel|kısa _InterlockedAnd16_rel (kısa uçucu, \*kısa)|
|_InterlockedAnd64|__int64 _InterlockedAnd64\_( \* \__int64 uçucu , _int64)|
|_InterlockedAnd64_acq|__int64 _InterlockedAnd64_acq\_( \* \__int64 uçucu , _int64)|
|_InterlockedAnd64_nf|__int64 _InterlockedAnd64_nf\_( \* \__int64 uçucu , _int64)|
|_InterlockedAnd64_rel|__int64 _InterlockedAnd64_rel\_(_int64 uçucu \*, \__int64)|
|_InterlockedAnd8|char _InterlockedAnd8(char \*uçucu, char)|
|_InterlockedAnd8_acq|char _InterlockedAnd8_acq(char \*uçucu, char)|
|_InterlockedAnd8_nf|char _InterlockedAnd8_nf(char \*uçucu, char)|
|_InterlockedAnd8_rel|char _InterlockedAnd8_rel(char \*uçucu, char)|
|_InterlockedAnd_acq|uzun _InterlockedAnd_acq (uzun uçucu, \*uzun)|
|_InterlockedAnd_nf|uzun _InterlockedAnd_nf (uzun uçucu, \*uzun)|
|_InterlockedAnd_rel|uzun _InterlockedAnd_rel (uzun uçucu, \*uzun)|
|_InterlockedCompareExchange|uzun __cdecl _InterlockedCompareExchange \*(uzun uçucu, uzun, uzun)|
|_InterlockedCompareExchange_acq|uzun _InterlockedCompareExchange_acq (uzun uçucu, \*uzun, uzun)|
|_InterlockedCompareExchange_nf|uzun _InterlockedCompareExchange_nf (uzun uçucu, \*uzun, uzun)|
|_InterlockedCompareExchange_rel|uzun _InterlockedCompareExchange_rel (uzun uçucu, \*uzun, uzun)|
|_InterlockedCompareExchange16|kısa _InterlockedCompareExchange16 (kısa uçucu, \*kısa, kısa)|
|_InterlockedCompareExchange16_acq|kısa _InterlockedCompareExchange16_acq (kısa uçucu, \*kısa, kısa)|
|_InterlockedCompareExchange16_nf|kısa _InterlockedCompareExchange16_nf (kısa uçucu, \*kısa, kısa)|
|_InterlockedCompareExchange16_rel|kısa _InterlockedCompareExchange16_rel (kısa uçucu, \*kısa, kısa)|
|_InterlockedCompareExchange64|__int64 _InterlockedCompareExchange64\_(_int64 \_uçucu \_ \*, _int64, _int64)|
|_InterlockedCompareExchange64_acq|\___int64 _InterlockedCompareExchange64_acq( \*_int64 \_uçucu \_, _int64, _int64)|
|_InterlockedCompareExchange64_nf|__int64 _InterlockedCompareExchange64_nf\_( \* \_uçucu \__int64 , _int64, _int64)|
|_InterlockedCompareExchange64_rel|__int64 _InterlockedCompareExchange64_rel\_(_int64 \_uçucu \_ \*, _int64, _int64)|
|_InterlockedCompareExchange8|char _InterlockedCompareExchange8 (char uçucu, \*char, char)|
|_InterlockedCompareExchange8_acq|char _InterlockedCompareExchange8_acq(char \*uçucu, char, char)|
|_InterlockedCompareExchange8_nf|char _InterlockedCompareExchange8_nf(char \*uçucu, char, char)|
|_InterlockedCompareExchange8_rel|char _InterlockedCompareExchange8_rel(char \*uçucu, char, char)|
|_InterlockedCompareExchangePointer|void \* _InterlockedCompareExchangePointer \* (void \* \*volatile \*, void , void )|
|_InterlockedCompareExchangePointer_acq|void \* _InterlockedCompareExchangePointer_acq \* (void \* \*volatile \*, void , void )|
|_InterlockedCompareExchangePointer_nf|void \* _InterlockedCompareExchangePointer_nf \* (void \* \*volatile \*, void , void )|
|_InterlockedCompareExchangePointer_rel|void \* _InterlockedCompareExchangePointer_rel \* (void \* \*volatile \*, void , void )|
|_InterlockedCompareExchange128|(uçucu\_ \* _Destination, _int64 _ExchangeHigh, \_ \__int64 _ExchangeLow, \_ \* _int64 _ComparandResult) _int64 imzasız char _InterlockedCompareExchange128|
|_InterlockedCompareExchange128_acq|(uçucu\_ \* _Destination, _int64 _ExchangeHigh, \_ \__ExchangeLow _int64, \_ \* _int64 _ComparandResult _int64) imzasız char _InterlockedCompareExchange128_acq|
|_InterlockedCompareExchange128_nf|(uçucu\_ \* _Destination, _int64 _ExchangeHigh, \__int64 \__ExchangeLow, \_ \* _int64 _ComparandResult _int64) imzasız char _InterlockedCompareExchange128_nf|
|_InterlockedCompareExchange128_rel|(uçucu\_ \* _Destination, _int64 _ExchangeHigh, \__int64 \__ExchangeLow, \_ \* _int64 _ComparandResult) _int64 imzasız char _InterlockedCompareExchange128_rel|
|_InterlockedDecrement|uzun __cdecl _InterlockedDecrement(uzun uçucu) \*|
|_InterlockedDecrement16|kısa _InterlockedDecrement16 (kısa uçucu) \*|
|_InterlockedDecrement16_acq|kısa _InterlockedDecrement16_acq (kısa uçucu) \*|
|_InterlockedDecrement16_nf|kısa _InterlockedDecrement16_nf (kısa uçucu \*)|
|_InterlockedDecrement16_rel|kısa _InterlockedDecrement16_rel (kısa uçucu) \*|
|_InterlockedDecrement64|__int64 _InterlockedDecrement64\_(_int64 uçucu \*)|
|_InterlockedDecrement64_acq|__int64 _InterlockedDecrement64_acq\_(_int64 uçucu) \*|
|_InterlockedDecrement64_nf|__int64\__InterlockedDecrement64_nf(_int64 \*uçucu)|
|_InterlockedDecrement64_rel|__int64 _InterlockedDecrement64_rel(\_ \*_int64 uçucu )|
|_InterlockedDecrement_acq|uzun _InterlockedDecrement_acq(uzun \*uçucu)|
|_InterlockedDecrement_nf|uzun _InterlockedDecrement_nf(uzun \*uçucu)|
|_InterlockedDecrement_rel|uzun _InterlockedDecrement_rel(uzun \*uçucu)|
|_InterlockedExchange|uzun __cdecl _InterlockedExchange \* (uzun uçucu _Target, uzun)|
|_InterlockedExchange_acq|uzun _InterlockedExchange_acq (uzun uçucu \* _Target, uzun)|
|_InterlockedExchange_nf|uzun _InterlockedExchange_nf (uzun uçucu \* _Target, uzun)|
|_InterlockedExchange_rel|uzun _InterlockedExchange_rel (uzun uçucu \* _Target, uzun)|
|_InterlockedExchange16|kısa _InterlockedExchange16 (kısa uçucu \* _Target, kısa)|
|_InterlockedExchange16_acq|kısa _InterlockedExchange16_acq (kısa uçucu \* _Target, kısa)|
|_InterlockedExchange16_nf|kısa _InterlockedExchange16_nf (kısa uçucu \* _Target, kısa)|
|_InterlockedExchange16_rel|kısa _InterlockedExchange16_rel (kısa uçucu \* _Target, kısa)|
|_InterlockedExchange64|__int64 _Target,\_ \_ \* _int64 _int64 _InterlockedExchange64|
|_InterlockedExchange64_acq|__int64 _InterlockedExchange64_acq(\_ \* uçucu \__int64 _Target, _int64)|
|_InterlockedExchange64_nf|__int64 _InterlockedExchange64_nf(\_ \* uçucu \__int64 _Target, _int64)|
|_InterlockedExchange64_rel|__int64\__InterlockedExchange64_rel(_int64 \* uçucu \__Target, _int64)|
|_InterlockedExchange8|char _InterlockedExchange8 (char uçucu \* _Target, char)|
|_InterlockedExchange8_acq|char _InterlockedExchange8_acq (char uçucu \* _Target, char)|
|_InterlockedExchange8_nf|char _InterlockedExchange8_nf(char \* uçucu _Target, char)|
|_InterlockedExchange8_rel|char _InterlockedExchange8_rel (char uçucu \* _Target, char)|
|_InterlockedExchangeAdd|uzun __cdecl _InterlockedExchangeAdd(uzun uçucu, \*uzun)|
|_InterlockedExchangeAdd16|kısa _InterlockedExchangeAdd16 (kısa uçucu, \*kısa)|
|_InterlockedExchangeAdd16_acq|kısa _InterlockedExchangeAdd16_acq (kısa uçucu, \*kısa)|
|_InterlockedExchangeAdd16_nf|kısa _InterlockedExchangeAdd16_nf (kısa uçucu, \*kısa)|
|_InterlockedExchangeAdd16_rel|kısa _InterlockedExchangeAdd16_rel (kısa uçucu, \*kısa)|
|_InterlockedExchangeAdd64|__int64 _InterlockedExchangeAdd64(\_ \*_int64 \_uçucu , _int64)|
|_InterlockedExchangeAdd64_acq|__int64 _InterlockedExchangeAdd64_acq\_(_int64 uçucu \*, \__int64)|
|_InterlockedExchangeAdd64_nf|__int64 _InterlockedExchangeAdd64_nf(\_ \*_int64 \_uçucu , _int64)|
|_InterlockedExchangeAdd64_rel|__int64 _InterlockedExchangeAdd64_rel\_(_int64 uçucu \*, \__int64)|
|_InterlockedExchangeAdd8|char _InterlockedExchangeAdd8(char \*uçucu, char)|
|_InterlockedExchangeAdd8_acq|char _InterlockedExchangeAdd8_acq(char \*uçucu, char)|
|_InterlockedExchangeAdd8_nf|char _InterlockedExchangeAdd8_nf(char \*uçucu, char)|
|_InterlockedExchangeAdd8_rel|char _InterlockedExchangeAdd8_rel(char \*uçucu, char)|
|_InterlockedExchangeAdd_acq|uzun _InterlockedExchangeAdd_acq (uzun uçucu, \*uzun)|
|_InterlockedExchangeAdd_nf|uzun _InterlockedExchangeAdd_nf (uzun uçucu, \*uzun)|
|_InterlockedExchangeAdd_rel|uzun _InterlockedExchangeAdd_rel (uzun uçucu, \*uzun)|
|_InterlockedExchangePointer|void \* _InterlockedExchangePointer \* (void \* uçucu \*_Target, void )|
|_InterlockedExchangePointer_acq|void \* _InterlockedExchangePointer_acq \* (void \* uçucu \*_Target, void )|
|_InterlockedExchangePointer_nf|void \* _InterlockedExchangePointer_nf \* (void \* uçucu \*_Target, void )|
|_InterlockedExchangePointer_rel|void \* _InterlockedExchangePointer_rel \* (void \* uçucu \*_Target, void )|
|_InterlockedIncrement|uzun __cdecl _InterlockedIncrement(uzun uçucu) \*|
|_InterlockedIncrement16|kısa _InterlockedIncrement16 (kısa uçucu) \*|
|_InterlockedIncrement16_acq|kısa _InterlockedIncrement16_acq (kısa uçucu) \*|
|_InterlockedIncrement16_nf|kısa _InterlockedIncrement16_nf(kısa \*uçucu)|
|_InterlockedIncrement16_rel|kısa _InterlockedIncrement16_rel (kısa uçucu) \*|
|_InterlockedIncrement64|__int64\__InterlockedIncrement64(_int64 \*uçucu)|
|_InterlockedIncrement64_acq|__int64 _InterlockedIncrement64_acq(\_ \*_int64 uçucu )|
|_InterlockedIncrement64_nf|__int64 _InterlockedIncrement64_nf\_( \*_int64 uçucu )|
|_InterlockedIncrement64_rel|__int64 _InterlockedIncrement64_rel\_(_int64 uçucu \*)|
|_InterlockedIncrement_acq|uzun _InterlockedIncrement_acq(uzun \*uçucu)|
|_InterlockedIncrement_nf|uzun _InterlockedIncrement_nf(uzun \*uçucu)|
|_InterlockedIncrement_rel|uzun _InterlockedIncrement_rel (uzun uçucu) \*|
|_InterlockedOr|uzun _InterlockedOr (uzun uçucu, \*uzun)|
|_InterlockedOr16|kısa _InterlockedOr16 (kısa uçucu, \*kısa)|
|_InterlockedOr16_acq|kısa _InterlockedOr16_acq (kısa uçucu, \*kısa)|
|_InterlockedOr16_nf|kısa _InterlockedOr16_nf (kısa uçucu, \*kısa)|
|_InterlockedOr16_rel|kısa _InterlockedOr16_rel (kısa uçucu, \*kısa)|
|_InterlockedOr64|__int64 _InterlockedOr64(\_ \*_int64 \_uçucu , _int64)|
|_InterlockedOr64_acq|__int64 _InterlockedOr64_acq\_( \* \__int64 uçucu , _int64)|
|_InterlockedOr64_nf|__int64 _InterlockedOr64_nf\_(_int64 uçucu \*, \__int64)|
|_InterlockedOr64_rel|__int64 _InterlockedOr64_rel\_(_int64 uçucu \*, \__int64)|
|_InterlockedOr8|char _InterlockedOr8(char \*uçucu, char)|
|_InterlockedOr8_acq|char _InterlockedOr8_acq(char \*uçucu, char)|
|_InterlockedOr8_nf|char _InterlockedOr8_nf(char \*uçucu, char)|
|_InterlockedOr8_rel|char _InterlockedOr8_rel(char \*uçucu, char)|
|_InterlockedOr_acq|uzun _InterlockedOr_acq (uzun uçucu, \*uzun)|
|_InterlockedOr_nf|uzun _InterlockedOr_nf (uzun uçucu, \*uzun)|
|_InterlockedOr_rel|uzun _InterlockedOr_rel (uzun uçucu, \*uzun)|
|_InterlockedXor|uzun _InterlockedXor (uzun uçucu, \*uzun)|
|_InterlockedXor16|kısa _InterlockedXor16 (kısa uçucu, \*kısa)|
|_InterlockedXor16_acq|kısa _InterlockedXor16_acq (kısa uçucu, \*kısa)|
|_InterlockedXor16_nf|kısa _InterlockedXor16_nf (kısa uçucu, \*kısa)|
|_InterlockedXor16_rel|kısa _InterlockedXor16_rel (kısa uçucu, \*kısa)|
|_InterlockedXor64|__int64 _InterlockedXor64\_(_int64 uçucu \*, \__int64)|
|_InterlockedXor64_acq|__int64 _InterlockedXor64_acq(\_ \*_int64 \_uçucu , _int64)|
|_InterlockedXor64_nf|__int64 _InterlockedXor64_nf\_( \* \__int64 uçucu , _int64)|
|_InterlockedXor64_rel|__int64 _InterlockedXor64_rel\_(_int64 uçucu \*, \__int64)|
|_InterlockedXor8|char _InterlockedXor8(char \*uçucu, char)|
|_InterlockedXor8_acq|char _InterlockedXor8_acq(char \*uçucu, char)|
|_InterlockedXor8_nf|char _InterlockedXor8_nf(char \*uçucu, char)|
|_InterlockedXor8_rel|char _InterlockedXor8_rel(char \*uçucu, char)|
|_InterlockedXor_acq|uzun _InterlockedXor_acq (uzun uçucu, \*uzun)|
|_InterlockedXor_nf|uzun _InterlockedXor_nf (uzun uçucu, \*uzun)|
|_InterlockedXor_rel|uzun _InterlockedXor_rel (uzun uçucu, \*uzun)|

[[En tepeye dön](#top)]

### <a name="_interlockedbittest-intrinsics"></a>_interlockedbittest içsel

Düz kilitli bit test intrinsics tüm platformlariçin ortak. ARM64 `_acq`ekler `_rel`, `_nf` ve türevleri, sadece bir işlemin bariyer semantiği değiştirmek, _nf açıklandığı gibi [(hiçbir çit) Soneki](#nf_suffix) bu makalede daha önce.

|İşlev Adı|Fonksiyon Prototipi|
|-------------------|------------------------|
|_interlockedbittestandreset|imzasız char _interlockedbittestandreset \*(uzun uçucu, uzun)|
|_interlockedbittestandreset_acq|imzasız char _interlockedbittestandreset_acq \*(uzun uçucu, uzun)|
|_interlockedbittestandreset_nf|imzasız char _interlockedbittestandreset_nf \*(uzun uçucu, uzun)|
|_interlockedbittestandreset_rel|imzasız char _interlockedbittestandreset_rel(uzun uçucu, \*uzun)|
|_interlockedbittestandreset64|imzasız char _interlockedbittestandreset64(__int64 uçucu \*, __int64)|
|_interlockedbittestandreset64_acq|imzasız char _interlockedbittestandreset64_acq(__int64 uçucu \*, __int64)|
|_interlockedbittestandreset64_nf|imzasız char _interlockedbittestandreset64_nf(__int64 uçucu \*, __int64)|
|_interlockedbittestandreset64_rel|imzasız char _interlockedbittestandreset64_rel(__int64 uçucu \*, __int64)|
|_interlockedbittestandset|imzasız char _interlockedbittestandset \*(uzun uçucu, uzun)|
|_interlockedbittestandset_acq|imzasız char _interlockedbittestandset_acq \*(uzun uçucu, uzun)|
|_interlockedbittestandset_nf|imzasız char _interlockedbittestandset_nf \*(uzun uçucu, uzun)|
|_interlockedbittestandset_rel|imzasız char _interlockedbittestandset_rel \*(uzun uçucu, uzun)|
|_interlockedbittestandset64|imzasız char _interlockedbittestandset64(__int64 uçucu \*, __int64)|
|_interlockedbittestandset64_acq|imzasız char _interlockedbittestandset64_acq(__int64 uçucu \*, __int64)|
|_interlockedbittestandset64_nf|imzasız char _interlockedbittestandset64_nf(__int64 uçucu \*, __int64)|
|_interlockedbittestandset64_rel|imzasız char _interlockedbittestandset64_rel(__int64 uçucu, \*__int64)|

[[En tepeye dön](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici içsel](../intrinsics/compiler-intrinsics.md)\
[ARM içsel](arm-intrinsics.md)\
[ARM assembler referansı](../assembler/arm/arm-assembler-reference.md)\
[C++ dil başvurusu](../cpp/cpp-language-reference.md)
