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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 46983843e128b59df89722c8d4694c30a858011f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348537"
---
# <a name="_configthreadlocale"></a>_configthreadlocale

İş parçacığı başına yerel seçenekleri yapılandırır.

## <a name="syntax"></a>Sözdizimi

```C
int _configthreadlocale( int per_thread_locale_type );
```

### <a name="parameters"></a>Parametreler

*per_thread_locale_type*<br/>
Ayarlama seçeneği. Aşağıdaki tabloda listelenen seçeneklerden biri.

## <a name="return-value"></a>Dönüş Değeri

Önceki iş parçacığı yerel durumu **(_DISABLE_PER_THREAD_LOCALE** veya **_ENABLE_PER_THREAD_LOCALE),** veya -1 hata.

## <a name="remarks"></a>Açıklamalar

İş parçacığına özgü yerel birimlerin kullanımını denetlemek için **_configurethreadlocale** işlevi kullanılır. İş parçacığı başına yerel durumu belirtmek veya belirlemek için aşağıdaki *per_thread_locale_type* seçeneklerinden birini kullanın:

| Seçenek | Açıklama |
|-|-|
| **_ENABLE_PER_THREAD_LOCALE** | Geçerli iş parçacığının iş parçacığına özgü bir yerel nokta kullanmasını sağlayabilir. Bu iş **parçacığında ayaryerele** sonraki çağrılar yalnızca iş parçacığının kendi yerel ayarını etkiler. |
| **_DISABLE_PER_THREAD_LOCALE** | Geçerli iş parçacığının genel yerel durumu kullanmasını sağlayabilir. Bu iş **parçacığında ayaryerele** sonraki çağrılar genel yerel ayar kullanarak diğer iş parçacığı etkiler. |
| **0** | Bu özel iş parçacığı için geçerli ayarı alır. |

Bu işlevler **setlocale**davranışını etkiler , **_tsetlocale**, **_wsetlocale**, ve **_setmbcp.** İş parçacığı başına yerel ayar devre dışı bırakıldığında, **kümeyerele** veya **_wsetlocale** sonraki herhangi bir çağrı, genel yerel alanı kullanan tüm iş parçacıklarının yerel liğini değiştirir. İş parçacığı başına yerel ayar etkinleştirildiğinde, **ayaryerel veya** **_wsetlocale** yalnızca geçerli iş parçacığının yerel liğini etkiler.

İş parçacığı başına yerel bir yerel ayar etkinleştirmek için **_configurethreadlocale** kullanıyorsanız, hemen sonra bu iş parçacığı tercih edilen yerel ayar ayarlamak için **setlocale** veya **_wsetlocale** aramanızı öneririz.

*per_thread_locale_type* tabloda listelenen değerlerden biri değilse, bu işlev [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin verilirse, bu işlev **errno'u** **EINVAL'e** ayarlar ve -1 döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_configthreadlocale**|\<locale.h>|

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
[Yerel Ayar](../../c-runtime-library/locale.md)<br/>
[Çoklu İş Parçacığı Kullanımı ve Yerel Ayarlar](../../parallel/multithreading-and-locales.md)<br/>
