---
title: fputc, fputwc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fputc
- fputwc
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
- fputc
- fputwc
- _fputtc
dev_langs: C++
helpviewer_keywords:
- streams, writing characters to
- fputtc function
- _fputtc function
- fputwc function
- fputc function
ms.assetid: 5a0a593d-43f4-4fa2-a401-ec4e23de4d2f
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 75065ba914356db06f75e80acc4ca3a6350237de
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="fputc-fputwc"></a>fputc, fputwc
Bir karakterin bir akışa yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int fputc(  
   int c,  
   FILE *stream   
);  
wint_t fputwc(  
   wchar_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Yazılacak karakter.  
  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri yazılmış karakteri döndürür. İçin `fputc`, dönüş değeri `EOF` bir hata olduğunu gösterir. İçin `fputwc`, dönüş değeri `WEOF` bir hata olduğunu gösterir. Varsa `stream` olan `NULL`, bu işlevler açıklandığı gibi geçersiz parametre işleyicisi çağırma [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Döndürmeleri yürütme devam etmek için izin verilip verilmediğini, `EOF` ve `errno` için `EINVAL`.  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hata kodları hakkında daha fazla bilgi için.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri tek karakter Yazar `c` için bir dosya konumunda belirtilen ilişkili dosya konumu göstergesi (tanımlıysa) ve uygun şekilde göstergesi ilerletir. Durumunda `fputc` ve `fputwc`, dosyanın ilişkilendirildiği `stream`. Dosya konumlandırma istekleri desteklemiyor veya içinde açılmış ekleme modu, karakteri akışın sonuna eklenir.  
  
 Akış ANSI modunda açılırsa iki işlevleri aynı şekilde davranır. `fputc`şu anda çıktı bir UNICODE akışa desteklemiyor.  
  
 Sürümleriyle `_nolock` soneki, diğer iş parçacıkları tarafından girişime korunmayan dışında aynıdır. Daha fazla bilgi için bkz:[_fputc_nolock _fputwc_nolock](../../c-runtime-library/reference/fputc-nolock-fputwc-nolock.md).  
  
 Yordamı özgü açıklamalar izleyin.  
  
|Yordam|Açıklamalar|  
|-------------|-------------|  
|`fputc`|Eşdeğer `putc`, ancak bir işlev ve bir makro değil, yalnızca bir işlevi olarak uygulanır.|  
|`fputwc`|Joker karakter sürümü `fputc`. Yazar `c` birden çok baytlı karakter veya mi göre geniş karakter olarak `stream` metin modunda veya ikili modunda açılır.|  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_fputtc`|`fputc`|`fputc`|`fputwc`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`fputc`|\<stdio.h >|  
|`fputwc`|\<stdio.h > veya \<wchar.h >|  
  
 Konsol desteklenmeyen [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Konsol ile ilişkili standart akış tanıtıcıları —`stdin`, `stdout`, ve `stderr`— C çalışma zamanı işlevleri de kullanabilmek için önce yeniden yönlendirilmesi gerekiyor [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_fputc.c  
// This program uses fputc  
// to send a character array to stdout.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char strptr1[] = "This is a test of fputc!!\n";  
   char *p;  
  
   // Print line to stream using fputc.   
   p = strptr1;  
   while( (*p != '\0') && fputc( *(p++), stdout ) != EOF ) ;  
  
}  
```  
  
```Output  
This is a test of fputc!!  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fgetc, fgetwc](../../c-runtime-library/reference/fgetc-fgetwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)