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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: acf885c923db3fdf91119b29a78d64824384166b
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82913505"
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
Yeni bir iş parçacığının yürütülmesini Başlatan bir yordamın başlangıç adresi. **_Beginthread**için, çağırma kuralı [__cdecl](../../cpp/cdecl.md) (yerel kod için) veya [__clrcall](../../cpp/clrcall.md) (yönetilen kod için). **_beginthreadex**için [__stdcall](../../cpp/stdcall.md) (yerel kod için) veya [__clrcall](../../cpp/clrcall.md) (yönetilen kod için).

*stack_size*<br/>
Yeni bir iş parçacığı için yığın boyutu veya 0.

*Arglist*<br/>
Yeni bir iş parçacığına geçirilecek bağımsız değişken listesi veya **null**.

*Güvenlik*<br/>
Döndürülen Tanıtıcının alt süreçler tarafından devralınıp alınmayacağını belirleyen [SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) yapısına yönelik işaretçi. *Güvenlik* **null**ise, tanıtıcı devralınamaz. Windows 95 uygulamaları için **null** olmalıdır.

*ınitflag*<br/>
Yeni bir iş parçacığının ilk durumunu denetleyen bayraklar. Hemen çalıştırmak için *initflag* 'ı 0 olarak ayarlayın veya iş parçacığını askıya alınmış durumda oluşturmak için **CREATE_SUSPENDED** ; iş parçacığını yürütmek için [ResumeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-resumethread) kullanın. Yığının ilk ayırma boyutu olarak *stack_size* kullanmak için *initflag* 'ı **STACK_SIZE_PARAM_IS_A_RESERVATION** bayrak olarak ayarlayın; Bu bayrak belirtilmemişse, *stack_size* tamamlama boyutunu belirtir.

*thrdadddr*<br/>
İş parçacığı tanımlayıcısını alan 32 bitlik bir değişkene işaret eder. **Null**ise, kullanılmaz.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevlerin her biri yeni oluşturulan iş parçacığına bir tanıtıcı döndürür; Ancak, yeni oluşturulan iş parçacığı çok hızlı bir şekilde çıkmadıysa **_beginthread** geçerli bir tanıtıcı döndürmeyebilir. (Açıklamalar bölümünde tartışmayı inceleyin.) Bir hata durumunda, **_beginthread** -1L döndürür ve **errno** çok fazla Iş parçacığı **varsa,** **EINVAL** için bağımsız değişken geçersizse veya yığın boyutu yanlışsa ya da yetersiz kaynak (bellek gibi) varsa **EACCES** olarak ayarlanır. Bir hatada, **_beginthreadex** 0 döndürür ve **errno** ve **_doserrno** ayarlanır.

*Start_address* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve-1 döndürür.

Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**Uintptr_t**hakkında daha fazla bilgi için bkz. [standart türler](../../c-runtime-library/standard-types.md).

## <a name="remarks"></a>Açıklamalar

