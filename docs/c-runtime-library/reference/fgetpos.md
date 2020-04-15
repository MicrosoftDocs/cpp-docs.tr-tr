---
title: fgetpos
ms.date: 4/2/2020
api_name:
- fgetpos
- _o_fgetpos
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
- fgetpos
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
ms.openlocfilehash: 0c16150a6240068e1453ec90b396c87ab9ece5a4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346917"
---
# <a name="fgetpos"></a>fgetpos

Bir akışın dosya konumu göstergesini alır.

## <a name="syntax"></a>Sözdizimi

```C
int fgetpos(
   FILE *stream,
   fpos_t *pos
);
```

### <a name="parameters"></a>Parametreler

*Akışı*<br/>
Hedef akışı.

*Pos*<br/>
Konum göstergesi depolama.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **fgetpos** 0 döndürür. Hata da, sıfır olmayan bir değer döndürür ve aşağıdaki bildirim sabitlerinden birine **errno** ayarlar (STDIO'da tanımlanır). H): **EBADF**, belirtilen akış geçerli bir dosya işaretçisi olmadığı veya erişilebilir olmadığı veya erişilen olmadığı anlamına gelir veya **EINVAL**, bu *akış* değeri veya *pos* değeri geçersiz olduğu anlamına gelir, ya da null işaretçi si gibi. *Akış* veya *pos* **bir NULL** işaretçisiyse, işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır.

## <a name="remarks"></a>Açıklamalar

**Fgetpos** işlevi *akış* bağımsız değişkeninin dosya konumu göstergesinin geçerli değerini alır ve *onu pos*tarafından işaret edilen nesnede depolar. **Fsetpos** işlevi daha sonra *akış* bağımsız değişkeninin işaretçisini **fgetpos'un** çağrıldığı anda konumuna sıfırlamak için *pos'ta* depolanan bilgileri kullanabilir. *Pos* değeri dahili bir biçimde saklanır ve yalnızca **fgetpos** ve **fsetpos**tarafından kullanılmak üzere tasarlanmıştır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fgetpos**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

## <a name="input-crt_fgetpostxt"></a>Giriş: crt_fgetpos.txt

```Input
fgetpos gets a stream's file-position indicator.
```

### <a name="output-crt_fgetpostxt"></a>Çıktı crt_fgetpos.txt

```Output
after fgetpos: gets a stream
after fsetpos: gets a stream
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[fsetpos](fsetpos.md)<br/>
