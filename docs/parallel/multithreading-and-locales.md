---
title: Çoklu İş Parçacığı Kullanımı ve Yerel Ayarlar
ms.date: 11/04/2016
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
ms.openlocfilehash: 82b410c592e5b68737514dda5a864c7bd15f6dc3
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008585"
---
# <a name="multithreading-and-locales"></a>Çoklu İş Parçacığı Kullanımı ve Yerel Ayarlar

C çalışma zamanı kitaplığı ve C++ standart kitaplığı, programınızın yerel ayarını değiştirmek için destek sağlar. Bu konuda, çok iş parçacıklı bir uygulamada her iki kütüphaneden yerel ayar işlevselliği kullanılırken ortaya çıkan sorunlar ele alınmaktadır.

## <a name="remarks"></a>Açıklamalar

C çalışma zamanı kitaplığı ile ve işlevlerini kullanarak çok iş parçacıklı uygulamalar oluşturabilirsiniz `_beginthread` `_beginthreadex` . Bu konu yalnızca, bu işlevler kullanılarak oluşturulan çok iş parçacıklı uygulamaları içerir. Daha fazla bilgi için bkz. [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md).

C çalışma zamanı kitaplığını kullanarak yerel ayarı değiştirmek için [setlocale](../preprocessor/setlocale.md) işlevini kullanın. Visual C++ önceki sürümlerinde bu işlev her zaman tüm uygulamanın tamamında yerel ayarı değiştirecektir. İş parçacığı başına temelinde yerel ayarı ayarlamaya yönelik destek artık vardır. Bu, [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) işlevi kullanılarak yapılır. [Setlocale](../preprocessor/setlocale.md) 'in yalnızca geçerli iş parçacığındaki yerel ayarı değiştirmesi gerektiğini belirtmek için `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` Bu iş parçacığını çağırın. Bunun tersine, çağırma, `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` iş parçacığının genel yerel ayarı kullanmasına neden olur ve bu iş parçacığında herhangi bir [setlocale](../preprocessor/setlocale.md) çağrısı, iş parçacığı başına yerel ayar olarak açıkça etkinleştirilmemiş tüm iş parçacıklarında yerel ayarı değiştirir.

