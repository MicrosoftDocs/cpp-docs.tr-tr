---
title: _setmode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _setmode
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
f1_keywords: _setmode
dev_langs: C++
helpviewer_keywords:
- Unicode [C++], console output
- files [C++], modes
- _setmode function
- file translation [C++], setting mode
- files [C++], translation
- setmode function
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d894433ea7ad4c0525c044e64aa1e9c6f66459e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="setmode"></a>_setmode
Dosya çevirisi modu ayarlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _setmode (  
   int fd,  
   int mode   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fd`  
 Dosya tanımlayıcısı.  
  
 `mode`  
 Yeni çeviri modu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa, önceki çeviri modu döndürür.  
  
 Bu işlev için geçersiz parametreler aktarılırsa geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlev dönüşleri -1 ve kümelerini yürütülmesine izin veriliyorsa `errno` ya da `EBADF`, geçersiz bir dosya tanımlayıcısı gösterir veya `EINVAL`, geçersiz bir gösterir `mode` bağımsız değişkeni.  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_setmode` İşlevi ayarlar `mode` tarafından verilen dosya çevirisi modu `fd`. Geçirme `_O_TEXT` olarak `mode` (çevrilmiş) metin ayarlar modu. Satır başı satır besleme (CR-LF) birleşimleri besleme karakteri girişte tek bir satır halinde çevrilir. Satır akış karakterleri CR LF birleşimleri çıktıyı içine çevrilir. Geçirme `_O_BINARY` bu çevirileri gizlenir kümeleri ikili (untranslated) modu.  
  
 Ayrıca iletebilirsiniz `_O_U16TEXT`, `_O_U8TEXT`, veya `_O_WTEXT` bu belgenin sonraki bölümlerinde ikinci örnekte gösterildiği gibi Unicode modunu etkinleştirmek için. `_setmode`genellikle varsayılan çeviri modunu değiştirmek için kullanılan `stdin` ve `stdout`, ancak herhangi bir dosya kullanın. Uygularsanız `_setmode` bir akış için dosya tanımlayıcısı için çağrı `_setmode` akışta giriş veya çıkış işlemleri gerçekleştirmeden önce.  
  
> [!CAUTION]
>  Verileri bir dosya akışı için temizleme açıkça kodu kullanarak yazarsanız [fflush](../../c-runtime-library/reference/fflush.md) kullanmadan önce `_setmode` modunu değiştirmek için. Kodu temizleme değil, beklenmeyen davranışları alabilirsiniz. Veri akışına yazdığınız değil, kod flush gerekmez.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|----------------------|  
|`_setmode`|\<io.h >|\<fcntl.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_setmode.c  
// This program uses _setmode to change  
// stdin from text mode to binary mode.  
  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
int main( void )  
{  
   int result;  
  
   // Set "stdin" to have binary mode:  
   result = _setmode( _fileno( stdin ), _O_BINARY );  
   if( result == -1 )  
      perror( "Cannot set mode" );  
   else  
      printf( "'stdin' successfully changed to binary mode\n" );  
}  
```  
  
```Output  
'stdin' successfully changed to binary mode  
```  
  
## <a name="example"></a>Örnek  
  
```  
// crt_setmodeunicode.c  
// This program uses _setmode to change  
// stdout to Unicode. Cyrillic and Ideographic  
// characters will appear on the console (if  
// your console font supports those character sets).  
  
#include <fcntl.h>  
#include <io.h>  
#include <stdio.h>  
  
int main(void) {  
    _setmode(_fileno(stdout), _O_U16TEXT);  
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_set_fmode](../../c-runtime-library/reference/set-fmode.md)