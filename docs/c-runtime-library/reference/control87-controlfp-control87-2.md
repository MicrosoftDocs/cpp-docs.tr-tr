---
title: _control87, _controlfp, __control87_2
ms.date: 04/05/2018
apiname:
- _control87
- _controlfp
- __control87_2
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
ms.openlocfilehash: e2ebfdc80a451ebf02563f78a62dd08618f92bcd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505878"
---
# <a name="control87-controlfp-control872"></a>_control87, _controlfp, __control87_2

Kayan nokta denetim sözcüğünü ayarlar ve alır. Daha güvenli bir sürümü **_controlfp** mevcuttur; bkz [_controlfp_s](controlfp-s.md).

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

*new*<br/>
Yeni Denetim sözcüğü bit değerleri.

*Maskesi*<br/>
Ayarlanacak yeni denetim sözcüğü bitleri için maske.

*x86_cw*<br/>
X87 için kontrol sözcüğüyle doldurulur kayan nokta birimi. 0 geçirin (**NULL**) yalnızca SSE2 denetim sözcüğünü ayarlamak için.

*sse2_cw*<br/>
SSE kayan nokta birimi için Denetim sözcüğü. 0 geçirin (**NULL**) yalnızca x87 ayarlamak için Denetim sözcüğünü.

## <a name="return-value"></a>Dönüş Değeri

İçin **_control87** ve **_controlfp**, değerdeki bitler kayan nokta denetim durumunu belirtmek döndürdü. Tarafından döndürülen bitlerin tam tanımı için **_control87**, FLOAT bakın. H

İçin **__control87_2**, dönüş değeri başarılı gösterir. 1 ' dir.

## <a name="remarks"></a>Açıklamalar