C++ çalışma zamanı kitaplığını kullanarak yerel ayarı değiştirmek için [yerel ayar sınıfını](../standard-library/locale-class.md)kullanın. [Locale:: Global](../standard-library/locale-class.md#global) metodunu çağırarak, iş parçacığı başına yerel ayarı açıkça etkinleştirilmemiş olan her iş parçacığında yerel ayarı değiştirirsiniz. Tek bir iş parçacığında veya bir uygulamanın bir bölümünde yerel ayarı değiştirmek için, `locale` Bu iş parçacığında veya kod bölümünde bir nesnenin örneğini oluşturmanız yeterlidir.

> [!NOTE]
> Çağıran [yerel ayar:: Global](../standard-library/locale-class.md#global) yerel ayarı hem C++ Standart Kitaplığı hem de C çalışma zamanı kitaplığı için değiştirir. Ancak, [setlocale](../preprocessor/setlocale.md) çağrısı yalnızca C çalışma zamanı kitaplığı için yerel ayarı değiştirir; C++ standart kitaplığı etkilenmemektedir.

Aşağıdaki örneklerde, birçok farklı senaryoda bir uygulamanın yerel ayarını değiştirmek için [setlocale](../preprocessor/setlocale.md) işlevinin, [locale sınıfının](../standard-library/locale-class.md)ve [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) işlevinin nasıl kullanılacağı gösterilmektedir.

## <a name="example-change-locale-with-per-thread-locale-enabled"></a>Örnek: iş parçacığı başına yerel ayar etkinken yerel ayarı değiştirin

Bu örnekte, ana iş parçacığı iki alt iş parçacığını çoğaltılır. İlk iş parçacığı olan Iş parçacığı A, çağırarak iş parçacığı başına yerel ayara izin vermez `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . İkinci iş parçacığı, Iş parçacığı B ve ana iş parçacığı, iş parçacığı başına yerel ayarı etkinleştirmeyin. Sonra bir iş parçacığı C çalışma zamanı kitaplığının [setlocale](../preprocessor/setlocale.md) işlevini kullanarak yerel ayarı değiştirmeye devam eder.

A Iş parçacığında iş parçacığı başına yerel ayar etkin olduğundan, yalnızca C çalışma zamanı kitaplığı "Fransızca" yerel ayarını kullanmaya başlar. B Iş parçacığındaki ve ana iş parçacığındaki C çalışma zamanı kitaplığı işlevleri "C" yerel ayarını kullanmaya devam eder. Ayrıca, [setlocale](../preprocessor/setlocale.md) C++ Standart Kitaplığı yerel ayarını etkilemediğinden, tüm C++ Standart Kitaplığı nesneleri "C" yerel ayarını kullanmaya devam eder.

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

## <a name="example-change-global-locale-with-per-thread-locale-enabled"></a>Örnek: genel yerel ayarı iş parçacığı başına yerel ayar etkin olarak değiştirme

Bu örnekte, ana iş parçacığı iki alt iş parçacığını çoğaltılır. İlk iş parçacığı olan Iş parçacığı A, çağırarak iş parçacığı başına yerel ayara izin vermez `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . İkinci iş parçacığı, Iş parçacığı B ve ana iş parçacığı, iş parçacığı başına yerel ayarı etkinleştirmeyin. Ardından A iş parçacığı, C++ standart kitaplığı 'nın [locale:: Global](../standard-library/locale-class.md#global) metodunu kullanarak yerel ayarı değiştirmeye devam eder.

A Iş parçacığında iş parçacığı başına yerel ayar etkin olduğundan, yalnızca C çalışma zamanı kitaplığı "Fransızca" yerel ayarını kullanmaya başlar. B Iş parçacığındaki ve ana iş parçacığındaki C çalışma zamanı kitaplığı işlevleri "C" yerel ayarını kullanmaya devam eder. Ancak, [locale:: Global](../standard-library/locale-class.md#global) yöntemi "genel" yerel ayarını değiştirdiği için, tüm iş parçacıklarında tüm C++ standart kitaplık nesneleri "Fransızca" yerel ayarını kullanmaya başlar.

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

## <a name="example-change-locale-without-per-thread-locale-enabled"></a>Örnek: iş parçacığı başına yerel ayar olmadan yerel ayarı değiştirin

Bu örnekte, ana iş parçacığı iki alt iş parçacığını çoğaltılır. İlk iş parçacığı olan Iş parçacığı A, çağırarak iş parçacığı başına yerel ayara izin vermez `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . İkinci iş parçacığı, Iş parçacığı B ve ana iş parçacığı, iş parçacığı başına yerel ayarı etkinleştirmeyin. B iş parçacığı daha sonra C çalışma zamanı kitaplığının [setlocale](../preprocessor/setlocale.md) işlevini kullanarak yerel ayarı değiştirmeye devam eder.

B Iş parçacığı için iş parçacığı başına yerel ayar etkin olmadığından, B Iş parçacığında ve ana iş parçacığındaki C çalışma zamanı kitaplığı işlevleri "Fransızca" yerel ayarını kullanmaya başlar. İş parçacığı A 'nın iş parçacığı başına yerel ayarı etkin olduğu için, A Iş parçacığında C çalışma zamanı kitaplığı işlevleri "C" yerel ayarını kullanmaya devam eder. Ayrıca, [setlocale](../preprocessor/setlocale.md) C++ Standart Kitaplığı yerel ayarını etkilemediğinden, tüm C++ Standart Kitaplığı nesneleri "C" yerel ayarını kullanmaya devam eder.

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

## <a name="example-change-global-locale-without-per-thread-locale-enabled"></a>Örnek: iş parçacığı başına yerel ayar olmadan genel yerel ayarı değiştirin

Bu örnekte, ana iş parçacığı iki alt iş parçacığını çoğaltılır. İlk iş parçacığı olan Iş parçacığı A, çağırarak iş parçacığı başına yerel ayara izin vermez `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` . İkinci iş parçacığı, Iş parçacığı B ve ana iş parçacığı, iş parçacığı başına yerel ayarı etkinleştirmeyin. Sonra B iş parçacığı, C++ standart kitaplığı 'nın [locale:: Global](../standard-library/locale-class.md#global) metodunu kullanarak yerel ayarı değiştirmeye devam eder.

B Iş parçacığı için iş parçacığı başına yerel ayar etkin olmadığından, B Iş parçacığında ve ana iş parçacığındaki C çalışma zamanı kitaplığı işlevleri "Fransızca" yerel ayarını kullanmaya başlar. İş parçacığı A 'nın iş parçacığı başına yerel ayarı etkin olduğu için, A Iş parçacığında C çalışma zamanı kitaplığı işlevleri "C" yerel ayarını kullanmaya devam eder. Ancak, [locale:: Global](../standard-library/locale-class.md#global) yöntemi "genel" yerel ayarını değiştirdiği için, tüm iş parçacıklarında tüm C++ standart kitaplık nesneleri "Fransızca" yerel ayarını kullanmaya başlar.

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
[Ayarlar](../c-runtime-library/locale.md)<br/>
[\<clocale>](../standard-library/clocale.md)<br/>
[\<locale>](../standard-library/locale.md)<br/>
[Locale sınıfı](../standard-library/locale-class.md)
