---
title: Çoklu iş parçacığı kullanımı ve yerel ayarları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- locales [C++], multithreading
- multithreading [C++], locales
- threading [C++], locales
- per-thread locale
ms.assetid: d6fb159a-eaca-4130-a51a-f95d62f71485
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 19cc3817faab71c209586ad952162229f846e0a7
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="multithreading-and-locales"></a>Çoklu İş Parçacığı Kullanımı ve Yerel Ayarlar
C çalışma zamanı kitaplığı ve C++ Standart Kitaplığı programınızın yerel ayarları değiştirmek için destek sağlar. Bu konu, her iki kitaplıkları birden çok iş parçacıklı uygulamada yerel ayar işlevselliğini kullanırken ortaya çıkan sorunları açıklar.  
  
## <a name="remarks"></a>Açıklamalar  
 C çalışma zamanı kitaplığı ile kullanarak birden çok iş parçacıklı uygulamalar oluşturabilirsiniz `_beginthread` ve `_beginthreadex` işlevleri. Bu konuda, yalnızca birden çok iş parçacıklı uygulamalar bu işlevleri kullanılarak oluşturulan kapsar. Daha fazla bilgi için bkz: [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md).  
  
 C çalışma zamanı kitaplığını kullanarak yerel ayarları değiştirmek için kullanmak [setlocale](../preprocessor/setlocale.md) işlevi. Visual C++ önceki sürümlerinde, bu işlev her zaman tüm uygulama boyunca Yereli değiştirirsiniz. Bir iş parçacığı başına temelinde yerel ayar için şimdi desteği yoktur. Bu yapılır kullanarak [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) işlevi. Belirtmek için [setlocale](../preprocessor/setlocale.md) yalnızca çağrı geçerli iş parçacığı yerel ayarı değiştirmelisiniz `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)` o iş parçacığı içinde. Buna karşılık, çağırma `_configthreadlocale(_DISABLE_PER_THREAD_LOCALE)` o iş parçacığı kullanımı genel yerel ve tüm çağrısına neden olacak [setlocale](../preprocessor/setlocale.md) iş parçacığı açıkça iş parçacığı başına yerel ayar etkinleştirmediyseniz tüm iş parçacığı yerel ayarı değiştirir.  
  
 C++ çalışma zamanı kitaplığını kullanarak yerel ayarları değiştirmek için kullanmak [locale sınıfı](../standard-library/locale-class.md). Çağırarak [locale::global](../standard-library/locale-class.md#global) yöntemi, açıkça iş parçacığı başına yerel ayar etkinleştirilmemiş her iş parçacığı yerel ayarı değiştirebilirsiniz. Yerel bir tek iş parçacığı ya da bir uygulama bölümünü değiştirmek için yalnızca bir örneğini oluşturmak bir `locale` nesnesi, iş parçacığı veya kod kısmı.  
  
> [!NOTE]
>  Çağırma [locale::global](../standard-library/locale-class.md#global) yerel C++ Standart Kitaplığı ve C çalışma zamanı kitaplığı için değiştirir. Ancak, çağırma [setlocale](../preprocessor/setlocale.md) C çalışma zamanı kitaplığı; C++ Standart Kitaplığı etkilenmez için yalnızca yerel değiştirir.  
  
 Aşağıdaki örnekler nasıl kullanılacağını [setlocale](../preprocessor/setlocale.md) işlevi, [locale sınıfı](../standard-library/locale-class.md)ve [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md) bir uygulamanın yerel ayarları değiştirmek için işlevi birkaç değişik senaryodan.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, iki alt iş parçacığı ana iş parçacığı olarak çoğaltılır. Çağırarak ilk iş parçacığı, iş parçacığı A, iş parçacığı başına yerel ayar sağlayan `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. İkinci bir iş parçacığı, iş parçacığı B yanı sıra, ana iş parçacığı, iş parçacığı başına yerel ayar etkinleştirmeyin. İş parçacığı yerel ayarı kullanılarak değiştirmeye geçer [setlocale](../preprocessor/setlocale.md) C çalışma zamanı kitaplığı işlevi.  
  
 İş parçacığı A etkin iş parçacığı başına yerel ayar yalnızca C çalışma zamanı kitaplığı işlevleri "Fransızca" yerel ayarını kullanarak iş parçacığı A Başlat olduğundan. İş parçacığı B ve ana iş parçacığı C çalışma zamanı kitaplığı işlevleri "C" yerel ayarını kullanmaya devam edin. Ayrıca, bu yana [setlocale](../preprocessor/setlocale.md) nesneleri "C" yerel ayarını kullanmaya devam eder, tüm C++ Standart Kitaplığı C++ Standart Kitaplığı yerel etkilemez.  
  
```  
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
 Bu örnekte, iki alt iş parçacığı ana iş parçacığı olarak çoğaltılır. Çağırarak ilk iş parçacığı, iş parçacığı A, iş parçacığı başına yerel ayar sağlayan `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. İkinci bir iş parçacığı, iş parçacığı B yanı sıra, ana iş parçacığı, iş parçacığı başına yerel ayar etkinleştirmeyin. İş parçacığı yerel ayarı kullanılarak değiştirmeye geçer [locale::global](../standard-library/locale-class.md#global) C++ Standart Kitaplığı yöntemi.  
  
 İş parçacığı A etkin iş parçacığı başına yerel ayar yalnızca C çalışma zamanı kitaplığı işlevleri "Fransızca" yerel ayarını kullanarak iş parçacığı A Başlat olduğundan. İş parçacığı B ve ana iş parçacığı C çalışma zamanı kitaplığı işlevleri "C" yerel ayarını kullanmaya devam edin. Ancak, bu yana [locale::global](../standard-library/locale-class.md#global) yöntemi değişiklikleri yerel ayarları "Genel", "Fransızca" yerel ayarını kullanarak tüm iş parçacıklarının tüm C++ Standart Kitaplığı nesneleri başlatın.  
  
```  
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
 Bu örnekte, iki alt iş parçacığı ana iş parçacığı olarak çoğaltılır. Çağırarak ilk iş parçacığı, iş parçacığı A, iş parçacığı başına yerel ayar sağlayan `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. İkinci bir iş parçacığı, iş parçacığı B yanı sıra, ana iş parçacığı, iş parçacığı başına yerel ayar etkinleştirmeyin. B iş parçacığı sonra kullanarak yerel ayarı değiştirmeye geçer [setlocale](../preprocessor/setlocale.md) C çalışma zamanı kitaplığı işlevi.  
  
 İş parçacığı B iş parçacığı başına yerel ayar etkin olmadığından iş parçacığı B ve ana iş parçacığı C çalışma zamanı kitaplığı işlevleri "Fransızca" yerel ayarını kullanarak başlatın. İş parçacığı bir iş parçacığı başına yerel ayar etkin olduğundan "C" yerel ayarını kullanmak için iş parçacığı A devam C çalışma zamanı kitaplığı işlevlerde. Ayrıca, bu yana [setlocale](../preprocessor/setlocale.md) nesneleri "C" yerel ayarını kullanmaya devam eder, tüm C++ Standart Kitaplığı C++ Standart Kitaplığı yerel etkilemez.  
  
```  
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
 Bu örnekte, iki alt iş parçacığı ana iş parçacığı olarak çoğaltılır. Çağırarak ilk iş parçacığı, iş parçacığı A, iş parçacığı başına yerel ayar sağlayan `_configthreadlocale(_ENABLE_PER_THREAD_LOCALE)`. İkinci bir iş parçacığı, iş parçacığı B yanı sıra, ana iş parçacığı, iş parçacığı başına yerel ayar etkinleştirmeyin. B iş parçacığı sonra kullanarak yerel ayarı değiştirmeye geçer [locale::global](../standard-library/locale-class.md#global) C++ Standart Kitaplığı yöntemi.  
  
 İş parçacığı B iş parçacığı başına yerel ayar etkin olmadığından iş parçacığı B ve ana iş parçacığı C çalışma zamanı kitaplığı işlevleri "Fransızca" yerel ayarını kullanarak başlatın. İş parçacığı bir iş parçacığı başına yerel ayar etkin olduğundan "C" yerel ayarını kullanmak için iş parçacığı A devam C çalışma zamanı kitaplığı işlevlerde. Ancak, bu yana [locale::global](../standard-library/locale-class.md#global) yöntemi değişiklikleri yerel ayarları "Genel", "Fransızca" yerel ayarını kullanarak tüm iş parçacıklarının tüm C++ Standart Kitaplığı nesneleri başlatın.  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eski kod (Visual C++) için çoklu iş parçacığı desteği](../parallel/multithreading-support-for-older-code-visual-cpp.md)   
 [_beginthread, _beginthreadex](../c-runtime-library/reference/beginthread-beginthreadex.md)   
 [_configthreadlocale](../c-runtime-library/reference/configthreadlocale.md)   
 [setlocale](../preprocessor/setlocale.md)   
 [Uluslararası duruma getirme](../c-runtime-library/internationalization.md)   
 [Yerel ayar](../c-runtime-library/locale.md)   
 [\<clocale >](../standard-library/clocale.md)   
 [\<yerel ayar >](../standard-library/locale.md)   
 [locale Sınıfı](../standard-library/locale-class.md)