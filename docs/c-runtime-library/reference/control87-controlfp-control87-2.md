---
title: _control87, _controlfp, __control87_2
ms.date: 08/29/2019
api_name:
- _control87
- _controlfp
- __control87_2
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _control87
- __control87_2
- control87
- _controlfp
- controlfp
- control87_2
- _control87_2
helpviewer_keywords:
- floating-point numbers, control word
- _control87 function
- control87 function
- controlfp function
- _controlfp function
- __control87_2 function
- floating-point functions, setting control word
- floating-point functions
- EM_AMBIGUOUS
- control87_2 function
ms.assetid: 0d09729d-d9a0-43d6-864c-43ff25e7e0c5
ms.openlocfilehash: 15700a5dabfbc3f8915e251bd8b9270f8f9c1a35
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70942911"
---
# <a name="_control87-_controlfp-__control87_2"></a>_control87, _controlfp, __control87_2

Kayan nokta denetim sözcüğünü alır ve ayarlar. Daha güvenli bir **_controlfp** sürümü kullanılabilir; bkz. [_controlfp_s](controlfp-s.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _control87(
   unsigned int new,
   unsigned int mask
);
unsigned int _controlfp(
   unsigned int new,
   unsigned int mask
);
int __control87_2(
   unsigned int new,
   unsigned int mask,
   unsigned int* x86_cw,
   unsigned int* sse2_cw
);
```

### <a name="parameters"></a>Parametreler

*Yeni*\
Yeni denetim-sözcük bit değerleri.

*maskesi*\
Ayarlanacak yeni denetim-sözcük bitleri için maske.

*x86_cw*\
X87 kayan nokta birimi için denetim sözcüğüyle doldurulmuştur. Yalnızca SSE2 denetim sözcüğünü ayarlamak için 0 (**null**) olarak geçirin.

*sse2_cw*\
SSE kayan nokta birimi için Word 'ü denetleme. Yalnızca x87 denetim sözcüğünü ayarlamak için 0 (**null**) olarak geçirin.

## <a name="return-value"></a>Dönüş değeri

**_Control87** ve **_controlfp**için, döndürülen değer içindeki bitler kayan nokta denetim durumunu gösterir. **_Control87**tarafından döndürülen bitlerin tüm tanımları için bkz. float. Olsun.

**__Control87_2**için, dönüş değeri 1 ' dir, bu da başarıyı gösterir.

## <a name="remarks"></a>Açıklamalar

**_Control87** işlevi kayan nokta denetim sözcüğünü alır ve ayarlar. Kayan nokta denetim sözcüğü, programın platforma bağlı olarak duyarlık, yuvarlama ve sonsuzluk modlarını değiştirmesini sağlar. Kayan nokta özel durumlarını maskelemek veya maskesini kaldırmak için **_control87 ' yi** de kullanabilirsiniz. *Maske* değeri 0 ' a eşitse, **_control87** kayan nokta denetim sözcüğünü alır. *Maske* sıfır değilse, denetim sözcüğü için yeni bir değer ayarlanır: *Maskede*bulunan (yani 1 ' e eşit) herhangi bir bit için, denetim sözcüğünü güncelleştirmek için *Yeni* içindeki karşılık gelen bit kullanılır. Diğer bir deyişle, **fpcntrl** = ((**fpcntrl** & ~*Mask*) &#124; (*Yeni* & *maske*)); burada **fpcntrl** , kayan nokta denetim kelimedir.

> [!NOTE]
> Varsayılan olarak, çalışma zamanı kitaplıkları tüm kayan nokta özel durumlarını maskelemez.

**_controlfp** , **_control87** ' nin, **_control87** işleviyle neredeyse aynı olan, platformdan bağımsız, taşınabilir bir sürümüdür. Kodunuz birden fazla platform hedefliyorsa, **_controlfp** veya **_controlfp_s**kullanın. **_Control87** ve **_controlfp** arasındaki fark, denormal değerlerini nasıl değerlendirdikleri değerlerdir. X86, x64, ARM ve ARM64 platformları için **_control87** , denormal OPERAND özel durum maskesini ayarlayabilir ve temizleyebilir. **_controlfp** , denormal işleneni özel durum maskesini değiştirmez. Bu örnek, farkı göstermektedir:

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call
_controlfp( _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged
```

Maske sabiti (*maske*) ve yeni denetim değerleri (*Yeni*) Için olası değerler, denetim sözcük maskeleri ve değerler tablosunda gösterilir. Onaltılık değerleri açıkça sağlamak yerine, aşağıda listelenen taşınabilir sabitleri ( **_Mcw_em**, **_em_geçersiz**ve benzeri) Bu işlevlere bağımsız değişkenler olarak kullanın.

Intel x86 ile türetilmiş platformlar, donanımda DENORMAL giriş ve çıkış değerlerini destekler. X86 davranışı DENORMAL değerlerini korumektir. ARM ve ARM64 platformları ve SSE2 desteği olan x64 platformları, DENORMAL işlenenlerini ve sonuçları temizlenmeden veya sıfıra zorlanacak şekilde etkinleştirir. **_Controlfp** ve **_control87** işlevleri, bu davranışı değiştirmek için bir maske sağlar. Aşağıdaki örnek, Bu maskenin kullanımını gösterir.

```C
_controlfp(_DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp(_DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM ve ARM64 platformlarında, **_control87** ve **_controlfp** işlevleri FPSCR Register için geçerlidir. Yalnızca MXCSR kaydına depolanan SSE2 denetim sözcüğü x64 platformlarında etkilenir. X86 platformlarında, **_control87** ve **_controlfp** , varsa, hem x87 hem de SSE2 için denetim sözcüklerini etkiler.

**__Control87_2** işlevi, hem x87 hem de SSE2 kayan nokta birimlerinin birlikte veya ayrı olarak denetlenmesini sağlar. Her iki birimi de etkilemek için, **x86_cw** ve **sse2_cw**için iki tamsayının adreslerini geçirin. Yalnızca bir birimi etkilemek istiyorsanız, bu parametre için bir adres geçirin, ancak diğeri için 0 (**null**) olarak geçirin. Bu parametrelerden biri için 0 geçirilirse, işlevin bu kayan nokta birimi üzerinde hiçbir etkisi yoktur. Kodunuzun bir kısmı x87 kayan nokta birimini kullandığında ve başka bir parça SSE2 kayan nokta birimini kullandığında yararlı olur.

Kayan nokta denetim sözcüklerinin farklı değerlerini ayarlamak için **__control87_2** kullanırsanız, **_control87** veya **_controlfp** , her iki kayan nokta biriminin durumunu temsil etmek için tek bir denetim sözcüğü döndüremeyebilir. Böyle bir durumda, bu işlevler döndürülen tamsayı değerindeki **EM_AMBIGUOUS** bayrağını iki denetim sözcüğü arasında bir tutarsızlık belirtecek şekilde ayarlar. **EM_AMBIGUOUS** bayrağı, döndürülen denetim sözcüğünün her iki kayan nokta denetim sözcüklerinin durumunu doğru şekilde temsil edemediğini belirten bir uyarıdır.

ARM, ARM64 ve x64 platformlarında Infinity modunu veya kayan nokta duyarlığını değiştirmek desteklenmez. Duyarlık denetim maskesi x64 platformunda kullanılıyorsa, işlev bir onaylama işlemi başlatır ve [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır.

> [!NOTE]
> **__control87_2** , ARM, ARM64 veya x64 platformlarında desteklenmez. **__Control87_2** KULLANıP programınızı ARM, ARM64 veya x64 platformları için derlerseniz, derleyici bir hata oluşturur.

Bu işlevler, derlemek için [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) kullandığınızda yok sayılır. Ortak dil çalışma zamanı (CLR) yalnızca varsayılan kayan nokta duyarlığını destekler.

### <a name="control-word-masks-and-values"></a>Sözcük maskelerini ve değerlerini denetleme

**_Mcw_em** maskesi için maskeyi temizlemek, donanım özel durumuna izin veren özel durumu ayarlar; Maskenin ayarlanması özel durumu gizler. **_Em_yetersizliği** veya **_Em_overflow** oluşursa, sonraki kayan nokta yönergesi yürütülene kadar donanım özel durumu oluşturulmaz. **_Em_yetersizliği** veya **_Em_overflow**sonrasında hemen bir donanım özel durumu oluşturmak için **FWAIT** ması yönergesini çağırın.

|Maskesi|Onaltılık değer|Sabit|Onaltılık değer|
|----------|---------------|--------------|---------------|
|**_Mcw_dn** (Denormal denetimi)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_Mcw_em** (Kesme özel durum maskesi)|0x0008001F|**_EM_GEÇERSIZ**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_SIFIRLAMASI BÖL**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_KLIK**<br /><br /> **_EM_INTAM**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_Mcw_ic** (Sonsuzluk denetim)<br /><br /> (ARM veya x64 platformlarında desteklenmez.)|0x00040000|**_IC_AFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_Mcw_rc** (Yuvarlama denetimi)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_Mcw_pc** (Duyarlık denetimi)<br /><br /> (ARM veya x64 platformlarında desteklenmez.)|0x00030000|**_Pc_24** (24 bit)<br /><br /> **_Pc_53** (53 bit)<br /><br /> **_Pc_64** (64 bit)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_control87**, **_controlfp**, **_control87_2**|\<float. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_cntrl87.c
// processor: x86
// compile by using: cl /W4 /arch:IA32 crt_cntrl87.c
// This program uses __control87_2 to output the x87 control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word_x87 = 0;
    int result;

    // Show original x87 control word and do calculation.
    result = __control87_2(0, 0, &control_word_x87, 0 );
    printf( "Original: 0x%.8x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    result = __control87_2(_PC_24, MCW_PC, &control_word_x87, 0 );
    printf( "24-bit:   0x%.8x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    result = __control87_2( _CW_DEFAULT, MCW_PC, &control_word_x87, 0 );
    printf( "Default:  0x%.8x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x0009001f
0.1 * 0.1 = 1.000000000000000e-02
24-bit:   0x000a001f
0.1 * 0.1 = 9.999999776482582e-03
Default:  0x0009001f
0.1 * 0.1 = 1.000000000000000e-02
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)\
[_clear87, _clearfp](clear87-clearfp.md)\
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)\
[_controlfp_s](controlfp-s.md)
