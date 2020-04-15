---
title: tmpfile_s
ms.date: 4/2/2020
api_name:
- tmpfile_s
- _o_tmpfile_s
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
- tmpfile_s
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
ms.openlocfilehash: 8f9dd58abdf1d3225341e40661c14ae3a5013257
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362469"
---
# <a name="tmpfile_s"></a>tmpfile_s

Geçici bir dosya oluşturur. [CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleri içeren [tmpfile'nin](tmpfile.md) bir sürümüdür.

## <a name="syntax"></a>Sözdizimi

```C
errno_t tmpfile_s(
   FILE** pFilePtr
);
```

### <a name="parameters"></a>Parametreler

*pFilePtr*<br/>
Oluşturulan işaretçinin adresini bir akışa depolamak için işaretçinin adresi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür, hata yla ilgili bir hata kodu.

### <a name="error-conditions"></a>Hata Koşulları

|*pFilePtr*|**Dönüş Değeri**|**Contents of***pFilePtr* içeriği  |
|----------------|----------------------|---------------------------------|
|**Null**|**Eınval**|değiştirilmedi|

Yukarıdaki parametre doğrulama hatası oluşursa, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve iade değeri **EINVAL**olduğunu.

## <a name="remarks"></a>Açıklamalar

**tmpfile_s** işlevi geçici bir dosya oluşturur ve *pFilePtr* bağımsız değişkeninde bu akışa bir işaretçi koyar. Geçici dosya kök dizinde oluşturulur. Kök dışındaki bir dizinde geçici bir dosya oluşturmak [için, fopen](fopen-wfopen.md)ile birlikte [tmpnam_s](tmpnam-s-wtmpnam-s.md) veya [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) kullanın.

Dosya açılamıyorsa, **tmpfile_s** *pFilePtr* parametresine **NULL** yazar. Bu geçici dosya, dosya kapatıldığında, program normal olarak sona erdiğinde veya geçerli çalışma dizininin değişmediğini varsayarak **_rmtmp** çağrıldığında otomatik olarak silinir. Geçici dosya **w+b** (ikili okuma/yazma) modunda açılır.

**TMP_MAX_S'den** fazla çabalarsanız hata oluşabilir (bkz. H) **tmpfile_s**ile aramalar .

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**tmpfile_s**|\<stdio.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

> [!NOTE]
> Bu örnek, Windows'da çalıştırmak için yönetim ayrıcalıkları gerektirebilir.

```C
// crt_tmpfile_s.c
// This program uses tmpfile_s to create a
// temporary file, then deletes this file with _rmtmp.
//

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char tempstring[] = "String to be written";
   int  i;
   errno_t err;

   // Create temporary files.
   for( i = 1; i <= 3; i++ )
   {
      err = tmpfile_s(&stream);
      if( err )
         perror( "Could not open new temporary file\n" );
      else
         printf( "Temporary file %d was created\n", i );
   }

   // Remove temporary files.
   printf( "%d temporary files deleted\n", _rmtmp() );
}
```

```Output
Temporary file 1 was created
Temporary file 2 was created
Temporary file 3 was created
3 temporary files deleted
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_rmtmp](rmtmp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
