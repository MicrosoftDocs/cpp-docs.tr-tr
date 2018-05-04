---
title: setlocale, _wsetlocale | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wsetlocale
- setlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wsetlocale
- _tsetlocale
- setlocale
dev_langs:
- C++
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 46f523ba11902f3eaa74fc649791313ee9388824
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="setlocale-wsetlocale"></a>setlocale, _wsetlocale

Çalışma zamanı yerel ayarını ayarlar veya alır.

## <a name="syntax"></a>Sözdizimi

```C
char *setlocale(
   int category,
   const char *locale
);
wchar_t *_wsetlocale(
   int category,
   const wchar_t *locale
);
```

### <a name="parameters"></a>Parametreler

*Kategori*<br/>
Yerel ayardan etkilenen kategori.

*Yerel ayar*<br/>
Yerel ayar tanımlayıcı.

## <a name="return-value"></a>Dönüş Değeri

Geçerli bir *yerel ayar* ve *kategori* verilir, bir işaretçi belirtilen ile ilişkili dizeyi döndürür *yerel ayar* ve *kategori*. Varsa *yerel ayar* veya *kategori* geçerli değil, bir null işaretçinin ve geçerli yerel ayarları programının değişip değişmediğini döndürür.

Örneğin, çağrı:

```C
setlocale( LC_ALL, "en-US" );
```

yalnızca dizeyi döndürür ve tüm kategorileri ayarlar

```Output
en-US
```

Tarafından döndürülen dize kopyalayabilirsiniz **setlocale** programın yerel ayar bilgileri bu bölümü geri yüklemek için. Genel veya iş parçacığı yerel depolama tarafından döndürülen dize için kullanıldığından **setlocale**. Daha sonra çağrılar **setlocale** önceki çağrıları tarafından döndürülen dize işaretçileri geçersiz kılar dize üzerine yazın.

## <a name="remarks"></a>Açıklamalar

Kullanım **setlocale** ayarlamak, değiştirmek veya bazılarını veya tümünü tarafından belirlenen geçerli programı yerel ayar bilgileri sorgulamak için işlevi *yerel ayar* ve *kategori*. *yerel ayar* kendisi için özelleştirebilirsiniz programınız belirli yönlerini yerleşim için (ülke/bölge ve dil) başvuruyor. Bazı yerel ayara bağımlı kategoriler tarih biçimlendirmesini ve parasal değerlerin görüntülenme biçimini içerir. Ayarlarsanız *yerel ayar* bilgisayarınızda desteklenen birden çok form sahip bir dil için varsayılan dizeye denetlemelisiniz **setlocale** dönüş dili yürürlükte olduğunu görmek için değeri. Örneğin, ayarlarsanız *yerel* "Çinceden" "Çince-Basitleştirilmiş" veya "Çince (Geleneksel)" dönüş değeri olabilir.

**_wsetlocale** bir joker karakter sürümü **setlocale**; *yerel ayar* yazmaç değerini **_wsetlocale** joker karakter dizelerdir. **_wsetlocale** ve **setlocale** Aksi takdirde aynı şekilde davranır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsetlocale**|**setlocale**|**setlocale**|**_wsetlocale**|

*Kategori* bağımsız değişkeni, etkilenen bir programın yerel ayar bilgileri bölümlerini belirtir. İçin kullanılan makroları *kategori* ve etkilediklerini program bölümlerini aşağıdaki gibidir:

|*Kategori* bayrağı|Etkiler|
|-|-|
**LC_ALL**|Aşağıda listelenen tüm kategoriler.
**LC_COLLATE**|**Strcoll**, **_stricoll**, **wcscoll**, **_wcsicoll**, **strxfrm**, **_ strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**, ve **wcsxfrm** işlevleri.
**LC_CTYPE**|Karakter işleme işlevleri (dışında **isdigit**, **isxdigit**, **mbstowcs**, ve **mbtowc**, hangi etkilenmez).
**LC_MONETARY**|Tarafından döndürülen biçimlendirme parasal bilgileri **localeconv** işlevi.
**LC_NUMERIC**|Karakter biçimlendirilmiş çıktı yordamları için ondalık (gibi **printf**), veri dönüştürme yordamları ve tarafından döndürülen parasal biçimlendirme bilgi **localeconv**. Ondalık nokta karakteri yanı sıra **lc_numerıc** kümeleri binlik ayırıcı ve gruplandırma denetimi tarafından döndürülen dize [localeconv](localeconv.md).
**LC_TIME**|**Strftime** ve **wcsftime** işlevleri.

Bu işlev, kategori parametresini doğrular. Kategori parametre önceki tabloda verilen değerlerden biri değilse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, işlevi ayarlar **errno** için **EINVAL** ve döndürür **NULL**.

