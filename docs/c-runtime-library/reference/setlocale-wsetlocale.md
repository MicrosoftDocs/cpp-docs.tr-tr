---
title: setlocale, _wsetlocale
description: Microsoft C çalışma zamanı (CRT) kitaplığı işlevlerini ve öğesini açıklar setlocale _wsetlocale .
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 812aab43667416a5892d8e24d03d0e67cad8d0ac
ms.sourcegitcommit: b51703a96ee35ee2376d5f0775b70f03ccbe6d9a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88087000"
---
# <a name="no-locsetlocale-no-loc_wsetlocale"></a>setlocale, _wsetlocale

Çalışma zamanı yerel ayarını ayarlar veya alır.

## <a name="syntax"></a>Söz dizimi

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

*alan*\
Yerel ayardan etkilenen kategori.

*ayarlar*\
Yerel ayar tanımlayıcı.

## <a name="return-value"></a>Döndürülen değer

Geçerli bir *yerel ayar* ve *Kategori* verilirse, belirtilen *yerel ayar* ve *kategoriyle*ilişkili dizeye bir işaretçi döndürür. *Yerel ayar* veya *Kategori* geçerli değilse, null bir işaretçi döndürür ve programın geçerli yerel ayarları değiştirilmez.

Örneğin, çağrı:

```C
setlocale( LC_ALL, "en-US" );
```

yalnızca dizeyi döndürür ve tüm kategorileri ayarlar

```Output
en-US
```

`setlocale`Programın yerel ayar bilgilerinin o bölümünü geri yüklemek için tarafından döndürülen dizeyi kopyalayabilirsiniz. Küresel veya iş parçacığı yerel depolaması tarafından döndürülen dize için kullanılır `setlocale` . Daha sonra `setlocale` , önceki çağrılar tarafından döndürülen dize işaretçilerini geçersiz kılan dizenin üzerine yazmak için çağırır.

## <a name="remarks"></a>Açıklamalar

`setlocale` *Yerel ayar* ve *Kategori*tarafından belirtilen geçerli program yerel ayar bilgilerinin bazılarını veya tümünü ayarlamak, değiştirmek veya sorgulamak için işlevini kullanın. *yerel ayar* , programınızın belirli yönlerini özelleştirebileceğiniz yere (ülke/bölge ve dil) başvurur. Bazı yerel ayara bağımlı kategoriler tarih biçimlendirmesini ve parasal değerlerin görüntülenme biçimini içerir. Bilgisayarınızda birden çok form desteklenen bir dil için varsayılan dizeye *yerel ayar* ayarlarsanız, `setlocale` hangi dilin geçerli olduğunu görmek için dönüş değerini denetlemeniz gerekir. Örneğin, *yerel ayarı* "Çince" olarak ayarlarsanız, dönüş değeri "Çince-Basitleştirilmiş" ya da "Çince-Geleneksel" olabilir.

`_wsetlocale`, öğesinin geniş karakterli bir sürümüdür `setlocale` ; *yerel ayar* bağımsız değişkeni ve dönüş değeri `_wsetlocale` geniş karakterli dizelerdir. `_wsetlocale`ve `setlocale` aynı şekilde davranır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|`_tsetlocale`|`setlocale`|`setlocale`|`_wsetlocale`|

*Kategori* bağımsız değişkeni, bir programın etkilenen yerel ayar bilgilerinin parçalarını belirtir. *Kategori* için kullanılan makrolar ve bu programın etkilediği bölümleri şunlardır:

|*Kategori* bayrağı|Ekranlarını|
|-|-|
| `LC_ALL` | Aşağıda listelendiği gibi tüm kategoriler. |
| `LC_COLLATE` | ,,,,, `strcoll` `_stricoll` `wcscoll` `_wcsicoll` `strxfrm` `_strncoll` , `_strnicoll` , `_wcsncoll` , `_wcsnicoll` Ve `wcsxfrm` işlevleri. |
| `LC_CTYPE` | Karakter işleme işlevleri ( `isdigit` etkilenmeden,, `isxdigit` ve hariç `mbstowcs` `mbtowc` ). |
| `LC_MONETARY` | İşlevin döndürdüğü parasal biçimlendirme bilgileri `localeconv` . |
| `LC_NUMERIC` | Biçimlendirilmiş çıkış yordamları (gibi `printf` ) için, veri dönüştürme yordamları için ve tarafından döndürülen parasal olmayan biçimlendirme bilgileri için ondalık nokta karakteri `localeconv` . Ondalık noktası karakterinin yanı sıra, `LC_NUMERIC` binlerce ayırıcıyı ve [localeconv](localeconv.md)tarafından döndürülen gruplama denetimi dizesini ayarlar. |
| `LC_TIME` | `strftime`Ve `wcsftime` işlevleri. |

