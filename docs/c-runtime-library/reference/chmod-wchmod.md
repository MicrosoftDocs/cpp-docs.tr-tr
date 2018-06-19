---
title: _chmod, _wchmod | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _chmod function
- wchmod function
- file permissions [C++]
- chmod function
- files [C++], changing permissions
- _wchmod function
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0e4944f871195b276189014ed9d5d294b9b445fd
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32399962"
---
# <a name="chmod-wchmod"></a>_chmod, _wchmod

Dosya izni ayarlarını değiştirir.

## <a name="syntax"></a>Sözdizimi

```C
int _chmod( const char *filename, int pmode );
int _wchmod( const wchar_t *filename, int pmode );
```

### <a name="parameters"></a>Parametreler

*Dosya adı*<br/>
Varolan dosyanın adı.

*pmode*<br/>
Dosya izni ayarı.

## <a name="return-value"></a>Dönüş Değeri

İzni ayarı başarıyla değiştirilirse bu işlevler 0 döndürür. Dönüş değeri-1 hata gösterir. Belirtilen dosya bulunamadı, **errno** ayarlanır **ENOENT**; bir parametre geçersiz **errno** ayarlanır **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Chmod** işlevi tarafından belirtilen dosya izni ayarı değişiklikleri *filename*. Okuma ve yazma erişimi dosya izni ayarı denetler. Tamsayı ifade *pmode* birini veya her ikisini SYS\Stat.h tanımlanan aşağıdaki bildirim sabitleri içerir.

|*pmode*|Açıklama|
|-|-|
**_S_IREAD**|Yalnızca okuma izin verilir.
**_S_IWRITE**|Yazma izin verilir. (Geçerli, okuma ve yazma izin verir.)
**_S_IREAD** &AMP;#124; **_S_IWRITE**|Okuma ve yazma izin verilir.

Her iki sabitleri verildiğinde, bunlar Bitsel ile birleştirilir veya işleci (**|**). Yazma izni verilmedi, dosya salt okunurdur. Tüm dosyaları her zaman okunabilir olduğunu unutmayın; salt yazılır izin vermek mümkün değildir. Bu nedenle, modları **_s_ıwrıte** ve **_s_ıread** | **_s_ıwrıte** eşdeğerdir.

**_wchmod** bir joker karakter sürümü **_chmod**; *filename* bağımsız değişkeni **_wchmod** bir joker karakter dizesidir. **_wchmod** ve **_chmod** Aksi takdirde aynı şekilde davranır.

Bu işlev parametrelerini doğrular. Varsa *pmode* bildirim sabitleri bir birleşimini değil veya başka bir kümesi içerir, sabitleri işlevi yalnızca bu yok sayar. Varsa *filename* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve işlev -1 döndürür.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tchmod**|**_chmod**|**_chmod**|**_wchmod**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_chmod**|\<io.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|
|**_wchmod**|\<io.h > veya \<wchar.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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
