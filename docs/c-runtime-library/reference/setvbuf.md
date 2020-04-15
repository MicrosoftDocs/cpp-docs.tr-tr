---
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 203265a8dd85854bcedd737359b856fdc4cce04d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316257"
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

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

*Arabellek*<br/>
Kullanıcı tarafından tahsis edilen arabellek.

*Modu*<br/>
Arabelleğe alma modu.

*Boyutu*<br/>
Arabellek boyutu baytlar içinde. İzin verilebilen aralık: 2 <= *boyut* <= INT_MAX (2147483647). Dahili olarak, *boyut* için sağlanan değer 2'nin en yakın katlarına yuvarlanır.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür.

*Akış* **NULL**ise veya *mod* veya *boyut* geçerli bir değişiklik içinde değilse, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlev -1 döndürür ve **EINVAL** **için errno** ayarlar.

Bu ve diğer hata kodları hakkında bilgi için [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

## <a name="remarks"></a>Açıklamalar

**Setvbuf** işlevi, programın *akış*için hem arabellek hem de arabellek boyutunu denetlemesini sağlar. *akış* açıldığından beri bir G/Ç işleminden geçmedi açık bir dosyaya başvurmalıdır. *Arabellek* tarafından işaret edilen **dizi, NULL**olmadığı sürece arabellek olarak kullanılır, bu durumda **setvbuf** uzunluk *boyutu* \* /2 2 bayt otomatik olarak tahsis edilen bir arabellek kullanır.

Mod **_IOFBF,** **_IOLBF**veya **_IONBF**olmalıdır. *Mod* **_IOFBF** veya **_IOLBF**ise, *boyut* arabellek boyutu olarak kullanılır. *Mod* **_IONBF**ise, akış arabelleğe alınır ve *boyut* ve *arabellek* yoksayılır. *Mod* için değerler ve anlamları şunlardır:

|*mod* değeri|Anlamı|
|-|-|
| **_IOFBF** | Tam arabelleğe alma; yani *arabellek* arabellek olarak kullanılır ve *boyut* arabellek boyutu olarak kullanılır. *Arabellek* **NULL**ise, otomatik olarak tahsis edilen arabellek *boyutu* bayt uzun kullanılır. |
| **_IOLBF** | Bazı sistemler için bu satır arabelleğe alma sağlar. Ancak, Win32 için, davranış **_IOFBF** ile aynıdır - Tam Arabelleğe alma. |
| **_IONBF** | *Arabellek* veya *boyutu*ne olursa olsun, hiçbir arabellek kullanılır. |

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setvbuf**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setbuf](setbuf.md)<br/>
