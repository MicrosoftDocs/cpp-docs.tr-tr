---
title: _controlfp_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _controlfp_s
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
dev_langs: C++
helpviewer_keywords:
- floating-point numbers, control word
- controlfp_s function
- floating-point functions, setting control word
- EM_AMBIGUOUS
- _controlfp_s function
ms.assetid: a51fc3f6-ab13-41f0-b227-6bf02d98e987
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e5f1f82f5d7ae8899d1045280f24c7af405c64b6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="controlfps"></a>_controlfp_s
Alır ve kayan nokta denetim sözcüğü ayarlar. Bu sürümü [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _controlfp_s(  
    unsigned int *currentControl,  
    unsigned int newControl,  
    unsigned int mask  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `currentControl`  
 Geçerli denetim sözcüğü bit değeri.  
  
 `newControl`  
 Yeni Denetim sözcüğü bit değerleri.  
  
 `mask`  
 Ayarlanacak yeni denetim sözcüğü bit maskesi.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa veya bir sıfır `errno` değer hata kodu.  
  
## <a name="remarks"></a>Açıklamalar  
 `_controlfp_s` İşlevidir platformdan bağımsız ve daha güvenli bir sürümü `_control87`, veri depolanan adresine kayan nokta denetim sözcüğü alır `currentControl` ve kullanarak ayarlar `newControl`. Değerleri bitleri kayan nokta denetim durumu gösterir. Kayan nokta denetim durumu duyarlık, yuvarlama ve platforma bağlı olarak kayan nokta Matematiği paketindeki sonsuz modlarını değiştirmek programın sağlar. Aynı zamanda `_controlfp_s` maske veya kayan nokta özel durumlar maskesini kaldırın.  
  
 Varsa değeri `mask` 0'a eşit olduğu `_controlfp_s` kayan nokta denetim sözcüğü alır ve alınan değeri depolar `currentControl`.  
  
 Varsa `mask` olan denetim sözcüğü için yeni bir değer sıfır olmayan, ayarlanır: ayarlanmış bit için (diğer bir deyişle, 1'e eşit) içinde `mask`, karşılık gelen bit `new` denetim sözcüğü güncelleştirmek için kullanılır. Diğer bir deyişle, `fpcntrl` `=` ((`fpcntrl` `& ~mask`) &#124; (`new & mask`)) nerede `fpcntrl` kayan nokta denetim sözcüğüdür. Bu senaryoda, `currentControl` sonra değerine ayarlanır değişikliği tamamlandıktan; eski denetim sözcüğü bit değeri değil.  
  
> [!NOTE]
>  Varsayılan olarak, çalışma zamanı kitaplıkları tüm kayan nokta özel durumları maske.  
  
 `_controlfp_s`neredeyse aynıdır `_control87` işlevi Intel (x86), [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]ve ARM platformlar. X86, hedefliyorsanız [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], veya kullanabileceğiniz ARM platformları `_control87` veya `_controlfp_s`.  
  
 Arasındaki farkı `_control87` ve `_controlfp_s` nasıl bunlar işler içinde olduğu `DENORMAL` değerleri. Intel (x86), için [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)]ve ARM platformları `_control87` ayarlayabilir ve normal dışı işlenen özel durum maskesi temizleyin. `_controlfp_s`normal dışı işlenen özel durum maskesi değiştirmez. Bu örnekte fark gösterilmektedir:  
  
```C  
_control87( _EM_INVALID, _MCW_EM );   
// DENORMAL is unmasked by this call.  
unsigned int current_word = 0;  
_controlfp_s( &current_word, _EM_INVALID, _MCW_EM );   
// DENORMAL exception mask remains unchanged.  
```  
  
 Maske sabiti için olası değerler (`mask`) ve yeni denetim değerleri (`newControl`) aşağıdaki onaltılık değerler tabloda gösterilmiştir. Aşağıda listelenen taşınabilir sabitleri kullanın (`_MCW_EM`, `_EM_INVALID`ve benzeri) bu işlevler için bağımsız değişken olarak onaltılık sağladığını yerine değerleri açıkça.  
  
 Intel (x86) türetilmiş platformları DENORMAL giriş desteği ve donanım değerlerde çıktı. Korumak için davranıştır x86 normal dışı değerler. ARM platform ve [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] SSE2 desteğine sahip platformları DENORMAL işlenenler ve Temizlenen veya sıfır sonuçları etkinleştirin. `_controlfp_s`, `_controlfp`, Ve `_control87` işlevleri sağlayan bu davranışı değiştirmek için maske. Aşağıdaki örnekte bu maskesi kullanımını göstermektedir:  
  
```C  
unsigned int current_word = 0;  
_controlfp_s(&current_word, _DN_SAVE, _MCW_DN);     
// Denormal values preserved on ARM platforms and on x64 processors with  
// SSE2 support. NOP on x86 platforms.  
_controlfp_s(&current_word, _DN_FLUSH, _MCW_DN);     
// Denormal values flushed to zero by hardware on ARM platforms   
// and x64 processors with SSE2 support. Ignored on other x86 platforms.  
```  
  
 ARM platformlarda `_controlfp_s` işlevi FPSCR kasaya uygulanır. Üzerinde [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] mimariler, depolanan SSE2 denetim sözcüğü MXCSR kayıt etkilenir. Intel (x86) platformlarda `_controlfp_s` x87 ve SSE2 denetim sözcükleri etkiler. İki denetim sözcükler birbiriyle tutarsız olması mümkündür (önceki çağrısı nedeniyle [__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md), örneğin); iki denetim sözcükler arasında bir tutarsızlık ise `_controlfp_s` Ayarlar`EM_AMBIGUOUS`içinde bayrak `currentControl`. Bu, döndürülen denetim sözcüğü hem kayan nokta denetim sözcükler durumunu doğru şekilde temsil edemeyebilir değil, bir uyarıdır.  
  
 ARM üzerinde ve [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] mimariler, sonsuzluk modu veya kayan nokta duyarlık değiştirme desteklenmez. Duyarlık denetimi maske üzerinde kullanılıyorsa [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] platform, işlevi bir onaylama işlemi başlatır ve açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
 Maske doğru ayarlanmazsa, bu işlev geçersiz bir parametre istisna açıklandığı gibi oluşturur [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür `EINVAL` ve ayarlar `errno` için `EINVAL`.  
  
 Bu işlev, kullandığınızda göz ardı edilir [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md) ortak dil çalışma zamanı (CLR) yalnızca varsayılan kayan nokta duyarlık desteklediğinden derlemek için.  
  
### <a name="mask-constants-and-values"></a>Maske sabitleri ve değerleri  
  
 İçin `_MCW_EM` temizlemeden maskesi ayarlar donanım özel durumu verir özel durum; bu ayar, özel durum gizler. Varsa bir `_EM_UNDERFLOW` veya `_EM_OVERFLOW` oluşur, sonraki kayan nokta yönergesi yürütülene dek hiçbir donanım özel durumu oluşur. Donanım özel durum oluşturmak için hemen sonra `_EM_UNDERFLOW` veya `_EM_OVERFLOW`, FWAIT MASM yönerge çağırın.  
  
|Maskesi|Onaltılık değer|Sabit|Onaltılık değer|  
|----------|---------------|--------------|---------------|  
|`_MCW_DN`(Denetim normal dışı)|0x03000000|`_DN_SAVE`<br /><br /> `_DN_FLUSH`|0x00000000<br /><br /> 0x01000000|  
|`_MCW_EM`(Özel durum maskesi kesme)|0x0008001F|`_EM_INVALID`<br /><br /> `_EM_DENORMAL`<br /><br /> `_EM_ZERODIVIDE`<br /><br /> `_EM_OVERFLOW`<br /><br /> `_EM_UNDERFLOW`<br /><br /> `_EM_INEXACT`|0x00000010<br /><br /> 0x00080000<br /><br /> 0x00000008<br /><br /> 0x00000004<br /><br /> 0x00000002<br /><br /> 0x00000001|  
|`_MCW_IC`(Sonsuz denetimi)<br /><br /> (ARM üzerinde desteklenmez veya [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] platformları.)|0x00040000|`_IC_AFFINE`<br /><br /> `_IC_PROJECTIVE`|0x00040000<br /><br /> 0x00000000|  
|`_MCW_RC`(Yuvarlama denetimi)|0x00000300|`_RC_CHOP`<br /><br /> `_RC_UP`<br /><br /> `_RC_DOWN`<br /><br /> `_RC_NEAR`|0x00000300<br /><br /> 0x00000200<br /><br /> 0x00000100<br /><br /> 0x00000000|  
|`_MCW_PC`(Precision denetimi)<br /><br /> (ARM üzerinde desteklenmez veya [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] platformları.)|0x00030000|`_PC_24`(24 bit)<br /><br /> `_PC_53`(53 BITS)<br /><br /> `_PC_64`(64 bit)|0x00020000<br /><br /> 0x00010000<br /><br /> 0x00000000|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_controlfp_s`|\<float.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)   
 [_clear87, _clearfp](../../c-runtime-library/reference/clear87-clearfp.md)   
 [_status87, _statusfp, _statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)