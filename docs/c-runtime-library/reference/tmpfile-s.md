---
description: 'Hakkında daha fazla bilgi edinin: tmpfile_s'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 1b5830375644cdcdd3d0c400d00735319b3af671
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326146"
---
# <a name="tmpfile_s"></a>tmpfile_s

Geçici bir dosya oluşturur. Bu, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle bir [tmpfile](tmpfile.md) sürümüdür.

## <a name="syntax"></a>Sözdizimi

```C
errno_t tmpfile_s(
   FILE** pFilePtr
);
```

### <a name="parameters"></a>Parametreler

*pFilePtr*<br/>
Oluşturulan işaretçinin adresini bir akışa depolayan işaretçinin adresi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür. hata durumunda hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*pFilePtr*|**Dönüş Değeri**|*PFilePtr* içeriği  |
|----------------|----------------------|---------------------------------|
|**DEĞER**|**EıNVAL**|değiştirilmedi|

Yukarıdaki parametre doğrulama hatası oluşursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve dönüş değeri **EINVAL**' dir.

## <a name="remarks"></a>Açıklamalar

**Tmpfile_s** işlevi geçici bir dosya oluşturur ve *pFilePtr* bağımsız değişkeninde bu akışa bir işaretçi koyar. Geçici dosya kök dizinde oluşturulur. Kök dışında bir dizinde geçici bir dosya oluşturmak için, [fopen](fopen-wfopen.md)ile birlikte [tmpnam_s](tmpnam-s-wtmpnam-s.md) veya [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) kullanın.

Dosya açılamadığı **tmpfile_s** , *pFilePtr* parametresine **null** yazar. Dosya kapatıldığında, program normal olarak sonlandırıldığında veya **_rmtmp** çağrıldığında, geçerli çalışma dizininin değişmediği varsayılarak bu geçici dosya otomatik olarak silinir. Geçici dosya **w + b** (ikili okuma/yazma) modunda açılır.

**TMP_MAX_S** daha fazlasını denerseniz hata oluşabilir (bkz. stdio. H) **tmpfile_s** çağırır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**tmpfile_s**|\<stdio.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

> [!NOTE]
> Bu örnek, Windows 'da çalıştırmak için yönetici ayrıcalıkları gerektirebilir.

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

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[_rmtmp](rmtmp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