*Yerel* bağımsız değişkeni bir işaretçidir yerel belirten bir dize. Biçimi hakkında bilgi için *yerel ayar* bağımsız değişkeni, bkz: [yerel ayar adları, diller ve ülke/bölge dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Varsa *yerel* yerel boş bir dize noktalarına uygulama tanımlı yerel ortam olduğu. Değerini **C** C çeviri en az ANSI uyumlu ortamını belirtir. **C** yerel ayar varsayar, tüm **char** veri türleri: 1 bayt ve bunların değer her zaman 256'dan az olur.

Program açılışında, aşağıdaki ifadenin eşdeğeri çalıştırılır:

`setlocale( LC_ALL, "C" );`

*Yerel* bağımsız değişkeni bir yerel ayar adı, bir dil dizesi, bir dil dize ve ülke/bölge kodu, bir kod sayfası veya bir dil dize, ülke/bölge kodu ve kod sayfası alabilir. Kullanılabilen yerel veri adları, diller, ülke/bölge kodları ve kod sayfaları paketleri UTF-7 ve UTF-8 gibi karakter başına iki bayttan fazlasını gerektiren kod sayfaları dışında Windows NLS API tarafından desteklenenlerin tamamını içermektedir. UTF-7 veya UTF-8 kod sayfası değeri sağlarsanız, **setlocale** , NULL döndürme başarısız olur. Yerel ayar adları tarafından desteklenen kümesi **setlocale** açıklanan [yerel ayar adları, diller ve ülke/bölge dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). Tarafından desteklenen dil ve ülke/bölge dizeleri kümesi **setlocale** listelenen [dil dizeleri](../../c-runtime-library/language-strings.md) ve [ülke/bölge dizeleri](../../c-runtime-library/country-region-strings.md). Kod içinde gömülü veya depolama için seri hale getirilmiş yerel ayar dizelerinin devamlılığı ve performansı için yerel ayar adı biçimi öneririz. Yerel ayar adı dizelerinin bir işletim sistemi güncelleştirmesi tarafından değiştirilmesi olasılığı dil ve ülke/bölge adı biçiminin değiştirilmesi olasılığından daha düşüktür.

Olarak geçirilen bir null işaretçinin *yerel ayar* bağımsız değişkeni söyler **setlocale** yerine uluslararası ortamı ayarlamak için sorgulanamıyor. Varsa *yerel* bağımsız değişkeni null işaretçi, programın geçerli yerel ayarı değiştirilmedi. Bunun yerine, **setlocale** ile ilişkili dize için bir işaretçi döndürür *kategori* iş parçacığının geçerli yerel olarak. Varsa *kategori* bağımsız değişkeni **LC_ALL**, işlevi her kategorisinin noktalı virgüllerle ayrılmış geçerli ayarı belirten bir dize döndürür. Örneğin, çağrı

```C
// Set all categories and return "en-US"
setlocale(LC_ALL, "en-US");
// Set only the LC_MONETARY category and return "fr-FR"
setlocale(LC_MONETARY, "fr-FR");
printf("%s\n", setlocale(LC_ALL, NULL));
```

dizisi

```Output
LC_COLLATE=en-US;LC_CTYPE=en-US;LC_MONETARY=fr-FR;LC_NUMERIC=en-US;LC_TIME=en-US
```

ile ilişkili dize olduğu **LC_ALL** kategorisi.

Aşağıdaki örnekler ilgilidir **LC_ALL** kategorisi. ".OCP" ve ".ACP" dizelerinden biri, bir kod sayfası numarası yerine sırasıyla kullanıcı varsayılan OEM kod sayfasının ve kullanıcının varsayılan ANSI kod sayfasının kullanımını belirlemek için kullanılabilir.

- `setlocale( LC_ALL, "" );`

   Yerel ayarı, işletim sisteminden alınan kullanıcının varsayılan ANSI kod sayfası olan varsayılana ayarlar.

- `setlocale( LC_ALL, ".OCP" );`

   Yerel ayarı açıkça işletim sisteminden alınan geçerli OEM kod sayfasına ayarlar.

- `setlocale( LC_ALL, ".ACP" );`

   Yerel ayarı işletim sisteminden alınan geçerli ANSI kod sayfasına ayarlar.

- `setlocale( LC_ALL, "<localename>" );`

   Tarafından belirtilen yerel ayar adına yerel ayarlar  *\<localename >*.

- `setlocale( LC_ALL, "<language>_<country>" );`

   Yerel ayar dil ve ülke/bölge tarafından belirtilen ayarlar  *\<dil >* ve  *\<Ülke >*, ana bilgisayardan alınan varsayılan kod sayfası ile birlikte İşletim Sistemi.

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   Yerel dil, ülke/bölge ve kod sayfası tarafından belirtilen ayarlar  *\<dil >*,  *\<Ülke >*, ve  *\<code_page >* dizeleri. Dilin, ülkenin/bölgenin ve kod sayfasının çeşitli birleşimlerini kullanabilirsiniz. Örneğin, bu çağrı yerel ayarı kod sayfası 1252 ile Fransızca Kanada olarak ayarlar:

   `setlocale( LC_ALL, "French_Canada.1252" );`

   Bu çağrı yerel ayarı varsayılan ANSI kod sayfasıyla Fransızca Kanada olarak ayarlar:

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   Bu çağrı yerel ayarı varsayılan OEM kod sayfasıyla Fransızca Kanada olarak ayarlar:

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   Tarafından belirtilen dil için yerel ayarlar  *\<dil >* ve belirtilen dil ve kullanıcı varsayılan ANSI ülke/bölge için ana bilgisayardan alınan kod sayfası için varsayılan ülke/bölge kullanır İşletim Sistemi. Örneğin, aşağıdaki çağrılarını için **setlocale** işlevsel olarak eşdeğerdir:

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   Performans ve bakım için ilk biçimi öneririz.

- `setlocale( LC_ALL, ".<code_page>" );`

   Kod sayfası tarafından belirtilen değere ayarlar *< code_page >*, belirtilen kod sayfası (ana bilgisayar işletim sistemi tarafından tanımlandığı gibi) dilini ve varsayılan ülke/bölge ile birlikte.

Kategori ya da olmalıdır **LC_ALL** veya **LC_CTYPE** kod sayfası, bir değişiklik etkilemek için. Örneğin, ana bilgisayar işletim sisteminin dilini ve varsayılan ülke/bölge "ABD" ve "İngilizce" ise, aşağıdaki iki çağrılar **setlocale** işlevsel olarak eşdeğerdir:

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

Daha fazla bilgi için bkz: [setlocale](../../preprocessor/setlocale.md) pragma yönergesi [C/C++ ön işlemci başvurusu](../../preprocessor/c-cpp-preprocessor-reference.md).

İşlev [_configthreadlocale](configthreadlocale.md) denetlemek için kullanılıp kullanılmadığını **setlocale** tüm iş parçacıkları bir program, yerel ya da yalnızca çağıran iş parçacığı yerel etkiler.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setlocale**|\<Locale.h >|
|**_wsetlocale**|\<Locale.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_setlocale.c
//
// This program demonstrates the use of setlocale when
// using two independent threads.
//

#include <locale.h>
#include <process.h>
#include <windows.h>
#include <stdio.h>
#include <time.h>

#define BUFF_SIZE 100

// Retrieve the date in the current
// locale's format.
int get_date(unsigned char* str)
{
    __time64_t ltime;
    struct tm  thetime;

    // Retrieve the current time
    _time64(&ltime);
    _gmtime64_s(&thetime, &ltime);

    // Format the current time structure into a string
    // "%#x" is the long date representation in the
    // current locale
    if (!strftime((char *)str, BUFF_SIZE, "%#x",
                  (const struct tm *)&thetime))
    {
        printf("strftime failed!\n");
        return -1;
    }
    return 0;
}

// This thread sets its locale to the argument
// and prints the date.
uintptr_t __stdcall SecondThreadFunc( void* pArguments )
{
    unsigned char str[BUFF_SIZE];
    char * locale = (char *)pArguments;

    // Set the thread locale
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, locale));

    // Retrieve the date string from the helper function
    if (get_date(str) == 0)
    {
        printf("The date in %s locale is: '%s'\n", locale, str);
    }

    _endthreadex( 0 );
    return 0;
}

