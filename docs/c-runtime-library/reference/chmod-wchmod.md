---
title: _chmod, _wchmod
ms.date: 11/04/2016
apiname:
- _chmod
- _wchmod
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
ms.openlocfilehash: 278ee1e6dda9e153b55676ce5c0ca389f383efd1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62348478"
---
# <a name="chmod-wchmod"></a>_chmod, _wchmod

Dosya izin ayarlarını değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
int _chmod( const char *filename, int pmode );
int _wchmod( const wchar_t *filename, int pmode );
```

### <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
Var olan dosyanın adı.

*pmode*<br/>
Dosya için izin ayarının.

## <a name="return-value"></a>Dönüş Değeri

İzin başarıyla değiştirilirse bu işlevler, 0 döndürür. Dönüş değeri-1 hata gösterir. Belirtilen dosya bulunamadı, **errno** ayarlanır **ENOENT**; bir parametre geçersiz **errno** ayarlanır **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Chmod** işlevi tarafından belirtilen dosya izni ayarını değiştirir *filename*. İzin ayarının okuma ve dosyaya yazma erişimi denetler. Tamsayı ifadesini *pmode* birini veya her ikisini SYS\Stat.h tanımlanan aşağıdaki bildirim sabitleri içerir.

| *pmode* | Açıklama |
|-|-|
| **\_S\_IREAD** | Yalnızca okuma izin verilir. |
| **\_S\_IWRITE** | Yazma izin verilir. (Aslında, okuma ve yazma verir.) |
| **\_S\_IREAD** &#124; **\_S\_IWRITE** | Okuma ve yazma izin verilir. |

Her iki sabitleri verildiğinde, bunlar ile bit düzeyinde birleştirilir veya işleci (**\|**). Yazma izni verilmemişse, dosyanın salt okunur. Tüm dosyaları her zaman okunabilir olduğunu unutmayın; Salt yazma izni vermek mümkün değildir. Bu nedenle, modları **_s_ıwrıte** ve **_s_ıread** \| **_s_ıwrıte** eşdeğerdir.

**_wchmod** geniş karakterli sürümüdür **_chmod**; *filename* bağımsız değişkeni **_wchmod** geniş karakterli bir dizedir. **_wchmod** ve **_chmod** aynı şekilde davranır.

Bu işlev, parametrelerini doğrular. Varsa *pmode* bildirim sabitlerinden birini birleşimi değil veya alternatif bir kümesini içerir, sabitleri işlevi yalnızca bu yok sayar. Varsa *filename* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlev -1 döndürür.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchmod**|**_chmod**|**_chmod**|**_wchmod**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_chmod**|\<io.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|
|**_wchmod**|\<io.h > veya \<wchar.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[_access, _waccess](access-waccess.md)<br/>
[_creat, _wcreat](creat-wcreat.md)<br/>
[_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_stat, _wstat işlevleri](stat-functions.md)<br/>
