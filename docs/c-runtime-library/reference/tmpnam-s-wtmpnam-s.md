---
description: 'Hakkında daha fazla bilgi edinin: tmpnam_s _wtmpnam_s'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: fefaa0ca54ecd1a4ae0a61f10ab502cf5310648a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155793"
---
# <a name="tmpnam_s-_wtmpnam_s"></a>tmpnam_s, _wtmpnam_s

Geçici dosyalar oluşturmak için kullanabileceğiniz adlar oluşturun. Bunlar, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan şekilde, güvenlik geliştirmeleriyle [tmpnam ve _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md) sürümleridir.

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

*üstbilgisine*<br/>
Oluşturulan adı tutacak işaretçi.

*Sizeınchars*<br/>
Arabelleğin karakter cinsinden boyutu.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her ikisi de başarılı olursa 0 veya hata durumunda bir hata numarası döndürür.

### <a name="error-conditions"></a>Hata koşulları

| *üstbilgisine* | *Sizeınchars* | **Dönüş Değeri** |  *Str* içeriği |
|--|--|--|--|
| **DEĞER** | herhangi biri | **EıNVAL** | değiştirilmedi |
| **null** değil (geçerli belleğe işaret eder) | çok kısa | **ERANGE** | değiştirilmedi |

*Str* **null** ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve **EINVAL** döndürür.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri, şu anda mevcut olmayan bir dosyanın adını döndürür. **tmpnam_s** , [Gettemppathw](/windows/win32/api/fileapi/nf-fileapi-gettemppathw)tarafından döndürülen belirlenmiş Windows geçici dizininde benzersiz bir ad döndürür. Bir dosya adının ters eğik çizgiyle ön halden önceden sonlandırıldığına ve \fname21 gibi yol bilgilerine sahip olmadığına, bu adın geçerli çalışma dizini için geçerli olduğunu gösterir.

**Tmpnam_s** için, bu oluşturulan dosya adını *Str* içinde saklayabilirsiniz. **Tmpnam_s** tarafından döndürülen bir dizenin en fazla uzunluğu, **L_tmpnam_s**, stdio. H içinde tanımlanır. *Str* **null** ise **tmpnam_s** , sonucu iç statik bir arabellekte bırakır. Bu nedenle, sonraki çağrılar bu değeri yok eder. **Tmpnam_s** tarafından oluşturulan ad, program tarafından oluşturulan bir dosya adından ve **tmpnam_s** ilk çağrıdan sonra, 32 (. 1-. 1vvvvvu, stdio 'da **TMP_MAX_S** olduğunda). H **INT_MAX**).

**tmpnam_s** çok baytlı karakter dizesi bağımsız değişkenlerini, uygun şekilde otomatik olarak işler ve işletim SISTEMINDEN alınan OEM kod sayfasına göre çok baytlı karakter dizilerini tanıyor. **_wtmpnam_s** , **tmpnam_s** geniş karakterli bir sürümüdür; **_wtmpnam_s** bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. **_wtmpnam_s** ve **tmpnam_s** , **_wtmpnam_s** çok baytlı karakter dizelerini işleyememesi dışında aynı şekilde davranır.

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir ve bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ttmpnam_s**|**tmpnam_s**|**tmpnam_s**|**_wtmpnam_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**tmpnam_s**|\<stdio.h>|
|**_wtmpnam_s**|\<stdio.h> veya \<wchar.h>|

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

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[malloc](malloc.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
