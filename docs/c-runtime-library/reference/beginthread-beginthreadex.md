---
title: _beginthread, _beginthreadex
ms.date: 4/2/2020
api_name:
- _beginthread
- _beginthreadex
- _o__beginthread
- _o__beginthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- beginthread
- _beginthread
- beginthreadex
- _beginthreadex
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
ms.openlocfilehash: 2d2851a7e76a43501145b1e55e8028b72c2a8afb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348671"
---
# <a name="_beginthread-_beginthreadex"></a>_beginthread, _beginthreadex

Bir iş parçacığı oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
uintptr_t _beginthread( // NATIVE CODE
   void( __cdecl *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthread( // MANAGED CODE
   void( __clrcall *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthreadex( // NATIVE CODE
   void *security,
   unsigned stack_size,
   unsigned ( __stdcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
uintptr_t _beginthreadex( // MANAGED CODE
   void *security,
   unsigned stack_size,
   unsigned ( __clrcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
```

### <a name="parameters"></a>Parametreler

*start_address*<br/>
Yeni bir iş parçacığının yürütülmesine başlayan bir yordamın adresini başlatın. _beginthread **_beginthread**için, arama kuralı ya [__cdecl](../../cpp/cdecl.md) (yerel kod için) ya da [__clrcall](../../cpp/clrcall.md) (yönetilen kod için); **_beginthreadex**için, [__stdcall](../../cpp/stdcall.md) (yerel kod için) veya [__clrcall](../../cpp/clrcall.md) (yönetilen kod için)

*stack_size*<br/>
Yeni bir iş parçacığı veya 0 için yığın boyutu.

*Arglist*<br/>
Bağımsız değişken listesi yeni bir iş parçacığına veya **NULL'a**geçirilecek.

*Güvenlik*<br/>
Döndürülen tanıtıcının alt işlemler tarafından devralınıp alınamayacağını belirleyen [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) bir yapıyı işaretle. *Güvenlik* **NULL**ise, işletmek devralınamaz. Windows 95 uygulamaları için **NULL** olmalıdır.

*initflag*<br/>
Yeni bir iş parçacığının ilk durumunu denetleyen bayraklar. Hemen çalışacak şekilde 0'a *initflag* veya askıya alınmış durumda iş parçacığı oluşturmak için **CREATE_SUSPENDED** ayarlayın; iş parçacığı yürütmek için [ResumeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-resumethread) kullanın. *stack_size* baytlar halinde yığının ilk rezerv boyutu olarak kullanmak için **STACK_SIZE_PARAM_IS_A_RESERVATION** bayrak için *initflag* ayarlayın; bu bayrak *belirtilmemişse, stack_size* işleme boyutunu belirtir.

*thrdaddr*<br/>
İş parçacığı tanımlayıcısını alan 32 bitlik bir değişkene işaret ediyor. **NULL**ise kullanılmaz.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevlerin her biri yeni oluşturulan iş parçacığıiçin bir tanıtıcı döndürür; ancak, yeni oluşturulan iş parçacığı çok hızlı çıkarsa, **_beginthread** geçerli bir tanıtıcı döndürmeyebilir. (Açıklamalar bölümündeki tartışmaya bakın.) Bir hatada, **_beginthread** -1L döndürür ve çok fazla iş parçacığı varsa **errno** **EAGAIN'ye,** bağımsız değişken geçersizse veya yığın boyutu yanlışsa **EINVAL'e** veya yetersiz kaynak varsa (bellek gibi) **EACCES'e** ayarlanır. Bir hata **da, _beginthreadex** 0 döndürür ve **errno** ve **_doserrno** ayarlanır.

*start_address* **NULL**ise, Geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **EINVAL** ve return -1 **için errno** ayarlayın.

Bu ve diğer iade kodları hakkında daha fazla bilgi için [errno, _doserrno, _sys_errlist ve _sys_nerr'a](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)bakın.

**uintptr_t**hakkında daha fazla bilgi için [Standart Türleri'ne](../../c-runtime-library/standard-types.md)bakın.

## <a name="remarks"></a>Açıklamalar

_beginthread **_beginthread** *işlevi, start_address*bir yordamın yürütülmesibaşlar bir iş parçacığı oluşturur. *start_address'daki* yordam, **__cdecl** (yerel kod için) veya **__clrcall** (yönetilen kod için) arama kuralını kullanmalı ve iade değeri ne olmalıdır. İş parçacığı bu yordamdan döndüğünde, otomatik olarak sonlandırılır. İş parçacıkları hakkında daha fazla bilgi için, [Eski Kod için Çok İş Parçacığı Desteği (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)konusuna bakın.

**_beginthreadex** Win32 [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) **API'sini _beginthread'dan** daha yakından andırır. **_beginthreadex** aşağıdaki şekillerde **_beginthread** farklıdır:

- **_beginthreadex** üç ek parametre vardır: *initflag*, *Güvenlik*, ve **threadaddr**. Yeni iş parçacığı, belirli bir güvenlik ile askıya alınmış bir durumda oluşturulabilir ve *thrdaddr*kullanılarak erişilebilir , iş parçacığı tanımlayıcısı olan.

- **_beginthreadex** geçirilen *start_address* yordamı, **__stdcall** (yerel kod için) veya **__clrcall** (yönetilen kod için) arama kuralını kullanmalı ve iş parçacığı çıkış kodunu döndürmelidir.

- **_beginthreadex** -1L yerine 0 hata üzerinde döndürür.

- **_beginthreadex** kullanılarak oluşturulan bir iş [parçacığı, _endthreadex](endthread-endthreadex.md)için yapılan bir çağrı yla sonlandırılır.

**_beginthreadex** işlevi iş parçacığının nasıl oluşturulduğu üzerinde **_beginthread** daha fazla denetim sağlar. **_endthreadex** fonksiyonu da daha esnektir. Örneğin, **_beginthreadex,** güvenlik bilgilerini kullanabilir, iş parçacığının ilk durumunu (çalışan veya askıya alınmış) ayarlayabilir ve yeni oluşturulan iş parçacığının iş parçacığı tanımlayıcısını alabilirsiniz. Senkronizasyon API'leri ile **_beginthreadex** tarafından döndürülen iş parçacığı tutamacını da kullanabilirsiniz, bu da **_beginthread.**

**_beginthreadex** kullanmak **_beginthread**daha güvenli. **_beginthread** tarafından oluşturulan iş parçacığı hızla çıkarsa, **_beginthread'nin** arayanı çağırana döndürülen iş parçacığı geçersiz olabilir veya başka bir iş parçacığına işaret edebilir. Ancak, **_beginthreadex** tarafından döndürülen tutamacın **_beginthreadex**arayan tarafından kapatılması gerekir, bu nedenle **_beginthreadex** bir hata döndürmediyse geçerli bir tutamaç olduğu garanti edilir.

İş parçacığına son vermek için [_endthread](endthread-endthreadex.md) veya **_endthreadex** açıkça arayabilirsiniz; ancak, iş parçacığı parametre olarak geçirilen yordamdan döndüğünde **_endthread** veya **_endthreadex** otomatik olarak çağrılır. İş parçacığının **_endthread** veya **_endthreadex** için bir çağrıyla sonlandırması, iş parçacığı için ayrılan kaynakların doğru şekilde kurtarılmasını sağlamaya yardımcı olur.

**_endthread** iş parçacığı tutamacını otomatik olarak kapatırken, **_endthreadex** kapatmaz. Bu nedenle, **_beginthread** ve **_endthread**kullandığınızda, Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) API'yi arayarak iş parçacığı tutamacını açıkça kapatmayın. Bu davranış Win32 [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) API farklıdır.

> [!NOTE]
> Libcmt.lib ile bağlantılı çalıştırılabilir bir dosya için Win32 **ExitThread** API'yi aramayın, böylece çalışma zamanı sisteminin ayrılan kaynakları geri kazanmasını engellemeyin. **_endthread** ve **_endthreadex** ayrılan iş parçacığı kaynaklarını geri almak ve sonra **ExitThread**arayın.

İşletim sistemi, **_beginthread** veya **_beginthreadex** çağrıldığında yığının tahsisini işler; iş parçacığı yığınının adresini bu işlevlerden herhangi biri için geçirmeniz gerekmemektedir. Buna ek olarak, *stack_size* bağımsız değişkeni 0 olabilir ve bu durumda işletim sistemi ana iş parçacığı için belirtilen yığınla aynı değeri kullanır.

*arglist* yeni oluşturulan iş parçacığına geçirilecek bir parametredir. Genellikle, bir karakter dizesi gibi bir veri öğesinin adresidir. *arglist* gerekli değilse **NULL** olabilir, ancak **_beginthread** ve **_beginthreadex** yeni iş parçacığı geçmek için bazı değer verilmelidir. Herhangi bir iş parçacığı [iptal,](abort.md) **çıkış,** **_exit**veya **ExitProcess**çağırırsa tüm iş parçacıkları sonlandırılır.

Yeni iş parçacığının yerel durumu, işlem başına küresel geçerli yerel bilgi kullanılarak başharfe çevrilir. İş parçacığı başına yerel [ayar, _configthreadlocale](configthreadlocale.md) için yapılan bir çağrıyla (genel olarak veya yalnızca yeni iş parçacıkları için) etkinleştirilmişse, iş parçacığı **kümesi yerelliğini** veya **_wsetlocale**çağırarak diğer iş parçacıklarından bağımsız olarak yerelkonumunu değiştirebilir. İş parçacığı başına yerel bayrak kümesiolmayan iş parçacıkları, iş parçacığı başına yerel bayrak kümesine sahip olmayan diğer tüm iş parçacıklarındaki yerel bilgileri ve yeni oluşturulan tüm iş parçacıklarını etkileyebilir. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

**/clr** kodu **için, _beginthread** ve **_beginthreadex** her biri iki aşırı yükvardır. Biri yerel bir çağrı-kuralı işlev işaretçisi alır ve diğer **bir __clrcall** işlev işaretçisi alır. İlk aşırı yükleme uygulama etki alanı güvenli değildir ve asla olmayacaktır. **/clr** kodu yazıyorsanız, yeni iş parçacığının yönetilen kaynaklara erişmeden önce doğru uygulama etki alanına girdiğinden emin olmalısınız. Bunu, örneğin, [call_in_appdomain Fonksiyonu](../../dotnet/call-in-appdomain-function.md)kullanarak yapabilirsiniz. İkinci aşırı yükleme uygulama etki alanı güvenlidir; yeni oluşturulan iş parçacığı her zaman **_beginthread** veya **_beginthreadex**arayan uygulama etki alanında sona erecek.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_beginthread**|\<process.h>|
|**_beginthreadex**|\<process.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="libraries"></a>Kitaplıklar

Yalnızca C çalışma [zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) çok iş parçacığı sürümleri.

**_beginthread** veya **_beginthreadex**kullanmak için uygulamanın çok iş parçacıklı C çalışma zamanı kitaplıklarından birine bağlanması gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte **_beginthread** ve **_endthread**kullanır.

```C
// crt_BEGTHRD.C
// compile with: /MT /D "_X86_" /c
// processor: x86
#include <windows.h>
#include <process.h>    /* _beginthread, _endthread */
#include <stddef.h>
#include <stdlib.h>
#include <conio.h>

void Bounce( void * );
void CheckKey( void * );

// GetRandom returns a random integer between min and max.
#define GetRandom( min, max ) ((rand() % (int)(((max) + 1) - (min))) + (min))
// GetGlyph returns a printable ASCII character value
#define GetGlyph( val ) ((char)((val + 32) % 93 + 33))

BOOL repeat = TRUE;                 // Global repeat flag
HANDLE hStdOut;                     // Handle for console window
CONSOLE_SCREEN_BUFFER_INFO csbi;    // Console information structure

int main()
{
    int param = 0;
    int * pparam = &param;

    // Get display screen's text row and column information.
    hStdOut = GetStdHandle( STD_OUTPUT_HANDLE );
    GetConsoleScreenBufferInfo( hStdOut, &csbi );

    // Launch CheckKey thread to check for terminating keystroke.
    _beginthread( CheckKey, 0, NULL );

    // Loop until CheckKey terminates program or 1000 threads created.
    while( repeat && param < 1000 )
    {
        // launch another character thread.
        _beginthread( Bounce, 0, (void *) pparam );

        // increment the thread parameter
        param++;

        // Wait one second between loops.
        Sleep( 1000L );
    }
}

// CheckKey - Thread to wait for a keystroke, then clear repeat flag.
void CheckKey( void * ignored )
{
    _getch();
    repeat = 0;    // _endthread implied
}

// Bounce - Thread to create and control a colored letter that moves
// around on the screen.
//
// Params: parg - the value to create the character from
void Bounce( void * parg )
{
    char       blankcell = 0x20;
    CHAR_INFO  ci;
    COORD      oldcoord, cellsize, origin;
    DWORD      result;
    SMALL_RECT region;

    cellsize.X = cellsize.Y = 1;
    origin.X = origin.Y = 0;

    // Generate location, letter and color attribute from thread argument.
    srand( _threadid );
    oldcoord.X = region.Left = region.Right =
        GetRandom(csbi.srWindow.Left, csbi.srWindow.Right - 1);
    oldcoord.Y = region.Top = region.Bottom =
        GetRandom(csbi.srWindow.Top, csbi.srWindow.Bottom - 1);
    ci.Char.AsciiChar = GetGlyph(*((int *)parg));
    ci.Attributes = GetRandom(1, 15);

    while (repeat)
    {
        // Pause between loops.
        Sleep( 100L );

        // Blank out our old position on the screen, and draw new letter.
        WriteConsoleOutputCharacterA(hStdOut, &blankcell, 1, oldcoord, &result);
        WriteConsoleOutputA(hStdOut, &ci, cellsize, origin, &region);

        // Increment the coordinate for next placement of the block.
        oldcoord.X = region.Left;
        oldcoord.Y = region.Top;
        region.Left = region.Right += GetRandom(-1, 1);
        region.Top = region.Bottom += GetRandom(-1, 1);

        // Correct placement (and beep) if about to go off the screen.
        if (region.Left < csbi.srWindow.Left)
            region.Left = region.Right = csbi.srWindow.Left + 1;
        else if (region.Right >= csbi.srWindow.Right)
            region.Left = region.Right = csbi.srWindow.Right - 2;
        else if (region.Top < csbi.srWindow.Top)
            region.Top = region.Bottom = csbi.srWindow.Top + 1;
        else if (region.Bottom >= csbi.srWindow.Bottom)
            region.Top = region.Bottom = csbi.srWindow.Bottom - 2;

        // If not at a screen border, continue, otherwise beep.
        else
            continue;
        Beep((ci.Char.AsciiChar - 'A') * 100, 175);
    }
    // _endthread given to terminate
    _endthread();
}
```

Örnek uygulamayı sonlamak için herhangi bir tuşa basın.

## <a name="example"></a>Örnek

Aşağıdaki örnek kod, senkronizasyon API [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject)ile **_beginthreadex** tarafından döndürülen iş parçacığı tutamacını nasıl kullanabileceğinizi gösterir. Ana iş parçacığı devam etmeden önce ikinci iş parçacığının sonlandırılmasını bekler. İkinci iş parçacığı **_endthreadex**çağırdığında, iş parçacığı nesnesinin sinyal durumuna gitmesine neden olur. Bu, birincil iş parçacığının çalışmaya devam etmesini sağlar. Bu, **_beginthread** ve **_endthread**ile yapılamaz , çünkü **_endthread** **CloseHandle**çağırır , sinyal durumuna ayarlanamadan önce iş parçacığı nesnesini yok eder.

```cpp
// crt_begthrdex.cpp
// compile with: /MT
#include <windows.h>
#include <stdio.h>
#include <process.h>

unsigned Counter;
unsigned __stdcall SecondThreadFunc( void* pArguments )
{
    printf( "In second thread...\n" );

    while ( Counter < 1000000 )
        Counter++;

    _endthreadex( 0 );
    return 0;
}

int main()
{
    HANDLE hThread;
    unsigned threadID;

    printf( "Creating second thread...\n" );

    // Create the second thread.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc, NULL, 0, &threadID );

    // Wait until second thread terminates. If you comment out the line
    // below, Counter will not be correct because the thread has not
    // terminated, and Counter most likely has not been incremented to
    // 1000000 yet.
    WaitForSingleObject( hThread, INFINITE );
    printf( "Counter should be 1000000; it is-> %d\n", Counter );
    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
Creating second thread...
In second thread...
Counter should be 1000000; it is-> 1000000
```

## <a name="see-also"></a>Ayrıca bkz.

- [Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)
- [_endthread, _endthreadex](endthread-endthreadex.md)
- [Iptal](abort.md)
- [exit, _Exit, _exit](exit-exit-exit.md)
- [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)
