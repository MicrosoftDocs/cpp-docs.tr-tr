---
title: ARM64 içleri
description: Microsoft C++ derleyicisi tarafından desteklenen ARM64 içlerini listesi.
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
author: sigatrev
ms.author: magardn
ms.date: 11/14/2019
ms.openlocfilehash: 30881c2b45714f91bf9035819b11ae41322b7086
ms.sourcegitcommit: e805200eaef4fe7a65a00051bbd305273af94fe7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/18/2019
ms.locfileid: "74163673"
---
# <a name="arm64-intrinsics"></a>ARM64 içleri

Microsoft C++ DERLEYICISI (MSVC), aşağıdaki Iç bilgileri ARM64 mimarisinde kullanılabilir hale getirir. ARM hakkında daha fazla bilgi için [ARM geliştirici belgeleri](https://developer.arm.com/docs) Web sitesinin mimari ve yazılım geliştirme araçları bölümlerine bakın.

## <a name="top"></a>NEON

ARM64 için NEON vektör yönerge kümesi uzantıları Tek Yönerge Birden Çok Veri (SıMD) özellikleri sağlar. Bunlar, x86 ve x64 mimari işlemcileri için ortak olan MMX ve SSE vektör yönerge kümelerinde yer alan protokollere benzer.

NEON iç bilgiler, *arm64_neon. h*üstbilgi dosyasında sağlandığı gibi desteklenir. NEON iç MSVC desteği, ARM Bilgi Merkezi Web sitesinde [ARM Neon Iç başvurusunda](https://static.docs.arm.com/ihi0073/c/IHI0073C_arm_neon_intrinsics_ref.pdf) belgelenen ARM64 derleyicisine benzer.

##  <a name="A"></a>ARM64-özel iç öğe listesi

|İşlev adı|Yönergenin|İşlev prototipi|
|-------------------|-----------------|------------------------|
|__break|BRK dili|void __break (int)|
|__addx18byte||void __addx18byte (işaretsiz Long, işaretsiz Char)|
|__addx18word||void __addx18word (işaretsiz Long, işaretsiz Short)|
|__addx18dword||void __addx18dword (işaretsiz Long, unsigned long)|
|__addx18qword||void __addx18qword (işaretsiz Long, işaretsiz __int64)|
|__cas8|KASB|imzasız __int8 __cas8 (imzasız __int8 geçici * _Target, imzasız __int8 _Comp, işaretsiz __int8 _Value)|
|__cas16|Aya|İmzasız __int16 __cas16 (İmzasız __int16 geçici * _Target, İmzasız __int16 _Comp, işaretsiz __int16 _Value)|
|__cas32|CAS|imzasız __int32 __cas32 (imzasız __int32 geçici * _Target, imzasız __int32 _Comp, işaretsiz __int32 _Value)|
|__cas64|CAS|imzasız __int64 __cas64 (imzasız __int64 geçici * _Target, imzasız __int64 _Comp, işaretsiz __int64 _Value)|
|__casa8|KASABLANB|imzasız __int8 __casa8 (imzasız __int8 geçici * _Target, imzasız __int8 _Comp, işaretsiz __int8 _Value)|
|__casa16|KASABLANH|İmzasız __int16 __casa16 (İmzasız __int16 geçici * _Target, İmzasız __int16 _Comp, işaretsiz __int16 _Value)|
|__casa32|CASA|imzasız __int32 __casa32 (imzasız __int32 geçici * _Target, imzasız __int32 _Comp, işaretsiz __int32 _Value)|
|__casa64|CASA|imzasız __int64 __casa64 (imzasız __int64 geçici * _Target, imzasız __int64 _Comp, işaretsiz __int64 _Value)|
|__casl8|CASLB|imzasız __int8 __casl8 (imzasız __int8 geçici * _Target, imzasız __int8 _Comp, işaretsiz __int8 _Value)|
|__casl16|CASLH|İmzasız __int16 __casl16 (İmzasız __int16 geçici * _Target, İmzasız __int16 _Comp, işaretsiz __int16 _Value)|
|__casl32|CASL|imzasız __int32 __casl32 (imzasız __int32 geçici * _Target, imzasız __int32 _Comp, işaretsiz __int32 _Value)|
|__casl64|CASL|imzasız __int64 __casl64 (imzasız __int64 geçici * _Target, imzasız __int64 _Comp, işaretsiz __int64 _Value)|
|__casal8|KASALB|imzasız __int8 __casal8 (imzasız __int8 geçici * _Target, imzasız __int8 _Comp, işaretsiz __int8 _Value)|
|__casal16|KASALH|İmzasız __int16 __casal16 (İmzasız __int16 geçici * _Target, İmzasız __int16 _Comp, işaretsiz __int16 _Value)|
|__casal32|CASAL|imzasız __int32 __casal32 (imzasız __int32 geçici * _Target, imzasız __int32 _Comp, işaretsiz __int32 _Value)|
|__casal64|CASAL|imzasız __int64 __casal64 (imzasız __int64 geçici * _Target, imzasız __int64 _Comp, işaretsiz __int64 _Value)|
|__crc32b|CRC32B|imzasız __int32 __crc32b (imzasız __int32, işaretsiz __int32)|
|__crc32h|CRC32H|imzasız __int32 __crc32h (imzasız __int32, işaretsiz __int32)|
|__crc32w|CRC32W|imzasız __int32 __crc32w (imzasız __int32, işaretsiz __int32)|
|__crc32d|CRC32X|imzasız __int32 __crc32d (imzasız __int32, işaretsiz __int64)|
|__crc32cb|CRC32CB|imzasız __int32 __crc32cb (imzasız __int32, işaretsiz __int32)|
|__crc32ch|CRC32CH|imzasız __int32 __crc32ch (imzasız __int32, işaretsiz __int32)|
|__crc32cw|CRC32CW|imzasız __int32 __crc32cw (imzasız __int32, işaretsiz __int32)|
|__crc32cd|CRC32CX|imzasız __int32 __crc32cd (imzasız __int32, işaretsiz __int64)|
|__dmb|DMB|void __dmb (işaretsiz int `_Type`)<br /><br /> Yönerge akışına bir bellek engeli işlemi ekler. `_Type` parametresi, engelin zorladığı kısıtlama türünü belirtir.<br /><br /> Zorlanacak kısıtlama türleri hakkında daha fazla bilgi için bkz. [bellek engeli kısıtlamaları](#BarrierRestrictions).|
|__dsb|DSB|void __dsb (işaretsiz int _Type)<br /><br /> Yönerge akışına bir bellek engeli işlemi ekler. `_Type` parametresi, engelin zorladığı kısıtlama türünü belirtir.<br /><br /> Zorlanacak kısıtlama türleri hakkında daha fazla bilgi için bkz. [bellek engeli kısıtlamaları](#BarrierRestrictions).|
|__isb|ISB|void __isb (işaretsiz int _Type)<br /><br /> Yönerge akışına bir bellek engeli işlemi ekler. `_Type` parametresi, engelin zorladığı kısıtlama türünü belirtir.<br /><br /> Zorlanacak kısıtlama türleri hakkında daha fazla bilgi için bkz. [bellek engeli kısıtlamaları](#BarrierRestrictions).|
|__getReg||imzasız __int64 __getReg (int)|
|__getRegFp||Double __getRegFp (int)|
|__getCallerReg||imzasız __int64 __getCallerReg (int)|
|__getCallerRegFp||Double __getCallerRegFp (int)|
|__hvc|HVC|işaretsiz int __hvc (işaretsiz int,...)|
|__hlt|HLT|int __hlt (işaretsiz int,...)|
|__incx18byte||void __incx18byte (imzasız Long)|
|__incx18word||void __incx18word (imzasız Long)|
|__incx18dword||void __incx18dword (imzasız Long)|
|__incx18qword||void __incx18qword (imzasız Long)|
|__iso_volatile_load16||__int16 \__iso_volatile_load16 (const volatile \__int16 \*)<br /><br /> Daha fazla bilgi için bkz. [__İso_volatile_load/Store iç](#IsoVolatileLoadStore)bilgileri.|
|__iso_volatile_load32||__int32 \__iso_volatile_load32 (const volatile \__int32 \*)<br /><br /> Daha fazla bilgi için bkz. [__İso_volatile_load/Store iç](#IsoVolatileLoadStore)bilgileri.|
|__iso_volatile_load64||__int64 \__iso_volatile_load64 (const volatile \__int64 \*)<br /><br /> Daha fazla bilgi için bkz. [__İso_volatile_load/Store iç](#IsoVolatileLoadStore)bilgileri.|
|__iso_volatile_load8||__int8 \__iso_volatile_load8 (const volatile \__int8 \*)<br /><br /> Daha fazla bilgi için bkz. [__İso_volatile_load/Store iç](#IsoVolatileLoadStore)bilgileri.|
|__iso_volatile_store16||void __iso_volatile_store16 (geçici \__int16 \*, \__int16)<br /><br /> Daha fazla bilgi için bkz. [__İso_volatile_load/Store iç](#IsoVolatileLoadStore)bilgileri.|
|__iso_volatile_store32||void __iso_volatile_store32 (geçici \__int32 \*, \__int32)<br /><br /> Daha fazla bilgi için bkz. [__İso_volatile_load/Store iç](#IsoVolatileLoadStore)bilgileri.|
|__iso_volatile_store64||void __iso_volatile_store64 (geçici \__int64 \*, \__int64)<br /><br /> Daha fazla bilgi için bkz. [__İso_volatile_load/Store iç](#IsoVolatileLoadStore)bilgileri.|
|__iso_volatile_store8||void __iso_volatile_store8 (geçici \__int8 \*, \__int8)<br /><br /> Daha fazla bilgi için bkz. [__İso_volatile_load/Store iç](#IsoVolatileLoadStore)bilgileri.|
|__ldar8|LDARB|imzasız __int8 __ldar8 (imzasız __int8 geçici * _Target)|
|__ldar16|LDARH|İmzasız __int16 __ldar16 (İmzasız __int16 geçici * _Target)|
|__ldar32|LDAR|imzasız __int32 __ldar32 (imzasız __int32 geçici * _Target)|
|__ldar64|LDAR|imzasız __int64 __ldar64 (imzasız __int64 geçici * _Target)|
|__ldapr8|LDASORUN|imzasız __int8 __ldapr8 (imzasız __int8 geçici * _Target)|
|__ldapr16|LDAPRH|İmzasız __int16 __ldapr16 (İmzasız __int16 geçici * _Target)|
|__ldapr32|LDAPR|imzasız __int32 __ldapr32 (imzasız __int32 geçici * _Target)|
|__ldapr64|LDAPR|imzasız __int64 __ldapr64 (imzasız __int64 geçici * _Target)|
|__mulh||\__int64 __mulh (\__int64, \__int64)|
|__prefetch|PRFM|void __cdecl \__prefetch (const void \*)<br /><br /> Önceden getirme işlemi, belirtilen adrese veya en yakın olan belleğe yakında erişilebilen sisteme `PLDL1KEEP` bir `PRFM` bellek ipucu sağlar. Bazı sistemler, çalışma zamanı performansını artırmak için bu bellek erişim deseninin iyileştirgetirilmesini tercih edebilir. Ancak, görünümün C++ dil noktasındaki işlevin herhangi bir observable etkisi yoktur ve hiçbir şey yapmayabilir.|
|__prefetch2|PRFM|void __cdecl \__prefetch (const void \*, uint8_t prfop)<br /><br /> Belirtilen adrese, belirtilen adrese veya hatta yakın bir süre önce erişim sağlanmış olarak sisteme sağlanan önceden getirme işlemini içeren bir `PRFM` bellek ipucu sağlar. Bazı sistemler, çalışma zamanı performansını artırmak için bu bellek erişim deseninin iyileştirgetirilmesini tercih edebilir. Ancak, görünümün C++ dil noktasındaki işlevin herhangi bir observable etkisi yoktur ve hiçbir şey yapmayabilir.|
|__readx18byte||işaretsiz karakter __readx18byte (işaretsiz Long)|
|__readx18word||işaretsiz kısa __readx18word (imzasız Long)|
|__readx18dword||işaretsiz Long __readx18dword (imzasız Long)|
|__readx18qword||imzasız __int64 __readx18qword (işaretsiz Long)|
|__setReg||void __setReg (int, imzasız __int64)|
|__setRegFp||void __setRegFp (int, Double)|
|__setCallerReg||void __setCallerReg (int, imzasız __int64)|
|__setCallerRegFp||void __setCallerRegFp (int, Double)|
|__sev|ÖNEM DERECESI|void __sev (void)|
|__static_assert||void __static_assert (int, const char \*)|
|__stlr8|STLRB|void __stlr8 (imzasız __int8 geçici * _Target, imzasız __int8 _Value)|
|__stlr16|STLRH|void __stlr16 (İmzasız __int16 geçici * _Target, İmzasız __int16 _Value)|
|__stlr32|STLR|void __stlr32 (imzasız __int32 geçici * _Target, imzasız __int32 _Value)|
|__stlr64|STLR|void __stlr64 (imzasız __int64 geçici * _Target, imzasız __int64 _Value)|
|__swp8|SWPB|imzasız __int8 __swp8 (imzasız __int8 geçici * _Target, imzasız __int8 _Value)|
|__swp16|SWPH|İmzasız __int16 __swp16 (İmzasız __int16 geçici * _Target, İmzasız __int16 _Value)|
|__swp32|SWP|imzasız __int32 __swp32 (imzasız __int32 geçici * _Target, imzasız __int32 _Value)|
|__swp64|SWP|imzasız __int64 __swp64 (imzasız __int64 geçici * _Target, imzasız __int64 _Value)|
|__swpa8|SWPAB|imzasız __int8 __swpa8 (imzasız __int8 geçici * _Target, imzasız __int8 _Value)|
|__swpa16|SWPAH|İmzasız __int16 __swpa16 (İmzasız __int16 geçici * _Target, İmzasız __int16 _Value)|
|__swpa32|SWPA dili|imzasız __int32 __swpa32 (imzasız __int32 geçici * _Target, imzasız __int32 _Value)|
|__swpa64|SWPA dili|imzasız __int64 __swpa64 (imzasız __int64 geçici * _Target, imzasız __int64 _Value)|
|__swpl8|SWPLB|imzasız __int8 __swpl8 (imzasız __int8 geçici * _Target, imzasız __int8 _Value)|
|__swpl16|SWPLH|İmzasız __int16 __swpl16 (İmzasız __int16 geçici * _Target, İmzasız __int16 _Value)|
|__swpl32|SWPL|imzasız __int32 __swpl32 (imzasız __int32 geçici * _Target, imzasız __int32 _Value)|
|__swpl64|SWPL|imzasız __int64 __swpl64 (imzasız __int64 geçici * _Target, imzasız __int64 _Value)|
|__swpal8|SWPALB|imzasız __int8 __swpal8 (imzasız __int8 geçici * _Target, imzasız __int8 _Value)|
|__swpal16|SWPALH|İmzasız __int16 __swpal16 (İmzasız __int16 geçici * _Target, İmzasız __int16 _Value)|
|__swpal32|SWPAL|imzasız __int32 __swpal32 (imzasız __int32 geçici * _Target, imzasız __int32 _Value)|
|__swpal64|SWPAL|imzasız __int64 __swpal64 (imzasız __int64 geçici * _Target, imzasız __int64 _Value)|
|__sys|DOSYASıNDA|işaretsiz int __sys (int, __int64)|
|__svc|'SI|işaretsiz int __svc (işaretsiz int,...)|
|__wfe|WFE|void __wfe (void)|
|__wfi|WFı|void __wfi (void)|
|__writex18byte||void __writex18byte (işaretsiz Long, işaretsiz Char)|
|__writex18word||void __writex18word (işaretsiz Long, işaretsiz Short)|
|__writex18dword||void __writex18dword (işaretsiz Long, unsigned long)|
|__writex18qword||void __writex18qword (işaretsiz Long, işaretsiz __int64)|
|__umulh||imzasız \__int64 __umulh (işaretsiz \__int64, imzasız \__int64)|
|_CopyDoubleFromInt64||Double _CopyDoubleFromInt64 (\__int64)|
|_CopyFloatFromInt32||kayan _CopyFloatFromInt32 (\__int32)|
|_CopyInt32FromFloat||__int32 _CopyInt32FromFloat (float)|
|_CopyInt64FromDouble||__int64 _CopyInt64FromDouble (çift)|
|_CountLeadingOnes||işaretsiz int _CountLeadingOnes (imzasız Long)|
|_CountLeadingOnes64||işaretsiz int _CountLeadingOnes64 (imzasız \__int64)|
|_CountLeadingSigns||işaretsiz int _CountLeadingSigns (uzun)|
|_CountLeadingSigns64||işaretsiz int _CountLeadingSigns64 (\__int64)|
|_CountLeadingZeros||işaretsiz int _CountLeadingZeros (imzasız Long)|
|_CountLeadingZeros64||işaretsiz int _CountLeadingZeros64 (imzasız \__int64)|
|_ReadStatusReg|MRS|\__int64 _ReadStatusReg (int)|
|_WriteStatusReg|Mrs|void _WriteStatusReg (int, \__int64)|

[[En üste dön](#top)]

###  <a name="BarrierRestrictions"></a>Bellek engeli kısıtlamaları

İç işlevler `__dmb` (veri belleği engeli), `__dsb` (veri eşitleme engeli) ve `__isb` (yönerge eşitleme engeli), paylaşım etki alanı ve işlemden etkilenen erişim türü açısından bellek engeli kısıtlamasını belirtmek için aşağıdaki önceden tanımlanmış değerleri kullanır.

|Kısıtlama değeri|Açıklama|
|-----------------------|-----------------|
|_ARM64_BARRIER_SY|Tam sistem, okuma ve yazma işlemleri.|
|_ARM64_BARRIER_ST|Tam sistem, yalnızca yazma.|
|_ARM64_BARRIER_LD|Tam sistem, salt okunurdur.|
|_ARM64_BARRIER_ISH|Dahili paylaşılabilir, okuma ve yazma işlemleri.|
|_ARM64_BARRIER_ISHST|Yalnızca iç paylaşılabilir, yalnızca yazar.|
|_ARM64_BARRIER_ISHLD|İç paylaşılabilir, salt okunurdur.|
|_ARM64_BARRIER_NSH|Paylaşılabilir olmayan, okuma ve yazma işlemleri.|
|_ARM64_BARRIER_NSHST|Yalnızca paylaşılabilir olmayan, yazma işlemleri.|
|_ARM64_BARRIER_NSHLD|Paylaşılabilir olmayan, salt okunurdur.|
|_ARM64_BARRIER_OSH|Dış paylaşılabilir, okuma ve yazma işlemleri.|
|_ARM64_BARRIER_OSHST|Yalnızca dış paylaşılabilir, yalnızca yazar.|
|_ARM64_BARRIER_OSHLD|Dış paylaşılabilir, salt okunurdur.|

`__isb` iç için geçerli olan tek kısıtlama _ARM64_BARRIER_SY; diğer tüm değerler mimari tarafından ayrılmıştır.

###  <a name="IsoVolatileLoadStore"></a>__iso_volatile_load/Store iç bilgileri

Bu iç işlevler, derleyici iyileştirmelerine tabi olmayan yükleri ve depoları açıkça gerçekleştirir.

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
Okunacak veya yazılacak bellek konumunun adresi.

*Değer*\
Belirtilen bellek konumuna yazılacak değer (yalnızca mağaza iç bilgileri).

#### <a name="return-value-load-intrinsics-only"></a>Dönüş değeri (yalnızca yük iç bilgileri)

*Konuma*göre belirtilen bellek konumunun değeri.

#### <a name="remarks"></a>Açıklamalar

Derleyici iyileştirmelerine tabi olmayan bellek erişimlerini açık bir şekilde gerçekleştirmek için `__iso_volatile_load8/16/32/64` ve `__iso_volatile_store8/16/32/64` iç bilgileri kullanabilirsiniz. Derleyici, bu işlemlerin göreli sırasını kaldıramaz, eşitleyemiyorum ya da değiştirebilir. Ancak, örtülü donanım belleği engelleri oluşturmaz. Bu nedenle, donanım, birden çok iş parçacığında observable bellek erişimlerini yine de yeniden sıralayabilir. Daha kesin olarak, bu iç bilgiler, **/volatile: ISO**altında derlenmiş şekilde aşağıdaki ifadelerle eşdeğerdir.

```cpp
int a = __iso_volatile_load32(p);    // equivalent to: int a = *(const volatile __int32*)p;
__iso_volatile_store32(p, a);        // equivalent to: *(volatile __int32*)p = a;
```

İç yapıın geçici değişkenleri karşılamak için geçici işaretçiler içerdiğine dikkat edin. Ancak, geçici işaretçileri bağımsız değişken olarak kullanma gereksinimi veya önerisi yoktur. Normal, geçici olmayan bir tür kullanılırsa, bu işlemlerin semantiği tamamen aynıdır.

**/Volatile: ISO** komut satırı bağımsız değişkeni hakkında daha fazla bilgi için bkz. [/volatile (volatile anahtar sözcük yorumu)](../build/reference/volatile-volatile-keyword-interpretation.md).

##  <a name="I"></a>Diğer mimarilerde iç bilgiler için ARM64 desteği

Aşağıdaki tabloda, ARM64 platformlarında desteklenen diğer mimarilerin iç bilgileri listelenmektedir. ARM64 üzerindeki bir iç davranışın diğer donanım mimarilerinin davranışından farklı olduğu durumlarda, ek ayrıntılar belirtilmiştir.

|İşlev adı|İşlev prototipi|
|-------------------|------------------------|
|__assume|void __assume (int)|
|__code_seg|void __code_seg (const char \*)|
|__debugbreak|void __cdecl \__debugbreak (void)|
|__fastfail|__declspec (noreturn) void \__fastfail (işaretsiz int)|
|__nop|void __nop (void)|
|__yield|void __yield (void) **Note:** ARM64 platformlarında, bu işlev yield yönergesini üretir. Bu yönerge, iş parçacığının yürütmeden geçici olarak askıya alınmış bir görevi (örneğin, bir SpinLock — programı olumsuz etkilemeden) yaptığını gösterir. Daha önce harcanabilecek yürütme döngüleri sırasında CPU 'nun diğer görevleri yürütmesine olanak sağlar.|
|_AddressOfReturnAddress|void \* _AddressOfReturnAddress (void)|
|_BitScanForward|işaretsiz karakter _BitScanForward (işaretsiz Long \* _Index, imzasız Long _Mask)|
|_BitScanForward64|işaretsiz karakter _BitScanForward64 (işaretsiz Long \* _Index, imzasız __int64 _Mask)|
|_BitScanReverse|işaretsiz karakter _BitScanReverse (işaretsiz Long \* _Index, imzasız Long _Mask)|
|_BitScanReverse64|işaretsiz karakter _BitScanReverse64 (işaretsiz Long \* _Index, imzasız __int64 _Mask)|
|_bittest|işaretsiz char _bittest (uzun const \*, Long)|
|_bittest64|işaretsiz char _bittest64 (__int64 const \*, __int64)|
|_bittestandcomplement|işaretsiz karakter _bittestandcomplement (uzun \*, uzun)|
|_bittestandcomplement64|işaretsiz char _bittestandcomplement64 (__int64 \*, __int64)|
|_bittestandreset|işaretsiz karakter _bittestandreset (uzun \*, uzun)|
|_bittestandreset64|işaretsiz char _bittestandreset64 (__int64 \*, __int64)|
|_bittestandset|işaretsiz karakter _bittestandset (uzun \*, uzun)|
|_bittestandset64|işaretsiz char _bittestandset64 (__int64 \*, __int64)|
|_byteswap_uint64|imzasız __int64 \__cdecl _byteswap_uint64 (imzasız \__int64)|
|_byteswap_ulong|imzasız Long __cdecl _byteswap_ulong (işaretsiz Long)|
|_byteswap_ushort|işaretsiz kısa __cdecl _byteswap_ushort (işaretsiz kısa)|
|_disable|void __cdecl _disable (void) **Note:** ARM64 platformlarında, bu işlev yönerge `MSR DAIFCLR,#2`oluşturur; yalnızca iç öğe olarak kullanılabilir.|
|_enable|void __cdecl _enable (void) **Note:** ARM64 platformlarında, bu işlev yönerge `MSR DAIFSET,#2`oluşturur; yalnızca iç öğe olarak kullanılabilir.|
|_lrotl|imzasız Long __cdecl _lrotl (işaretsiz Long, int)|
|_lrotr|imzasız Long __cdecl _lrotr (işaretsiz Long, int)|
|_ReadBarrier|void _ReadBarrier (void)|
|_ReadWriteBarrier|void _ReadWriteBarrier (void)|
|_ReturnAddress|void \* _ReturnAddress (void)|
|_rotl|işaretsiz int __cdecl _rotl (işaretsiz int _Value, int _Shift)|
|_rotl16|işaretsiz kısa _rotl16 (işaretsiz kısa _Value, işaretsiz char _Shift)|
|_rotl64|imzasız __int64 \__cdecl _rotl64 (imzasız \__int64 _Value, int _Shift)|
|_rotl8|işaretsiz char _rotl8 (işaretsiz char _Value, işaretsiz char _Shift)|
|_rotr|işaretsiz int __cdecl _rotr (işaretsiz int _Value, int _Shift)|
|_rotr16|işaretsiz kısa _rotr16 (işaretsiz kısa _Value, işaretsiz char _Shift)|
|_rotr64|imzasız __int64 \__cdecl _rotr64 (imzasız \__int64 _Value, int _Shift)|
|_rotr8|işaretsiz char _rotr8 (işaretsiz char _Value, işaretsiz char _Shift)|
|_setjmpex|int __cdecl _setjmpex (jmp_buf)|
|_WriteBarrier|void _WriteBarrier (void)|

[[En üste dön](#top)]

## <a name="interlocked-intrinsics"></a>Kenetlenmiş içgörüleri

Birbirine kenetlenmiş iç ağlar, atomik okuma-değiştirme-yazma işlemleri gerçekleştirmek için kullanılan bir dizi iç kümesidir. Bazıları tüm platformlarda ortaktır. Bunlar, çok sayıda bu nedenle ayrı olarak listelenirler. Tanımları çoğunlukla yedekli olduğundan, bunları genel terimlerle düşünmek daha kolay olur. Adları tam davranışları türetmek için kullanılabilir.

Aşağıdaki tabloda, bitmesiz test ile kilitlenmiş iç içgörüleri ARM64 desteği özetlenmektedir. Tablodaki her bir hücre, sıranın en solundaki işlem adı ve `_Interlocked`için sütunun en üstteki hücresinde bulunan tür adı eklenerek türetilmiş bir ada karşılık gelir. Örneğin, `Xor` satırı ve `8` sütununun kesişimindeki hücre `_InterlockedXor8` öğesine karşılık gelir ve tam olarak desteklenmektedir. Desteklenen işlevlerin çoğu bu isteğe bağlı sonekleri sunar: `_acq`, `_rel`ve `_nf`. `_acq` soneki bir "alma" anlam olduğunu gösterir ve `_rel` soneki bir "yayın" anlam olduğunu gösterir. `_nf` veya "çit yok" soneki ARM ve ARM64 için benzersizdir ve sonraki bölümde ele alınmıştır.

||8|16|32|64|128|P|
|-|-------|--------|--------|--------|-------|-------|
|Ekle|Yok.|Yok.|Tam|Tam|Yok.|Yok.|
|'|Tam|Tam|Tam|Tam|Yok.|Yok.|
|CompareExchange|Tam|Tam|Tam|Tam|Tam|Tam|
|Azaltma|Yok.|Tam|Tam|Tam|Yok.|Yok.|
|Exchange|Tam|Tam|Tam|Tam|Yok.|Tam|
|ExchangeAdd|Tam|Tam|Tam|Tam|Yok.|Yok.|
|Ilamadı|Yok.|Tam|Tam|Tam|Yok.|Yok.|
|Veya|Tam|Tam|Tam|Tam|Yok.|Yok.|
|XOR|Tam|Tam|Tam|Tam|Yok.|Yok.|

Anahtar

- **Full**: düz, `_acq`, `_rel`ve `_nf` formları destekler.

- **Hiçbiri**: desteklenmiyor

###  <a name="nf_suffix"></a>_nf (çit yok) soneki

`_nf` veya "sınır yok" soneki, işlemin her türlü bellek engeli olarak davranmadığını belirtir (düz, `_acq`ve `_rel`), hepsi bir tür engel olarak davranır. `_nf` formlarının olası bir kullanımı, aynı anda birden çok iş parçacığı tarafından güncellenen bir istatistik sayacı sürdürmek, ancak birden çok iş parçacığı yürütülürken değeri başka bir şekilde kullanılmadığında oluşur.

### <a name="list-of-interlocked-intrinsics"></a>Kenetlenmiş içgörüleri listesi

|İşlev adı|İşlev prototipi|
|-------------------|------------------------|
|_InterlockedAdd|uzun _InterlockedAdd (uzun _volatile \*, uzun)|
|_InterlockedAdd64|__int64 _InterlockedAdd64 (\__int64 geçici \*, \__int64)|
|_InterlockedAdd64_acq|__int64 _InterlockedAdd64_acq (\__int64 geçici \*, \__int64)|
|_InterlockedAdd64_nf|__int64 _InterlockedAdd64_nf (\__int64 geçici \*, \__int64)|
|_InterlockedAdd64_rel|__int64 _InterlockedAdd64_rel (\__int64 geçici \*, \__int64)|
|_InterlockedAdd_acq|uzun _InterlockedAdd_acq (uzun geçici \*, uzun)|
|_InterlockedAdd_nf|uzun _InterlockedAdd_nf (uzun geçici \*, uzun)|
|_InterlockedAdd_rel|uzun _InterlockedAdd_rel (uzun geçici \*, uzun)|
|_InterlockedAnd|uzun _InterlockedAnd (uzun geçici \*, uzun)|
|_InterlockedAnd16|kısa _InterlockedAnd16 (kısa geçici \*, kısa)|
|_InterlockedAnd16_acq|kısa _InterlockedAnd16_acq (kısa geçici \*, kısa)|
|_InterlockedAnd16_nf|kısa _InterlockedAnd16_nf (kısa geçici \*, kısa)|
|_InterlockedAnd16_rel|kısa _InterlockedAnd16_rel (kısa geçici \*, kısa)|
|_InterlockedAnd64|__int64 _InterlockedAnd64 (\__int64 geçici \*, \__int64)|
|_InterlockedAnd64_acq|__int64 _InterlockedAnd64_acq (\__int64 geçici \*, \__int64)|
|_InterlockedAnd64_nf|__int64 _InterlockedAnd64_nf (\__int64 geçici \*, \__int64)|
|_InterlockedAnd64_rel|__int64 _InterlockedAnd64_rel (\__int64 geçici \*, \__int64)|
|_InterlockedAnd8|Char _InterlockedAnd8 (Char volatile \*, Char)|
|_InterlockedAnd8_acq|Char _InterlockedAnd8_acq (Char volatile \*, Char)|
|_InterlockedAnd8_nf|Char _InterlockedAnd8_nf (Char volatile \*, Char)|
|_InterlockedAnd8_rel|Char _InterlockedAnd8_rel (Char volatile \*, Char)|
|_InterlockedAnd_acq|uzun _InterlockedAnd_acq (uzun geçici \*, uzun)|
|_InterlockedAnd_nf|uzun _InterlockedAnd_nf (uzun geçici \*, uzun)|
|_InterlockedAnd_rel|uzun _InterlockedAnd_rel (uzun geçici \*, uzun)|
|_InterlockedCompareExchange|uzun __cdecl _InterlockedCompareExchange (uzun geçici \*, uzun, uzun)|
|_InterlockedCompareExchange_acq|uzun _InterlockedCompareExchange_acq (uzun geçici \*, uzun, uzun)|
|_InterlockedCompareExchange_nf|uzun _InterlockedCompareExchange_nf (uzun geçici \*, uzun, uzun)|
|_InterlockedCompareExchange_rel|uzun _InterlockedCompareExchange_rel (uzun geçici \*, uzun, uzun)|
|_InterlockedCompareExchange16|kısa _InterlockedCompareExchange16 (kısa geçici \*, kısa, kısa)|
|_InterlockedCompareExchange16_acq|kısa _InterlockedCompareExchange16_acq (kısa geçici \*, kısa, kısa)|
|_InterlockedCompareExchange16_nf|kısa _InterlockedCompareExchange16_nf (kısa geçici \*, kısa, kısa)|
|_InterlockedCompareExchange16_rel|kısa _InterlockedCompareExchange16_rel (kısa geçici \*, kısa, kısa)|
|_InterlockedCompareExchange64|__int64 _InterlockedCompareExchange64 (\__int64 geçici \*, \__int64, \__int64)|
|_InterlockedCompareExchange64_acq|__int64 _InterlockedCompareExchange64_acq (\__int64 geçici \*, \__int64, \__int64)|
|_InterlockedCompareExchange64_nf|__int64 _InterlockedCompareExchange64_nf (\__int64 geçici \*, \__int64, \__int64)|
|_InterlockedCompareExchange64_rel|__int64 _InterlockedCompareExchange64_rel (\__int64 geçici \*, \__int64, \__int64)|
|_InterlockedCompareExchange8|Char _InterlockedCompareExchange8 (Char volatile \*, Char, Char)|
|_InterlockedCompareExchange8_acq|Char _InterlockedCompareExchange8_acq (Char volatile \*, Char, Char)|
|_InterlockedCompareExchange8_nf|Char _InterlockedCompareExchange8_nf (Char volatile \*, Char, Char)|
|_InterlockedCompareExchange8_rel|Char _InterlockedCompareExchange8_rel (Char volatile \*, Char, Char)|
|_InterlockedCompareExchangePointer|void \* _InterlockedCompareExchangePointer (void \* geçici \*, void \*, void \*)|
|_InterlockedCompareExchangePointer_acq|void \* _InterlockedCompareExchangePointer_acq (void \* geçici \*, void \*, void \*)|
|_InterlockedCompareExchangePointer_nf|void \* _InterlockedCompareExchangePointer_nf (void \* geçici \*, void \*, void \*)|
|_InterlockedCompareExchangePointer_rel|void \* _InterlockedCompareExchangePointer_rel (void \* geçici \*, void \*, void \*)|
|_InterlockedCompareExchange128|işaretsiz karakter _InterlockedCompareExchange128 (\__int64 geçici \* _Destination, \__int64 _ExchangeHigh, \__int64 _ExchangeLow, \__int64 \* _ComparandResult)|
|_InterlockedCompareExchange128_acq|işaretsiz karakter _InterlockedCompareExchange128_acq (\__int64 geçici \* _Destination, \__int64 _ExchangeHigh, \__int64 _ExchangeLow, \__int64 \* _ComparandResult)|
|_InterlockedCompareExchange128_nf|işaretsiz karakter _InterlockedCompareExchange128_nf (\__int64 geçici \* _Destination, \__int64 _ExchangeHigh, \__int64 _ExchangeLow, \__int64 \* _ComparandResult)|
|_InterlockedCompareExchange128_rel|işaretsiz karakter _InterlockedCompareExchange128_rel (\__int64 geçici \* _Destination, \__int64 _ExchangeHigh, \__int64 _ExchangeLow, \__int64 \* _ComparandResult)|
|_InterlockedDecrement|uzun __cdecl _InterlockedDecrement (uzun geçici \*)|
|_InterlockedDecrement16|Short _InterlockedDecrement16 (kısa geçici \*)|
|_InterlockedDecrement16_acq|Short _InterlockedDecrement16_acq (kısa geçici \*)|
|_InterlockedDecrement16_nf|Short _InterlockedDecrement16_nf (kısa geçici \*)|
|_InterlockedDecrement16_rel|Short _InterlockedDecrement16_rel (kısa geçici \*)|
|_InterlockedDecrement64|__int64 _InterlockedDecrement64 (\__int64 geçici \*)|
|_InterlockedDecrement64_acq|__int64 _InterlockedDecrement64_acq (\__int64 geçici \*)|
|_InterlockedDecrement64_nf|__int64 _InterlockedDecrement64_nf (\__int64 geçici \*)|
|_InterlockedDecrement64_rel|__int64 _InterlockedDecrement64_rel (\__int64 geçici \*)|
|_InterlockedDecrement_acq|uzun _InterlockedDecrement_acq (uzun geçici \*)|
|_InterlockedDecrement_nf|uzun _InterlockedDecrement_nf (uzun geçici \*)|
|_InterlockedDecrement_rel|uzun _InterlockedDecrement_rel (uzun geçici \*)|
|_InterlockedExchange|uzun __cdecl _InterlockedExchange (uzun geçici \* _Target, uzun)|
|_InterlockedExchange_acq|uzun _InterlockedExchange_acq (uzun geçici \* _Target, uzun)|
|_InterlockedExchange_nf|uzun _InterlockedExchange_nf (uzun geçici \* _Target, uzun)|
|_InterlockedExchange_rel|uzun _InterlockedExchange_rel (uzun geçici \* _Target, uzun)|
|_InterlockedExchange16|kısa _InterlockedExchange16 (kısa geçici \* _Target, kısa)|
|_InterlockedExchange16_acq|kısa _InterlockedExchange16_acq (kısa geçici \* _Target, kısa)|
|_InterlockedExchange16_nf|kısa _InterlockedExchange16_nf (kısa geçici \* _Target, kısa)|
|_InterlockedExchange16_rel|kısa _InterlockedExchange16_rel (kısa geçici \* _Target, kısa)|
|_InterlockedExchange64|__int64 _InterlockedExchange64 (\__int64 geçici \* _Target, \__int64)|
|_InterlockedExchange64_acq|__int64 _InterlockedExchange64_acq (\__int64 geçici \* _Target, \__int64)|
|_InterlockedExchange64_nf|__int64 _InterlockedExchange64_nf (\__int64 geçici \* _Target, \__int64)|
|_InterlockedExchange64_rel|__int64 _InterlockedExchange64_rel (\__int64 geçici \* _Target, \__int64)|
|_InterlockedExchange8|Char _InterlockedExchange8 (Char volatile \* _Target, Char)|
|_InterlockedExchange8_acq|Char _InterlockedExchange8_acq (Char volatile \* _Target, Char)|
|_InterlockedExchange8_nf|Char _InterlockedExchange8_nf (Char volatile \* _Target, Char)|
|_InterlockedExchange8_rel|Char _InterlockedExchange8_rel (Char volatile \* _Target, Char)|
|_InterlockedExchangeAdd|uzun __cdecl _InterlockedExchangeAdd (uzun geçici \*, uzun)|
|_InterlockedExchangeAdd16|kısa _InterlockedExchangeAdd16 (kısa geçici \*, kısa)|
|_InterlockedExchangeAdd16_acq|kısa _InterlockedExchangeAdd16_acq (kısa geçici \*, kısa)|
|_InterlockedExchangeAdd16_nf|kısa _InterlockedExchangeAdd16_nf (kısa geçici \*, kısa)|
|_InterlockedExchangeAdd16_rel|kısa _InterlockedExchangeAdd16_rel (kısa geçici \*, kısa)|
|_InterlockedExchangeAdd64|__int64 _InterlockedExchangeAdd64 (\__int64 geçici \*, \__int64)|
|_InterlockedExchangeAdd64_acq|__int64 _InterlockedExchangeAdd64_acq (\__int64 geçici \*, \__int64)|
|_InterlockedExchangeAdd64_nf|__int64 _InterlockedExchangeAdd64_nf (\__int64 geçici \*, \__int64)|
|_InterlockedExchangeAdd64_rel|__int64 _InterlockedExchangeAdd64_rel (\__int64 geçici \*, \__int64)|
|_InterlockedExchangeAdd8|Char _InterlockedExchangeAdd8 (Char volatile \*, Char)|
|_InterlockedExchangeAdd8_acq|Char _InterlockedExchangeAdd8_acq (Char volatile \*, Char)|
|_InterlockedExchangeAdd8_nf|Char _InterlockedExchangeAdd8_nf (Char volatile \*, Char)|
|_InterlockedExchangeAdd8_rel|Char _InterlockedExchangeAdd8_rel (Char volatile \*, Char)|
|_InterlockedExchangeAdd_acq|uzun _InterlockedExchangeAdd_acq (uzun geçici \*, uzun)|
|_InterlockedExchangeAdd_nf|uzun _InterlockedExchangeAdd_nf (uzun geçici \*, uzun)|
|_InterlockedExchangeAdd_rel|uzun _InterlockedExchangeAdd_rel (uzun geçici \*, uzun)|
|_InterlockedExchangePointer|void \* _InterlockedExchangePointer (void \* geçici \* _Target, void \*)|
|_InterlockedExchangePointer_acq|void \* _InterlockedExchangePointer_acq (void \* geçici \* _Target, void \*)|
|_InterlockedExchangePointer_nf|void \* _InterlockedExchangePointer_nf (void \* geçici \* _Target, void \*)|
|_InterlockedExchangePointer_rel|void \* _InterlockedExchangePointer_rel (void \* geçici \* _Target, void \*)|
|_InterlockedIncrement|uzun __cdecl _InterlockedIncrement (uzun geçici \*)|
|_InterlockedIncrement16|Short _InterlockedIncrement16 (kısa geçici \*)|
|_InterlockedIncrement16_acq|Short _InterlockedIncrement16_acq (kısa geçici \*)|
|_InterlockedIncrement16_nf|Short _InterlockedIncrement16_nf (kısa geçici \*)|
|_InterlockedIncrement16_rel|Short _InterlockedIncrement16_rel (kısa geçici \*)|
|_InterlockedIncrement64|__int64 _InterlockedIncrement64 (\__int64 geçici \*)|
|_InterlockedIncrement64_acq|__int64 _InterlockedIncrement64_acq (\__int64 geçici \*)|
|_InterlockedIncrement64_nf|__int64 _InterlockedIncrement64_nf (\__int64 geçici \*)|
|_InterlockedIncrement64_rel|__int64 _InterlockedIncrement64_rel (\__int64 geçici \*)|
|_InterlockedIncrement_acq|uzun _InterlockedIncrement_acq (uzun geçici \*)|
|_InterlockedIncrement_nf|uzun _InterlockedIncrement_nf (uzun geçici \*)|
|_InterlockedIncrement_rel|uzun _InterlockedIncrement_rel (uzun geçici \*)|
|_InterlockedOr|uzun _InterlockedOr (uzun geçici \*, uzun)|
|_InterlockedOr16|kısa _InterlockedOr16 (kısa geçici \*, kısa)|
|_InterlockedOr16_acq|kısa _InterlockedOr16_acq (kısa geçici \*, kısa)|
|_InterlockedOr16_nf|kısa _InterlockedOr16_nf (kısa geçici \*, kısa)|
|_InterlockedOr16_rel|kısa _InterlockedOr16_rel (kısa geçici \*, kısa)|
|_InterlockedOr64|__int64 _InterlockedOr64 (\__int64 geçici \*, \__int64)|
|_InterlockedOr64_acq|__int64 _InterlockedOr64_acq (\__int64 geçici \*, \__int64)|
|_InterlockedOr64_nf|__int64 _InterlockedOr64_nf (\__int64 geçici \*, \__int64)|
|_InterlockedOr64_rel|__int64 _InterlockedOr64_rel (\__int64 geçici \*, \__int64)|
|_InterlockedOr8|Char _InterlockedOr8 (Char volatile \*, Char)|
|_InterlockedOr8_acq|Char _InterlockedOr8_acq (Char volatile \*, Char)|
|_InterlockedOr8_nf|Char _InterlockedOr8_nf (Char volatile \*, Char)|
|_InterlockedOr8_rel|Char _InterlockedOr8_rel (Char volatile \*, Char)|
|_InterlockedOr_acq|uzun _InterlockedOr_acq (uzun geçici \*, uzun)|
|_InterlockedOr_nf|uzun _InterlockedOr_nf (uzun geçici \*, uzun)|
|_InterlockedOr_rel|uzun _InterlockedOr_rel (uzun geçici \*, uzun)|
|_InterlockedXor|uzun _InterlockedXor (uzun geçici \*, uzun)|
|_InterlockedXor16|kısa _InterlockedXor16 (kısa geçici \*, kısa)|
|_InterlockedXor16_acq|kısa _InterlockedXor16_acq (kısa geçici \*, kısa)|
|_InterlockedXor16_nf|kısa _InterlockedXor16_nf (kısa geçici \*, kısa)|
|_InterlockedXor16_rel|kısa _InterlockedXor16_rel (kısa geçici \*, kısa)|
|_InterlockedXor64|__int64 _InterlockedXor64 (\__int64 geçici \*, \__int64)|
|_InterlockedXor64_acq|__int64 _InterlockedXor64_acq (\__int64 geçici \*, \__int64)|
|_InterlockedXor64_nf|__int64 _InterlockedXor64_nf (\__int64 geçici \*, \__int64)|
|_InterlockedXor64_rel|__int64 _InterlockedXor64_rel (\__int64 geçici \*, \__int64)|
|_InterlockedXor8|Char _InterlockedXor8 (Char volatile \*, Char)|
|_InterlockedXor8_acq|Char _InterlockedXor8_acq (Char volatile \*, Char)|
|_InterlockedXor8_nf|Char _InterlockedXor8_nf (Char volatile \*, Char)|
|_InterlockedXor8_rel|Char _InterlockedXor8_rel (Char volatile \*, Char)|
|_InterlockedXor_acq|uzun _InterlockedXor_acq (uzun geçici \*, uzun)|
|_InterlockedXor_nf|uzun _InterlockedXor_nf (uzun geçici \*, uzun)|
|_InterlockedXor_rel|uzun _InterlockedXor_rel (uzun geçici \*, uzun)|

[[En üste dön](#top)]

### <a name="_interlockedbittest-intrinsics"></a>_interlockedbittest iç bilgiler

Düz olarak kilitlenen bit testi iç bilgileri tüm platformlarda ortaktır. ARM64, bu makalenin önceki kısımlarında bulunan [_nf (sınır yok) soneki](#nf_suffix) bölümünde açıklandığı gibi, yalnızca bir işlemin bariyer semantiğini değiştiren `_acq`, `_rel`ve `_nf` çeşitleri ekler.

|İşlev adı|İşlev prototipi|
|-------------------|------------------------|
|_interlockedbittestandreset|işaretsiz char _interlockedbittestandreset (uzun geçici \*, uzun)|
|_interlockedbittestandreset_acq|işaretsiz char _interlockedbittestandreset_acq (uzun geçici \*, uzun)|
|_interlockedbittestandreset_nf|işaretsiz char _interlockedbittestandreset_nf (uzun geçici \*, uzun)|
|_interlockedbittestandreset_rel|işaretsiz char _interlockedbittestandreset_rel (uzun geçici \*, uzun)|
|_interlockedbittestandreset64|işaretsiz karakter _interlockedbittestandreset64 (__int64 volatile \*, __int64)|
|_interlockedbittestandreset64_acq|işaretsiz karakter _interlockedbittestandreset64_acq (__int64 volatile \*, __int64)|
|_interlockedbittestandreset64_nf|işaretsiz karakter _interlockedbittestandreset64_nf (__int64 volatile \*, __int64)|
|_interlockedbittestandreset64_rel|işaretsiz karakter _interlockedbittestandreset64_rel (__int64 volatile \*, __int64)|
|_interlockedbittestandset|işaretsiz char _interlockedbittestandset (uzun geçici \*, uzun)|
|_interlockedbittestandset_acq|işaretsiz char _interlockedbittestandset_acq (uzun geçici \*, uzun)|
|_interlockedbittestandset_nf|işaretsiz char _interlockedbittestandset_nf (uzun geçici \*, uzun)|
|_interlockedbittestandset_rel|işaretsiz char _interlockedbittestandset_rel (uzun geçici \*, uzun)|
|_interlockedbittestandset64|işaretsiz karakter _interlockedbittestandset64 (__int64 volatile \*, __int64)|
|_interlockedbittestandset64_acq|işaretsiz karakter _interlockedbittestandset64_acq (__int64 volatile \*, __int64)|
|_interlockedbittestandset64_nf|işaretsiz karakter _interlockedbittestandset64_nf (__int64 volatile \*, __int64)|
|_interlockedbittestandset64_rel|işaretsiz karakter _interlockedbittestandset64_rel (__int64 volatile \*, __int64)|

[[En üste dön](#top)]

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç](../intrinsics/compiler-intrinsics.md) bilgileri\
[ARM iç](arm-intrinsics.md) bilgileri\
[ARM Assembler başvurusu](../assembler/arm/arm-assembler-reference.md)\
[C++dil başvurusu](../cpp/cpp-language-reference.md)
