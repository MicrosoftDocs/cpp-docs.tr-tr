---
title: _fgetchar, _fgetwchar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fgetchar
- _fgetwchar
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
- fgetwchar
- _fgettchar
- _fgetchar
- _fgetwchar
- fgettchar
dev_langs:
- C++
helpviewer_keywords:
- fgetwchar function
- _fgetchar function
- fgettchar function
- _fgetwchar function
- _fgettchar function
- standard input, reading from
- fgetchar function
ms.assetid: 8bce874c-701a-41a3-b1b2-feff266fb5b9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0eabf9bd54764aaa37bd860eb5bdb7d1ac5232ab
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="fgetchar-fgetwchar"></a>_fgetchar, _fgetwchar
Bir karakteri okur `stdin`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _fgetchar( void );  
wint_t _fgetwchar( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_fgetchar` olarak okuma karakteri döndürür bir `int` veya return `EOF` bir hata veya dosya sonu belirtmek için. **_** `fgetwchar` döndürür, olarak bir [wint_t](../../c-runtime-library/standard-types.md), okuma karakterine karşılık gelen veya verir geniş karakter `WEOF` bir hata veya dosya sonu belirtmek için. Her iki işlevlerini kullanmak `feof` veya `ferror` hata bir dosya sonu durumu arasında ayrım yapmak için.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin bir tek karakteri okuma `stdin`. İşlev sonra ilişkili dosya işaretçisini (tanımlıysa) sonraki karaktere işaret edecek şekilde artırır. Akış dosya sonu ise dosya sonu gösterge akış için ayarlanır.  
  
 `_fgetchar` eşdeğer olan `fgetc( stdin )`. Ayrıca eşdeğer olan `getchar`, ancak bir işlev ve bir makro değil, yalnızca bir işlevi olarak uygulanır. `_fgetwchar` joker karakter sürümü `_fgetchar`.  
  
 Bu işlevler ANSI standardı ile uyumlu değildir.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_fgettchar`|`_fgetchar`|`_fgetchar`|`_fgetwchar`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_fgetchar`|\<stdio.h >|  
|`_fgetwchar`|\<stdio.h > veya \<wchar.h >|  
  
 Konsol Evrensel Windows Platformu (UWP) uygulamaları desteklenmez. Konsol ile ilişkili standart akış tanıtıcıları —`stdin`, `stdout`, ve `stderr`— C çalışma zamanı işlevleri de kullanabilmek için önce yeniden yönlendirilmesi gerekiyor [! INCLUDEUWP uygulamalar. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_fgetchar.c  
// This program uses _fgetchar to read the first  
// 80 input characters (or until the end of input)  
// and place them into a string named buffer.  
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char buffer[81];  
   int  i, ch;  
  
   // Read in first 80 characters and place them in "buffer":  
   ch = _fgetchar();  
   for( i=0; (i < 80 ) && ( feof( stdin ) == 0 ); i++ )  
   {  
      buffer[i] = (char)ch;  
      ch = _fgetchar();  
   }  
  
   // Add null to end string   
   buffer[i] = '\0';  
   printf( "%s\n", buffer );  
}  
```  
  
```Output  
  
      Line one.  
Line two.Line one.  
Line two.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fputc, fputwc](../../c-runtime-library/reference/fputc-fputwc.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)