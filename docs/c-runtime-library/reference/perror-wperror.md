---
title: perror, _wperror
ms.date: 11/04/2016
apiname:
- _wperror
- perror
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wperror
- _tperror
- perror
helpviewer_keywords:
- _tperror function
- tperror function
- wperror function
- error messages, printing
- printing error messages
- _wperror function
- perror function
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
ms.openlocfilehash: c9026a96ecc74640eb2bcd7004d5d1e0fc287e38
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156115"
---
# <a name="perror-wperror"></a>perror, _wperror

Bir hata iletisi yazdırın.

## <a name="syntax"></a>Sözdizimi

```C
void perror(
   const char *message
);
void _wperror(
   const wchar_t *message
);
```

### <a name="parameters"></a>Parametreler

*message*<br/>
Yazdırmak için dize iletisi.

## <a name="remarks"></a>Açıklamalar

**Perror** işlevi bir hata iletisi yazdırır **stderr**. **_wperror** geniş karakterli sürümüdür **_perror**; *ileti* bağımsız değişkeni **_wperror** geniş karakterli bir dizedir. **_wperror** ve **_perror** aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tperror**|**perror**|**perror**|**_wperror**|

*İleti* bir iki nokta üst üste, ardından bir sistem hatası iletisi hata oluşturan son kitaplık çağrısı için ilk olarak, yazdırılır ve son yeni satır karakteriyle. Varsa *ileti* null bir işaretçi veya boş bir dize işaretçisi **perror** yalnızca sistem hatası iletisi yazdırır.

Hata numarasını değişkeninde depolanan [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) (ERRNO içinde tanımlanır. H). Sistem hata mesajlarına değişken üzerinden erişilen [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), hata numarasıyla sıralanan mesajlar dizisi olan. **perror** kullanarak ilgili hata iletisi yazdırır **errno** değeri bir dizin olarak **_sys_errlist**. Değişkenin değerini [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) içindeki öğelerin maksimum sayısını olarak tanımlanan **_sys_errlist** dizisi.

Doğru sonuçlar için çağrı **perror** sonra hemen bir yordamı ile ilgili bir hata döndürür. Aksi halde, sonraki çağrılar üzerine yazıp **errno** değeri.

Windows işletim sistemi, bazı **errno** değerleri ERRNO içinde listelenir. H kullanılmayan. Bu değerler, UNIX işletim sistemi tarafından kullanılmak üzere ayrılmıştır. Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bir listesi için **errno** Windows işletim sistemi tarafından kullanılan değerler. **perror** için boş bir dize yazdırır **errno** değeri bu platformlar tarafından kullanılmaz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**perror**|\<stdio.h > veya \<stdlib.h >|
|**_wperror**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

## <a name="example"></a>Örnek

```C
// crt_perror.c
// compile with: /W3
/* This program attempts to open a file named
* NOSUCHF.ILE. Because this file probably doesn't exist,
* an error message is displayed. The same message is
* created using perror, strerror, and _strerror.
*/

#include <fcntl.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <io.h>
#include <stdlib.h>
#include <stdio.h>
#include <string.h>
#include <share.h>

int main( void )
{
   int  fh;

   if( _sopen_s( &fh, "NOSUCHF.ILE", _O_RDONLY, _SH_DENYNO, 0 ) != 0 )
   {
      /* Three ways to create error message: */
      perror( "perror says open failed" );
      printf( "strerror says open failed: %s\n",
         strerror( errno ) ); // C4996
      printf( _strerror( "_strerror says open failed" ) ); // C4996
      // Note: strerror and _strerror are deprecated; consider
      // using strerror_s and _strerror_s instead.
   }
   else
   {
      printf( "open succeeded on input file\n" );
      _close( fh );
   }
}
```

```Output
perror says open failed: No such file or directory
strerror says open failed: No such file or directory
_strerror says open failed: No such file or directory
```

## <a name="see-also"></a>Ayrıca bkz.

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[clearerr](clearerr.md)<br/>
[ferror](ferror.md)<br/>
[strerror, _strerror, _wcserror, \__wcserror](strerror-strerror-wcserror-wcserror.md)<br/>
