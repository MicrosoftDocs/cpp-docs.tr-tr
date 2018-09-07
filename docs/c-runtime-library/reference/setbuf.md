---
title: setbuf | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- setbuf
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
- setbuf
dev_langs:
- C++
helpviewer_keywords:
- setbuf function
- stream buffering
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea1c979b261b81f80d95e4219f948dd2a3f5849e
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100359"
---
# <a name="setbuf"></a>setbuf

Denetim akışı arabelleğe alma. Bu işlev kullanım dışı; kullanma [setvbuf](setvbuf.md) yerine.

## <a name="syntax"></a>Sözdizimi

```C
void setbuf(
   FILE *stream,
   char *buffer
);
```

### <a name="parameters"></a>Parametreler

*Stream*<br/>
İşaretçi **dosya** yapısı.

*Arabellek*<br/>
Kullanıcı tarafından ayrılan bir arabellek.

## <a name="remarks"></a>Açıklamalar

**Setbuf** işlev denetimleri için arabelleğe alma *stream*. *Stream* bağımsız değişkeni, okuma yazılan veya açık bir dosyaya başvurmalıdır. Varsa *arabellek* bağımsız değişkeni **NULL**, hazırlanmamış arabelleğe alınan bir akıştır. Arabellek uzunluğu bir karakter dizisi olarak işaret etmiyor, varsa **BUFSIZ**burada **BUFSIZ** STDIO içinde tanımlanan arabellek boyutu olan. H Kullanıcı tarafından belirtilen arabellek, belirtilen akışa için varsayılan sistem tarafından ayrılmış arabellek yerine g/ç için kullanılan arabelleğe alma. **Stderr** akış varsayılan olarak beklemediğiniz arabelleğe alınan ancak kullanabilirsiniz **setbuf** arabelleklere atamak **stderr**.

**setbuf** almıştır [setvbuf](setvbuf.md), yeni kodu için tercih edilen yordamı olduğu. **setbuf** mevcut kodlarda uyumluluk için tutulmaktadır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setbuf**|\<stdio.h >|

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fclose, _fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[setvbuf](setvbuf.md)<br/>
