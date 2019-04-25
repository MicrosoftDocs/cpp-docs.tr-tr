---
title: tmpnam_s, _wtmpnam_s
ms.date: 11/04/2016
apiname:
- tmpnam_s
- _wtmpnam_s
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
ms.openlocfilehash: 9bf994d16362ef461d8d25d72466721ba9a5890f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62155543"
---
# <a name="tmpnams-wtmpnams"></a>tmpnam_s, _wtmpnam_s

Geçici dosyalar oluşturmak için kullanabileceğiniz adları oluşturun. Bunlar sürümleridir [tmpnam ve _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

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

*str*<br/>
Oluşturulan ad tutacak işaretçisi.

*sizeInChars*<br/>
Arabelleğin karakter cinsinden boyutu.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her ikisi de, hata durumunda 0 başarılı olursa ya da bir hata numarası döndürür.

### <a name="error-conditions"></a>Hata koşulları

|||||
|-|-|-|-|
|*str*|*sizeInChars*|**Dönüş değeri**|**İçeriğini***str*|
|**NULL**|Tüm|**EINVAL**|değiştirilmedi|
|Değil **NULL** (geçerli bellek noktaları)|çok kısa|**ERANGE**|değiştirilmedi|

Varsa *str* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve dönüş **EINVAL**.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, şu anda mevcut olmayan bir dosya adını döndürür. **tmpnam_s** tarafından döndürülen belirlenen Windows geçici dizinde benzersiz bir ad verir [GetTempPathW](/windows/desktop/api/fileapi/nf-fileapi-gettemppathw). Bir dosya adı bekletilen ters eğik çizgi ve \fname21 gibi hiçbir yol bilgisi olduğunda bu adı geçerli çalışma dizini için geçerli olduğunu belirttiğinden unutmayın.

İçin **tmpnam_s**, bu oluşturulan dosya adında depolayabilirsiniz *str*. Tarafından döndürülen bir dize uzunluğu en fazla **tmpnam_s** olduğu **L_tmpnam_s**STDIO içinde tanımlanmış. H Varsa *str* olduğu **NULL**, ardından **tmpnam_s** sonucu bir iç statik arabellek bırakır. Bu nedenle sonraki çağrılar, bu değer yok. Tarafından oluşturulan adı **tmpnam_s** bir program tarafından oluşturulan dosya adı ve ilk çağrısından sonra oluşan **tmpnam_s**, sıralı sayıların temel 32 bir dosya uzantısı (.1-.1vvvvvu olduğunda **TMP _MAX_S** STDIO içinde. H ise **INT_MAX**).

**tmpnam_s** otomatik olarak algılamayı OEM kod sayfasına göre çok baytlı karakter dizileri işler çok baytlı karakter dizesi bağımsız değişken olarak uygun alınan işletim sisteminden. **_wtmpnam_s** geniş karakterli sürümüdür **tmpnam_s**; bağımsız değişkeni ve dönüş değeri **_wtmpnam_s** geniş karakterli dizelerdir. **_wtmpnam_s** ve **tmpnam_s** aynı şekilde davranır **_wtmpnam_s** çok baytlı karakter dizelerini işlemez.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğu bir boyut bağımsız değişkeni belirtme gereksinimi ortadan otomatik olarak çıkarabilir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam_s**|**tmpnam_s**|**tmpnam_s**|**_wtmpnam_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**tmpnam_s**|\<stdio.h >|
|**_wtmpnam_s**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
