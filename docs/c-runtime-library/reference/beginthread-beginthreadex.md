---
title: _beginthread, _beginthreadex | Microsoft Docs
ms.custom: ''
ms.date: 02/27/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f04d6bc5ab0864a1dfc27a1de8b09f1740f845d9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
Yeni bir iş parçacığı yürütülmeye yordamının adresi başlatın. İçin **_beginthread**, ya da çağırma olduğu [__cdecl](../../cpp/cdecl.md) (için yerel kodu) veya [__clrcall](../../cpp/clrcall.md) (için yönetilen kod) için; **_beginthreadex**, ya da [__stdcall](../../cpp/stdcall.md) (için yerel kodu) veya [__clrcall](../../cpp/clrcall.md) (için yönetilen kod).

*stack_size*<br/>
Yeni bir iş parçacığı veya 0 yığın boyutu.

*arglist*<br/>
Yeni bir iş parçacığı veya NULL iletilecek bağımsız değişken listesi.

*Güvenlik*<br/>
İşaretçi bir [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) yapısı alt işlemleri tarafından döndürülen tanıtıcı devralınan olup olmadığını belirler. Varsa *güvenlik* null, tanıtıcı devralındı. NULL için Windows 95 uygulamaları olması gerekir.

*initflag*<br/>
Yeni bir iş parçacığı ilk durumunu denetlemek bayraklar. Ayarlama *initflag* hemen çalıştırmak için 0 veya için **AfxBeginThread'e** askıya alınmış durumda; iş parçacığı oluşturmak için kullanmak [ResumeThread'i](http://msdn.microsoft.com/library/windows/desktop/ms685086.aspx) iş parçacığını yürütmek için. Ayarlama *initflag* için **STACK_SIZE_PARAM_IS_A_RESERVATION** kullanmak için bayrağı *stack_size* gibi ilkyedekbaytyığınboyutu;Bubayrakolupolmadığınıbelirtilmedi*stack_size* tamamlama boyutunu belirtir.

*thrdaddr*<br/>
Noktaları 32-bit değişkene bir iş parçacığı tanımlayıcısını alır. NULL ise, kullanılmaz.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, bu işlevlerin her biri için yeni oluşturulan iş parçacığı bir işleyici döner; Ancak, yeni oluşturulan iş parçacığı çok hızlı bir şekilde bulunup bulunmadığını **_beginthread** geçerli bir tanıtıcı döndürmeyebilir. (Tartışma Açıklamalar bölümüne bakın.) Bir hata **_beginthread** -1 M döndürür ve **errno** ayarlanır **EAGAIN** varsa çok fazla iş parçacığı için **EINVAL** bağımsız değişken ise geçersiz veya yığın boyutu yanlış veya **EACCES** (örneğin bellek) yetersiz kaynak. Bir hata **_beginthreadex** 0 döndürür ve **errno** ve **_doserrno** ayarlanır.

Varsa *start_address* null, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür.

Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Hakkında daha fazla bilgi için **uintptr_t**, bkz: [standart türler](../../c-runtime-library/standard-types.md).

## <a name="remarks"></a>Açıklamalar

**_Beginthread** işlev oluşturur yordamının yürütülmeye bir iş parçacığı *start_address*. Yordam sırasında *start_address* kullanmalısınız **__cdecl** (için yerel kodu) veya **__clrcall** (yönetilen kod için) çağırma ve bir dönüş değerine sahip olmalıdır. İş parçacığı bu yordamından geri döndüğünde, otomatik olarak sonlandırılır. İş parçacıkları hakkında daha fazla bilgi için bkz: [eski kod (Visual C++) için çoklu iş parçacığı desteği](../../parallel/multithreading-support-for-older-code-visual-cpp.md).

**_beginthreadex** Win32 benzer [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453.aspx) API daha fazla daha yakından **_beginthread** yapar. **_beginthreadex** farklıdır **_beginthread** aşağıdaki yollarla:

- **_beginthreadex** üç ek parametrelere sahip: *initflag*, *güvenlik*, ve **threadaddr**. Yeni bir iş parçacığı askıya alınmış durumda, belirtilen bir güvenlik ile oluşturulan ve kullanarak erişilebilir *thrdaddr*, iş parçacığı tanımlayıcısı olduğu.

- Yordam sırasında *start_address* için geçirilen **_beginthreadex** kullanmalısınız **__stdcall** (için yerel kodu) veya **__clrcall** (için yönetilen kod) çağırma ve bir iş parçacığı çıkış kodu döndürmesi gerekir.

- **_beginthreadex** 0-1 M yerine hatası döndürür.

- Kullanılarak oluşturulan bir iş parçacığı **_beginthreadex** için yapılan bir çağrı tarafından sonlandırıldı [_endthreadex](endthread-endthreadex.md).

**_Beginthreadex** işlevi size daha iş parçacığı nasıl oluşturulacağını üzerinde daha fazla denetim **_beginthread** yapar. **_Endthreadex** işlevidir ayrıca daha esnektir. Örneğin, **_beginthreadex**, güvenlik bilgilerini kullanmak, ilk durumunu (çalışıyor veya askıya alındı) iş parçacığı ayarlamak ve yeni oluşturulan iş parçacığı iş parçacığı tanımlayıcısını alın. Tarafından döndürülen iş parçacığı tutamacı de kullanabilirsiniz **_beginthreadex** eşitleme ile yapamayacağı API'leri ile **_beginthread**.

Kullanmak daha güvenlidir **_beginthreadex** daha **_beginthread**. Varsa tarafından oluşturulan iş parçacığı **_beginthread** hızla çağırana döndürülen tanıtıcı çıkar **_beginthread** geçersiz veya başka bir iş parçacığı noktası olabilir. Ancak, tarafından döndürülen tanıtıcı **_beginthreadex** çağıran tarafından kapatılması gerekir **_beginthreadex**, geçerli bir tanıtıcı olması garanti **_beginthreadex** bir hata döndürmedi.

Çağırabilirsiniz [_endthread](endthread-endthreadex.md) veya **_endthreadex** açıkça bir iş parçacığı; sonlandırmak için ancak **_endthread** veya **_endthreadex** çağrılır otomatik olarak zaman iş parçacığı bir parametre olarak geçirilen yordamı döndürür. Bir iş parçacığı çağrısıyla sonlandırma **_endthread** veya **_endthreadex** iş parçacığı için ayrılan kaynakların doğru kurtarma sağlamaya yardımcı olur.

**_endthread** ise iş parçacığı tutamacı otomatik olarak kapanır **_endthreadex** desteklemez. Bu nedenle, kullandığınızda **_beginthread** ve **_endthread**, açıkça iş parçacığı tutamacı Win32 çağırarak kapatmayın [CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API. Bu davranış Win32 farklıdır [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) API.

> [!NOTE]
> Libcmt.lib ile bağlantılı bir yürütülebilir dosya için Win32 çağırmayın **ExitThread** API çalışma zamanı sistem geri kazanma gelen önlemez böylece ayrılan kaynakları. **_endthread** ve **_endthreadex** ayrılmış iş parçacığı kaynaklarını geri kazanmak ve ardından arama **ExitThread**.

Yığın ayırma işletim sistemi işleme olduğunda ya da **_beginthread** veya **_beginthreadex** olarak adlandırılır; iş parçacığı yığınının adresini ya da bu işlevlerin geçirmek zorunda değilsiniz. Ayrıca, *stack_size* bağımsız değişkeni, 0, içinde durum işletim sistemi kullanan aynı değeri belirtilen yığın ana iş parçacığı olabilir.

*arglist* yeni oluşturulan iş parçacığına iletilecek parametre. Genellikle, bu karakter dizesi gibi bir veri öğesi adresidir. *arglist* gerekmiyorsa, boş olabilir ancak **_beginthread** ve **_beginthreadex** için yeni bir iş parçacığı geçirmek için bir değer verilmesi gerekir. Tüm iş parçacıklarının tüm çağrıları uzatırsanız sonlandırılır [abort](abort.md), **çıkmak**, **_exit**, veya **ExitProcess**.

İşlem başına genel geçerli yerel ayar bilgileri kullanarak yeni bir iş parçacığı yerel başlatılır. İş parçacığı başına yerel ayar için bir çağrı tarafından etkin olup olmadığını [_configthreadlocale](configthreadlocale.md) (genel olarak veya yeni iş parçacıklarının yalnızca), iş parçacığının kendi yerel bağımsız olarak diğer iş parçacıklarından çağırarak değiştirebilirsiniz **setlocale** veya **_wsetlocale**. İş parçacığı başına yerel ayar bayrağı ayarlanmış sahip olmayan iş parçacıklarının tüm yeni oluşturulan iş parçacıklarını yanı sıra iş parçacığı başına yerel ayar bayrağı ayarlanmış de sahip olmayan tüm diğer iş parçacığı yerel ayar bilgileri etkileyebilir. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Karışık ve saf kod için **_beginthread** ve **_beginthreadex** her iki aşırı sahip. Bir yerel arama kuralı işlev işaretçisi alır ve diğer sürer bir **__clrcall** işlev işaretçisi. İlk aşırı uygulama etki alanı için güvenli ve hiçbir zaman değil olabilir. Karma veya saf kod yazıyorsanız, yönetilen kaynaklara erişim izni vermeden önce yeni bir iş parçacığı doğru uygulama etki alanı girdiğinden emin olmanız gerekir. Örneğin, kullanarak bunu [call_in_appdomain işlevi](../../dotnet/call-in-appdomain-function.md). İkinci aşırı yüklemesi uygulama etki alanı için güvenli, Yeni oluşturulan iş parçacığı çağıran uygulama etki alanı her zaman ulaşır **_beginthread** veya **_beginthreadex**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_beginthread**|\<Process.h >|
|**_beginthreadex**|\<Process.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Birden çok iş parçacıklı sürümlerini [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

Kullanılacak **_beginthread** veya **_beginthreadex**, uygulamanın birden çok iş parçacıklı C çalışma zamanı kitaplıkları biriyle bağlamanız gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek kullanır **_beginthread** ve **_endthread**.

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

// Bounce - Thread to create and and control a colored letter that moves
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

Aşağıdaki örnek kod tarafından döndürülen iş parçacığı tutamacı nasıl kullanabileceğinizi gösteren **_beginthreadex** API eşitlemeyle [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx). Ana iş parçacığı devam etmeden önce sonlandırmak ikinci iş parçacığı için bekler. İkinci bir iş parçacığı çağırdığında **_endthreadex**, iş durumuna gitmek kendi iş parçacığı nesnesi neden olur. Bu birincil iş parçacığı çalışmaya devam etmesini sağlar. Bu ile yapılamaz **_beginthread** ve **_endthread**, çünkü **_endthread** çağrıları **CloseHandle**, iş parçacığı yok eder İş durumu ayarlayabilmeniz için önce nesne.

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

[Süreç ve Ortam Denetimi](../../c-runtime-library/process-and-environment-control.md)<br/>
[_endthread, _endthreadex](endthread-endthreadex.md)<br/>
[abort](abort.md)<br/>
[exit, _Exit, _exit](exit-exit-exit.md)<br/>
[GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)<br/>
