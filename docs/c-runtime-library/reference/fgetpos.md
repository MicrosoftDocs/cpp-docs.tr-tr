---
title: fgetpos
ms.date: 11/04/2016
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
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
ms.openlocfilehash: e213c9830ffe6edf04b12a80828f14cc48f77524
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333936"
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

*Stream*<br/>
Hedef akış.

*POS*<br/>
Depolama konumu göstergesi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **fgetpos** 0 döndürür. İsteğe bağlı olarak hata durumunda, sıfır olmayan bir değer döndürür ve ayarlar **errno** aşağıdakilerden birini bildirim Sabitleri (STDIO içinde tanımlanır. H): **EBADF**, belirtilen akış başka bir deyişle, geçerli dosya işaretçisi değil veya erişilebilir değil veya **EINVAL**, anlamına *stream* değeri ya da değerini *pos*olduğu ya da bir null işaretçi ise gibi geçersiz. Varsa *stream* veya *pos* olduğu bir **NULL** işaretçisi işlevi çağıran geçersiz parametre işleyicisi açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md).

## <a name="remarks"></a>Açıklamalar

**Fgetpos** işlevi, geçerli değerini alır *stream* bağımsız değişkenin dosya konumu göstergesi ve depoları içinde nesne tarafından işaret edilen *pos*. **Fsetpos** işlevi daha sonra depolanan bilgileri kullanmak *pos* sıfırlamak için *stream* bağımsız değişkenin konumuna zaman işaretçisine **fgetpos** çağrıldı. *Pos* değeri iç bir biçimde depolanır ve yalnızca tarafından kullanılması amaçlanan **fgetpos** ve **fsetpos**.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fgetpos**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

### <a name="output-crtfgetpostxt"></a>Çıkış crt_fgetpos.txt

```Output
after fgetpos: gets a stream
after fsetpos: gets a stream
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fsetpos](fsetpos.md)<br/>
