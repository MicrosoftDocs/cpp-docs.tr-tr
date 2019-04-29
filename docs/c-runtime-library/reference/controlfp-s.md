---
title: _controlfp_s
ms.date: 04/05/2018
apiname:
- _controlfp_s
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 0624cbfb4870ca87efebac01a8de682b588a4ca3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335396"
---
# <a name="controlfps"></a>_controlfp_s

Kayan nokta denetim sözcüğünü ayarlar ve alır. Bu sürümü [_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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
Geçerli denetim sözcüğü bit değeri.

*newControl*<br/>
Yeni Denetim sözcüğü bit değerleri.

*mask*<br/>
Ayarlanacak yeni denetim sözcüğü bitleri için maske.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır ya da bir **errno** değer hata kodu.

## <a name="remarks"></a>Açıklamalar

**_Controlfp_s** işlev bir platformdan bağımsız ve daha güvenli sürümü, **_control87**, içinde depolanan adresinin kayan nokta denetim sözcüğünü alır  *currentControl* ve kullanarak ayarlar *newControl*. Değerlerdeki bitler, kayan nokta denetim durumunu gösterir. Kayan nokta denetim durumu programın duyarlılık, yuvarlama ve sonsuzluk modlarını platforma bağlı olarak kayan nokta matematik paketindeki değiştirmesini sağlar. Ayrıca **_controlfp_s** maskelemek veya kayan nokta özel durum maskesini kaldırmak için.

Varsa değerini *maskesi* 0'a eşit olan **_controlfp_s** kayan nokta denetim sözcüğünü alır ve alınan değeri depolar *currentControl*.

Varsa *maskesi* olan sıfır değilse, Denetim sözcüğü için yeni bir değer ayarlanır: Tüm bit için ayarlanır (yani 1'e eşit olan) içinde *maskesi*, karşılık gelen bit *yeni* denetim sözcüğünü güncellemek için kullanılır. Diğer bir deyişle, *fpcntrl* = ((*fpcntrl* & ~*maskesi*) &#124; (*newControl* & *maskesi* )) burada *fpcntrl* kayan nokta denetim sözcüğüdür. Bu senaryoda, *currentControl* sonraki değere ayarlanmıştır değişikliğini tamamladıktan; eski denetim sözcüğü bit değeri değil.

> [!NOTE]
> Varsayılan olarak, çalışma zamanı kitaplıkları tüm kayan nokta özel durumları maskeleyebilir.

**_controlfp_s** hemen hemen aynıdır **_control87** (x86) x64 ve ARM platformları üzerinde Intel işlev. X86, x64 veya ARM platformlarını hedefliyorsanız, kullanabileceğiniz **_control87** veya **_controlfp_s**.

Arasındaki fark **_control87** ve **_controlfp_s** olan değerleri denormal nasıl işledikleridir. Intel (x86), x 64 ve ARM platformları için **_control87** ayarlayabilir ve DENORMAL OPERAND özel durum maskesini temizleyin. **_controlfp_s** DENORMAL OPERAND özel durum maskesini değiştirmez. Bu örnek farklılığı gösterir:

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call.
unsigned int current_word = 0;
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged.
```

Maske sabiti için olası değerler (*maskesi*) ve yeni denetim değerleri (*newControl*) aşağıdaki onaltılık değerler tablosunda gösterilmektedir. Aşağıda listelenen taşınabilir sabitleri kullanın (**_MCW_EM**, **_EM_INVALID**ve benzeri) bu işlevlere bağımsız değişkenler olarak, onaltılık değerleri sağlamak yerine açıkça.

Intel (x86) türetilmiş platformlar donanımda değerleri ve daha DENORMAL giriş destekler. Korumak için bir davranıştır x86 normal dışı değerleri. ARM platformu ve SSE2 platformlarına destek x64 DENORMAL işlenenlerini etkinleştirir ve Temizlenen veya sıfır zorunda sonuçları etkinleştirin. **_Controlfp_s**, **_controlfp**, ve **_control87** işlevleri bu davranışı değiştirmek için bir maske sağlar. Aşağıdaki örnek bu maskenin kullanımını gösterir:

```C
unsigned int current_word = 0;
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM platformlarında, **_controlfp_s** işlevi FPSCR yazmacına uygular. X64 mimarilerinde, yalnızca depolanan SSE2 denetim sözcüğünü MXCSR kayıt etkilenir. Intel (x86) platformlarda **_controlfp_s** x87 hem de SSE2 denetim sözcüklerini etkiler. İki denetim kelimesi birbiriyle tutarsız olması mümkündür (önceki arama nedeniyle [__control87_2](control87-controlfp-control87-2.md), örneğin); iki denetim kelimesi arasında bir tutarsızlık varsa **_controlfp_s** ayarlar **em_ambıguous** bayrağını *currentControl*. Bu, getirilen denetim sözcüğünün her iki kayan nokta denetimi sözcüklerinin durumunu doğru şekilde temsil etmeyebileceğine, bir uyarıdır.

ARM ve x64 mimarilerinde, sonsuzluk modunun veya kayan nokta duyarlılığının değiştirilmesi desteklenmiyor. Duyarlık denetimi maskesi x64 üzerinde kullanıldığında açıklandığı gibi geçersiz parametre işleyicisi çağrılır ve platform, işlev bir sav [Parameter Validation](../../c-runtime-library/parameter-validation.md).

Maske doğru ayarlanmazsa, bu işlev geçersiz parametre özel durum açıklandığı oluşturur [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevi döndürür **EINVAL** ve ayarlar **errno** için **EINVAL**.

Bu işlev kullandığınızda yok sayılır [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) çünkü ortak dil çalışma zamanı (CLR) yalnızca varsayılan kayan nokta duyarlığını destekler.

### <a name="mask-constants-and-values"></a>Maske sabitleri ve değerleri

İçin **_MCW_EM** maskeyi temizlemek, donanım özel durumuna izin veren özel durumu belirler; ayarlamak ise özel durumu gizler. Varsa bir **_EM_UNDERFLOW** veya **_EM_OVERFLOW** gerçekleşir, sonraki kayan nokta yönergesi yürütülene kadar herhangi bir donanım özel durumu harekete geçirilir. Bir donanım özel durumu oluşturmak için hemen sonra **_EM_UNDERFLOW** veya **_EM_OVERFLOW**, FWAIT MASM yönergesini çağırın.

|Maskesi|Onaltılık değer|Sabit|Onaltılık değer|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (normal dışı denetim)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (özel durum maskesi kesme)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (sonsuzluk denetimi)<br /><br /> (ARM veya x64 platformları desteklenmez.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (yuvarlama denetimi)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (duyarlılık denetimi)<br /><br /> (ARM veya x64 platformları desteklenmez.)|0x00030000|**_PC_24** (24 bit)<br /><br /> **_PC_53** (53 BITS)<br /><br /> **_PC_64** (64 bit)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_controlfp_s**|\<float.h >|

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

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_control87, _controlfp, \__control87_2](control87-controlfp-control87-2.md)<br/>
