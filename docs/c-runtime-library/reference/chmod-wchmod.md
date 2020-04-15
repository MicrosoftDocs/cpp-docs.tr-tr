---
title: _chmod, _wchmod
ms.date: 4/2/2020
api_name:
- _chmod
- _wchmod
- _o__chmod
- _o__wchmod
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
- _chmod
- _wchmod
- wchmod
helpviewer_keywords:
- _chmod function
- wchmod function
- file permissions [C++]
- chmod function
- files [C++], changing permissions
- _wchmod function
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
ms.openlocfilehash: faceb49c921162da042f863abbebbe2ef0a52153
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350096"
---
# <a name="_chmod-_wchmod"></a>_chmod, _wchmod

Dosya izin ayarlarını değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
int _chmod( const char *filename, int pmode );
int _wchmod( const wchar_t *filename, int pmode );
```

### <a name="parameters"></a>Parametreler

*filename*<br/>
Varolan dosyanın adı.

*pmode*<br/>
Dosya için izin ayarı.

## <a name="return-value"></a>Dönüş Değeri

İzin ayarı başarıyla değiştirilirse, bu işlevler 0 döndürüler. -1'in geri dönüş değeri başarısızlığı gösterir. Belirtilen dosya bulunamadıysa, **errno** **ENOENT**olarak ayarlanır; bir parametre geçersizse, **errno** **EINVAL**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**_chmod** işlevi *dosya adı*ile belirtilen dosyanın izin ayarını değiştirir. İzin ayarı, dosyanın okuma ve yazma erişimini denetler. İnteger ifade *pmode* sys\Stat.h tanımlanan aşağıdaki bildirim sabitlerinden birini veya her ikisini içerir.

| *pmode* | Anlamı |
|-|-|
| **\_S\_IREAD** | Sadece okumaya izin verilir. |
| **\_S\_IWRITE** | Yazmaya izin verilir. (Aslında, okuma ve yazma izin verir.) |
| **\_S\_IREAD** &#124; ** \_\_S IWRITE** | Okuma ve yazmaya izin verilir. |

Her iki sabit de verildiğinde, bitwise veya işleç**\|**( ) ile birleştirilir. Yazma izni verilmezse, dosya salt okunur. Tüm dosyaların her zaman okunabilir olduğunu unutmayın; yalnızca yazma izni vermek mümkün değildir. Böylece, **_S_IWRITE** ve **_S_IREAD** \| **_S_IWRITE** modları eşdeğerdir.

**_wchmod** **_chmod**geniş karakterli bir versiyonudur; **_wchmod** için *dosya adı* bağımsız değişkeni geniş karakterli bir dizedir. **_wchmod** ve **_chmod** aynı şekilde davranan.

Bu işlev parametrelerini doğrular. *Pmode,* apaçık sabitlerden birinin bir leşi değilse veya alternatif bir sabit kümesi içeriyorsa, işlev bunları yok sayar. *Dosya adı* **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlev -1 döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchmod**|**_chmod**|**_chmod**|**_wchmod**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_chmod**|\<io.h>|\<sys/types.h>, \<sys/stat.h \<>, errno.h>|
|**_wchmod**|\<io.h> \<veya wchar.h>|\<sys/types.h>, \<sys/stat.h \<>, errno.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_chmod.c
// This program uses _chmod to
// change the mode of a file to read-only.
// It then attempts to modify the file.
//

#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdio.h>
#include <stdlib.h>
#include <errno.h>

// Change the mode and report error or success
void set_mode_and_report(char * filename, int mask)
{
   // Check for failure
   if( _chmod( filename, mask ) == -1 )
   {
      // Determine cause of failure and report.
      switch (errno)
      {
         case EINVAL:
            fprintf( stderr, "Invalid parameter to chmod.\n");
            break;
         case ENOENT:
            fprintf( stderr, "File %s not found\n", filename );
            break;
         default:
            // Should never be reached
            fprintf( stderr, "Unexpected error in chmod.\n" );
       }
   }
   else
   {
      if (mask == _S_IREAD)
        printf( "Mode set to read-only\n" );
      else if (mask & _S_IWRITE)
        printf( "Mode set to read/write\n" );
   }
   fflush(stderr);
}

int main( void )
{

   // Create or append to a file.
   system( "echo /* End of file */ >> crt_chmod.c_input" );

   // Set file mode to read-only:
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );

   system( "echo /* End of file */ >> crt_chmod.c_input " );

   // Change back to read/write:
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );

   system( "echo /* End of file */ >> crt_chmod.c_input " );
}
```

```Output

A line of text.
```

```Output

      A line of text.Mode set to read-only
Access is denied.
Mode set to read/write
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_stat, _wstat Fonksiyonlar](stat-functions.md)<br/>
