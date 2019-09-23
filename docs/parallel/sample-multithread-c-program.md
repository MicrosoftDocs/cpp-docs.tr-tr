---
title: Örnek Çoklu İş Parçacığı Kullanan C Programı
ms.date: 08/09/2019
ms.assetid: 4706f6cd-ff9c-4dbf-99a2-1c999b568f17
ms.openlocfilehash: eb1a07558dd9446e167c27ad08891f88c37fb4ec
ms.sourcegitcommit: b3d19b5f59f3a5d90c24f9f16c73bad4c5eb6944
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71195810"
---
# <a name="sample-multithread-c-program"></a>Örnek Çoklu İş Parçacığı Kullanan C Programı

Sıçrama. c, her harf `a` veya `A` yazıldığında yeni bir iş parçacığı oluşturan örnek bir çoklu iş parçacıklı programdır. Her bir iş parçacığı, ekran etrafında farklı bir rengin harfine sıçrayın. 32 adede kadar iş parçacığı oluşturulabilir. Programın normal sonlandırılması, `q` veya `Q` yazıldığında oluşur.

## <a name="compile-and-link-a-multithread-program"></a>Çoklu iş parçacığı programı derleme ve bağlama

Programlar varsayılan olarak çok iş parçacıklı olarak derlenir.

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-within-the-development-environment"></a>Çoklu iş parçacığı programı sıçramasını derlemek ve geliştirme ortamının içinden bağlamak için

::: moniker range=">=vs-2019"

1. **Dosya** menüsünde **Yeni** > **Proje**' yi seçin.

1. **Yeni proje oluştur** iletişim kutusunda **C++** , **Windows**ve **konsol** etiketleri olan **konsol uygulaması** şablonunu seçin. Devam etmek için **İleri ' yi** seçin.

1. **Yeni projenizi yapılandırın** iletişim kutusunda, projeniz Için "sıçrama" gibi bir ad girin. Devam etmek için **Oluştur** ' a tıklayın.

1. **Çözüm Gezgini** penceresinde, projenizin altındaki **kaynak dosyalar** klasörünü açın ve kaynak dosyanızın adını. c uzantısına sahip olacak şekilde değiştirin.

1. Düzenle penceresinde, varolan kaynak kodu silin ve örnek kodla değiştirin.

1. **Build** menüsünde **Build Solution**öğesini seçin.

1. Hata ayıklayıcıda programı başlatmak için **F5** tuşuna basın.

::: moniker-end

::: moniker range="<=vs-2017"

1. **Dosya** menüsünde **Yeni** > **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunda sol bölmedeki  **C++ görsel** ' i seçin ve ardından orta bölmedeki **boş proje** ' yi seçin.

1. **Ad** düzenleme kutusunda, projeniz Için "sıçrama" gibi bir ad girin. Boş projeyi oluşturmak için **Tamam ' ı** seçin.

1. **Çözüm Gezgini** penceresinde, projenizin altındaki **kaynak dosyalar** klasörünü açın ve C kaynak kodunu içeren dosyayı projeye ekleyin.

1. **Build (Oluştur) menüsünde,** **Build Solution** komutunu seçerek projeyi derleyin.

1. Hata ayıklayıcıda programı başlatmak için **F5** tuşuna basın.

::: moniker-end

### <a name="to-compile-and-link-the-multithread-program-bouncec-from-the-command-line"></a>Çoklu iş parçacığı programı SIÇRAMASIZ. c programını komut satırından derlemek ve bağlamak için

1. Programı derleyin ve bağlayın:

    ```cmd
    cl bounce.c
    ```

## <a name="example"></a>Örnek

Komut satırında oluşturmak için, bu örneği. c uzantılı bir kaynak dosyasına kopyalayın ve kaydedin. IDE 'de, şablon tarafından oluşturulan kaynak kodları şu örnekle değiştirin:

