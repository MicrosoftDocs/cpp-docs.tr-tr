---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 4b36cc9f5ed83b68cb15c39be91165ed7aa86d7b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348530"
---
# <a name="_controlfp_s"></a>_controlfp_s

Kayan nokta kontrol sözcüğü alır ve ayarlar. [crt](../../c-runtime-library/security-features-in-the-crt.md)Güvenlik Özellikleri açıklandığı gibi [_control87, \__controlfp _control87_2](control87-controlfp-control87-2.md) bu sürümü güvenlik geliştirmeleri vardır.

## <a name="syntax"></a>Sözdizimi

```C
errno_t _controlfp_s(
    unsigned int *currentControl,
    unsigned int newControl,
    unsigned int mask
);
```

### <a name="parameters"></a>Parametreler

*akımKontrol*<br/>
Geçerli denetim sözcük bit değeri.

*newControl*<br/>
Yeni denetim sözcük bit değerleri.

*maske*<br/>
Yeni denetim sözcük bitlerinin ayarlaması için maske.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır veya **hatalı** değer hata kodu.

## <a name="remarks"></a>Açıklamalar

**_controlfp_s** işlevi **_control87**bir platform bağımsız ve daha güvenli bir sürümüdür , *hangi currentControl* depolanan adrese kayan nokta kontrol sözcüğü alır ve *newControl*kullanarak ayarlar. Değerlerdeki bitler kayan nokta denetim durumunu gösterir. Kayan nokta denetim durumu, programın platforma bağlı olarak kayan nokta matematik paketindeki hassas, yuvarlama ve sonsuzluk modlarını değiştirmesini sağlar. Yüzen nokta özel durumlarını maskelemek veya maskelemek için **_controlfp_s** de kullanabilirsiniz.

*Maskenin* değeri 0'a eşitse, **_controlfp_s** kayan nokta denetim sözcüğüne alır ve alınan değeri *geçerliDenetim'de*depolar.

*Maske* sıfır değilse, denetim sözcüğü için yeni bir değer ayarlanır: *Maskede*ayarlanan herhangi bir bit için (yani 1'e eşittir), denetim sözcüğü güncelleştirmek için *yeni* deki karşılık gelen bit kullanılır. Başka bir deyişle, *fpcntrl* = ((*fpcntrl* & ~*maske*) &#124;*(newControl* & *mask*)) *fpcntrl* yüzen nokta kontrol kelime. Bu senaryoda, *geçerli Denetim,* değişiklik tamamlandıktan sonra değere ayarlanır; eski denetim sözcük bit değeri değildir.

> [!NOTE]
> Varsayılan olarak, çalışma zamanı kitaplıkları tüm kayan nokta özel durumlarını maskeler.

**_controlfp_s,** Intel (x86), x64 ve ARM platformlarında **_control87** fonksiyonuile hemen hemen aynıdır. X86, x64 veya ARM platformlarını hedefliyorsanız, **_control87** veya **_controlfp_s**kullanabilirsiniz.

**_control87** ve **_controlfp_s** arasındaki fark, normal olmayan değerleri nasıl ele aldıklarıdır. Intel (x86), x64 ve ARM platformları için **_control87** DENORMAL OPERAND özel durum maskesini ayarlayabilir ve temizleyebilir. **_controlfp_s** DENORMAL OPERAND özel durum maskesini değiştirmez. Bu örnek farkı gösterir:

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call.
unsigned int current_word = 0;
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged.
```

Maske sabiti *(maske)* ve yeni kontrol değerleri *(newControl)* için olası değerler aşağıdaki Hexadecimal Değerler tablosunda gösterilmiştir. Hexadecimal değerleri açıkça sağlamak yerine, bu işlevlere bağımsız değişken olarak aşağıda listelenen taşınabilir sabitleri **(_MCW_EM,** **_EM_INVALID,** vb.) kullanın.

Intel (x86) türetilmiş platformlar donanımdaki DENORMAL giriş ve çıkış değerlerini destekler. X86 davranışı DENORMAL değerleri korumaktır. ARM platformu ve SSE2 desteğine sahip x64 platformları DENORMAL operands ve sonuçları yıkamak için, ya da sıfıra zorlanır sağlar. **_controlfp_s**, **_controlfp**ve **_control87** işlevleri bu davranışı değiştirmek için bir maske sağlar. Aşağıdaki örnek, bu maskenin kullanımını gösterir:

```C
unsigned int current_word = 0;
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM **platformlarında, _controlfp_s** işlevi FPSCR kaydı için geçerlidir. X64 mimarilerde, yalnızca MXCSR kaydında depolanan SSE2 denetim sözcüğü etkilenir. Intel (x86) **platformlarında, _controlfp_s** varsa hem x87 hem de SSE2 için kontrol sözcüklerini etkiler. İki denetim sözcükünün birbiriyle tutarsız olması mümkündür (örneğin, [__control87_2](control87-controlfp-control87-2.md)için daha önceki bir çağrı nedeniyle); iki denetim sözcük arasında bir tutarsızlık varsa, **_controlfp_s** *geçerliDenetim'de* **EM_AMBIGUOUS** bayrağını ayarlar. Bu, döndürülen denetim sözcüğünün her iki kayan nokta denetim sözcüklerinin durumunu doğru bir şekilde temsil etmeyebileceğine dair bir uyarıdır.

ARM ve x64 mimarilerinde, sonsuzluk modunun veya kayan nokta hassasiyetinin değiştirilmesi desteklenmez. Hassas denetim maskesi x64 platformunda kullanılırsa, işlev bir iddia yı yükseltir ve geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır.

Maske doğru ayarlanmamışsa, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz bir parametre özel durumu oluşturur. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL** döndürür ve **EINVAL** **için errno** ayarlar.

Ortak dil çalışma süresi (CLR) yalnızca varsayılan kayan nokta hassasiyetini desteklediğinden derlemek için [/clr (Ortak Dil Çalışma Süresi Derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) kullandığınızda bu işlev yoksayılır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="mask-constants-and-values"></a>Maske sabitleri ve değerleri

**maske_MCW_EM** temizleme, donanım özel durum sağlar özel durum ayarlar; ayarı özel durumu gizler. Bir **_EM_UNDERFLOW** veya **_EM_OVERFLOW** oluşursa, bir sonraki kayan nokta yönergesi yürütülene kadar donanım özel durum atılmaz. **_EM_UNDERFLOW** veya **_EM_OVERFLOW**hemen sonra bir donanım özel durumu oluşturmak için FWAIT MASM talimatını arayın.

|Maskeleme|Hex değeri|Sabit|Hex değeri|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (Denormal kontrol)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (Kesme özel durum maskesi)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (Sonsuzluk kontrolü)<br /><br /> (ARM veya x64 platformlarında desteklenmez.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (Yuvarlama kontrolü)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (Hassas kontrol)<br /><br /> (ARM veya x64 platformlarında desteklenmez.)|0x00030000|**_PC_24** (24 bit)<br /><br /> **_PC_53** (53 bit)<br /><br /> **_PC_64** (64 bit)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_controlfp_s**|\<float.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
