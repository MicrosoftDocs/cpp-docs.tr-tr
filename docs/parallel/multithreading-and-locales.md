---
title: Çoklu İş Parçacığı Kullanımı ve Yerel Ayarlar
ms.date: 11/04/2016
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
ms.openlocfilehash: c12a3fa1922db7a1ec0a7bcd43ddf09000d97961
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293608"
---
# <a name="multithreading-and-locales"></a>Çoklu İş Parçacığı Kullanımı ve Yerel Ayarlar

Hem C Çalışma Zamanı Kitaplığı hem de C++ Standart Kitaplığı programınızın yerel ayarı değiştirmek için destek sağlar. Bu konu, çok iş parçacıklı bir uygulamada hem kitaplıkların yerel ayar işlevselliği kullanıldığında ortaya çıkan sorunları açıklar.

## <a name="remarks"></a>Açıklamalar

C çalışma zamanı kitaplığı ile kullanarak birden çok iş parçacıklı uygulamalar oluşturabilirsiniz `_beginthread` ve `_beginthreadex` işlevleri. Bu konu, yalnızca bu işlevler kullanılarak oluşturulmuş birden çok iş parçacıklı uygulamalar kapsar. Daha fazla bilgi için [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md).

C Çalışma Zamanı Kitaplığı'nı kullanarak yerel ayarı değiştirmek için kullanın [setlocale](../preprocessor/setlocale.md) işlevi. Visual C++ önceki sürümlerinde, bu işlev her zaman uygulamanın tamamı boyunca Yereli değiştirirsiniz. Bir iş parçacığı başına temelinde yerel ayar için şimdi desteği yoktur. Bu yapılır kullanarak [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) işlevi. Belirtmek için [setlocale](../preprocessor/setlocale.md) yalnızca çağrı geçerli iş parçacığı yerel ayarı değiştirmelisiniz `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` , bir iş parçacığı. Buna karşılık, çağırma `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` neden olur, iş parçacığı kullanımı genel yerel ayar ve yapılan tüm çağrıların [setlocale](../preprocessor/setlocale.md) iş parçacığı yerel ayarı açıkça iş parçacığı başına yerel ayar etkinleştirmediniz tüm iş parçacıklarının değiştirir.

C++ Çalışma Zamanı Kitaplığı'nı kullanarak yerel ayarı değiştirmek için kullanın [locale sınıfı](../standard-library/locale-class.md). Çağırarak [locale::global](../standard-library/locale-class.md#global) yöntemi açıkça iş parçacığı başına yerel ayar etkinleştirmedi her iş parçacığı yerel ayarı değiştirebilirsiniz. Yerel bir tek iş parçacığı veya bir uygulamanın bir bölümünü değiştirmek için yalnızca bir örneğini oluşturmak bir `locale` nesne iş parçacığı veya bir kod parçası.

