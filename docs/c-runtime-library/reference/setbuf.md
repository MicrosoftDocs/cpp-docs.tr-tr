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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: f96cffb8770cda78ebff8d873b441ddc288bc41f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332071"
---
# <a name="setbuf"></a>setbuf

Akış arabelleğe alma denetimleri. Bu işlev amortismana hazırdır; yerine [setvbuf](setvbuf.md) kullanın.

## <a name="syntax"></a>Sözdizimi

```C
void setbuf(
   FILE *stream,
   char *buffer
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
**DOSYA** yapısı için işaretçi.

*Arabellek*<br/>
Kullanıcı tarafından tahsis edilen arabellek.

## <a name="remarks"></a>Açıklamalar

**Setbuf** işlevi *akış*için arabelleğe alma denetimleri. *Akış* bağımsız değişkeni, okunmamış veya yazılmayan açık bir dosyaya başvurmalıdır. Arabellek bağımsız *değişkeni* **NULL**ise, akış arabelleğe almaz. Değilse, arabellek **bufsiz** STDIO tanımlanan arabellek boyutu uzunluk **BUFSIZ**bir karakter dizi işaret etmelidir. H. Kullanıcı tarafından belirtilen arabellek, verilen akış için varsayılan sistem ayrılmış arabellek yerine, G/Ç arabellek için kullanılır. **Stderr** akışı varsayılan olarak arabelleğe almaz, ancak **stderr**için arabellek atamak için **setbuf** kullanabilirsiniz.

**setbuf** [setvbuf](setvbuf.md), yeni kod için tercih edilen rutin yerini almıştır. **setvbuf**aksine, **setbuf** hataları raporlama yolu yoktur. **setvbuf** ayrıca hem arabellek modunu hem de arabellek boyutunu kontrol etmenizi sağlar. **setbuf** varolan kod ile uyumluluk için var.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setbuf**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setvbuf](setvbuf.md)<br/>
