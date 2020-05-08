---
title: _configthreadlocale
ms.date: 4/2/2020
api_name:
- _configthreadlocale
- _o__configthreadlocale
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
- _configthreadlocale
- configthreadlocale
helpviewer_keywords:
- configthreadlocale function
- locales, per-thread
- _configthreadlocale function
- per-thread locale
- thread locale
ms.assetid: 10e4050e-b587-4f30-80bc-6c76b35fc770
ms.openlocfilehash: 26bcfe0d93a8c2b1a14e6afc0d413a5c7e4a7f6e
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82917315"
---
# <a name="_configthreadlocale"></a>_configthreadlocale

İş parçacığı başına yerel ayar seçeneklerini yapılandırır.

## <a name="syntax"></a>Sözdizimi

```C
int _configthreadlocale( int per_thread_locale_type );
```

### <a name="parameters"></a>Parametreler

*per_thread_locale_type*<br/>
Ayarlanacak seçenek. Aşağıdaki tabloda listelenen seçeneklerden biridir.

## <a name="return-value"></a>Dönüş Değeri

Önceki iş parçacığı başına yerel ayar durumu (**_DISABLE_PER_THREAD_LOCALE** veya **_ENABLE_PER_THREAD_LOCALE**) veya hata durumunda-1.

## <a name="remarks"></a>Açıklamalar

**_Configurethreadlocale** işlevi, iş parçacığına özgü yerel ayarların kullanımını denetlemek için kullanılır. İş parçacığı başına yerel ayar durumunu belirtmek veya belirlemek için bu *per_thread_locale_type* seçeneklerden birini kullanın:

| Seçenek | Açıklama |
|-|-|
| **_ENABLE_PER_THREAD_LOCALE** | Geçerli iş parçacığının iş parçacığına özgü yerel ayar kullanmasını sağlayın. Bu iş parçacığında **setlocale** 'e yapılan sonraki çağrılar yalnızca iş parçacığının kendi yerel ayarını etkiler. |
| **_DISABLE_PER_THREAD_LOCALE** | Geçerli iş parçacığının genel yerel ayarı kullanmasını sağlayın. Bu iş parçacığında **setlocale** 'e yapılan sonraki çağrılar, genel yerel ayarı kullanan diğer iş parçacıklarını etkiler. |
| **0** | Bu belirli iş parçacığının geçerli ayarını alır. |

Bu işlevler, **setlocale**, **_tsetlocale**, **_wsetlocale**ve **_setmbcp**davranışlarını etkiler. İş parçacığı başına yerel ayar devre dışı bırakıldığında, **setlocale** veya **_wsetlocale** için sonraki tüm çağrı, genel yerel ayarı kullanan tüm iş parçacıklarının yerel ayarını değiştirir. İş parçacığı başına yerel ayar etkinleştirildiğinde, **setlocale** veya **_wsetlocale** yalnızca geçerli iş parçacığının yerel ayarını etkiler.

İş parçacığı başına yerel ayarı etkinleştirmek için **_configurethreadlocale** kullanırsanız, bu iş parçacığında tercih edilen yerel ayarı hemen daha sonra ayarlamak için **setlocale** veya **_wsetlocale** çağırmanız önerilir.

*Per_thread_locale_type* tabloda listelenen değerlerden biri değilse, bu Işlev [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve-1 döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_configthreadlocale**|\<locale. h>|

## <a name="example"></a>Örnek

```cpp
// crt_configthreadlocale.cpp
//
// This program demonstrates the use of _configthreadlocale when
// using two independent threads.
//
// Compile by using: cl /EHsc /W4 crt_configthreadlocale.cpp

#include <locale.h>
#include <mbctype.h>
#include <process.h>
#include <windows.h>
#include <stdio.h>
#include <time.h>

#define BUFF_SIZE 100

// Retrieve the date and time in the current
// locale's format.
int get_time(unsigned char* str)
{
    __time64_t  ltime;
    struct tm   thetime;

    // Retieve the time
    _time64(&ltime);
    _gmtime64_s(&thetime, &ltime);

    // Format the current time structure into a string
    // using %#x is the long date representation,
    // appropriate to the current locale
    if (!strftime((char *)str, BUFF_SIZE, "%#x",
                  (const struct tm*)&thetime))
    {
        printf("strftime failed!\n");
        return -1;
    }
    return 0;
}

// This thread sets its locale to German
// and prints the time.
unsigned __stdcall SecondThreadFunc( void* /*pArguments*/ )
{
    unsigned char str[BUFF_SIZE];

    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Set the thread code page
    _setmbcp(_MB_CP_ANSI);

    // Set the thread locale
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "German"));

    // Retrieve the time string from the helper function
    if (get_time(str) == 0)
    {
        printf("The time in German locale is: '%s'\n", str);
    }

    _endthreadex( 0 );
    return 0;
}

// The main thread spawns a second thread (above) and then
// sets the locale to English and prints the time.
int main()
{
    HANDLE          hThread;
    unsigned        threadID;
    unsigned char   str[BUFF_SIZE];

    // Enable per-thread locale causes all subsequent locale
    // setting changes in this thread to only affect this thread.
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);

    // Retrieve the time string from the helper function
    printf("The thread locale is now set to %s.\n",
           setlocale(LC_ALL, "English"));

    // Create the second thread.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc,
                                      NULL, 0, &threadID );

    if (get_time(str) == 0)
    {
        // Retrieve the time string from the helper function
        printf("The time in English locale is: '%s'\n\n", str);
    }

    // Wait for the created thread to finish.
    WaitForSingleObject( hThread, INFINITE );

    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
The thread locale is now set to English_United States.1252.
The time in English locale is: 'Wednesday, May 12, 2004'

The thread locale is now set to German_Germany.1252.
The time in German locale is: 'Mittwoch, 12. Mai 2004'
```

## <a name="see-also"></a>Ayrıca bkz.

[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[_beginthread, _beginthreadex](beginthread-beginthreadex.md)<br/>
[Ayarlar](../../c-runtime-library/locale.md)<br/>
[Çoklu İş Parçacığı Kullanımı ve Yerel Ayarlar](../../parallel/multithreading-and-locales.md)<br/>
