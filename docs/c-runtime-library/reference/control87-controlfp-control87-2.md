---
title: _control87, _controlfp, __control87_2 | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 098e5760718e4e2d2a9063700b09d0381e76df1f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="control87-controlfp-control872"></a>_control87, _controlfp, __control87_2

Alır ve kayan nokta denetim sözcüğü ayarlar. Daha güvenli bir sürümünü **_controlfp** kullanılabilir; bkz [_controlfp_s](controlfp-s.md).

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
Ayarlanacak yeni denetim sözcüğü bit maskesi.

*x86_cw*<br/>
Denetim sözcüğü x87 için oturum doldurulmuş kayan nokta birim. 0 olarak geçirin (**NULL**) yalnızca SSE2 denetim sözcüğü ayarlamak için.

*sse2_cw*<br/>
Denetim sözcüğünü SSE kayan nokta birimi. 0 olarak geçirin (**NULL**) yalnızca x87 ayarlamak için Denetim word.

## <a name="return-value"></a>Dönüş Değeri

İçin **_control87** ve **_controlfp**, değer bitleri döndürdü kayan nokta denetim durumu olduğunu gösterir. Tarafından döndürülen bitleri eksiksiz bir açıklaması için **_control87**, FLOAT bakın. H.

İçin **__control87_2**, dönüş değeri başarı gösteren 1 ' dir.

## <a name="remarks"></a>Açıklamalar

**_Control87** işlevi alır ve kayan nokta denetim sözcüğü ayarlar. Kayan nokta denetim sözcüğü duyarlık, yuvarlama ve platforma bağlı olarak kayan nokta Matematiği paketindeki sonsuz modlarını değiştirmek programın sağlar. Aynı zamanda **_control87** maske veya kayan nokta özel durumlar maskesini kaldırın. Varsa değeri *maskesi* 0'a eşit olduğu **_control87** kayan nokta denetim sözcüğü alır. Varsa *maskesi* olan denetim sözcüğü için yeni bir değer sıfır olmayan, ayarlanır: açık olan tüm bit için (diğer bir deyişle, 1'e eşit) içinde *maskesi*, karşılık gelen bit *yeni* denetimi güncelleştirmek için kullanılır Word. Diğer bir deyişle, **fpcntrl** = ((**fpcntrl** & ~*maskesi*) &#124; (*yeni* & *maskesi*)) Burada **fpcntrl** kayan nokta denetim sözcüğüdür.

> [!NOTE]
> Varsayılan olarak, çalışma zamanı kitaplıkları tüm kayan nokta özel durumları maske.

**_controlfp** bir platformdan bağımsız, taşınabilir sürümü **_control87**. Neredeyse aynıdır **_control87** x86, x64 ve ARM platformlarda işlevi. X86, x64 veya ARM platformları hedefleme kullanırsanız **_control87** veya **_controlfp**.

Arasındaki farkı **_control87** ve **_controlfp** bunlar DENORMAL değerleri nasıl işler içinde değil. X86, x64 ve ARM platformları **_control87** ayarlayabilir ve normal dışı işlenen özel durum maskesi temizleyin. **_controlfp** normal dışı işlenen özel durum maskesi değiştirmez. Bu örnekte fark gösterilmektedir:

```C
_control87( _EM_INVALID, _MCW_EM );
// DENORMAL is unmasked by this call
_controlfp( _EM_INVALID, _MCW_EM );
// DENORMAL exception mask remains unchanged
```

Maske sabiti için olası değerler (*maskesi*) ve yeni denetim değerleri (*yeni*) aşağıdaki onaltılık değerler tabloda gösterilmiştir. Aşağıda listelenen taşınabilir sabitleri kullanın (**_MCW_EM**, **_EM_INVALID**, vb.) bu işlevler için bağımsız değişken olarak onaltılık sağladığını yerine değerleri açıkça.

Intel x86 türetilmiş platformları DENORMAL giriş desteği ve donanım değerlerde çıktı. Korumak için davranıştır x86 normal dışı değerler. ARM platform ve SSE2 sahip platformlarını destekleyen x64 DENORMAL işlenenler ve Temizlenen veya sıfır zorunda sonuçları etkinleştirin. **_Controlfp** ve **_control87** işlevleri sağlayan bu davranışı değiştirmek için maske. Aşağıdaki örnekte bu maskesi kullanımını göstermektedir.

```C
_controlfp(_DN_SAVE, _MCW_DN);
// Denormal values preserved on ARM platforms and on x64 processors with
// SSE2 support. NOP on x86 platforms.
_controlfp(_DN_FLUSH, _MCW_DN);
// Denormal values flushed to zero by hardware on ARM platforms
// and x64 processors with SSE2 support. Ignored on other x86 platforms.
```

ARM platformlarda **_control87** ve **_controlfp** işlevleri FPSCR kasa uygulamak. X64 üzerinde mimariler, depolanan SSE2 denetim sözcüğü MXCSR kayıt etkilenir. X86 üzerinde platformları, **_control87** ve **_controlfp** varsa x87 ve SSE2 denetim sözcükleri etkiler. İşlev **__control87_2** x87 ve SSE2 kayan nokta birimleri birlikte veya ayrı olarak denetlenmesini sağlar. Her iki birimleri etkileyen istiyorsanız, iki tamsayılara adreslerini geçirin **x86_cw** ve **sse2_cw**. Yalnızca tek bir birim etkileyen istiyorsanız, bu parametre için bir adres geçirmek ancak diğer için 0 (boş) geçirin. 0 Bu parametrelerden birini geçirilirse işlevi kayan nokta o birimi üzerinde etkisi yoktur. Bu işlev SSE2 kayan nokta birim kod kullanır x87 kayan nokta birimi bir parçası ve başka bir kod parçası, burada kullanır durumlarda yararlı olabilir. Kullanırsanız **__control87_2** bir programı'nın bir parçası olarak ayarlamak için kayan nokta denetim sözcükleri farklı değerler ve ardından **_control87** veya **_controlfp** daha da fazla Denetim sözcüğünü ardından işlemek **_control87** ve **_controlfp** hem kayan nokta birimleri durumunu göstermek için bir tek denetim sözcüğü döndüremedi olabilir. Böyle bir durumda, bu işlevler kümesi **EM_AMBIGUOUS** iki denetim sözcükler arasında bir tutarsızlık olduğunu belirtmek için döndürülen tamsayı değeri bayrağı. Bu, döndürülen denetim sözcüğü hem kayan nokta denetim sözcükler durumunu doğru şekilde temsil edemeyebilir değil, bir uyarıdır.

ARM ve x64 sonsuz modu veya kayan nokta duyarlık değiştirme mimarileri desteklenmiyor. Duyarlık denetimi maske üzerinde x64 kullanılıp kullanılmadığını platform, işlevi bir onaylama işlemi başlatır ve açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).