> [!NOTE]
> Çağırma [locale::global](../standard-library/locale-class.md#global) yerel C++ Standart Kitaplığı ve C çalışma zamanı kitaplığı için değiştirir. Ancak, çağırma [setlocale](../preprocessor/setlocale.md) C çalışma zamanı kitaplığı; C++ Standart Kitaplığı etkilenmez için yalnızca yerel ayarı değiştirir.

Aşağıdaki örnekler nasıl kullanılacağını [setlocale](../preprocessor/setlocale.md) işlevi [locale sınıfı](../standard-library/locale-class.md)ve [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) bulunan bir uygulamanın yerel ayarı değiştirmek için işlevi birkaç farklı senaryolar.

## <a name="example"></a>Örnek

Bu örnekte, iki alt iş parçacığı ana iş parçacığı olarak çoğaltılır. Çağırarak ilk iş parçacığı, iş parçacığı, bir iş parçacığı başına yerel ayar sağlayan `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. İkinci iş parçacığının, iş parçacığı B yanı sıra, ana iş parçacığı başına iş parçacığı yerel ayarı etkinleştirmeyin. İş parçacığı yerel ayarı kullanarak değiştirmeye geçer [setlocale](../preprocessor/setlocale.md) C çalışma zamanı kitaplığı işlevi.

Bir iş parçacığı etkin iş parçacığı başına yerel ayar yalnızca "Fransızca" yerel ayarı kullanarak bir iş parçacığı Başlangıç'ta C çalışma zamanı kitaplığı işlevleri olduğundan. C çalışma zamanı kitaplığı işlevleri b iş parçacığı ve ana iş parçacığı "C" yerel kullanmaya devam edin. Ayrıca, bu yana [setlocale](../preprocessor/setlocale.md) tüm C++ Standart Kitaplığı nesneleri "C" yerel kullanmaya devam C++ Standart Kitaplığı yerel ayar etkilemez.

```cpp
// multithread_locale_1.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    setlocale(LC_ALL, "french");
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "French_France.1252"
[Thread A] locale::global is set to "C"

[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "C"
[Thread B] locale::global is set to "C"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "C"
[Thread main] locale::global is set to "C"
```

## <a name="example"></a>Örnek

Bu örnekte, iki alt iş parçacığı ana iş parçacığı olarak çoğaltılır. Çağırarak ilk iş parçacığı, iş parçacığı, bir iş parçacığı başına yerel ayar sağlayan `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. İkinci iş parçacığının, iş parçacığı B yanı sıra, ana iş parçacığı başına iş parçacığı yerel ayarı etkinleştirmeyin. İş parçacığı yerel ayarı kullanarak değiştirmeye geçer [locale::global](../standard-library/locale-class.md#global) C++ Standart Kitaplığı'nın yöntemi.

Bir iş parçacığı etkin iş parçacığı başına yerel ayar yalnızca "Fransızca" yerel ayarı kullanarak bir iş parçacığı Başlangıç'ta C çalışma zamanı kitaplığı işlevleri olduğundan. C çalışma zamanı kitaplığı işlevleri b iş parçacığı ve ana iş parçacığı "C" yerel kullanmaya devam edin. Ancak, bu yana [locale::global](../standard-library/locale-class.md#global) yöntemi değişiklikleri yerel ayarları "Genel", "Fransızca" yerel ayarını kullanarak tüm iş parçacıklarının tüm C++ Standart Kitaplığı nesneleri başlatın.

```cpp
// multithread_locale_2.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    locale::global(locale("french"));
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "French_France.1252"
[Thread A] locale::global is set to "French_France.1252"

[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "C"
[Thread B] locale::global is set to "French_France.1252"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "C"
[Thread main] locale::global is set to "French_France.1252"
```

## <a name="example"></a>Örnek

Bu örnekte, iki alt iş parçacığı ana iş parçacığı olarak çoğaltılır. Çağırarak ilk iş parçacığı, iş parçacığı, bir iş parçacığı başına yerel ayar sağlayan `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. İkinci iş parçacığının, iş parçacığı B yanı sıra, ana iş parçacığı başına iş parçacığı yerel ayarı etkinleştirmeyin. Daha sonra B iş parçacığı yerel ayarı kullanarak değiştirmeye devam eder [setlocale](../preprocessor/setlocale.md) C çalışma zamanı kitaplığı işlevi.

İş parçacığı B etkin iş parçacığı başına yerel ayar olmadığından "Fransızca" yerel ayarını kullanarak C çalışma zamanı kitaplığı işlevleri b iş parçacığı ve ana iş parçacığı başlatın. İş parçacığı bir iş parçacığı başına yerel ayar etkin olduğundan, "C" yerel ayarı kullanmaları için bir iş parçacığı devam C çalışma zamanı kitaplığı işlevleri. Ayrıca, bu yana [setlocale](../preprocessor/setlocale.md) tüm C++ Standart Kitaplığı nesneleri "C" yerel kullanmaya devam C++ Standart Kitaplığı yerel ayar etkilemez.

```cpp
// multithread_locale_3.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
BOOL configThreadLocaleCalled = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    configThreadLocaleCalled = TRUE;
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!configThreadLocaleCalled)
        Sleep(100);
    setlocale(LC_ALL, "french");
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "French_France.1252"
[Thread B] locale::global is set to "C"

[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "C"
[Thread A] locale::global is set to "C"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "French_France.1252"
[Thread main] locale::global is set to "C"
```

## <a name="example"></a>Örnek

Bu örnekte, iki alt iş parçacığı ana iş parçacığı olarak çoğaltılır. Çağırarak ilk iş parçacığı, iş parçacığı, bir iş parçacığı başına yerel ayar sağlayan `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. İkinci iş parçacığının, iş parçacığı B yanı sıra, ana iş parçacığı başına iş parçacığı yerel ayarı etkinleştirmeyin. Daha sonra B iş parçacığı yerel ayarı kullanarak değiştirmeye devam eder [locale::global](../standard-library/locale-class.md#global) C++ Standart Kitaplığı'nın yöntemi.

İş parçacığı B etkin iş parçacığı başına yerel ayar olmadığından "Fransızca" yerel ayarını kullanarak C çalışma zamanı kitaplığı işlevleri b iş parçacığı ve ana iş parçacığı başlatın. İş parçacığı bir iş parçacığı başına yerel ayar etkin olduğundan, "C" yerel ayarı kullanmaları için bir iş parçacığı devam C çalışma zamanı kitaplığı işlevleri. Ancak, bu yana [locale::global](../standard-library/locale-class.md#global) yöntemi değişiklikleri yerel ayarları "Genel", "Fransızca" yerel ayarını kullanarak tüm iş parçacıklarının tüm C++ Standart Kitaplığı nesneleri başlatın.

```cpp
// multithread_locale_4.cpp
// compile with: /EHsc /MD
#include <clocale>
#include <cstdio>
#include <locale>
#include <process.h>
#include <windows.h>

#define NUM_THREADS 2
using namespace std;

unsigned __stdcall RunThreadA(void *params);
unsigned __stdcall RunThreadB(void *params);

BOOL localeSet = FALSE;
BOOL configThreadLocaleCalled = FALSE;
HANDLE printMutex = CreateMutex(NULL, FALSE, NULL);

int main()
{
    HANDLE threads[NUM_THREADS];

    unsigned aID;
    threads[0] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadA, NULL, 0, &aID);

    unsigned bID;
    threads[1] = (HANDLE)_beginthreadex(
        NULL, 0, RunThreadB, NULL, 0, &bID);

    WaitForMultipleObjects(2, threads, TRUE, INFINITE);

    printf_s("[Thread main] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread main] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread main] locale::global is set to \"%s\"\n",
        locale().name().c_str());

    CloseHandle(threads[0]);
    CloseHandle(threads[1]);
    CloseHandle(printMutex);

    return 0;
}

unsigned __stdcall RunThreadA(void *params)
{
    _configthreadlocale(_ENABLE_PER_THREAD_LOCALE);
    configThreadLocaleCalled = TRUE;
    while (!localeSet)
        Sleep(100);

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread A] Per-thread locale is enabled.\n");
    printf_s("[Thread A] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread A] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}

unsigned __stdcall RunThreadB(void *params)
{
    while (!configThreadLocaleCalled)
        Sleep(100);
    locale::global(locale("french"));
    localeSet = TRUE;

    WaitForSingleObject(printMutex, INFINITE);
    printf_s("[Thread B] Per-thread locale is NOT enabled.\n");
    printf_s("[Thread B] CRT locale is set to \"%s\"\n",
        setlocale(LC_ALL, NULL));
    printf_s("[Thread B] locale::global is set to \"%s\"\n\n",
        locale().name().c_str());
    ReleaseMutex(printMutex);

    return 1;
}
```

```Output
[Thread B] Per-thread locale is NOT enabled.
[Thread B] CRT locale is set to "French_France.1252"
[Thread B] locale::global is set to "French_France.1252"

[Thread A] Per-thread locale is enabled.
[Thread A] CRT locale is set to "C"
[Thread A] locale::global is set to "French_France.1252"

[Thread main] Per-thread locale is NOT enabled.
[Thread main] CRT locale is set to "French_France.1252"
[Thread main] locale::global is set to "French_France.1252"
```

## <a name="see-also"></a>Ayrıca bkz.

[Eski Kod için Çoklu İş Parçacığı Kullanma Desteği (Visual C++)](multithreading-support-for-older-code-visual-cpp.md)<br/>
[_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)<br/>
[_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)<br/>
[setlocale](../preprocessor/setlocale.md)<br/>
[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[locale](../c-runtime-library/locale.md)<br/>
[\<clocale >](../standard-library/clocale.md)<br/>
[\<yerel ayar >](../standard-library/locale.md)<br/>
[locale Sınıfı](../standard-library/locale-class.md)
