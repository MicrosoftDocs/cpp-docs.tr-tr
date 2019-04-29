---
title: _beginthread, _beginthreadex
ms.date: 02/27/2018
apiname:
- _beginthread
- _beginthreadex
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: d70d2fb0ecb647d4854a6277d6c69cd9886e072f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349270"
---
# <a name="beginthread-beginthreadex"></a>_beginthread, _beginthreadex

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
Yeni bir iş parçacığının yürütülmesini başlayan bir yordamın başlangıç. İçin **_beginthread**, çağırma kuralı [__cdecl](../../cpp/cdecl.md) (için yerel kod için) veya [__clrcall](../../cpp/clrcall.md) (için yönetilen kod için); **_beginthreadex**, ya da [__stdcall](../../cpp/stdcall.md) (için yerel kod için) veya [__clrcall](../../cpp/clrcall.md) (için yönetilen kod için).

*stack_size*<br/>
Yeni bir iş parçacığı veya 0 yığın boyutu.

*arglist*<br/>
Yeni bir iş parçacığına geçirilecek bağımsız değişken listesi veya **NULL**.

*Güvenlik*<br/>
İşaretçi bir [SECURITY_ATTRIBUTES](https://msdn.microsoft.com/library/windows/desktop/aa379560) döndürülen tanıtıcının alt işlemler tarafından devralınıp alınmayacağını belirleyen yapısı. Varsa *güvenlik* olduğu **NULL**, tanıtıcı devralınamaz. Olmalıdır **NULL** Windows 95 uygulamaları için.

*initflag*<br/>
Yeni bir iş parçacığının ilk durumunu denetleyen bayraklar. Ayarlama *initflag* hemen çalıştırmak için 0 veya için **CREATE_SUSPENDED** askıya alınmış durumda; iş parçacığı oluşturmak için kullanmak [ResumeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-resumethread) iş parçacığını yürütmek için. Ayarlama *initflag* için **STACK_SIZE_PARAM_IS_A_RESERVATION** kullanılacak bayrağı *stack_size* gibi ilkyedekyığınınınbaytcinsindenboyutu;bubayrağıolupolmadığınıbelirtilmedi*stack_size* işleme boyutu belirtir.

*thrdaddr*<br/>
İş parçacığı tanıtıcısını alan 32-bit değişkene işaret eder. Eğer öyleyse **NULL**, bu kullanılmaz.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevlerin her biri yeni oluşturulan iş parçacığına bir tanıtıcı döndürür; Ancak, çok hızlı bir şekilde yeni oluşturulan iş parçacığından çıkar **_beginthread** geçerli bir tanıtıcı döndürmeyebilir. (Açıklamalar bölümü içindeki tartışmalara bakın.) Bir hatada **_beginthread** -1 L döndürür ve **errno** ayarlanır **EAGAIN** varsa çok fazla iş parçacığı için **EINVAL** bağımsız değişken ise geçersiz veya yığın boyutu yanlış, veya **SPAWN** (örneğin bellek) yetersiz kaynak varsa. Bir hatada **_beginthreadex** 0 döndürür ve **errno** ve **_doserrno** ayarlanır.

Varsa *start_address* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Hakkında daha fazla bilgi için **uintptr_t**, bkz: [standart türler](../../c-runtime-library/standard-types.md).

## <a name="remarks"></a>Açıklamalar

**_Beginthread** işlevi oluşturur bir kuralı yürütmeye başlayan bir iş parçacığı *start_address*. İçindeki yordam *start_address* kullanmalısınız **__cdecl** (için yerel kod için) veya **__clrcall** (yönetilen kod için için) çağırma kuralı ve dönüş değeri olması gerekir. İş parçacığı yordamdan döndüğünde otomatik olarak sonlandırılır. İş parçacıkları hakkında daha fazla bilgi için bkz. [(Visual C++) eski kod için çoklu iş parçacığı Destek](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

**_beginthreadex** Win32 benzer [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread) daha fazla API daha yakından **_beginthread** yapar. **_beginthreadex** farklıdır **_beginthread** aşağıdaki yollarla:

- **_beginthreadex** üç ek parametreye sahiptir: *initflag*, *güvenlik*, ve **threadaddr**. Yeni iş parçacığı, belirtilen güvenlikle askıya alınmış durumda oluşturulabilir ve kullanarak erişilebilir *thrdaddr*, iş parçacığı tanımlayıcısı olan.

- İçindeki yordam *start_address* yapan **_beginthreadex** kullanmalısınız **__stdcall** (için yerel kod için) veya **__clrcall** (için yönetilen kod) çağırma kuralı ve bir iş parçacığı çıkış kodu döndürmesi gerekir.

- **_beginthreadex** 0-1 L yerine hata döndürür.

- Kullanılarak oluşturulan bir iş parçacığı **_beginthreadex** yapılan bir çağrıyla sonlandırılır [_endthreadex](endthread-endthreadex.md).

**_Beginthreadex** işlevi iş parçacığının daha nasıl oluşturulduğunu daha fazla denetim verir **_beginthread** yapar. **_Endthreadex** işlevidir ayrıca daha esnektir. Örneğin, **_beginthreadex**, güvenlik bilgilerini kullanabilir, (çalışıyor veya askıda) iş parçacığının ilk durumunu ayarlayabilir ve yeni oluşturulan iş parçacığının iş parçacığı tanıtıcısını alın. Tarafından döndürülen iş parçacığı işleyicisini de kullanabilirsiniz **_beginthreadex** ile yapamayacağınız API ' ların eşitlenmesini **_beginthread**.

Kullanılması daha güvenlidir **_beginthreadex** daha **_beginthread**. Varsa tarafından oluşturulan iş parçacığı **_beginthread** çağırana döndürülen tanıtıcı hızlı bir şekilde çıkarsa **_beginthread** geçersiz olabilir veya başka bir iş parçacığına gelin. Ancak, tarafından döndürülen tanıtıcı **_beginthreadex** çağıran tarafından kapatılmalıdır **_beginthreadex**, geçerli bir tanıtıcı olması kesinleşir **_beginthreadex** bir hata döndürmedi.

Çağırabilirsiniz [_endthread](endthread-endthreadex.md) veya **_endthreadex** açıkça bir iş parçacığını sonlandırmak için ancak **_endthread** veya **_endthreadex** çağrılır otomatik olarak bir parametre olarak iletilen bir yordamdan gelen zaman iş parçacığı döndürür. Çağrısıyla bir iş parçacığı sonlandırma **_endthread** veya **_endthreadex** iş parçacığına ayrılan kaynakların doğru şekilde kurtarılmasını sağlamaya yardımcı olur.

**_endthread** otomatik olarak iş parçacığı işleyicisini yapmadığında **_endthreadex** desteklemez. Bu nedenle, kullandığınız zaman **_beginthread** ve **_endthread**, açıkça iş parçacığı işleyicisini Win32 çağırarak kapatmayın [CloseHandle](/windows/desktop/api/handleapi/nf-handleapi-closehandle) API. Bu davranış, Win32 farklıdır [ExitThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitthread) API.

> [!NOTE]
> LIBCMT.lib ile bağlantılı bir yürütülebilir dosya için Win32 çağırmayın **ExitThread** API çalışma zamanı sistemi tekrar kullanılabilir hale önlememiş böylece ayrılan kaynaklar. **_endthread** ve **_endthreadex** ayrılan iş parçacığı kaynaklarını geri kazanır ve sonra çağrı **ExitThread**.

Yığın ayırma işlemi işletim sistemi işleme olduğunda ya da **_beginthread** veya **_beginthreadex** çağrılır; iş parçacığı yığınının adresini Bu işlevlerden birini geçirmeniz gerekmez. Ayrıca, *stack_size* bağımsız değişkeni 0, hangi durumda işletim sistemi kullanan aynı değeri belirtilen yığınla ana iş parçacığı için olabilir.

*arglist* yeni oluşturulan iş parçacığına geçirilecek bir parametredir. Genellikle bu karakter dizesi gibi bir veri öğesinin adresidir. *arglist* olabilir **NULL** gerekmiyorsa, ancak **_beginthread** ve **_beginthreadex** yeni iş parçacığına geçirmek için bir değer verilmelidir. Herhangi bir iş parçacığı, tüm iş parçacıkları sonlandırılır [iptal](abort.md), **çıkmak**, **_exit**, veya **ExitProcess**.

Yeni iş parçacığının yerel ayarı, işlem başına genel geçerli yerel ayar bilgisini kullanarak başlatılır. İş parçacığı başına yerel ayar için bir çağrı tarafından etkinleştirilip etkinleştirilmeyeceğini [_configthreadlocale](configthreadlocale.md) (genel olarak veya yeni iş parçacıkları için yalnızca), iş parçacığının kendi yerel bağımsız olarak diğer iş parçacıklarından çağırarak değiştirebilirsiniz **setlocale** veya **_wsetlocale**. İş parçacığı başına yerel ayar bayrağı ayarlanmış olmayan iş parçacıkları, yeni oluşturulan tüm iş parçacıklarının yanı sıra diğer iş parçacığı başına yerel ayar bayrağı ayarlanmış de olmayan iş parçacıkları yerel ayar bilgisini etkileyebilir. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

İçin **/CLR** kodu **_beginthread** ve **_beginthreadex** her iki aşırı yüklemesi vardır. Yerel bir çağırma kuralı işlevi işaretçisi alır ve diğer alan bir **__clrcall** işlev işaretçisi. İlk aşırı yükleme uygulama etki alanı için güvenli ve hiçbir zaman olmayacaktır değil olmalıdır. Yazıyorsanız **/CLR** kaynakları yönetilen kod emin olmanız gerekir, erişmeden önce yeni iş parçacığının doğru uygulama etki alanı girer. Örneğin, kullanarak bunu [call_in_appdomain işlevi](../../dotnet/call-in-appdomain-function.md). İkinci aşırı yükleme uygulama etki alanı için güvenli olduğunu; Yeni oluşturulan iş parçacığı her zaman çağıran uygulama etki alanında ulaşır **_beginthread** veya **_beginthreadex**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_beginthread**|\<Process.h >|
|**_beginthreadex**|\<Process.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Çoklu iş parçacığı sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

Kullanılacak **_beginthread** veya **_beginthreadex**, uygulamanın çok iş parçacıklı C çalışma zamanı kitaplıkları biriyle bağlamanız gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnekte **_beginthread** ve **_endthread**.

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

Örnek uygulamayı sonlandırmak için herhangi bir tuşa basın.

## <a name="example"></a>Örnek

Aşağıdaki örnek kod tarafından döndürülen iş parçacığı işleyicisini nasıl kullanabileceğinizi gösteren **_beginthreadex** API eşitlemeyle [WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject). Ana iş parçacığı devam etmeden önce sonlandırmak ikinci iş parçacığı için bekler. İkinci bir iş parçacığı çağırdığında **_endthreadex**, iş parçacığı nesnesinin verilmiş duruma dönmesine neden olur. Bu, birincil iş parçacığı çalışmaya devam etmesini sağlar. Bu ile yapılamaz **_beginthread** ve **_endthread**, çünkü **_endthread** çağrıları **CloseHandle**, iş parçacığı yok eder Sinyal verilmiş duruma dönmesine ayarlamadan önce nesne.

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
- [abort](abort.md)
- [exit, _Exit, _exit](exit-exit-exit.md)
- [GetExitCodeThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)
