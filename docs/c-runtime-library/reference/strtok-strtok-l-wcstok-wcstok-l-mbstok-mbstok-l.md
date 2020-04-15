---
title: strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l
ms.date: 4/2/2020
api_name:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
- _o__mbstok
- _o__mbstok_l
- _o_strtok
- _o_wcstok
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: d228d9824c534a21e4a22797e4b070e6d8d0b179
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365190"
---
# <a name="strtok-_strtok_l-wcstok-_wcstok_l-_mbstok-_mbstok_l"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l

Geçerli yerel alanı veya geçirilen belirli bir yerel alanı kullanarak bir dizedeki sonraki belirteci bulur. Bu işlevlerin daha güvenli sürümleri mevcuttur; [bkz. strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l.](strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md)

> [!IMPORTANT]
> **_mbstok** ve **_mbstok_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*strDelimit*<br/>
Delimiter karakter kümesi.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

*StrToken'de*bulunan bir sonraki belirteç için bir işaretçi döndürür. Başka belirteç bulunmadığında işlevler **NULL** döndürer. Her çağrı, döndürülen belirteçten sonra oluşan ilk sınır layıcıiçin null bir karakter ikame ederek *strToken'i* değiştirir.

## <a name="remarks"></a>Açıklamalar

**Strtok** işlevi *strToken*sonraki belirteci bulur. *strDelimit'teki* karakter kümesi, geçerli çağrıda *strToken'da* bulunacak belirteçolası sınırlayıcıları belirtir. **wcstok** ve **_mbstok** **strtok**geniş karakterli ve multibayt karakterli versiyonlarıdır. **Wcstok'un** bağımsız değişkenleri ve geri dönüş değeri geniş karakterli dizelerdir; **_mbstok** çok bayt karakterli dizeleri vardır. Bu üç işlev aynı şekilde çalışır.

> [!IMPORTANT]
> Bu işlevler, arabellek taşma sorunu tarafından ortaya çıkarılan olası bir tehdit le karşı lanır. Arabellek taşma sorunları, sık karşılaşılan bir sistem saldırısı yöntemidir ve bu da haksız bir ayrıcalık yükselmesine neden olabilir. Daha fazla bilgi için [bkz.](/windows/win32/SecBP/avoiding-buffer-overruns)

**Strtok**için ilk çağrıda , işlev önde gelen sınırlayıcıları atlar ve *strToken*ilk belirteci için bir işaretçi döndürür , null bir karakter ile belirteci sonlandırma. Daha fazla belirteçleri **strtok**aramaları bir dizi tarafından *strToken* geri kalanı dışarı kırılmış olabilir. **Strtok'a** yapılan her çağrı, **belirteç** bu çağrı tarafından döndürüldükten sonra null bir karakter ekleyerek *strToken'i* değiştirir. *StrToken'den*sonraki belirteci okumak için *strToken* bağımsız değişkeni için **NULL** değeri olan **strtok'u** arayın. **NULL** *strToken* bağımsız değişkeni, değiştirilen *strToken'de*bir sonraki belirteç için **strtok'un** aramasına neden olur. *strDelimit* bağımsız değişkeni, sınır aşanlar kümesinin değişebileceği şekilde bir çağrıdan diğerine herhangi bir değer alabilir.

Çıktı değeri, LC_CTYPE **kategori** ayarını ayarlayarak etkilenir. Daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md)bakın.

Bu işlevlerin **_l** soneki olmayan sürümleri, bu yerel eki bağımlı davranış için geçerli yerel alanı kullanır. **_l** soneki olan sürümler, bunun yerine geçirilen yerel parametreyi kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

> [!NOTE]
> Her işlev, dizeyi belirteçlere ayrıştmak için bir iş parçacığı yerel statik değişkenkullanır. Bu nedenle, birden çok iş parçacığı aynı anda istenmeyen etkileri olmadan bu işlevleri çağırabilirsiniz. Ancak, tek bir iş parçacığı içinde, bu işlevlerden birine çağrı bırakmanın veri bozulması ve yanlış sonuçlar oluşturma olasılığı yüksektir. Farklı dizeleri ayrıştırken, bir sonraki parçalama başlamadan önce bir dize ayrıştma bitirmek. Ayrıca, bu işlevlerden birini başka bir işlevin çağrıldığı bir döngü içinden ararken tehlike potansiyelinin farkında olun. Diğer işlev bu işlevlerden birini kullanırsa, ara sıra çağrılar sonuçlanır ve veri bozulması tetikler.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok**|**strtok**|**_mbstok**|**wcstok**|
|**_tcstok**|**_strtok_l**|**_mbstok_l**|**_wcstok_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtok**|\<string.h>|
|**wcstok**|\<string.h> \<veya wchar.h>|
|**_mbstok**, **_mbstok_l**|\<mbstring.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