> [!NOTE]
> **__control87_2** ARM veya x64 desteklenmiyor mimarileri. Kullanırsanız **__control87_2** ve ARM veya x64 programınızı derleme mimarileri derleyici hata oluşturur.

Kullandığınızda bu işlevler göz ardı edilir [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ortak dil çalışma zamanı (CLR) yalnızca varsayılan kayan nokta duyarlık desteklediğinden derlemek için.

**Onaltılık değerler**

İçin **_MCW_EM** maskesi temizleme maskesi ayarlar donanım özel durumu verir özel durum; maskesini ayarlarken, özel durum gizler. Varsa bir **_EM_UNDERFLOW** veya **_EM_OVERFLOW** oluşur, sonraki kayan nokta yönergesi yürütülene dek hiçbir donanım özel durumu oluşur. Donanım özel durum oluşturmak için hemen sonra **_EM_UNDERFLOW** veya **_EM_OVERFLOW**, çağrı **FWAIT** MASM yönerge.

|Maskesi|Onaltılık değer|Sabit|Onaltılık değer|
|----------|---------------|--------------|---------------|
|**_MCW_DN** (Denetim normal dışı)|0x03000000|**_DN_SAVE**<br /><br /> **_DN_FLUSH**|0x00000000<br /><br /> 0x01000000|
|**_MCW_EM** (kesme özel durum maskesi)|0x0008001F|**_EM_INVALID**<br /><br /> **_EM_DENORMAL**<br /><br /> **_EM_ZERODIVIDE**<br /><br /> **_EM_OVERFLOW**<br /><br /> **_EM_UNDERFLOW**<br /><br /> **_EM_INEXACT**|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|
|**_MCW_IC** (sonsuz denetimi)<br /><br /> (ARM veya x64 desteklenmez] platformları.)|0x00040000|**_IC_AFFINE**<br /><br /> **_IC_PROJECTIVE**|0x00040000<br /><br /> 0x00000000|
|**_MCW_RC** (Denetim yuvarlama)|0x00000300|**_RC_CHOP**<br /><br /> **_RC_UP**<br /><br /> **_RC_DOWN**<br /><br /> **_RC_NEAR**|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|
|**_MCW_PC** (duyarlık denetimi)<br /><br /> (ARM veya x64 platformları desteklenmez.)|0x00030000|**_PC_24** (24 bit)<br /><br /> **_PC_53** (53 BITS)<br /><br /> **_PC_64** (64 bit)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_control87**, **_controlfp**, **_control87_2**|\<float.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