**_Beginthread** işlevi, *start_address*bir yordamın yürütülmesini Başlatan bir iş parçacığı oluşturur. *Start_address* yordam, çağırma kuralı için **__cdecl** (yerel kod için) veya **__clrcall** (yönetilen kod için) kullanmalıdır ve dönüş değeri içermemelidir. İş parçacığı bu yordama döndüğünde otomatik olarak sonlandırılır. İş parçacıkları hakkında daha fazla bilgi için bkz. [daha eski kod Için çoklu Iş parçacığı desteği (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

**_beginthreadex** , Win32 [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) API 'sine **_beginthread** daha yakından benzer. **_beginthreadex** **_beginthread** aşağıdaki yollarla farklıdır:

- **_beginthreadex** üç ek parametreye sahiptir: *initflag*, *Security*ve **threadadddr**. Yeni iş parçacığı, belirtilen güvenlik ile askıya alınmış bir durumda oluşturulabilir ve iş parçacığı tanımlayıcısı olan *thrdadddr*kullanılarak erişilebilir.

- **_Beginthreadex** geçirilen *start_address* yordamı, çağrı kuralını **__stdcall** (yerel kod için) veya **__clrcall** (yönetilen kod için) kullanmalıdır ve bir iş parçacığı çıkış kodu döndürmelidir.

- **_beginthreadex** , hata durumunda-1L yerine 0 döndürür.

- **_Beginthreadex** kullanılarak oluşturulan bir iş parçacığı, [_endthreadex](endthread-endthreadex.md)çağrısıyla sonlandırılır.

**_Beginthreadex** işlevi, iş parçacığının **_beginthread** tarafından nasıl oluşturulduğuna ilişkin daha fazla denetim sağlar. **_Endthreadex** işlevi de daha esnektir. Örneğin, **_beginthreadex**ile güvenlik bilgilerini kullanabilir, iş parçacığının başlangıç durumunu ayarlayabilir (çalışır veya askıya alınır) ve yeni oluşturulan iş parçacığının iş parçacığı tanımlayıcısını alabilirsiniz. Ayrıca, **_beginthread**ile yapaistemediğiniz eşitleme apı 'leriyle **_beginthreadex** tarafından döndürülen iş parçacığı işleyicisini de kullanabilirsiniz.

**_Beginthread** **_beginthreadex** kullanmak daha güvenlidir. **_Beginthread** tarafından oluşturulan iş parçacığı hızla çıkdığında, **_beginthread** çağıranına döndürülen tanıtıcı geçersiz olabilir veya başka bir iş parçacığına işaret edebilir. Ancak, **_beginthreadex** tarafından döndürülen tanıtıcının **_beginthreadex**çağıranı tarafından kapatılması gerekir, bu nedenle **_beginthreadex** bir hata döndürmediğinde geçerli bir tanıtıcı olması garanti edilir.

Bir iş parçacığını sonlandırmak için [_endthread](endthread-endthreadex.md) veya **_endthreadex** açıkça çağırabilirsiniz; Ancak, iş parçacığı parametre olarak geçirilen yordamın döndürdüğü zaman **_endthread** veya **_endthreadex** otomatik olarak çağrılır. Bir iş parçacığını **_endthread** veya **_endthreadex** çağrısıyla sonlandırarak iş parçacığı için ayrılan kaynakların doğru kurtarılmasına yardımcı olur.

**_endthread** , iş parçacığı tanıtıcısını otomatik olarak kapatır, ancak **_endthreadex** yapmaz. Bu nedenle, **_beginthread** ve **_Endthread**kullandığınızda, Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) API 'sini çağırarak iş parçacığı tanıtıcısını açıkça kapatmayın. Bu davranış, Win32 [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) API 'sinden farklıdır.

> [!NOTE]
> Libcmt. lib ile bağlantılı bir yürütülebilir dosya için, Win32 **ExitThread** API 'sini çağırmayın, böylece çalışma zamanı sisteminin geri kazanma tarafından ayrılmış kaynaklardan engellenmesini önleyin. **_endthread** ve **_endthreadex** ayrılmış iş parçacığı kaynaklarını geri kazanın ve sonra **ExitThread**'i çağırın.

**_Beginthread** veya **_beginthreadex** çağrıldığında, işletim sistemi yığın ayırmayı işler; iş parçacığı yığınının adresini bu işlevlerden birine iletmeniz gerekmez. Ayrıca, *stack_size* bağımsız değişkeni 0 olabilir, bu durumda işletim sistemi ana iş parçacığı için belirtilen yığınla aynı değeri kullanır.

*Arglist* , yeni oluşturulan iş parçacığına geçirilecek bir parametredir. Genellikle, bir karakter dizesi gibi bir veri öğesinin adresidir. *Arglist* gerekli değilse **null** olabilir, ancak **_beginthread** ve **_beginthreadex** yeni iş parçacığına geçirilecek bazı değerler verilmelidir. Herhangi bir iş parçacığı [iptal](abort.md), **Çıkış**, **_exit**veya **ExitProcess**'i çağırırsa tüm iş parçacıkları sonlandırılır.

Yeni iş parçacığının yerel ayarı, işlem başına küresel geçerli yerel ayar bilgileri kullanılarak başlatılır. İş parçacığı başına yerel ayar, [_configthreadlocale](configthreadlocale.md) çağrısıyla (genel olarak veya yalnızca yeni iş parçacıkları için) etkinleştirilirse, iş parçacığı, **setlocale** veya **_wsetlocale**çağırarak yerel ayarını diğer iş parçacıklarından bağımsız olarak değiştirebilir. İş parçacığı başına yerel ayar bayrağı kümesi olmayan iş parçacıkları, iş parçacığı başına yerel ayar bayrağı ayarlanmamış olan diğer tüm iş parçacıklarında yerel ayar bilgilerini ve yeni oluşturulan tüm iş parçacıklarını etkileyebilir. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

**/Clr** kodu için **_beginthread** ve **_beginthreadex** her birinin iki aşırı yüklemesi vardır. Bir yerel çağrı kuralı işlev işaretçisini alır ve diğeri **__clrcall** işlev işaretçisi alır. İlk aşırı yükleme uygulama etki alanı açısından güvenli değildir ve hiçbir şekilde olmayacaktır. **/Clr** kodu yazıyorsanız, yeni iş parçacığının yönetilen kaynaklara erişmeden önce doğru uygulama etki alanına girdiğinden emin olmanız gerekir. Bunu, örneğin [Call_in_appdomain işlevi](../../dotnet/call-in-appdomain-function.md)kullanarak yapabilirsiniz. İkinci aşırı yükleme uygulama etki alanı güvenlidir; Yeni oluşturulan iş parçacığı her zaman **_beginthread** veya **_beginthreadex**çağıranın uygulama etki alanında sona alınacaktır.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_beginthread**|\<Process. h>|
|**_beginthreadex**|\<Process. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) çok iş parçacıklı sürümleri.

**_Beginthread** veya **_beginthreadex**kullanmak için, uygulama çok iş parçacıklı C çalışma zamanı kitaplıklarından birine bağlanmalıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnekte **_beginthread** ve **_endthread**kullanılmaktadır.

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

Aşağıdaki örnek kod, eşitleme API [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject)ile **_beginthreadex** tarafından döndürülen iş parçacığı işleyicisini nasıl kullanabileceğinizi gösterir. Ana iş parçacığı, devam etmeden önce ikinci iş parçacığının sonlanmasını bekler. İkinci iş parçacığı **_endthreadex**çağırdığında, iş parçacığı nesnesinin sinyal durumuna geçmesine neden olur. Bu, birincil iş parçacığının çalışmaya devam etmesine olanak tanır. Bu, **_beginthread** ve **_endthread**ile **yapılamaz, çünkü** **_endthread** , iş parçacığı nesnesini, sinyal veren bir duruma ayarlayabilmesi için yok eder.

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
- [durdurulmaya](abort.md)
- [exit, _Exit, _exit](exit-exit-exit.md)
- [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)
