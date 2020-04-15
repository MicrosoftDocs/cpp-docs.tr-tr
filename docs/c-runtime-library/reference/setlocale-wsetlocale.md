---
title: setlocale, _wsetlocale
description: Microsoft C çalışma zamanı (CRT) setlocale _wsetlocalekitaplığını açıklar ve.
ms.date: 4/2/2020
api_name:
- _wsetlocale
- setlocale
- _o__wsetlocale
- _o_setlocale
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
- api-ms-win-crt-locale-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wsetlocale
- _tsetlocale
- setlocale
helpviewer_keywords:
- wsetlocale function
- setlocale function
- tsetlocale function
- locales, defining
- _tsetlocale function
- defining locales
- _wsetlocale function
ms.assetid: 3ffb684e-5990-4202-9553-b5339af9520d
no-loc:
- setlocale
- _wsetlocale
ms.openlocfilehash: 2834229839153c3154caadf71e5fb30d84ed2f1a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81353718"
---
# <a name="setlocale-_wsetlocale"></a>setlocale, _wsetlocale

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

*Kategori*\
Yerel ayardan etkilenen kategori.

*Yerel ayar*\
Yerel ayar tanımlayıcı.

## <a name="return-value"></a>Döndürülen değer

Geçerli bir *yerel alan* ve *kategori* verilirse, işaretçiyi belirtilen *yerel alan* ve *kategoriyle*ilişkili dizedöndürür. Yerel *ayar* veya *kategori* geçerli değilse, null işaretçisi döndürür ve programın geçerli yerel ayarları değişmez.

Örneğin, çağrı:

```C
setlocale( LC_ALL, "en-US" );
```

yalnızca dizeyi döndürür ve tüm kategorileri ayarlar

```Output
en-US
```

Programın yerel bilgilerinin bu bölümünü geri yüklemek için **setlocale** tarafından döndürülen dizekopyalayabilirsiniz. **Kümeyerel**tarafından döndürülen dize için global veya iş parçacığı yerel depolama kullanılır. Daha **sonra,** önceki çağrılar tarafından döndürülen dize işaretçilerini geçersiz sayan dize üzerinde ayarlamak için çağrılar.

## <a name="remarks"></a>Açıklamalar

*Yerel* ayar ve *kategori*tarafından belirtilen geçerli program yerel bilgilerinin bazılarını veya tümünü ayarlamak, değiştirmek veya sorgulamak için **ayaryerel işlevini** kullanın. *yerel,* programınızın belirli yönlerini özelleştirebileceğiniz yerelliği (ülke/bölge ve dil) anlamına gelir. Bazı yerel ayara bağımlı kategoriler tarih biçimlendirmesini ve parasal değerlerin görüntülenme biçimini içerir. Bilgisayarınızda desteklenen *locale* birden çok form olan bir dil için varsayılan dize olarak yerel ayarlasanız, hangi dilin etkin olduğunu görmek için **ayaryerel dönüş** değerini denetlemeniz gerekir. Örneğin, *yerel birimi* "çince" olarak ayarlarsanız, iade değeri "çince basitleştirilmiş" veya "geleneksel çince" olabilir.

**_wsetlocale** **setlocale**geniş karakterli bir sürümüdür; *_wsetlocale'nin yerel* değişkeni **_wsetlocale** ve döndürme değeri geniş karakterli dizeleridir. **_wsetlocale** ve **setlocale** aynı şekilde başka türlü çalışır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsetlocale**|**setlocale**|**setlocale**|**_wsetlocale**|

*Kategori* bağımsız değişkeni, bir programın etkilenen yerel bilgilerinin bölümlerini belirtir. *Kategori* için kullanılan makrolar ve etkilediği programın bölümleri aşağıdaki gibidir:

|*kategori* bayrağı|Etkiledi -ğini|
|-|-|
| **LC_ALL** | Tüm kategoriler, aşağıda listelenen. |
| **LC_COLLATE** | **Strcoll**, **_stricoll**, **wcscoll**, **_wcsicoll**, **strxfrm**, **_strncoll**, **_strnicoll**, **_wcsncoll**, **_wcsnicoll**, ve **wcsxfrm** fonksiyonları. |
| **LC_CTYPE** | Karakter işleme işlevleri **(isdigit**hariç , **isxdigit**, **mbstowcs**, ve **mbtowc**, etkilenmez). |
| **LC_MONETARY** | **Localeconv** işlevi tarafından döndürülen parasal biçimlendirme bilgileri. |
| **LC_NUMERIC** | Biçimlendirilmiş çıktı yordamları **(printf**gibi), veri dönüştürme yordamları ve **localeconv**tarafından döndürülen parasal olmayan biçimlendirme bilgileri için ondalık nokta karakteri. Ondalık nokta karakterine ek olarak, **LC_NUMERIC** binlerce ayırıcıyı ve [localeconv](localeconv.md)tarafından döndürülen gruplandırma denetim dizesini ayarlar. |
| **LC_TIME** | **Strftime** ve **wcsftime** fonksiyonları. |

