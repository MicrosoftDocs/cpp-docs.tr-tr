---
title: strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _mbstok_l
- _mbstok
- wcstok
- _mbstok
- strtok
- _wcstok_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _mbstok
- strtok
- _tcstok
- wcstok
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 45e2155f830a302f316aa96ce41b65a71709bc0d
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451803"
---
# <a name="strtok-strtokl-wcstok-wcstokl-mbstok-mbstokl"></a>strtok, _strtok_l, wcstok, _wcstok_l, _mbstok, _mbstok_l

Sonraki belirteç geçerli yerel ya da geçirilen belirtilen bir yerel ayar kullanarak bir dize bulur. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [strtok_s, _strtok_s_l, wcstok_s, _wcstok_s_l, _mbstok_s, _mbstok_s_l](strtok-s-strtok-s-l-wcstok-s-wcstok-s-l-mbstok-s-mbstok-s-l.md).

> [!IMPORTANT]
> **_mbstok** ve **_mbstok_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *strtok(
   char *strToken,
   const char *strDelimit
);
wchar_t *wcstok(
   wchar_t *strToken,
   const wchar_t *strDelimit
);
unsigned char *_mbstok(
   unsigned char*strToken,
   const unsigned char *strDelimit
);
unsigned char *_mbstok(
   unsigned char*strToken,
   const unsigned char *strDelimit,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*strToken*<br/>
Belirteç veya belirteçler içeren dize.

*strDelimit*<br/>
Ayırıcı karakter kümesi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

İşaretçi bulunan sonraki belirteç döndüren *strToken*. Döndürmeleri **NULL** başka belirteç bulunduğunda. Her çağrı değiştirir *strToken* tarafından döndürülen belirteç sonra oluşan ilk sınırlayıcısı için bir null karakter değiştirerek.

## <a name="remarks"></a>Açıklamalar

**Strtok** işlev bulur sonraki belirteç *strToken*. Karakter kümesi *strDelimit* bulunamadı belirteç olası sınırlayıcılar belirtir *strToken* geçerli çağrıda. **wcstok** ve **_mbstok** joker karakter ve çok baytlı karakter sürümleri **strtok**. Bağımsız değişkenleri ve dönüş değerini **wcstok** joker karakter olan dizeleri; bu **_mbstok** çok baytlı karakter dizeleri belirtilmiştir. Bu üç işlevler aynı şekilde aksi davranır.

> [!IMPORTANT]
> Bu işlevlerin bir arabellek taşması sorunu duruma olası bir tehdit doğurur. Arabellek Taşması, sık yöntemi bir unwarranted ayrıcalıkların sonuçlanan sistem saldırı sorunlardır. Daha fazla bilgi için bkz: [önleme arabellek taşmasına neden](http://msdn.microsoft.com/library/windows/desktop/ms717795).

İlk çağrıda **strtok**, işlevi başında sınırlayıcıları atlar ve ilk belirteci için bir işaretçi döndürür *strToken*, bir null karakter belirteciyle sonlandırılıyor. Daha fazla belirteçleri dışında kalan ayrılabilir *strToken* çağrıları için bir dizi **strtok**. Her çağrı **strtok** değiştirir *strToken* sonrasında bir null karakter ekleyerek **belirteci** bu çağrı tarafından döndürülen. Sonraki belirtecinden okumak için *strToken*, çağrı **strtok** ile bir **NULL** değerini *strToken* bağımsız değişkeni. **NULL** *strToken* bağımsız değişkeni nedenler **strtok** sonraki belirteç değiştirilmiş aramak için *strToken*. *StrDelimit* bağımsız değişkeni, sonraki yapılan bir çağrı arasında bir değer alabilir, böylece sınırlayıcı kümesi farklılık gösterebilir.

Çıkış değerini ayarı tarafından etkilenen **LC_CTYPE** yerel kategori ayarı; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** bu yerel ayara bağımlı davranış geçerli yerel kullanılmak soneki; sürümleriyle **_l** soneki, yerel ayar parametresi kullanmasını dışında aynıdır Bunun yerine geçirildi. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

> [!NOTE]
> Her işlev dizeyi belirteçlere ayrıştırmak için bir iş parçacığı yerel statik değişkenini kullanır. Bu nedenle, birden çok iş parçacığı aynı anda istenmeyen etkileri olmadan bu işlevleri çağırabilir. Ancak, tek bir iş parçacığı içinde bu işlevler birine çağrılarını Interleaving veri bozulması ve tutarsız sonuçlar üretmek yüksek oranda olasıdır. Farklı dizeleri ayrıştırma, sonraki ayrıştırmak başlatmadan önce bir dizesini ayrıştırma tamamlayın. Ayrıca bir bu işlevlerin bir döngü içinde olduğu başka bir işlevi olarak da adlandırılır çağrılırken tehlike potansiyeli farkında olun. Bu işlevler birini kullanarak diğer işlevi sona eriyor, veri bozulması tetikleme çağrısı bir araya eklemeli sırası sonuçlanır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstok**|**strtok**|**_mbstok**|**wcstok**|
|**_tcstok**|**_strtok_l**|**_mbstok_l**|**_wcstok_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strtok**|\<String.h >|
|**wcstok**|\<String.h > veya \<wchar.h >|
|**_mbstok**, **_mbstok_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[strcspn, wcscspn, _mbscspn, _mbscspn_l](strcspn-wcscspn-mbscspn-mbscspn-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
