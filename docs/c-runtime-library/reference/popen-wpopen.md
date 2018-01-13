---
title: _popen, _wpopen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _popen
- _wpopen
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
- tpopen
- popen
- wpopen
- _popen
- _wpopen
- _tpopen
dev_langs: C++
helpviewer_keywords:
- tpopen function
- pipes, creating
- _popen function
- _tpopen function
- popen function
- wpopen function
- _wpopen function
ms.assetid: eb718ff2-c87d-4bd4-bd2e-ba317c3d6973
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e5cf1fc935bbee75eb8acc31cfd7ae0e8d92c3a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="popen-wpopen"></a>_popen, _wpopen
Bir kanal oluşturur ve bir komut çalıştırır.  
  
> [!IMPORTANT]
>  Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [/ZW ile desteklenmeyen CRT işlevleri](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Sözdizimi  
  
```
FILE *_popen(
const char *command,
const char *mode
);
FILE *_wpopen(
const wchar_t *command,
const wchar_t *mode
);
```  
  
#### <a name="parameters"></a>Parametreler  
 *komutu*  
 Yürütülecek komutu.  
  
 *modu*  
 Döndürülen akışa modu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Oluşturulan kanal bir uç ile ilişkili bir akış döndürür. Kanalın diğer ucundaki oluşturulan komutunun standart giriş veya standart çıktı ile ilişkilidir. İşlev dönüş **NULL** bir hata. Eğer gibi geçersiz bir parametre hatası olması durumunda *komutu* veya *modu* null işaretçinin veya *modu* geçerli bir moda değil `errno` ayarlanır `EINVAL`. Geçerli mod için Açıklamalar bölümüne bakın.  
  
 Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_popen` İşlevi bir kanal oluşturur ve Komut işlemcisi belirtilen dize ile oluşturulan bir kopyasını zaman uyumsuz olarak yürütür *komutu*. Karakter dizesi *modu* gibi istenen erişim türünü belirtir.  
  
 **"r"**  
 Arama işlemi döndürülen akışa kullanarak oluşturulan komutunun standart çıktı okuyabilir.  
  
 **"w"**  
 Arama işlemi döndürülen akışa kullanılarak oluşturulan komutunun standart girişine yazabilirsiniz.  
  
 **"b"**  
 İkili modda açık.  
  
 **"t"**  
 Metin modunda açın.  
  
> [!NOTE]
>  Bir Windows programı kullandıysanız `_popen` işlevi programın süresiz olarak yanıt vermemesine neden olan bir geçersiz dosya işaretçi döndürür. `_popen`bir konsol uygulamasında düzgün çalışır. Giriş ve çıkış yönlendiren bir Windows uygulaması oluşturmak için bkz: [yeniden yönlendirilen giriş ve çıkış ile bir alt işlem oluşturma](http://msdn.microsoft.com/library/windows/desktop/ms682499) Windows SDK.  
  
 `_wpopen`bir joker karakter sürümü `_popen`; *yolu* bağımsız değişkeni `_wpopen` bir joker karakter dizesidir. `_wpopen`ve `_popen` Aksi takdirde aynı şekilde davranır.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tpopen`|`_popen`|`_popen`|`_wpopen`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_popen`|\<stdio.h >|  
|`_wpopen`|\<stdio.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_popen.c  
/* This program uses _popen and _pclose to receive a   
 * stream of text from a system process.  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
  
   char   psBuffer[128];  
   FILE   *pPipe;  
  
        /* Run DIR so that it writes its output to a pipe. Open this  
         * pipe with read text attribute so that we can read it   
         * like a text file.   
         */  
  
   if( (pPipe = _popen( "dir *.c /on /p", "rt" )) == NULL )  
      exit( 1 );  
  
   /* Read pipe until end of file, or an error occurs. */  
  
   while(fgets(psBuffer, 128, pPipe))  
   {  
      printf(psBuffer);  
   }  
  
   /* Close pipe and print return value of pPipe. */  
   if (feof( pPipe))  
   {  
     printf( "\nProcess returned %d\n", _pclose( pPipe ) );  
   }  
   else  
   {  
     printf( "Error: Failed to read the pipe to the end.\n");  
   }  
}  
```  
  
## <a name="sample-output"></a>Örnek Çıktı  
 Bu çıktı var. yalnızca bir dosya .c dosya adı uzantısı ile geçerli dizinde varsayar.  
  
```  
 Volume in drive C is CDRIVE  
 Volume Serial Number is 0E17-1702  
  
 Directory of D:\proj\console\test1  
  
07/17/98  07:26p                   780 popen.c  
               1 File(s)            780 bytes  
                             86,597,632 bytes free  
  
Process returned 0  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Süreç ve ortam denetimi](../../c-runtime-library/process-and-environment-control.md)   
 [_pclose](../../c-runtime-library/reference/pclose.md)   
 [_pipe](../../c-runtime-library/reference/pipe.md)
