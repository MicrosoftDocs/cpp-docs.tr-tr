---
title: _chdir, _wchdir
ms.date: 4/2/2020
api_name:
- _wchdir
- _chdir
- _o__chdir
- _o__wchdir
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- tchdir
- _chdir
- _wchdir
- _tchdir
- wchdir
helpviewer_keywords:
- _tchdir function
- _chdir function
- _wchdir function
- tchdir function
- wchdir function
- chdir function
- directories [C++], changing
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
ms.openlocfilehash: a3f224e68e4b5a43274616892012ceba737d6d17
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333383"
---
# <a name="_chdir-_wchdir"></a>_chdir, _wchdir

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

*dirname*<br/>
Yeni çalışma dizininin yolu.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevler başarılı olursa 0 değeri döndürer. -1'in geri dönüş değeri başarısızlığı gösterir. Belirtilen yol bulunamadıysa, **errno** **ENOENT**olarak ayarlanır. *Dirname* **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev -1 döndürür.

## <a name="remarks"></a>Açıklamalar

_chdir **_chdir** işlevi, geçerli çalışma dizini *dirname*ile belirtilen dizine değiştirir. *Dirname* parametresi varolan bir dizine başvurmalıdır. Bu işlev, herhangi bir sürücüde geçerli çalışma dizini değiştirebilirsiniz. *Dirname'de*yeni bir sürücü harfi belirtilirse, varsayılan sürücü harfi de değiştirilir. Örneğin, A varsayılan sürücü harfiyse ve \BIN geçerli çalışma diziniyse, aşağıdaki çağrı C sürücüsünün geçerli çalışma dizinini değiştirir ve C'yi yeni varsayılan sürücü olarak belirler:

```C
_chdir("c:\temp");
```

Yollarda isteğe bağlı ters eğik çizgi karakterini** (&#92;) **kullandığınızda, tek bir ters eğik çizgiyi** (&#92;) **temsil etmek için c dizesine (&#92;&#92;) iki ters eğik çizgi** (&#92;&#92;) **yerleştirmeniz gerekir.

**_wchdir** **_chdir**geniş karakterli bir versiyonudur; **_wchdir** *dirname* bağımsız değişkeni geniş karakterli bir dizedir. **_wchdir** ve **_chdir** aynı şekilde davranan.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mapping"></a>Genel Metin Rutin Eşleme:

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchdir**|**_chdir**|**_chdir**|**_wchdir**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_chdir**|\<direct.h>|\<errno.h>|
|**_wchdir**|\<direct.h> \<veya wchar.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Dizin Kontrolü](../../c-runtime-library/directory-control.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