Bu işlev, kategori parametresini doğrular. Kategori parametresi önceki tabloda verilen değerlerden biri değilse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa işlev `errno` olarak ayarlanır `EINVAL` ve döndürür `NULL` .

*Yerel ayar* bağımsız değişkeni, yerel ayarı belirten bir dizeye yönelik bir işaretçidir. *Yerel ayar* bağımsız değişkeninin biçimi hakkında daha fazla bilgi için bkz. [yerel ayar adları, diller ve ülke/bölge dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md). *Yerel ayar* boş bir dizeye işaret ediyorsa, yerel ayar uygulama tanımlı yerel ortamdır. Değeri `C` , C çevirisi için en az ANSI uyumlu ortamı belirtir. `C`Yerel ayar tüm ``char`` veri türlerinin 1 bayt olduğunu ve değerinin her zaman 256 ' den küçük olduğunu varsayar.

Program açılışında, aşağıdaki ifadenin eşdeğeri çalıştırılır:

`setlocale( LC_ALL, "C" );`

*Yerel ayar* bağımsız değişkeni bir yerel ayar adı, bir dil dizesi, bir dil dizesi ve ülke/bölge kodu, kod sayfası veya dil dizesi, ülke/bölge kodu ve kod sayfası alabilir. Kullanılabilir yerel ayar adları, diller, ülke/bölge kodları ve kod sayfaları kümesi, Windows NLS API 'SI tarafından desteklenen tüm bunları içerir. Tarafından desteklenen yerel ayar adları kümesi, `setlocale` [yerel ayar adları, diller ve ülke/bölge dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)bölümünde açıklanmaktadır. Tarafından desteklenen dil ve ülke/bölge dizeleri kümesi, `setlocale` [dil dizeleri](../../c-runtime-library/language-strings.md) ve [ülke/bölge dizeleri](../../c-runtime-library/country-region-strings.md)bölümünde listelenmiştir. Kod içinde gömülü veya depolama için seri hale getirilmiş yerel ayar dizelerinin devamlılığı ve performansı için yerel ayar adı biçimi öneririz. Yerel ayar adı dizelerinin bir işletim sistemi güncelleştirmesi tarafından değiştirilmesi olasılığı dil ve ülke/bölge adı biçiminin değiştirilmesi olasılığından daha düşüktür.

*Yerel ayar* bağımsız değişkeni olarak geçirilmiş bir null işaretçi, `setlocale` Uluslararası ortamı ayarlamak için yerine sorgu belirtir. *Yerel ayar* bağımsız değişkeni null işaretçisiyse, programın geçerli yerel ayarı değiştirilmez. Bunun yerine, `setlocale` iş parçacığının geçerli yerel ayarı *kategorisiyle* ilişkili dize için bir işaretçi döndürür. *Kategori* bağımsız değişkeni ise `LC_ALL` , işlev noktalı virgülle ayırarak her kategorinin geçerli ayarını gösteren bir dize döndürür. Örneğin, çağrı

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

kategori ile ilişkili dize `LC_ALL` .

Aşağıdaki örnekler `LC_ALL` kategoriye aittir. Dizeden birini kullanabilirsiniz. OCP "ve". Bu yerel ayar adı için sırasıyla Kullanıcı-varsayılan OEM kod sayfası ve Kullanıcı varsayılan ANSI kod sayfası kullanımını belirtmek için kod sayfası numarası yerine ACP "kullanılabilir.

- `setlocale( LC_ALL, "" );`

   Yerel ayarı, işletim sisteminden alınan kullanıcının varsayılan ANSI kod sayfası olan varsayılana ayarlar. Yerel ayar adı, [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)tarafından döndürülen değere ayarlanır. Kod sayfası [GetACP](/windows/win32/api/winnls/nf-winnls-getacp)tarafından döndürülen değere ayarlanır.

- `setlocale( LC_ALL, ".OCP" );`

   Yerel ayarı işletim sisteminden alınan geçerli OEM kod sayfasına ayarlar. Yerel ayar adı, [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)tarafından döndürülen değere ayarlanır. Kod sayfası, [Getlocaleınfoex](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)tarafından kullanıcının varsayılan yerel ayar adı için [LOCALE_IDEFAULTCODEPAGE](/windows/win32/intl/locale-idefault-constants) değerine ayarlanır.

