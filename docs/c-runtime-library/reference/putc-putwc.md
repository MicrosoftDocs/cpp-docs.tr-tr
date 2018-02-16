---
title: putc, putwc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- putwc
- putc
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _puttc
- putwc
- putc
dev_langs:
- C++
helpviewer_keywords:
- streams, writing characters to
- characters, writing
- putwc function
- putc function
- _puttc function
- puttc function
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4a3c07cab44f6b709affa22f470dfd7a8840b729
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="putc-putwc"></a>putc, putwc
Bir karakterin bir akışa yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int putc(  
   int c,  
   FILE *stream   
);  
wint_t putwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Yazılacak karakter.  
  
 `stream`  
 İşaretçi **dosya** yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yazılan karakteri döndürür. Bir hata veya dosya sonu koşulu belirtmek için `putc` ve `putchar` iade `EOF`; `putwc` ve `putwchar` dönmek **WEOF**. Tüm dört yordamları için kullanmak [ferror](../../c-runtime-library/reference/ferror.md) veya [feof](../../c-runtime-library/reference/feof.md) bir hata veya dosya sonu için denetlemek için. Null işaretçinin aktarılırsa `stream`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş `EOF` veya **WEOF** ve `errno` için `EINVAL`.  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 `putc` Yordamı Yazar tek karakter `c` çıktısına `stream` geçerli konumundaki. Herhangi bir tamsayı için geçirilebilir `putc`, ancak yalnızca alt 8 bit yazılır. `putchar` Yordamdır aynı **putc (** `c` **, stdout)**. Okuma hatası oluşursa, her yordam için akış için hata göstergesi ayarlanır. `putc` ve `putchar` benzer `fputc` ve `_fputchar`, sırasıyla hem işlevleri de makroları olarak uygulanan ancak (bkz [seçme arasında işlevler ve makrolar](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)). `putwc` ve `putwchar` joker karakter sürümleri `putc` ve `putchar`sırasıyla. `putwc` ve `putc` akış ANSI modunda açılırsa aynı şekilde davranır. `putc` şu anda çıktı bir UNICODE akışa desteklemiyor.  
  
 Sürümleriyle **_nolock** soneki, diğer iş parçacıkları tarafından girişime korunmayan dışında aynıdır. Daha fazla bilgi için bkz: **_putc_nolock, _putwc_nolock**.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_puttc`|`putc`|`putc`|**putwc**|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`putc`|\<stdio.h >|  
|`putwc`|\<stdio.h > veya \<wchar.h >|  
  
Konsol Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsol ile ilişkili standart akış tanıtıcıları `stdin`, `stdout`, ve `stderr`, C çalışma zamanı işlevleri UWP uygulamalarında kullanabilmek için önce yeniden yönlendirilmesi gerekiyor. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_putc.c  
/* This program uses putc to write buffer  
 * to a stream. If an error occurs, the program  
 * stops before writing the entire buffer.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char *p, buffer[] = "This is the line of output\n";  
   int  ch;  
  
   ch = 0;  
   /* Make standard out the stream and write to it. */  
   stream = stdout;  
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )  
      ch = putc( *p, stream );  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
This is the line of output  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)