---
title: fgetpos | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- fgetpos
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
- fgetpos
dev_langs:
- C++
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b111a911083354c8d9478b2c914a0a5f7dfe7725
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397391"
---
# <a name="fgetpos"></a>fgetpos

Bir akışın dosya konumu göstergesi alır.

## <a name="syntax"></a>Sözdizimi

```C
int fgetpos(
   FILE *stream,
   fpos_t *pos
);
```

### <a name="parameters"></a>Parametreler

*Akış*<br/>
Hedef akış.

*POS*<br/>
Konum göstergesi depolama.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **fgetpos** 0 döndürür. İsteğe bağlı olarak, arıza sıfır olmayan bir değer döndürür ve ayarlar **errno** aşağıdakilerden birini bildirim Sabitleri (STDIO içinde tanımlanmıştır. H): **EBADF**, belirtilen stream başka bir deyişle, geçerli dosya işaretçisi değil veya erişilebilir değil veya **EINVAL**, anlamına *akış* veya değeri*pos* olduğu ya da null işaretçi gelmesi gibi geçersiz. Varsa *akış* veya *pos* olan bir **NULL** işaretçisi işlevi çağırır geçersiz parametre işleyicisi açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>Açıklamalar

**Fgetpos** işlevi alır geçerli değeri *akış* bağımsız değişkeninin dosya konumu göstergesi ve nesne içinde işaret için tarafından depoları *pos*. **Fsetpos** işlevi daha sonra depolanan bilgileri kullanmak *pos* sıfırlamak için *akış* bağımsız değişkeninin işaretçi zaman konumuna **fgetpos** çağrıldı. *Pos* değeri iç bir biçimde depolanır ve yalnızca tarafından kullanılmaya yöneliktir **fgetpos** ve **fsetpos**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fgetpos**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fgetpos.c
// This program uses fgetpos and fsetpos to
// return to a location in a file.

#include <stdio.h>

int main( void )
{
   FILE   *stream;
   fpos_t pos;
   char   buffer[20];

   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {
      perror( "Trouble opening file" );
      return -1;
   }

   // Read some data and then save the position.
   fread( buffer, sizeof( char ), 8, stream );
   if( fgetpos( stream, &pos ) != 0 ) {
      perror( "fgetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fgetpos: %.13s\n", buffer );

   // Restore to old position and read data
   if( fsetpos( stream, &pos ) != 0 ) {
      perror( "fsetpos error" );
      return -1;
   }

   fread( buffer, sizeof( char ), 13, stream );
   printf( "after fsetpos: %.13s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crtfgetpostxt"></a>Giriş: crt_fgetpos.txt

```Input
fgetpos gets a stream's file-position indicator.
```

### <a name="output-crtfgetpostxt"></a>Çıktı crt_fgetpos.txt

```Output
after fgetpos: gets a stream
after fsetpos: gets a stream
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fsetpos](fsetpos.md)<br/>