```C
// sample_multithread_c_program.c
// compile with: /c
//
//  Bounce - Creates a new thread each time the letter 'a' is typed.
//  Each thread bounces a character of a different color around
//  the screen. All threads are terminated when the letter 'Q' is
//  entered.
//

#include <windows.h>
#include <stdlib.h>
#include <string.h>
#include <stdio.h>
#include <conio.h>
#include <process.h>

#define MAX_THREADS  32

// The function getrandom returns a random number between
// min and max, which must be in integer range.
#define getrandom( min, max ) (SHORT)((rand() % (int)(((max) + 1) - \
                               (min))) + (min))

int main(void);                    // Thread 1: main
void KbdFunc(void);                // Keyboard input, thread dispatch
void BounceProc(void* MyID);       // Threads 2 to n: display
void ClearScreen(void);            // Screen clear
void ShutDown(void);               // Program shutdown
void WriteTitle(int ThreadNum);    // Display title bar information

HANDLE  hConsoleOut;                 // Handle to the console
HANDLE  hRunMutex;                   // "Keep Running" mutex
HANDLE  hScreenMutex;                // "Screen update" mutex
int     ThreadNr;                    // Number of threads started
CONSOLE_SCREEN_BUFFER_INFO csbiInfo; // Console information
COORD   consoleSize;
BOOL    bTrails;

int main() // Thread One
{
    // Get display screen information & clear the screen.
    hConsoleOut = GetStdHandle(STD_OUTPUT_HANDLE);
    GetConsoleScreenBufferInfo(hConsoleOut, &csbiInfo);
    consoleSize.X = csbiInfo.srWindow.Right;
    consoleSize.Y = csbiInfo.srWindow.Bottom;
    ClearScreen();
    WriteTitle(0);

    // Create the mutexes and reset thread count.
    hScreenMutex = CreateMutexW(NULL, FALSE, NULL);  // Cleared
    hRunMutex = CreateMutexW(NULL, TRUE, NULL);      // Set
    ThreadNr = 0;
    bTrails = FALSE;

    // Start waiting for keyboard input to dispatch threads or exit.
    KbdFunc();

    // All threads done. Clean up handles.
    if (hScreenMutex) CloseHandle(hScreenMutex);
    if (hRunMutex) CloseHandle(hRunMutex);
    if (hConsoleOut) CloseHandle(hConsoleOut);
}

void ShutDown(void) // Shut down threads
{
    while (ThreadNr > 0)
    {
        // Tell thread to die and record its death.
        ReleaseMutex(hRunMutex);
        ThreadNr--;
    }

    // Clean up display when done
    WaitForSingleObject(hScreenMutex, INFINITE);
    ClearScreen();
}

void KbdFunc(void) // Dispatch and count threads.
{
    int         KeyInfo;

    do
    {
        KeyInfo = _getch();
        if (tolower(KeyInfo) == 'a' &&
            ThreadNr < MAX_THREADS)
        {
            ThreadNr++;
            _beginthread(BounceProc, 0, &ThreadNr);
            WriteTitle(ThreadNr);
        }
        if (tolower(KeyInfo) == 't')
        {
            bTrails = !bTrails;
        }
    } while (tolower(KeyInfo) != 'q');

    ShutDown();
}

void BounceProc(void* pMyID)
{
    wchar_t MyCell, OldCell;
    WORD    MyAttrib, OldAttrib = 0;
    wchar_t BlankCell = 0x20;
    COORD   Coords, Delta;
    COORD   Old = { 0,0 };
    DWORD   Dummy;
    char* MyID = (char*)pMyID;

    // Generate update increments and initial
    // display coordinates.
    srand((unsigned int)* MyID * 3);

    Coords.X = getrandom(0, consoleSize.X - 1);
    Coords.Y = getrandom(0, consoleSize.Y - 1);
    Delta.X = getrandom(-3, 3);
    Delta.Y = getrandom(-3, 3);

    // Set up character & generate color
    // attribute from thread number.
    if (*MyID > 16)
        MyCell = 0x60 + *MyID - 16; // lower case
    else
        MyCell = 0x40 + *MyID;      // upper case
    MyAttrib = *MyID & 0x0f;   // force black background

    do
    {
        // Wait for display to be available, then lock it.
        WaitForSingleObject(hScreenMutex, INFINITE);

        if (!bTrails)
        {
            // If we still occupy the old screen position, blank it out.
            ReadConsoleOutputCharacterW(hConsoleOut, &OldCell, 1,
                Old, &Dummy);
            ReadConsoleOutputAttribute(hConsoleOut, &OldAttrib, 1,
                Old, &Dummy);
            if ((OldCell == MyCell) && (OldAttrib == MyAttrib))
                WriteConsoleOutputCharacterW(hConsoleOut, &BlankCell, 1,
                    Old, &Dummy);
        }

        // Draw new character, then clear screen lock
        WriteConsoleOutputCharacterW(hConsoleOut, &MyCell, 1,
            Coords, &Dummy);
        WriteConsoleOutputAttribute(hConsoleOut, &MyAttrib, 1,
            Coords, &Dummy);
        ReleaseMutex(hScreenMutex);

        // Increment the coordinates for next placement of the block.
        Old.X = Coords.X;
        Old.Y = Coords.Y;
        Coords.X += Delta.X;
        Coords.Y += Delta.Y;

        // If we are about to go off the screen, reverse direction
        if (Coords.X < 0 || Coords.X >= consoleSize.X)
        {
            Delta.X = -Delta.X;
            Beep(400, 50);
        }
        if (Coords.Y < 0 || Coords.Y > consoleSize.Y)
        {
            Delta.Y = -Delta.Y;
            Beep(600, 50);
        }
    }
    // Repeat while RunMutex is still taken.
    while (WaitForSingleObject(hRunMutex, 75L) == WAIT_TIMEOUT);
}

void WriteTitle(int ThreadNum)
{
    enum
    {
        sizeOfNThreadMsg = 120
    };
    wchar_t    NThreadMsg[sizeOfNThreadMsg] = { L"" };

    swprintf_s(NThreadMsg, sizeOfNThreadMsg,
        L"Threads running: %02d.  Press 'A' "
        L"to start a thread, 'T' to toggle "
        L"trails, 'Q' to quit.", ThreadNum);
    SetConsoleTitleW(NThreadMsg);
}

void ClearScreen(void)
{
    DWORD    dummy = 0;
    COORD    Home = { 0, 0 };
    FillConsoleOutputCharacterW(hConsoleOut, L' ',
        consoleSize.X * consoleSize.Y,
        Home, &dummy);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)
