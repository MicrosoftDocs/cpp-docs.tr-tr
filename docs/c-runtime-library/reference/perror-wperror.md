---
title: perror, _wperror
ms.date: 4/2/2020
api_name:
- _wperror
- perror
- _o__wperror
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 0c50e77863b4b136ac59b6f79d8e529691032609
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338540"
---
# <a name="perror-_wperror"></a>perror, _wperror

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

*İleti*<br/>
Yazdırmak için string iletisi.

## <a name="remarks"></a>Açıklamalar

**perror** işlevi **stderr**için bir hata iletisi yazdırır. **_wperror** **_perror**geniş karakterli bir versiyonudur; **_wperror** için *ileti* bağımsız değişkeni geniş karakterli bir dizedir. **_wperror** ve **_perror** aynı şekilde davranan.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tperror**|**perror**|**perror**|**_wperror**|

*ileti* önce yazdırılır, ardından bir üst üste, ardından hatayı oluşturan son kitaplık çağrısı için sistem hatası iletisi ve son olarak da yeni bir satır karakteri tarafından yazdırılır. *İleti* null işaretçiveya null dize işaretçisi ise, **perror** yalnızca sistem hata iletisini yazdırır.

Hata numarası değişken [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) (ERRNO tanımlanır) depolanır. H). Sistem hata iletilerine, hata numarasıyla sıralanan iletiler dizisi olan [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)değişkeni üzerinden erişilir. **perror,** _sys_errlist için bir dizin olarak **errno** değerini kullanarak uygun hata iletisini yazdırır. **_sys_errlist** Değişken [_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) **değeri, _sys_errlist** dizisindeki en yüksek öğe sayısı olarak tanımlanır.

Doğru sonuçlar için, kitaplık yordamı bir hatayla döndükten hemen sonra **perror'ı** arayın. Aksi takdirde, sonraki aramalar **errno** değerinin üzerine yazabilir.

Windows işletim sisteminde, ERRNO'da listelenen bazı **errno** değerleri. H kullanılmaz. Bu değerler UNIX işletim sistemi tarafından kullanılmak üzere ayrılmıştır. Windows işletim sistemi tarafından kullanılan **errno** değerlerinin listesi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bakın. **perror,** bu platformlar tarafından kullanılmayan herhangi bir **errno** değeri için boş bir dize yazdırır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**perror**|\<stdio.h> \<veya stdlib.h>|
|**_wperror**|\<stdio.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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
[strerror, _strerror, \__wcserror, _wcserror](strerror-strerror-wcserror-wcserror.md)<br/>
