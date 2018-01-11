---
title: _getcwd, _wgetcwd | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wgetcwd
- _getcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd
- wgetcwd
- _wgetcwd
- tgetcwd
- _tgetcwd
dev_langs: C++
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 14047c8143d982bc6b26bef6e46679341d9abd36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="getcwd-wgetcwd"></a>_getcwd, _wgetcwd
Geçerli çalışma dizini alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_getcwd(   
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetcwd(   
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `buffer`  
 Yol için depolama konumu.  
  
 `maxlen`  
 Yolun karakter cinsinden en büyük uzunluğu: `char` için `_getcwd` ve `wchar_t` için `_wgetcwd`.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür `buffer`. A `NULL` değeri belirten bir hata döndürür ve `errno` ya da ayarlamak `ENOMEM`, ayırmak için yeterli bellek olduğunu belirten `maxlen` bayt (olduğunda bir `NULL` bağımsız değişken olarak verilen `buffer`), veya `ERANGE`, yolun daha uzun olduğunu belirten `maxlen` karakter. Varsa `maxlen` küçük veya ona eşit sıfır olarak açıklandığı gibi bu işlev bir geçersiz parametre işleyicisi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_getcwd` İşlevi varsayılan sürücüsü için geçerli çalışma dizininin tam yolunu alır ve konumunda depolar `buffer`. Tamsayı bağımsız değişkeni `maxlen` yolu için uzunluk üst sınırını belirtir. (Sonlandırma null karakteri dahil) yolunun uzunluğu aşması durumunda bir hata meydana `maxlen`. `buffer` Bağımsız değişkeni olabilir `NULL`; arabellek boyutu en az bir `maxlen` (daha fazla yalnızca gerekirse) otomatik olarak ayrılır, kullanarak `malloc`, yolun depolamak için. Bu arabelleğin daha sonra çağırarak serbest bırakılabilirler `free` ve onu `_getcwd` dönüş değeri (ayrılan arabellek için bir işaretçi).  
  
 `_getcwd`Geçerli çalışma dizini yolu temsil eden bir dize döndürür. Geçerli çalışma dizini kök ise dizesi bir ters eğik ( `\` ). Geçerli çalışma dizini kökü dışında bir dizin ise, dize olmayan bir ters eğik çizgi ile dizin adı ile sona erer.  
  
 `_wgetcwd`bir joker karakter sürümü `_getcwd`; `buffer` yazmaç değerini `_wgetcwd` joker karakter dizelerdir. `_wgetcwd`ve `_getcwd` Aksi takdirde aynı şekilde davranır.  
  
 Zaman `_DEBUG` ve `_CRTDBG_MAP_ALLOC` tanımlanır, çağrılar `_getcwd` ve `_wgetcwd` yapılan çağrılar tarafından değiştirilen `_getcwd_dbg` ve `_wgetcwd_dbg` bellek ayırmaları hata ayıklama için izin vermek için. Daha fazla bilgi için bkz: [_getcwd_dbg, _wgetcwd_dbg](../../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetcwd`|`_getcwd`|`_getcwd`|`_wgetcwd`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_getcwd`|\<Direct.h >|  
|`_wgetcwd`|\<Direct.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_getcwd.c  
// This program places the name of the current directory in the   
// buffer array, then displays the name of the current directory   
// on the screen. Passing NULL as the buffer forces getcwd to allocate  
// memory for the path, which allows the code to support file paths  
// longer than _MAX_PATH, which are supported by NTFS.  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* buffer;  
  
   // Get the current working directory:   
   if( (buffer = _getcwd( NULL, 0 )) == NULL )  
      perror( "_getcwd error" );  
   else  
   {  
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );  
      free(buffer);  
   }  
}  
```  
  
```Output  
C:\Code  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizin denetimi](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)