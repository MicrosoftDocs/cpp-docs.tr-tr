---
description: 'Hakkında daha fazla bilgi edinin: _controlfp_s'
title: _controlfp_s
ms.date: 4/2/2020
api_name:
- _controlfp_s
- _o__controlfp_s
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- controlfp_s
- _controlfp_s
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
ms.openlocfilehash: 2fed3263374df4bdac012c6d41d89adf9232c338
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146477"
---
# <a name="_controlfp_s"></a>_controlfp_s

Kayan nokta denetim sözcüğünü alır ve ayarlar. [_Control87, _controlfp \_ _control87_2](control87-controlfp-control87-2.md) bu sürümünde [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _controlfp_s(
    unsigned int *currentControl,
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>Parametreler

*currentControl*<br/>
Geçerli denetim-sözcük bit değeri.

*newControl*<br/>
Yeni denetim-sözcük bit değerleri.

*maske*<br/>
Ayarlanacak yeni denetim-sözcük bitleri için maske.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır veya **errno** değeri hata kodu.

## <a name="remarks"></a>Açıklamalar

**_Controlfp_s** işlevi, kayan nokta denetim sözcüğünü *currentControl* içinde depolanan adrese alan ve *newControl* kullanarak ayarlayan **_control87** platformdan bağımsız ve daha güvenli bir sürümdür. Değerlerde bulunan bitler, kayan nokta denetim durumunu gösterir. Kayan nokta denetim durumu, programın platforma bağlı olarak kayan nokta matematik paketindeki duyarlık, yuvarlama ve sonsuzluk modlarını değiştirmesini sağlar. Kayan nokta özel durumlarını maskelemek veya maskesini kaldırmak için **_controlfp_s** de kullanabilirsiniz.

*Maske* değeri 0 ' a eşitse, **_controlfp_s** kayan nokta denetim sözcüğünü alır ve alınan değeri *currentControl* içinde depolar.

*Maske* sıfır değilse, denetim sözcüğü için yeni bir değer ayarlanır: *maskenin* içindeki ayarlanmış herhangi bir bit (yani 1 ' e eşit) için, denetim sözcüğünü güncelleştirmek için *Yeni* içindeki karşılık gelen bit kullanılır. Diğer bir deyişle, *fpcntrl* = ((*fpcntrl* & ~*Mask*) &#124; (*newControl*  &  *Mask*)); burada *fpcntrl* , kayan nokta denetim kelimedir. Bu senaryoda, *currentControl* değişiklik tamamlandıktan sonra değere ayarlanır; Bu, eski denetim sözcük bit değeri değildir.

> [!NOTE]
> Varsayılan olarak, çalışma zamanı kitaplıkları tüm kayan nokta özel durumlarını maskelemez.

**_controlfp_s** , Intel (x86), x64 ve ARM platformlarındaki **_control87** işleviyle neredeyse aynıdır. X86, x64 veya ARM platformlarını hedefliyorsanız **_control87** veya **_controlfp_s** kullanabilirsiniz.

**_Control87** ve **_controlfp_s** arasındaki fark, denormal değerlerini nasıl değerlendirdikleri değerlerdir. Intel (x86), x64 ve ARM platformları için **_control87** , denormal işleneni özel durum maskesini ayarlayabilir ve temizleyebilir. **_CONTROLFP_S** denormal işleneni özel durum maskesini değiştirmez. Bu örnek, farkı göstermektedir:

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call.
unsigned int current_word = 0;
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged.
```

Maske sabiti (*maske*) ve yeni denetim değerleri (*newControl*) Için olası değerler aşağıdaki onaltılık değerler tablosunda gösterilmiştir. Onaltılık değerleri açıkça sağlamak yerine, aşağıda listelenen taşınabilir sabitleri (**_MCW_EM**, **_EM_INVALID** vb.) Bu işlevlere bağımsız değişkenler olarak kullanın.

Intel (x86)-türetilmiş platformlar, donanımda DENORMAL giriş ve çıkış değerlerini destekler. X86 davranışı DENORMAL değerlerini korumektir. ARM platformu ve SSE2 desteği olan x64 platformları, DENORMAL işlenenleri ve sonuçları temizlenmeden veya sıfıra zorlanacak şekilde etkinleştirir. **_Controlfp_s**, **_controlfp** ve **_control87** işlevleri, bu davranışı değiştirmek için bir maske sağlar. Aşağıdaki örnek, Bu maskenin kullanımını gösterir:

```C
unsigned int current_word = 0;
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM platformlarında **_controlfp_s** işlevi FPSCR Register için geçerlidir. X64 mimarilerinde, yalnızca MXCSR kaydına depolanmış olan SSE2 denetim sözcüğü etkilenir. Intel (x86) platformlarında **_controlfp_s** , varsa, hem x87 hem de SSE2 için denetim sözcüklerini etkiler. İki denetim kelimeyle birbirleriyle tutarsız olması mümkündür (örneğin, önceki [__control87_2](control87-controlfp-control87-2.md)çağrısı nedeniyle); iki denetim sözcüğü arasında bir tutarsızlık varsa **_Controlfp_s** *currentcontrol* içindeki **EM_AMBIGUOUS** bayrağını ayarlar. Bu, döndürülen denetim sözcüğünün her iki kayan nokta denetim sözcüklerinin durumunu doğru şekilde temsil edemediğini belirten bir uyarıdır.

ARM ve x64 mimarilerinde sonsuzluk modunu veya kayan nokta hassasiyetini değiştirme desteklenmez. Duyarlık denetim maskesi x64 platformunda kullanılıyorsa, işlev bir onaylama işlemi başlatır ve [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır.

Maske doğru ayarlanmamışsa, bu işlev [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklanan şekilde geçersiz bir parametre özel durumu oluşturur. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **EINVAL** döndürür ve **errno** 'ı **EINVAL** olarak ayarlar.

Ortak dil çalışma zamanı (CLR) yalnızca varsayılan kayan nokta duyarlığını desteklediğinden, bu işlev derlemek için [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) kullandığınızda yok sayılır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="mask-constants-and-values"></a>Maske sabitleri ve değerleri

**_MCW_EM** maskesi için, Temizleme, donanım özel durumuna izin veren özel durumu belirler; Bu ayar özel durumu gizler. Bir **_EM_UNDERFLOW** veya **_EM_OVERFLOW** oluşursa, bir sonraki kayan nokta yönergesi yürütülene kadar herhangi bir donanım özel durumu oluşturulmaz. **_EM_UNDERFLOW** veya **_EM_OVERFLOW** sonrasında hemen bir donanım özel durumu oluşturmak için FWAIT ması yönergesini çağırın.

|Maskeleme|Onaltılık değer|Sabit|Onaltılık değer|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (denormal denetimi)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (kesme özel durum maskesi)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (sonsuz denetim)<br /><br /> (ARM veya x64 platformlarında desteklenmez.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (yuvarlama denetimi)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (duyarlık denetimi)<br /><br /> (ARM veya x64 platformlarında desteklenmez.)|0x00030000|**_PC_24** (24 bit)<br /><br /> **_PC_53** (53 bit)<br /><br /> **_PC_64** (64 bit)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_controlfp_s**|\<float.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_contrlfp_s.c
// processor: x86
// This program uses _controlfp_s to output the FP control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word;
    int err;

    // Show original FP control word and do calculation.
    err = _controlfp_s(&control_word, 0, 0);
    if ( err ) /* handle error here */;

    printf( "Original: 0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    err = _controlfp_s(&control_word, _PC_24, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "24-bit:   0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    err = _controlfp_s(&control_word, _CW_DEFAULT, MCW_PC);
    if ( err ) /* handle error here */;

    printf( "Default:  0x%.4x\n", control_word );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x9001f
0.1 * 0.1 = 1.000000000000000e-002
24-bit:   0xa001f
0.1 * 0.1 = 9.999999776482582e-003
Default:  0x9001f
0.1 * 0.1 = 1.000000000000000e-002
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_control87, _controlfp, \_ _control87_2](control87-controlfp-control87-2.md)<br/>