Bu işlev, kategori parametresini doğrular. Kategori parametresi önceki tabloda verilen değerlerden biri değilse, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, işlev **EINVAL** **için errno** ayarlar ve **NULL**döndürür.

*Yerel* değişken, yerel ile'yi belirten bir dize işaretçisidir. *Yerel* değişkenin biçimi hakkında bilgi için Bkz. [Yerel Adlar, Diller ve Ülke/Bölge Dizeleri.](../../c-runtime-library/locale-names-languages-and-country-region-strings.md) Yerel nokta boş bir *dizeyi* işaret ederse, yerel alan uygulama tanımlı yerel ortamdır. **C** değeri, C çevirisi için en az ANSI uyumlu ortamı belirtir. **C** yerel alanı, tüm **char** veri türlerinin 1 bayt olduğunu ve değerlerinin her zaman 256'dan az olduğunu varsayar.

Program açılışında, aşağıdaki ifadenin eşdeğeri çalıştırılır:

`setlocale( LC_ALL, "C" );`

*Yerel* değişken, yerel ad, dil dizesi, dil dizesi ve ülke/bölge kodu, kod sayfası veya dil dizesi, ülke/bölge kodu ve kod sayfası alabilir. Kullanılabilir yerel adlar, diller, ülke/bölge kodları ve kod sayfaları kümesi, Windows NLS API tarafından desteklenen tüm bu adları içerir. **Setlocale** tarafından desteklenen yerel adlar kümesi Yerel [Adlar, Diller ve Ülke/Bölge Dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)olarak açıklanır. **Setlocale** tarafından desteklenen dil ve ülke/bölge dizeleri kümesi [Dil Dizeleri](../../c-runtime-library/language-strings.md) ve [Ülke/Bölge Dizeleri](../../c-runtime-library/country-region-strings.md)olarak listelenir. Kod içinde gömülü veya depolama için seri hale getirilmiş yerel ayar dizelerinin devamlılığı ve performansı için yerel ayar adı biçimi öneririz. Yerel ayar adı dizelerinin bir işletim sistemi güncelleştirmesi tarafından değiştirilmesi olasılığı dil ve ülke/bölge adı biçiminin değiştirilmesi olasılığından daha düşüktür.

*Yerel* değişken, uluslararası ortamı ayarlamak yerine **ayaryerel'i** sorguya ayarlarken geçirilen null işaretçi. *Yerel* değişken null işaretçisiise, programın geçerli yerel ayar ını değiştirmez. Bunun yerine, **ayaryerel iş** parçacığının geçerli yerel *alanının kategorisiyle* ilişkili dize için bir işaretçi döndürür. *Kategori* bağımsız değişkeni **LC_ALL**ise, işlev her kategorinin geçerli ayarını gösteren ve yarı iki nokta üst üste ayrılmış bir dize döndürür. Örneğin, çağrı

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

**LC_ALL** kategorisi ile ilişkili dizedir.

Aşağıdaki örnekler **LC_ALL** kategorisi ile ilgilidir. Ya dizeleri ". OCP" ve ". ACP" kullanıcı varsayılan OEM kod sayfası nın ve kullanıcı varsayılan ANSI kod sayfasının kullanımını belirtmek için sırasıyla bir kod sayfası numarası yerine kullanılabilir.

- `setlocale( LC_ALL, "" );`

   Yerel ayarı, işletim sisteminden alınan kullanıcının varsayılan ANSI kod sayfası olan varsayılana ayarlar. Yerel ad [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)tarafından döndürülen değere ayarlanır. Kod sayfası [GetACP](/windows/win32/api/winnls/nf-winnls-getacp)tarafından döndürülen değere ayarlanır.

- `setlocale( LC_ALL, ".OCP" );`

   Yerel alanı işletim sisteminden elde edilen geçerli OEM kod sayfasına ayarlar. Yerel ad [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)tarafından döndürülen değere ayarlanır. Kod sayfası [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)tarafından kullanıcı varsayılan yerel adı için [LOCALE_IDEFAULTCODEPAGE](/windows/win32/intl/locale-idefault-constants) değeri ayarlanır.

