---
title: _chdir, _wchdir | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wchdir
- _chdir
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tchdir
- _chdir
- _wchdir
- _tchdir
- wchdir
dev_langs: C++
helpviewer_keywords:
- _tchdir function
- _chdir function
- _wchdir function
- tchdir function
- wchdir function
- chdir function
- directories [C++], changing
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 343121b4484f97e0778098991c71731ed3c6ef2e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="chdir-wchdir"></a>_chdir, _wchdir
Geçerli çalışma dizini değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _chdir(   
   const char *dirname   
);  
int _wchdir(   
   const wchar_t *dirname   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `dirname`  
 Yeni çalışma dizini yolu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevler, başarılı olursa 0 değerini döndürür. Dönüş değeri-1 hata gösterir. Belirtilen yol bulunamadı, `errno` ayarlanır `ENOENT`. Varsa `dirname` null, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlev -1 döndürür.  
  
## <a name="remarks"></a>Açıklamalar  
 `_chdir` İşlev tarafından belirtilen dizin için geçerli çalışma dizini değiştirir `dirname`. `dirname` Parametresi varolan bir dizin başvurması gerekir. Bu işlev, herhangi bir sürücüdeki geçerli çalışma dizini değiştirebilirsiniz. Yeni bir sürücü harfi belirtilmişse `dirname`, varsayılan sürücü harfini de değiştirilir. Örneğin, bir varsayılan sürücü harfini ve \BIN geçerli çalışma dizini ise aşağıdaki çağrıyı C sürücüsü için geçerli çalışma dizini değiştirir ve yeni bir varsayılan sürücü olarak C oluşturur:  
  
```  
_chdir("c:\\temp");  
```  
  
 İsteğe bağlı bir ters eğik çizgi karakteri kullandığınızda (`\`) yollarında, iki ters eğik çizgi yerleştirmeniz gerekir (`\\`) tek bir ters eğik çizgi temsil etmek için bir C dize olarak (`\`).  
  
 `_wchdir`bir joker karakter sürümü `_chdir`; `dirname` bağımsız değişkeni `_wchdir` bir joker karakter dizesi`. _wchdir` ve `_chdir` Aksi takdirde aynı şekilde davranır.  
  
### <a name="generic-text-routine-mapping"></a>Genel metin rutin eşleme:  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tchdir`|`_chdir`|`_chdir`|`_wchdir`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_chdir`|\<Direct.h >|\<errno.h >|  
|`_wchdir`|\<Direct.h > veya \<wchar.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_chdir.c  
// arguments: C:\WINDOWS  
  
/* This program uses the _chdir function to verify  
   that a given directory exists. */  
  
#include <direct.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( int argc, char *argv[] )  
{  
  
   if(_chdir( argv[1] ) )  
   {  
      switch (errno)  
      {  
      case ENOENT:  
         printf( "Unable to locate the directory: %s\n", argv[1] );  
         break;  
      case EINVAL:  
         printf( "Invalid buffer.\n");  
         break;  
      default:  
         printf( "Unknown error.\n");  
      }  
   }  
   else  
      system( "dir *.exe");  
}  
```  
  
```Output  
Volume in drive C has no label.  
 Volume Serial Number is 2018-08A1  
  
 Directory of c:\windows  
  
08/29/2002  04:00 AM         1,004,032 explorer.exe  
12/17/2002  04:43 PM            10,752 hh.exe  
03/03/2003  09:24 AM            33,792 ieuninst.exe  
10/29/1998  04:45 PM           306,688 IsUninst.exe  
08/29/2002  04:00 AM            66,048 NOTEPAD.EXE  
03/03/2003  09:24 AM            33,792 Q330994.exe  
08/29/2002  04:00 AM           134,144 regedit.exe  
02/28/2003  06:26 PM            46,352 setdebug.exe  
08/29/2002  04:00 AM            15,360 TASKMAN.EXE  
08/29/2002  04:00 AM            49,680 twunk_16.exe  
08/29/2002  04:00 AM            25,600 twunk_32.exe  
08/29/2002  04:00 AM           256,192 winhelp.exe  
08/29/2002  04:00 AM           266,752 winhlp32.exe  
              13 File(s)      2,249,184 bytes  
               0 Dir(s)  67,326,029,824 bytes free  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dizin denetimi](../../c-runtime-library/directory-control.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [Sistem, _wsystem](../../c-runtime-library/reference/system-wsystem.md)