**_Control87** işlevi alır ve kayan nokta denetim sözcüğünü ayarlar. Kayan nokta denetim sözcüğü programın duyarlılık, yuvarlama ve sonsuzluk modlarını platforma bağlı olarak kayan nokta matematik paketindeki değiştirmesini sağlar. Ayrıca **_control87** maskelemek veya kayan nokta özel durum maskesini kaldırmak için. Varsa değerini *maskesi* 0'a eşit olan **_control87** kayan nokta denetim sözcüğünü alır. Varsa *maskesi* olan sıfır değilse, Denetim sözcüğü için yeni bir değer ayarlanır: açık olan bitler (yani 1'e eşit olan) içinde *maskesi*, karşılık gelen bit *yeni* denetim güncelleştirmek için kullanılır Word. Diğer bir deyişle, **fpcntrl** = ((**fpcntrl** & ~*maskesi*) &#124; (*yeni* & *maskesi*)) Burada **fpcntrl** kayan nokta denetim sözcüğüdür.

> [!NOTE]
> Varsayılan olarak, çalışma zamanı kitaplıkları tüm kayan nokta özel durumları maskeleyebilir.

**_controlfp** bir platformdan bağımsız, taşınabilir sürümü **_control87**. Neredeyse aynıdır **_control87** x86 x64 ve ARM platformları üzerinde işlevi. X86, x64 veya ARM platformlarını hedefliyorsanız kullanın **_control87** veya **_controlfp**.

Arasındaki fark **_control87** ve **_controlfp** nasıl DENORMAL değerleri işledikleridir olduğu. X86 x64 ve ARM platformları için **_control87** ayarlayabilir ve DENORMAL OPERAND özel durum maskesini temizleyin. **_controlfp** DENORMAL OPERAND özel durum maskesini değiştirmez. Bu örnek farklılığı gösterir:

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call
_controlfp( _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged
```

Maske sabiti için olası değerler (*maskesi*) ve yeni denetim değerleri (*yeni*) aşağıdaki onaltılık değerler tablosunda gösterilmektedir. Aşağıda listelenen taşınabilir sabitleri kullanın (**_MCW_EM**, **_EM_INVALID**, vb.) bu işlevlere bağımsız değişkenler olarak, onaltılık değerleri sağlamak yerine açıkça.

Intel x86 türetilmiş platformlar donanımda değerleri ve daha DENORMAL giriş destekler. Korumak için bir davranıştır x86 normal dışı değerleri. ARM platformu ve SSE2 platformlarına destek x64 DENORMAL işlenenlerini etkinleştirir ve Temizlenen veya sıfır zorunda sonuçları etkinleştirin. **_Controlfp** ve **_control87** işlevleri bu davranışı değiştirmek için bir maske sağlar. Aşağıdaki örnek bu maskenin kullanımını gösterir.

```C
_controlfp(_DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp(_DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM platformlarında, **_control87** ve **_controlfp** işlevleri FPSCR yazmacına uygulayın. X64 mimarilerinde, yalnızca depolanan SSE2 denetim sözcüğünü MXCSR kayıt etkilenir. X86 platformları **_control87** ve **_controlfp** varsa x87 hem de SSE2 denetim sözcüklerini etkiler. İşlev **__control87_2** hem x87 hem de SSE2 kayan nokta birimlerinin birlikte veya ayrı ayrı denetlenmesini sağlar. Her iki birimi de etkilemek istiyorsanız, için iki tamsayı adresini geçirin **x86_cw** ve **sse2_cw**. Yalnızca tek bir birimin etkilenmesini istiyorsanız, bu parametre için bir adres geçirin ancak 0 geçirin (**NULL**) diğer. Bu parametrelerden biri için 0 geçirilirse, işlevin kayan nokta biriminde etkisi yoktur. Bu işlev, burada kod kullandığı x87 kayan nokta birimi bir parçası ve başka bir kod parçası, SSE2 kayan nokta birimini kullandığı durumlarda yararlı olabilir. Kullanırsanız **__control87_2** bir programın bir bölümünde ve kayan nokta denetim kelimeleri için farklı değerler ayarlayın ve ardından **_control87** veya **_controlfp** daha da fazla Denetim sözcüğünü işlemek **_control87** ve **_controlfp** her iki kayan nokta birimi durumunu gösterecek tek denetim kelimesini döndüremedi olabilir. Böyle bir durumda, bu işlevler kümesi **em_ambıguous** iki denetim kelimesi arasında bir tutarsızlık olduğunu belirtmek için döndürülen tamsayı değerinde bayrağı. Bu, getirilen denetim sözcüğünün her iki kayan nokta denetimi sözcüklerinin durumunu doğru şekilde temsil etmeyebileceğine, bir uyarıdır.

ARM ve x64 mimarilerinde, sonsuzluk modunun veya kayan nokta duyarlılığının değiştirilmesi desteklenmiyor. Duyarlık denetimi maskesi x64 üzerinde kullanıldığında açıklandığı gibi geçersiz parametre işleyicisi çağrılır ve platform, işlev bir sav [Parameter Validation](../../c-runtime-library/parameter-validation.md).

> [!NOTE]
> **__control87_2** ARM veya x64 desteklenmeyen mimari. Kullanırsanız **__control87_2** ve programınızı ARM veya x64 için derleme mimarileri, derleyici bir hata oluşturur.

Bu işlevler kullandığınızda yok sayılır [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) çünkü ortak dil çalışma zamanı (CLR) yalnızca varsayılan kayan nokta duyarlığını destekler.

**Onaltılık değerler**

İçin **_MCW_EM** maskesi maskeyi temizlemek, donanım özel durumuna izin veren özel durumu belirler; maskeyi ayarlamak ise özel durumu gizler. Varsa bir **_EM_UNDERFLOW** veya **_EM_OVERFLOW** gerçekleşir, sonraki kayan nokta yönergesi yürütülene kadar herhangi bir donanım özel durumu harekete geçirilir. Bir donanım özel durumu oluşturmak için hemen sonra **_EM_UNDERFLOW** veya **_EM_OVERFLOW**, çağrı **FWAIT** MASM yönergesini.

|Maskesi|Onaltılık değer|Sabit|Onaltılık değer|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (normal dışı denetim)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (özel durum maskesi kesme)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (sonsuzluk denetimi)<br /><br /> (ARM veya x64 desteklenmez] platformlar.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (yuvarlama denetimi)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (duyarlılık denetimi)<br /><br /> (ARM veya x64 platformları desteklenmez.)|0x00030000|**_PC_24** (24 bit)<br /><br /> **_PC_53** (53 BITS)<br /><br /> **_PC_64** (64 bit)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_control87**, **_controlfp**, **_control87_2**|\<float.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_cntrl87.c
// processor: x86
// This program uses __control87_2 to output the x87 control
// word, set the precision to 24 bits, and reset the status to
// the default.

#include <stdio.h>
#include <float.h>
#pragma fenv_access (on)

int main( void )
{
    double a = 0.1;
    unsigned int control_word_x87;

    // Show original x87 control word and do calculation.
    control_word_x87 = __control87_2(0, 0,
                                     &control_word_x87, 0);
    printf( "Original: 0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Set precision to 24 bits and recalculate.
    control_word_x87 = __control87_2(_PC_24, MCW_PC,
                                     &control_word_x87, 0);
    printf( "24-bit:   0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );

    // Restore default precision-control bits and recalculate.
    control_word_x87 = __control87_2( _CW_DEFAULT, MCW_PC,
                                     &control_word_x87, 0 );
    printf( "Default:  0x%.4x\n", control_word_x87 );
    printf( "%1.1f * %1.1f = %.15e\n", a, a, a * a );
}
```

```Output
Original: 0x0001
0.1 * 0.1 = 1.000000000000000e-002
24-bit:   0x0001
0.1 * 0.1 = 9.999999776482582e-003
Default:  0x0001
0.1 * 0.1 = 1.000000000000000e-002
```

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[_clear87, _clearfp](clear87-clearfp.md)<br/>
[_status87, _statusfp, _statusfp2](status87-statusfp-statusfp2.md)<br/>
[_controlfp_s](controlfp-s.md)<br/>