- `setlocale( LC_ALL, ".ACP" );`

   Yerel ayarı işletim sisteminden alınan geçerli ANSI kod sayfasına ayarlar. Yerel ad [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)tarafından döndürülen değere ayarlanır. Kod sayfası [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)tarafından kullanıcı varsayılan yerel adı için [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) değeri ayarlanır.

- `setlocale( LC_ALL, "<localename>" );`

   Yerel adı niçin yerel * \< *adla>ayarlar. Kod sayfası [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)tarafından belirtilen yerel ad için [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) değeri ayarlanır.

- `setlocale( LC_ALL, "<language>_<country>" );`

   Yerel alanı, ana bilgisayar işletim sisteminden elde edilen varsayılan kod sayfasıyla birlikte * \<dil>* ve * \<ülke>* tarafından belirtilen dile ve ülke/bölgeye ayarlar. Kod sayfası [GetLocaleInfoEx](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)tarafından belirtilen yerel ad için [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) değeri ayarlanır.

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   Yer yerini dil, ülke>ve * \<code_page>* dizeleri * \<>* belirtilen dil, * \<ülke/bölge *ve kod sayfasına ayarlar. Dilin, ülkenin/bölgenin ve kod sayfasının çeşitli birleşimlerini kullanabilirsiniz. Örneğin, bu çağrı yerel ayarı kod sayfası 1252 ile Fransızca Kanada olarak ayarlar:

   `setlocale( LC_ALL, "French_Canada.1252" );`

   Bu çağrı yerel ayarı varsayılan ANSI kod sayfasıyla Fransızca Kanada olarak ayarlar:

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   Bu çağrı yerel ayarı varsayılan OEM kod sayfasıyla Fransızca Kanada olarak ayarlar:

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   Yerel bilgisayarı * \<dil>* tarafından belirtilen dile ayarlar ve ana bilgisayar işletim sisteminden elde edilen belirtilen dil için varsayılan ülke/bölge ve söz sahibi işletim sisteminden elde edilen o ülke/bölge için kullanıcı varsayılan ANSI kod sayfasını kullanır. Örneğin, **ayaryerele** için aşağıdaki çağrılar işlevsel olarak eşdeğerdir:

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   Performans ve bakım için ilk biçimi öneririz.

- `setlocale( LC_ALL, ".<code_page>" );`

   Kod sayfasını, belirtilen kod sayfası için varsayılan ülke/bölge ve dil (ana bilgisayar işletim sistemi tarafından tanımlandığı şekilde) ile *birlikte,>code_page<* tarafından belirtilen değere ayarlar.

Kategori, kod sayfası değişikliğini etkilemek için **LC_ALL** veya **LC_CTYPE** olmalıdır. Örneğin, ana bilgisayar işletim sisteminin varsayılan ülkesi/bölgesi ve dili "Abd" ve "İngilizce" ise, aşağıdaki iki **çağrıyı ayarla** işlevsel olarak eşdeğerdir:

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

Daha fazla bilgi için [C/C++ Önişlemci Başvurusu'ndaki](../../preprocessor/c-cpp-preprocessor-reference.md) [setlocale](../../preprocessor/setlocale.md) pragma yönergesi'ne bakın.

[_configthreadlocale](configthreadlocale.md) işlevi, **setlocale'nin** bir programdaki tüm iş parçacıklarının veya yalnızca çağrı iş parçacığının yerel kümesini mi etkilediğini denetlemek için kullanılır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**setlocale**|\<locale.h>|
|**_wsetlocale**|\<locale.h> \<veya wchar.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

    // Enable per-thread locale causes all subsequent locale
    // setting changes in this thread to only affect this thread.
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

[Yerel Adlar, Diller ve Ülke/Bölge Dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[_configthreadlocale](configthreadlocale.md)\
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)\
[Yerel ayar](../../c-runtime-library/locale.md)\
[Localeconv](localeconv.md)\
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)\
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)\
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)\
[_setmbcp](setmbcp.md)\
[strcoll Fonksiyonları](../../c-runtime-library/strcoll-functions.md)\
[strftime, wcsftime, _strftime_l, _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)\
[strxfrm, wcsxfrm, _strxfrm_l, _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)\
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)\
[wctomb, _wctomb_l](wctomb-wctomb-l.md)