- `setlocale( LC_ALL, ".ACP" );`

   Yerel ayarı işletim sisteminden alınan geçerli ANSI kod sayfasına ayarlar. Yerel ayar adı, [GetUserDefaultLocaleName](/windows/win32/api/winnls/nf-winnls-getuserdefaultlocalename)tarafından döndürülen değere ayarlanır. Kod sayfası, [Getlocaleınfoex](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)tarafından kullanıcının varsayılan yerel ayar adı için [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) değerine ayarlanır.

- `setlocale( LC_ALL, "<localename>" );`

   Yerel ayarı tarafından belirtilen yerel ayar adına ayarlar *\<localename>* . Kod sayfası, [Getlocaleınfoex](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)tarafından belirtilen yerel ayar adı için [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) değerine ayarlanır.

- `setlocale( LC_ALL, "<language>_<country>" );`

   Yerel ayarı ve ile belirtilen ülkeye/bölgeye *\<language>* *\<country>* , ana bilgisayar işletim sisteminden alınan varsayılan kod sayfasıyla birlikte ayarlar. Kod sayfası, [Getlocaleınfoex](/windows/win32/api/winnls/nf-winnls-getlocaleinfoex)tarafından belirtilen yerel ayar adı için [LOCALE_IDEFAULTANSICODEPAGE](/windows/win32/intl/locale-idefault-constants) değerine ayarlanır.

- `setlocale( LC_ALL, "<language>_<country>.<code_page>" );`

   Yerel ayarı,, ve dizeleri tarafından belirtilen dile, ülkeye/bölgeye ve kod sayfasına ayarlar *\<language>* *\<country>* *\<code_page>* . Dilin, ülkenin/bölgenin ve kod sayfasının çeşitli birleşimlerini kullanabilirsiniz. Örneğin, bu çağrı yerel ayarı kod sayfası 1252 ile Fransızca Kanada olarak ayarlar:

   `setlocale( LC_ALL, "French_Canada.1252" );`

   Bu çağrı yerel ayarı varsayılan ANSI kod sayfasıyla Fransızca Kanada olarak ayarlar:

   `setlocale( LC_ALL, "French_Canada.ACP" );`

   Bu çağrı yerel ayarı varsayılan OEM kod sayfasıyla Fransızca Kanada olarak ayarlar:

   `setlocale( LC_ALL, "French_Canada.OCP" );`

- `setlocale( LC_ALL, "<language>" );`

   Yerel ayarı tarafından belirtilen dile ayarlar *\<language>* ve belirtilen dile ait varsayılan ülkeyi/bölgeyi ve bu ülkenin/bölgenin ana bilgisayar işletim sisteminden elde edilen Kullanıcı varsayılan ANSI kod sayfasını kullanır. Örneğin, için aşağıdaki çağrılar işlevsel olarak `setlocale` eşdeğerdir:

   `setlocale( LC_ALL, "en-US" );`

   `setlocale( LC_ALL, "English" );`

   `setlocale( LC_ALL, "English_United States.1252" );`

   Performans ve bakım için ilk biçimi öneririz.

- `setlocale( LC_ALL, ".<code_page>" );`

   Kod sayfasını, belirtilen kod sayfası için varsayılan ülke/bölge ve dil (ana bilgisayar işletim sistemi tarafından tanımlandığı şekilde) ile birlikte *<code_page>* tarafından belirtilen değere ayarlar.

Kategori, `LC_ALL` `LC_CTYPE` kod sayfası değişikliğini uygulamak için ya da olmalıdır. Örneğin, ana bilgisayar işletim sisteminin varsayılan ülkesi/bölgesi ve dili "Birleşik Devletler" ve "English" ise, aşağıdaki iki çağrı `setlocale` işlevsel olarak eşdeğerdir:

`setlocale( LC_ALL, ".1252" );`

`setlocale( LC_ALL, "English_United States.1252");`

Daha fazla bilgi için bkz [setlocale](../../preprocessor/setlocale.md) . [C/C++ Önişlemci Başvurusu](../../preprocessor/c-cpp-preprocessor-reference.md)içindeki pragma yönergesi.

İşlev [_configthreadlocale](configthreadlocale.md) , `setlocale` bir programdaki tüm iş parçacıklarının yerel ayarını veya yalnızca çağıran iş parçacığının yerel ayarını etkileyip etkilemediğini denetlemek için kullanılır.

## <a name="utf-8-support"></a>UTF-8 desteği

