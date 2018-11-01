---
title: tmpfile_s
ms.date: 11/04/2016
apiname:
- tmpfile_s
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
- tmpfile_s
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
ms.openlocfilehash: 341e1c8ed6dd20ec7e6a3d71999fb365e45e614a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50488120"
---
# <a name="tmpfiles"></a>tmpfile_s

Geçici bir dosya oluşturur. Bir sürümüdür [tmpfile](tmpfile.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t tmpfile_s(
   FILE** pFilePtr
);
```

### <a name="parameters"></a>Parametreler

*pFilePtr*<br/>
Bir akışa oluşturulan işaretçisinin adresi depolamak için bir işaretçi adresi.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa 0 döndürür bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*pFilePtr*|**Dönüş değeri**|**İçeriğini***pFilePtr* |
|----------------|----------------------|---------------------------------|
|**NULL**|**EINVAL**|değiştirilmedi|

Yukarıdaki parametre doğrulama hatası meydana gelirse, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve dönüş değeri **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**Tmpfile_s** işlevi geçici bir dosya oluşturur ve bu akışı için bir işaretçi koyar *pFilePtr* bağımsız değişken. Geçici dosya kök dizininde oluşturulur. Kök dışında bir dizinde, geçici bir dosya oluşturmak için kullanın [tmpnam_s](tmpnam-s-wtmpnam-s.md) veya [tempnam](tempnam-wtempnam-tmpnam-wtmpnam.md) birlikte [fopen](fopen-wfopen.md).

Dosya açılamıyor, **tmpfile_s** Yazar **NULL** için *pFilePtr* parametresi. Bu geçici dosya dosya kapatıldığında normalde veya program sona erdiğinde otomatik olarak silinir **_rmtmp** çağrılır, varsayarak geçerli çalışma dizini değişmez. Geçici dosya açılır **w + b** (ikili okuma/yazma) modu.

Çalışırsanız hata meydana gelebilir birden fazla **TMP_MAX_S** (STDIO bakın. H) çağrılarını **tmpfile_s**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**tmpfile_s**|\<stdio.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

> [!NOTE]
> Bu örnek, Windows üzerinde çalıştırmak için yönetici ayrıcalıkları gerektirebilir.

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_rmtmp](rmtmp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
