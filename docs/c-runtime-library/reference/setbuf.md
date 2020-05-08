---
title: setbuf
ms.date: 4/2/2020
api_name:
- setbuf
- _o_setbuf
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
- setbuf
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
ms.openlocfilehash: 40f23db88abf9733eada9e775aacda83cba5829a
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82910341"
---
# <a name="setbuf"></a>setbuf

Akış arabelleğini denetler. Bu işlev kullanım dışıdır; Bunun yerine [setvarabelleğe](setvbuf.md) kullanın.

## <a name="syntax"></a>Sözdizimi

```C
void setbuf(
   FILE *stream,
   char *buffer
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

*arabelleğin*<br/>
Kullanıcı tarafından ayrılan arabellek.

## <a name="remarks"></a>Açıklamalar

**Setarabelleğe** işlevi *akış*için arabelleğe almayı denetler. *Stream* bağımsız değişkeni, okunamaz veya yazılmayan açık bir dosyaya başvurmalıdır. *Buffer* bağımsız değişkeni **null**ise, akışın ara belleğe alınmamış olması gerekir. Aksi takdirde, arabellek **bufsız**length bir karakter dizisine işaret etmelidir; burada **BUFSıZ** , stdio içinde tanımlanan arabellek boyutudur. Olsun. Belirtilen akış için varsayılan sistem tarafından ayrılan arabellek yerine Kullanıcı tarafından belirtilen arabellek g/ç arabelleğe alma için kullanılır. **Stderr** akışı varsayılan olarak arabelleğe alınmamış, ancak **stderr**'e arabellekler atamak için **setarabelleğe** kullanabilirsiniz.

**setarabelleğe** , yeni kod için tercih edilen yordam olan [setvarabelleğe](setvbuf.md)ile değiştirilmiştir. **Setvarabelleğe**'nin aksine, **setarabelleğe** hata bildirme yolu yoktur. **setvbuffer** Ayrıca hem arabelleğe alma modunu hem de arabellek boyutunu denetlemenize olanak tanır. Mevcut kodla uyumluluk için **setarabelleğe** var.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setbuf**|\<stdio. h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_setbuf.c
// compile with: /W3
// This program first opens files named DATA1 and
// DATA2. Then it uses setbuf to give DATA1 a user-assigned
// buffer and to change DATA2 so that it has no buffer.

#include <stdio.h>

int main( void )
{
   char buf[BUFSIZ];
   FILE *stream1, *stream2;

   fopen_s( &stream1, "data1", "a" );
   fopen_s( &stream2, "data2", "w" );

   if( (stream1 != NULL) && (stream2 != NULL) )
   {
      // "stream1" uses user-assigned buffer:
      setbuf( stream1, buf ); // C4996
      // Note: setbuf is deprecated; consider using setvbuf instead
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );

      // "stream2" is unbuffered
      setbuf( stream2, NULL ); // C4996
      printf( "stream2 buffering disabled\n" );
      _fcloseall();
   }
}
```

```Output
stream1 set to user-defined buffer at: 0012FCDC
stream2 buffering disabled
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setvbuf](setvbuf.md)<br/>