Windows 10 Build 17134 ' den itibaren (2018 Nisan güncelleştirme), evrensel C çalışma zamanı UTF-8 kod sayfasını kullanmayı destekler. Bu `char` , C çalışma zamanı işlevlerine geçirilen DIZELERIN UTF-8 kodlamasında dizeler beklediği anlamına gelir. UTF-8 modunu etkinleştirmek için kullanırken kod sayfası olarak "UTF-8" kullanın `setlocale` . Örneğin, `setlocale(LC_ALL, ".utf8")` yerel ayar için geçerli varsayılan WINDOWS ANSI kod sayfasını (ACP) ve kod sayfası IÇIN UTF-8 ' i kullanacaktır.

Çağrıldıktan sonra `setlocale(LC_ALL, ".UTF8")` , " 😊 " öğesine geçiş yapabilirsiniz `mbtowcs` ve `wchar_t` daha önce bunu yapmak için kullanılabilir bir yerel ayar olmadığı halde bir dizeye doğru bir şekilde çevrilir.

UTF-8 modu, `char` varsayılan WINDOWS ANSI kod sayfası (ACP) kullanılarak tarihsel olarak çevrilmiş dizeler içeren işlevler için de etkinleştirilir. Örneğin, [`_mkdir("😊")`](../reference/mkdir-wmkdir.md) BIR UTF-8 kod sayfası kullanılırken çağırmak, programınızı çalıştırmadan önce ACP 'nın UTF-8 olarak değiştirilmesini gerektirmek yerine, bu emojiye sahip bir dizini doğru şekilde oluşturacaktır. Benzer şekilde, [`_getcwd()`](../reference/getcwd-wgetcwd.md) Bu klasörün içine ÇAĞıRMAK UTF-8 kodlu bir dize döndürür. Uyumluluk için C yerel ayar kodu sayfası UTF-8 olarak ayarlanmamışsa, bu, hala kullanır.

UTF-8 kullanamayacak olan C çalışma zamanının, program başlatılırken ayarlandığı ve varsayılan Windows ANSI kod sayfası (ACP) kullanması gereken aşağıdaki yönleri: [`__argv`](../argc-argv-wargv.md) , [`_acmdln`](../acmdln-tcmdln-wcmdln.md) ve [`_pgmptr`](../pgmptr-wpgmptr.md) .

Bu [ `mbrtoc16` `mbrtoc32` desteğe,, ](../reference/mbrtoc16-mbrtoc323.md), [ `c16rtomb` `c32rtomb` ve](../reference/c16rtomb-c32rtomb1.md) UTF-8 dar dizeleri, UTF-16 ( `wchar_t` Windows platformlarındaki aynı kodlama) ve UTF-32 arasında çeviri yapmak için de vardı. Uyumluluk nedenleriyle, bu API 'Ler aracılığıyla yalnızca UTF-8 ' e veya UTF-8 ' i çevirmektedir `setlocale` .

Windows 7 gibi Windows 10 ' dan önceki bir işletim sisteminde bu özelliği kullanmak için, [uygulama yerel dağıtımı](../../windows/universal-crt-deployment.md#local-deployment) kullanmanız veya Windows SDK veya üzeri sürüm 17134 ' i kullanarak statik olarak bağlamanız gerekir. 17134 ' dan önceki Windows 10 işletim sistemleri için yalnızca statik bağlama desteklenir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`setlocale`|\<locale.h>|
|`_wsetlocale`|\<locale.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Yerel ayar adları, diller ve ülke/bölge dizeleri](../../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[_configthreadlocale](configthreadlocale.md)\
[_create_locale, _wcreate_locale](create-locale-wcreate-locale.md)\
[Ayarlar](../../c-runtime-library/locale.md)\
[localeconv](localeconv.md)\
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)\
[strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)\
[mbstowcs, _mbstowcs_l](mbstowcs-mbstowcs-l.md)\
[mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md)\
[_setmbcp](setmbcp.md)\
[strcoll Işlevleri](../../c-runtime-library/strcoll-functions.md)\
[strftime, wcsftime, _strftime_l _wcsftime_l](strftime-wcsftime-strftime-l-wcsftime-l.md)\
[strxfrm, wcsxfrm, _strxfrm_l _wcsxfrm_l](strxfrm-wcsxfrm-strxfrm-l-wcsxfrm-l.md)\
[wcstombs, _wcstombs_l](wcstombs-wcstombs-l.md)\
[wctomb, _wctomb_l](wctomb-wctomb-l.md)
