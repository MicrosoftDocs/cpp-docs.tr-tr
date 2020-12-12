---
description: 'Daha fazla bilgi edinin: setvarabelleğe'
title: setvbuf
ms.date: 4/2/2020
api_name:
- setvbuf
- _o_setvbuf
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setvbuf
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
ms.openlocfilehash: 8010bdea7a2542e8797ea8c352d9221cdb4cc0b9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303498"
---
# <a name="setvbuf"></a>setvbuf

Akış arabelleği ve arabellek boyutunu denetler.

## <a name="syntax"></a>Sözdizimi

```C
int setvbuf(
   FILE *stream,
   char *buffer,
   int mode,
   size_t size
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

*arabelleğin*<br/>
Kullanıcı tarafından ayrılan arabellek.

*modundaysa*<br/>
Arabelleğe alma modu.

*boyutla*<br/>
Bayt cinsinden arabellek boyutu. İzin verilen Aralık: 2 <= *size* <= INT_MAX (2147483647). Dahili olarak, *Boyut* için sağlanan değer, 2 ' nin en yakın katına yuvarlanır.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa 0 döndürür.

*Stream* **null** ise veya *mod* veya *Boyut* geçerli bir değişiklik içinde değilse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev-1 döndürür ve **errno** 'ı **EINVAL** olarak ayarlar.

Bu ve diğer hata kodları hakkında bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Setvbuffer** işlevi, programın *akış* için hem arabelleğe alma hem de arabellek boyutunu denetlemesine izin verir. *akış* , açılmasından bu yana bir g/ç işlemi olmayan açık bir dosyaya başvurmalıdır. *Arabelleğe* göre işaret eden dizi, **null** olmadığı sürece arabellek olarak kullanılır. Bu durumda, **setvbuffer** , uzunluk *boyutu*/2 2 bayt olan otomatik olarak ayrılmış bir arabellek kullanır \* .

Mod **_IOFBF**, **_IOLBF** veya **_IONBF** olmalıdır. *Mod* **_IOFBF** veya **_IOLBF** ise, *Boyut* arabelleğin boyutu olarak kullanılır. *Mod* **_IONBF**, akış arabelleğe alınmamış ve *Boyut* ve *arabellek* yok sayılır. *Mod* ve anlamları değerleri şunlardır:

|*mod* değeri|Anlamı|
|-|-|
| **_IOFBF** | Tam arabelleğe alma; diğer bir deyişle *, arabellek* ve *Boyut* arabelleği boyutu olarak kullanılır. *Arabellek* **null** ise, otomatik olarak ayrılan arabellek *boyutu* baytları kullanılır. |
| **_IOLBF** | Bazı sistemlerde bu, satır arabelleğe almayı sağlar. Ancak, Win32 için davranış **_IOFBF** tam arabelleğe alma ile aynıdır. |
| **_IONBF** | *Arabellek veya* *boyuttan* bağımsız olarak hiçbir arabellek kullanılmaz. |

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setvbuf**|\<stdio.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="example"></a>Örnek

```C
// crt_setvbuf.c
// This program opens two streams: stream1
// and stream2. It then uses setvbuf to give stream1 a
// user-defined buffer of 1024 bytes and stream2 no buffer.
//

#include <stdio.h>

int main( void )
{
   char buf[1024];
   FILE *stream1, *stream2;

   if( fopen_s( &stream1, "data1", "a" ) == 0 &&
       fopen_s( &stream2, "data2", "w" ) == 0 )
   {
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )
         printf( "Incorrect type or size of buffer for stream1\n" );
      else
         printf( "'stream1' now has a buffer of 1024 bytes\n" );
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )
         printf( "Incorrect type or size of buffer for stream2\n" );
      else
         printf( "'stream2' now has no buffer\n" );
      _fcloseall();
   }
}
```

```Output
'stream1' now has a buffer of 1024 bytes
'stream2' now has no buffer
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setbuf](setbuf.md)<br/>
