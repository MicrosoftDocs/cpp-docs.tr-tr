---
title: setvbuf
ms.date: 11/04/2016
apiname:
- setvbuf
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- setvbuf
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
ms.openlocfilehash: d4336c6cc478a035fcc0b9b059a7161d58bc4442
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356322"
---
# <a name="setvbuf"></a>setvbuf

Akışı arabelleğe alma ve arabellek boyutu denetler.

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

*Stream*<br/>
İşaretçi **dosya** yapısı.

*Arabellek*<br/>
Kullanıcı tarafından ayrılan bir arabellek.

*Modu*<br/>
Arabelleğe alma modu.

*Boyutu*<br/>
Arabellek boyutu bayt cinsinden. İzin verilen aralık: 2 < = *boyutu* < = INT_MAX (2147483647). Dahili olarak, için sağlanan değer *boyutu* 2'in en yakın katına yuvarlanır.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür.

Varsa *stream* olduğu **NULL**, veya *modu* veya *boyutu* olduğu değil geçerli değişiklik içinde geçersiz parametre işleyicisi, açıklanan şekilde çağrılır [Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlev -1 döndürür ve kümeleri yürütülmesine izin veriliyorsa **errno** için **EINVAL**.

Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Setvbuf** işlevine izin verir, her iki kez arabelleğe alma denetlemek ve arabellek boyutu için program *stream*. *Akış* , açıldıktan sonra bir g/ç işlemi gerçekleştirmedi açık bir dosyaya başvurmalıdır. Dizi tarafından işaret edilen *arabellek* olduğu sürece bir arabellek olarak kullanılan **NULL**, bu durumda **setvbuf** kullandığı otomatik olarak ayrılan bir arabellek uzunluğu  *boyutu*/2 \* 2 baytı.

Modu olmalıdır **_ıofbf**, **_ıolbf**, veya **_ıonbf**. Varsa *modu* olduğu **_ıofbf** veya **_ıolbf**, ardından *boyutu* arabellek boyutu kullanılır. Varsa *modu* olduğu **_ıonbf**, akış arabellekten çıkarılan ve *boyutu* ve *arabellek* göz ardı edilir. Değerleri *modu* ve anlamlarını:

|*modu* değeri|Açıklama|
|-|-|
| **_IOFBF** | Tam arabelleğe; diğer bir deyişle, *arabellek* arabellek olarak kullanılır ve *boyutu* arabellek boyutu kullanılır. Varsa *arabellek* olduğu **NULL**, otomatik olarak ayrılan bir arabellek *boyutu* bayt uzunluğundadır kullanılır. |
| **_IOLBF** | Bazı sistemler için bu satırı arabelleğe almayı sağlar. Ancak, Win32 için aynı davranıştır **_ıofbf** -tam arabelleğe alma. |
| **_IONBF** | Arabellek kullanılan, bakılmaksızın *arabellek* veya *boyutu*. |

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setvbuf**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setbuf](setbuf.md)<br/>
