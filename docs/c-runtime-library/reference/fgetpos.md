---
description: 'Daha fazla bilgi edinin: fgetpos'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 72ee6e683d568de1650d5a046050230fa86dee24
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151768"
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

*ka*<br/>
Hedef akış.

*'un*<br/>
Konum göstergesi depolaması.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa **fgetpos** 0 döndürür. Hatada, sıfır dışında bir değer döndürür ve **errno** değerini aşağıdaki bildirim sabitlerinden birine ayarlar (stdio içinde tanımlanmıştır). H): **EBADF**, belirtilen akış geçerli bir dosya işaretçisi değil veya erişilebilir değil ya da **EINVAL**, yani *Stream* değeri ya da *POS* değeri geçersiz olduğu için (örneğin, null işaretçisiyse). *Stream* veya *POS* **null** bir Işaretçisiyse, işlev, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır.

## <a name="remarks"></a>Açıklamalar

**Fgetpos** işlevi, *akış* bağımsız değişkeninin dosya konumu göstergesinin geçerli değerini alır ve *POS* tarafından işaret edilen nesnede depolar. **Fsetpos** işlevi daha sonra *POS* 'ta depolanan bilgileri, **fgetpos** çağrıldığında *akış* bağımsız değişkeninin işaretçisini konumuna sıfırlamak için kullanabilir. *POS* değeri dahili bir biçimde depolanır ve yalnızca **fgetpos** ve **fsetpos** tarafından kullanılmak üzere tasarlanmıştır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fgetpos**|\<stdio.h>|

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

## <a name="input-crt_fgetpostxt"></a>Giriş: crt_fgetpos.txt

```Input
fgetpos gets a stream's file-position indicator.
```

### <a name="output-crt_fgetpostxt"></a>Çıkış crt_fgetpos.txt

```Output
after fgetpos: gets a stream
after fsetpos: gets a stream
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fsetpos](fsetpos.md)<br/>