// The main thread sets the locale to English
// and then spawns a second thread (above) and prints the date.
int main()
{
    HANDLE          hThread;
    unsigned        threadID;
    unsigned char   str[BUFF_SIZE];

    // Configure per-thread locale to cause all subsequently created
    // threads to have their own locale.
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Set the locale of the main thread to US English.
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "en-US"));

    // Create the second thread with a German locale.
    // Our thread function takes an argument of the locale to use.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,
                                      "de-DE", 0, &threadID );

    if (get_date(str) == 0)
    {
        // Retrieve the date string from the helper function
        printf("The date in en-US locale is: '%s'\n\n", str);
    }

    // Wait for the created thread to finish.
    WaitForSingleObject( hThread, INFINITE );

    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
The thread locale is now set to en-US.
The time in en-US locale is: 'Wednesday, May 12, 2004'

The thread locale is now set to de-DE.
The time in de-DE locale is: 'Mittwoch, 12. Mai 2004'
```

## <a name="see-also"></a>Ayrıca bkz.

[Yerel ayar adları, diller ve ülke/bölge dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[_configthreadlocale](configthreadlocale.md)<br/>
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)<br/>
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)<br/>
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)<br/>
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)<br/>
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)<br/>
[wctomb, _wctomb_l](wctomb-wctomb-l.md)<br/>
