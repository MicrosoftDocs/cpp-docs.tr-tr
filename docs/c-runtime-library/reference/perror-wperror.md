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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 64b9abe6313cc13e1e20f8f66ba486cdeb3e4892
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919328"
---
# <a name="perror-_wperror"></a>perror, _wperror

Bir hata iletisi yazdır.

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
Yazdırılacak dize iletisi.

## <a name="remarks"></a>Açıklamalar

**PError** işlevi **stderr**'e bir hata iletisi yazdırır. **_wperror** , **_perror**geniş karakterli bir sürümüdür; _wperror *ileti* bağımsız değişkeni **_wperror** geniş karakterli bir dizedir. **_wperror** ve **_perror** aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tperror**|**perror**|**perror**|**_wperror**|

*ileti* önce, ardından iki nokta üst üste, ardından hatayı üreten son kitaplık çağrısının sistem hata iletisi ve son olarak bir yeni satır karakteri ile yazdırılır. *İleti* null işaretçisiyse veya null bir dize işaretçisiyse, **pError** yalnızca sistem hata iletisini yazdırır.

Hata numarası [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) değişkeninde SAKLANıR (errno içinde tanımlanmıştır). H). Sistem hata iletilerine, hata numarasına göre sıralanmış bir ileti dizisi olan [_sys_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)değişken aracılığıyla erişilir. **pError** , **_sys_errlist**için dizin olarak **errno** değeri kullanarak uygun hata iletisini yazdırır. [_Sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) değişkeninin değeri, **_sys_errlist** dizisindeki en fazla öğe sayısı olarak tanımlanır.

Doğru sonuçlar için, bir kitaplık yordamı hata ile döndüğünde **pError** 'ı hemen çağırın. Aksi halde, sonraki çağrılar **errno** değerinin üzerine yazabilir.

Windows işletim sisteminde, bazı errno 'da listelenen bir değer **yok** . H kullanılmıyor. Bu değerler UNIX işletim sistemi tarafından kullanılmak üzere ayrılmıştır. Windows işletim sistemi tarafından kullanılan **errno** değeri listesi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) . **pError** , bu platformlar tarafından kullanılmayan herhangi bir **errno** değeri için boş bir dize yazdırır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**perror**|\<stdio. h> veya \<Stdlib. h>|
|**_wperror**|\<stdio. h> veya \<wchar. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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
[strerror, _strerror, _wcserror \__wcserror](strerror-strerror-wcserror-wcserror.md)<br/>
