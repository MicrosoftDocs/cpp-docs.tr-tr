---
title: tmpnam_s, _wtmpnam_s
ms.date: 4/2/2020
api_name:
- tmpnam_s
- _wtmpnam_s
- _o__wtmpnam_s
- _o_tmpnam_s
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
- tmpnam_s
- _wtmpnam_s
- L_tmpnam_s
helpviewer_keywords:
- tmpnam_s function
- file names [C++], creating temporary
- _wtmpnam_s function
- L_tmpnam_s constant
- temporary files, creating
- file names [C++], temporary
- wtmpnam_s function
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
ms.openlocfilehash: e34fbe64d342205659a4b0bdaf703248e62ed733
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362410"
---
# <a name="tmpnam_s-_wtmpnam_s"></a>tmpnam_s, _wtmpnam_s

Geçici dosyalar oluşturmak için kullanabileceğiniz adlar oluşturun. Bunlar, [CRT'deki Güvenlik Özellikleri'nde](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmelerine sahip [tmpnam ve _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) sürümleridir.

## <a name="syntax"></a>Sözdizimi

```C
errno_t tmpnam_s(
   char * str,
   size_t sizeInChars
);
errno_t _wtmpnam_s(
   wchar_t *str,
   size_t sizeInChars
);
template <size_t size>
errno_t tmpnam_s(
   char (&str)[size]
); // C++ only
template <size_t size>
errno_t _wtmpnam_s(
   wchar_t (&str)[size]
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Str*<br/>
Oluşturulan adı tutacak işaretçi.

*sizeInChars*<br/>
Karakterlerdeki arabelleğe boyutu.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her ikisi de başarılı olursa 0 döndürün veya hata üzerinde bir hata numarası.

### <a name="error-conditions"></a>Hata Koşulları

|||||
|-|-|-|-|
|*Str*|*sizeInChars*|**Dönüş Değeri**|**str içeriği***str*  |
|**Null**|herhangi bir|**Eınval**|değiştirilmemiş|
|**NULL** değil (geçerli belleğe işaret)|çok kısa|**Erange**|değiştirilmemiş|

*str* **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, bu işlevler EINVAL **için errno** ayarlayın ve **EINVAL** döndürün. **EINVAL**

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, şu anda var olmayan bir dosyanın adını döndürür. **tmpnam_s,** [GetTempPathW](/windows/win32/api/fileapi/nf-fileapi-gettemppathw)tarafından döndürülen belirlenen Windows geçici dizininde benzersiz bir ad döndürür. Bir dosya adının bir ters eğik çizgi yle önceden çevrildiğinde ve \fname21 gibi yol bilgisi olmadığında, bu, adın geçerli çalışma dizini için geçerli olduğunu gösterir.

**tmpnam_s**için, bu oluşturulan dosya adını *str'de*depolayabilirsiniz. **tmpnam_s** tarafından döndürülen bir dize maksimum uzunluğu **L_tmpnam_s**, STDIO tanımlanır. H. *str* **NULL**ise, **tmpnam_s** sonucu bir iç statik arabellekte bırakır. Böylece sonraki çağrılar bu değeri yok eder. **tmpnam_s** tarafından oluşturulan ad, program tarafından oluşturulan bir dosya adından oluşur ve **tmpnam_s**ilk çağrıdan sonra, STDIO'da **TMP_MAX_S** 32 (.1-.1vvvvvu) tabanında sıralı sayıların dosya uzantısı. H **INT_MAX**olduğunu).

**tmpnam_s,** işletim sisteminden elde edilen OEM kod sayfasına göre çok bayt karakter dizilerini tanıyarak, çok bayt karakterli dize bağımsız değişkenlerini otomatik olarak işler. **_wtmpnam_s** **tmpnam_s**geniş karakterli bir versiyonudur; _wtmpnam_s bağımsız değişkeni **_wtmpnam_s** ve geri dönüş değeri geniş karakterli dizeleridir. **_wtmpnam_s** ve **tmpnam_s,** **_wtmpnam_s** çok bayt karakterli dizeleri işlememesi dışında aynı şekilde çalışır.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkararak boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam_s**|**tmpnam_s**|**tmpnam_s**|**_wtmpnam_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**tmpnam_s**|\<stdio.h>|
|**_wtmpnam_s**|\<stdio.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

```C
// crt_tmpnam_s.c
// This program uses tmpnam_s to create a unique filename in the
// current working directory.
//

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char name1[L_tmpnam_s];
   errno_t err;
   int i;

   for (i = 0; i < 15; i++)
   {
      err = tmpnam_s( name1, L_tmpnam_s );
      if (err)
      {
         printf("Error occurred creating unique filename.\n");
         exit(1);
      }
      else
      {
         printf( "%s is safe to use as a temporary file.\n", name1 );
      }
   }
}
```

```Output
C:\Users\LocalUser\AppData\Local\Temp\u19q8.0 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.1 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.2 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.3 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.4 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.5 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.6 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.7 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.8 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.9 is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.a is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.b is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.c is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.d is safe to use as a temporary file.
C:\Users\LocalUser\AppData\Local\Temp\u19q8.e is safe to use as a temporary file.
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış I/O](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
