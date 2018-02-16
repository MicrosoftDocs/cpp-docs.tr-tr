---
title: perror, _wperror | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wperror
- perror
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
- _wperror
- _tperror
- perror
dev_langs:
- C++
helpviewer_keywords:
- _tperror function
- tperror function
- wperror function
- error messages, printing
- printing error messages
- _wperror function
- perror function
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3929d35ac258823a70bf063f2e90e3ce8f1dfb4a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="perror-wperror"></a>perror, _wperror
Bir hata iletisi yazdırın.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      void perror(  
   const char *string   
);  
void _wperror(  
   const wchar_t *string   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `string`  
 Yazdırmak için dize ileti.  
  
## <a name="remarks"></a>Açıklamalar  
 `perror` İşlevi bir hata iletisi yazdırır `stderr`. `_wperror` bir joker karakter sürümü **_perror**; `string` bağımsız değişkeni `_wperror` bir joker karakter dizesidir. `_wperror` ve **_perror** Aksi takdirde aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tperror`|`perror`|`perror`|`_wperror`|  
  
 `string` ilk olarak, bir iki nokta üst üste ve ardından bir hata üretilen son kitaplığı çağrı için sistem hata iletisini ve ardından yazdırılır ve son olarak yeni satır karakteri tarafından. Varsa `string` null işaretçi ya da boş bir dize için bir işaretçi `perror` yalnızca sistem hata iletisi yazdırır.  
  
 Hata numarası değişkende depolanır [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) (ERRNO içinde tanımlanmıştır. H). Sistem hata iletilerini değişken üzerinden erişilen [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), bir dizi hata numarasına göre sıralanmış iletileri olduğu. `perror` uygun hata iletisini kullanarak yazdırır `errno` değeri için bir dizin olarak `_sys_errlist`. Değişkenin değerini [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) öğe maksimum sayısı olarak tanımlanan `_sys_errlist` dizi.  
  
 Doğru sonuçlar için arama `perror` hemen bir hata ile kitaplığı yordamı döndükten sonra. Aksi halde, sonraki çağrılar kılabilirsiniz `errno` değeri.  
  
 Windows işletim sistemi, bazı `errno` değerleri ERRNO içinde listelenen. H kullanılmayan. Bu değerler UNIX işletim sistemi tarafından kullanılmak üzere ayrılmıştır. Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) listesini `errno` Windows işletim sistemi tarafından kullanılan değerler. `perror` boş bir dize için yazdırır `errno` değeri bu platformlar tarafından kullanılmaz.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`perror`|\<stdio.h > veya \<stdlib.h >|  
|`_wperror`|\<stdio.h > veya \<wchar.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_perror.c  
// compile with: /W3  
/* This program attempts to open a file named  
 * NOSUCHF.ILE. Because this file probably doesn't exist,  
 * an error message is displayed. The same message is  
 * created using perror, strerror, and _strerror.  
 */  
  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <share.h>  
  
int main( void )  
{  
   int  fh;  
  
   if( _sopen_s( &fh, "NOSUCHF.ILE", _O_RDONLY, _SH_DENYNO, 0 ) != 0 )  
   {  
      /* Three ways to create error message: */  
      perror( "perror says open failed" );  
      printf( "strerror says open failed: %s\n",  
         strerror( errno ) ); // C4996  
      printf( _strerror( "_strerror says open failed" ) ); // C4996  
      // Note: strerror and _strerror are deprecated; consider  
      // using strerror_s and _strerror_s instead.  
   }  
   else  
   {  
      printf( "open succeeded on input file\n" );  
      _close( fh );  
   }  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
perror says open failed: No such file or directory  
strerror says open failed: No such file or directory  
_strerror says open failed: No such file or directory  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [strerror, _strerror, _wcserror, \__wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)