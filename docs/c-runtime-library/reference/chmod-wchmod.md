---
title: _chmod, _wchmod
ms.date: 11/04/2016
api_name:
- _chmod
- _wchmod
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
ms.openlocfilehash: b224133212f19627a8f975dbbe8c80176e29f112
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939201"
---
# <a name="_chmod-_wchmod"></a>_chmod, _wchmod

Dosya izni ayarlarını değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
int _chmod( const char *filename, int pmode );
int _wchmod( const wchar_t *filename, int pmode );
```

### <a name="parameters"></a>Parametreler

*kısaltın*<br/>
Mevcut dosyanın adı.

*pmode*<br/>
Dosya için izin ayarı.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevler, izin ayarı başarıyla değiştiyse 0 döndürür. -1 dönüş değeri hata olduğunu gösterir. Belirtilen dosya bulunamazsa, **errno** , **ENOENT**olarak ayarlanır; bir parametre geçersizse, **errno** **EINVAL**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**_Chmod** işlevi dosya *adı*ile belirtilen dosyanın izin ayarını değiştirir. İzin ayarı, dosyaya okuma ve yazma erişimini denetler. *Pmode* tamsayı ifadesi, Sys\stat.exe içinde tanımlanan aşağıdaki bildirim sabitlerinden birini veya her ikisini içerir.

| *pmode* | Açıklama |
|-|-|
| **\_S\_İREAD** | Yalnızca okuma izni verilir. |
| **\_S\_İWRİTE** | Yazma izni veriliyor. (Aslında, okuma ve yazma izni verir.) |
| **\_S\_IREAD** &#124; **SIWRİTE\_ \_** | Okuma ve yazma izni verildi. |

Her iki sabit de verildiğinde, bit düzeyinde OR işleci ( **\|** ) ile birleştirilir. Yazma izni verilmezse, dosya salt okunurdur. Tüm dosyaların her zaman okunabilir olduğunu unutmayın; salt yazılır izin vermek mümkün değildir. Bu nedenle, **_s_iwrite** ve **_s_iread** \| **_s_iwrite** modları eşdeğerdir.

**_wchmod** , **_chmod**; öğesinin geniş karakterli bir sürümüdür. **_wchmod** için *filename* bağımsız değişkeni geniş karakterli bir dizedir. **_wchmod** ve **_chmod** aynı şekilde davranır.

Bu işlev, parametrelerini doğrular. *Pmode* , bildirim sabitlerinden birinin birleşimi değilse veya diğer bir sabitler kümesini içeriyorsa, işlev bunları yoksayar. *Filename* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev-1 döndürür.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchmod**|**_chmod**|**_chmod**|**_wchmod**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_chmod**|\<GÇ. h >|\<sys/Types. h >, \<sys/stat. h >, \<errno. h >|
|**_wchmod**|\<GÇ. h > veya \<wchar. h >|\<sys/Types. h >, \<sys/stat. h >, \<errno. h >|

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
[_stat, _wstat Işlevleri](stat-functions.md)<br/>
