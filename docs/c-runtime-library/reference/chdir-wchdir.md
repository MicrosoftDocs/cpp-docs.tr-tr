---
title: _chdir, _wchdir | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _tchdir function
- _chdir function
- _wchdir function
- tchdir function
- wchdir function
- chdir function
- directories [C++], changing
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 73abd8ef0ca29ee9e7f2312cc44a8178fc464261
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46064639"
---
# <a name="chdir-wchdir"></a>_chdir, _wchdir

Geçerli çalışma dizinini değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
int _chdir(
   const char *dirname
);
int _wchdir(
   const wchar_t *dirname
);
```

### <a name="parameters"></a>Parametreler

*DizinAdı*<br/>
Yeni çalışma dizini yolu.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevler, başarılı olursa 0 değerini döndürür. Dönüş değeri-1 hata gösterir. Belirtilen yol bulunamadı, **errno** ayarlanır **ENOENT**. Varsa *DizinAdı* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev -1 döndürür.

## <a name="remarks"></a>Açıklamalar

**_Chdir** işlevi tarafından belirtilen dizini geçerli çalışma dizini değişiklikleri *DizinAdı*. *DizinAdı* parametresi mevcut bir dizine başvurması gerekir. Bu işlev, herhangi bir sürücüdeki geçerli çalışma dizini değiştirebilirsiniz. Yeni bir sürücü harfi belirtilmişse *DizinAdı*, varsayılan sürücü harfini de değiştirilir. Örneğin, bir varsayılan sürücü harfi olduğu ve geçerli çalışma dizini \BIN ise, aşağıdaki çağrısı C sürücüsü için geçerli çalışma dizinini değiştirir ve yeni bir varsayılan sürücü olarak C kurar:

```C
_chdir("c:\temp");
```

İsteğe bağlı bir ters eğik çizgi karakteri kullandığınızda (**&#92;**) yolları, iki ters eğik çizgi koymanız gerekir (**&#92;&#92;**) tek bir ters eğik çizgi temsil etmek için bir C dize içinde ( **&#92;**).

**_wchdir** geniş karakterli sürümüdür **_chdir**; *DizinAdı* bağımsız değişkeni **_wchdir** geniş karakterli bir dizedir. **_wchdir** ve **_chdir** aynı şekilde davranır.

### <a name="generic-text-routine-mapping"></a>Genel metin yordam eşlemesi:

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchdir**|**_chdir**|**_chdir**|**_wchdir**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_chdir**|\<Direct.h >|\<errno.h >|
|**_wchdir**|\<Direct.h > veya \<wchar.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
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

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
