---
title: strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l
ms.date: 03/25/2019
api_name:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbstok
- strtok
- _tcstok
- wcstok
helpviewer_keywords:
- mbstok_l function
- strings [C++], searching
- tcstok function
- _tcstok function
- _strtok_l function
- strtok function
- mbstok function
- wcstok_l function
- _mbstok function
- tcstok_l function
- tokens, finding in strings
- _mbstok_l function
- wcstok function
- _wcstok_l function
- _tcstok_l function
- strtok_l function
ms.assetid: 904cb734-f0d7-4d77-ba81-4791ddf461ae
ms.openlocfilehash: 62ed9edc6ec5a7ee60223f1c5e908aa14f421a25
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957649"
---
# <a name="strtok-_strtok_l-wcstok-_wcstok_l-_mbstok-_mbstok_l"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l

Geçerli yerel ayarı veya geçirilen belirtilen yerel ayarı kullanarak bir dizedeki sonraki belirteci bulur. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).

> [!IMPORTANT]
> **_mbstok** ve **_mbstok_l** Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *strtok(
   char *strToken,
   const char *strDelimit
);
char *strtok_l(
   char *strToken,
   const char *strDelimit,
   _locale_t locale
);
wchar_t *wcstok(
   wchar_t *strToken,
   const wchar_t *strDelimit
);
wchar_t *wcstok_l(
   wchar_t *strToken,
   const wchar_t *strDelimit,
   _locale_t locale
);
unsigned char *_mbstok(
   unsigned char *strToken,
   const unsigned char *strDelimit
);
unsigned char *_mbstok_l(
   unsigned char *strToken,
   const unsigned char *strDelimit,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*strToken*<br/>
Belirteç veya belirteçleri içeren dize.

*Strsınırlandırın*<br/>
Sınırlayıcı karakter kümesi.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

*StrToken*'da bulunan bir sonraki belirtece bir işaretçi döndürür. Daha fazla belirteç bulunamadığında işlevler **null** döndürür. Her çağrı, döndürülen belirteçle sonra oluşan ilk sınırlayıcı için null bir karakter koyarak *strToken* 'ı değiştirir.

## <a name="remarks"></a>Açıklamalar

**Strtok** Işlevi, *strToken*'daki bir sonraki belirteci bulur. *Strsınırlandıran* karakter kümesi, geçerli çağrıda *strToken* içinde bulunan belirtecin olası sınırlayıcılarını belirtir. **wcstok** ve **_mbstok** , **strtok**'nin geniş karakterli ve çok baytlı karakter sürümleridir. **Wcstok** bağımsız değişkenleri ve dönüş değeri geniş karakterli dizelerdir; **_mbstok** , çok baytlı karakter dizeleridir. Bu üç işlev, aynı şekilde davranır.

> [!IMPORTANT]
> Bu işlevler, bir arabellek taşması sorunu ile ilgili olası bir tehdit doğurur. Arabellek taşması sorunları, sistem saldırılarına karşı sık kullanılan bir yöntemdir ve bu da garanti edilmemiş ayrıcalık yükselmesine neden olur. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

**Strtok**öğesine yapılan ilk çağrıda, işlev baştaki sınırlayıcıları atlar ve *strToken*'daki ilk belirtece bir işaretçi döndürür ve belirteci null karakterle sonlandırıyor. **Strtok**öğesine yapılan bir dizi çağrı Ile *strToken* 'ın geri kalanlarından daha fazla belirteç bozulabilir. Her **strtok** çağrısı, bu çağrı tarafından döndürülen **belirteçten** sonra bir null karakter ekleyerek *strToken* 'ı değiştirir. *StrToken*'dan bir sonraki belirteci okumak için, *strToken* bağımsız değişkeni olarak bir **null** değer ile **strtok** çağrısı yapın. **Null** *strToken* bağımsız değişkeni, **strtok** 'ın değiştirilmiş *strToken*'da bir sonraki belirteci aramasına neden olur. *Strsınırlandıran* bağımsız değişkeni, bir sonraki çağrıdan bir değer alabilir ve bu sayede sınırlayıcılar kümesi farklılık gösterebilir.

Çıkış değeri, yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir. Daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md).

**_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır. **_L** sonekine sahip sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

> [!NOTE]
> Her işlev, dizeyi belirteçlere ayrıştırmak için iş parçacığı yerel statik değişkenini kullanır. Bu nedenle, birden çok iş parçacığı bu işlevleri istenmeden etkiler olmadan aynı anda çağırabilir. Bununla birlikte, tek bir iş parçacığında, bu işlevlerden birine yönelik araya ekleme çağrıları, veri bozulması ve yanlış sonuçlar üretmesi büyük ihtimalle. Farklı dizeler ayrıştırılırken, bir sonraki ayrıştırmaya başlamadan önce bir dizeyi ayrıştırmayı son yapın. Ayrıca, bu işlevlerden biri başka bir işlevin çağrıldığı bir döngüden çağrıldığında olma tehlikesi için potansiyelini göz önünde bulundurun. Diğer işlev bu işlevlerden birini kullanarak sonlanıyorsa, araya eklemeli bir çağrı dizisi oluşur ve veri bozulması tetiklenecektir.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok**|**strtok**|**_mbstok**|**wcstok**|
|**_tcstok**|**_strtok_l**|**_mbstok_l**|**_wcstok_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtok**|\<String. h >|
|**wcstok**|\<String. h > veya \<wchar. h >|
|**_mbstok**, **_mbstok_l**|\<mbstring. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strtok.c
// compile with: /W3
// In this program, a loop uses strtok
// to print all the tokens (separated by commas
// or blanks) in the string named "string".
//
#include <string.h>
#include <stdio.h>

char string[] = "A string\tof ,,tokens\nand some  more tokens";
char seps[]   = " ,\t\n";
char *token;

int main( void )
{
   printf( "Tokens:\n" );

   // Establish string and get the first token:
   token = strtok( string, seps ); // C4996
   // Note: strtok is deprecated; consider using strtok_s instead
   while( token != NULL )
   {
      // While there are tokens in "string"
      printf( " %s\n", token );

      // Get next token:
      token = strtok( NULL, seps ); // C4996
   }
}
```

```Output
Tokens:
A
string
of
tokens
and
some
more
tokens
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
