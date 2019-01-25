---
title: 'İzlenecek yol: Geleneksel Windows masaüstü uygulaması (C++) oluştur'
ms.custom: get-started-article
ms.date: 09/18/2018
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.openlocfilehash: 07da91ea092b4e7bee974b0387e72ea0cacaec8e
ms.sourcegitcommit: c85c8a1226d8fbbaa29f4691ed719f8e6cc6575c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54893905"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>İzlenecek yol: Geleneksel Windows masaüstü uygulaması (C++) oluştur

Bu izlenecek yol, Visual Studio'da geleneksel Windows masaüstü uygulaması oluşturma işlemi gösterilmektedir. Örnek uygulama oluşturacağınız, "Hello, Windows Masaüstü!" görüntülemek için Windows API kullanır. bir pencere içinde. Diğer Windows Masaüstü uygulamaları oluşturmak için model Bu izlenecek yolda geliştirdiğiniz kodu kullanabilirsiniz.

Windows API (olarak da bilinen Win32 API, Windows Masaüstü API ve Windows Klasik API) Windows uygulamaları oluşturmak için bir C dili tabanlı çerçevedir. Bu, 1980 lerin beri var olmuştur ve onlarca Windows uygulamaları oluşturmak için kullanılır. Daha gelişmiş ve program daha kolay çerçeveleri, MFC, ATL ve .NET Framework gibi bir Windows API üstünde eklenmiştir. C +'da yazılmış UWP ve Store uygulamaları için bile en modern kod +/ WinRT altındaki Windows API kullanır. Windows API hakkında daha fazla bilgi için bkz. [Windows API dizin](/windows/desktop/apiindex/windows-api-list). Windows uygulamaları oluşturmak için birçok yolu vardır, ancak yukarıdaki işlemi ilk kuruluştur.

> [!IMPORTANT]
> Konuyu uzatmamak amacıyla bazı kod deyimlerini metinde göz ardı edilir. [Kodu derlemek](#build-the-code) bölümü bu belgenin sonunda tam kod gösterilir.

## <a name="prerequisites"></a>Önkoşullar

- Microsoft Windows 7 veya sonraki sürümleri çalıştıran bir bilgisayar. Windows 10 için en iyi geliştirme deneyimi öneririz.

- Visual Studio 2017 bir kopyası. Visual Studio yükleyip hakkında daha fazla bilgi için bkz. [Visual Studio'yu yükleyin](/visualstudio/install/install-visual-studio). Yükleyici çalıştırdığınızda emin **C++ ile masaüstü geliştirme** iş yükü denetlenir. Visual Studio yüklediğinizde bu iş yükü yüklenmediyse, endişelenmeyin. Yükleyiciyi yeniden çalıştırın ve şimdi yükleyin.

   ![C++ ile masaüstü geliştirme](../build/media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

- Visual Studio IDE kullanmanın temellerini olma. Windows Masaüstü uygulamaları önce kullandıysanız, büyük olasılıkla tutabilirsiniz. Bir giriş için bkz [Visual Studio IDE özellik Turu](/visualstudio/ide/visual-studio-ide).

- Bir anlayış yeterli örneği takip etmek için C++ dilinin temellerini. Merak etmeyin, biz vermekten hiçbir şey yapmaz.

## <a name="create-a-windows-desktop-project"></a>Windows Masaüstü projesi oluşturma

Windows masaüstü uygulaması için bir çalışma kodu girin ve ilk Windows Masaüstü projenizi oluşturmak için aşağıdaki adımları izleyin. Visual Studio'nun Visual Studio 2017 sürüm 15.3 eski bir sürümü kullanıyorsanız, atlayın [Visual Studio 2017 RTM'de, bir Windows Masaüstü projesi oluşturmak için](#create-in-vs2017-rtm).

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017-update-153-and-later"></a>Visual Studio 2017 güncelleştirme 15.3 ve daha sonra Windows Masaüstü proje oluşturmak için

1. Üzerinde **dosya** menüsünde seçin **yeni** seçip **proje**.

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede, **yüklü** > **Visual C++**, ardından **Windows Masaüstü**. Orta bölmede seçin **Windows Masaüstü Sihirbazı'nı**.

   İçinde **adı** kutusunda, proje için bir ad yazın örneğin, *DesktopApp*. **Tamam**’ı seçin.

   ![DesktopApp projesini adlandırın](../build/media/desktop-app-new-project-name-153.png "DesktopApp projesini adlandırın")

1. İçinde **Windows Masaüstü projesi** iletişim altında **uygulama türü**seçin **Windows uygulaması (.exe)**. Altında **ek seçenekler**seçin **boş proje**. Seçin **Tamam** projeyi oluşturmak için.

   ![Windows Masaüstü Proje Sihirbazı'nda DesktopApp oluşturma](../build/media/desktop-app-new-project-wizard-153.png "DesktopApp Windows Masaüstü Proje Sihirbazı'nda oluşturma")

1. İçinde **Çözüm Gezgini**, sağ **DesktopApp** projesinin **Ekle**ve ardından **yeni öğe**.

   ![DesktopApp projesine yeni öğe Ekle](../build/media/desktop-app-project-add-new-item-153.gif "DesktopApp projesine yeni öğe Ekle")

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda **C++ dosyası (.cpp)**. İçinde **adı** kutusuna, dosya için bir ad yazın örneğin, *HelloWindowsDesktop.cpp*. Seçin **ekleme**.

   ![DesktopApp projesine Ekle .cpp dosyası](../build/media/desktop-app-add-cpp-file-153.png "DesktopApp projesine Ekle .cpp dosyası")

Projeniz oluşturuldu ve kaynak dosyanızı Düzenleyicisi'nde açılır. Devam etmek için İleri atlayabilirsiniz [kod oluşturma](#create-the-code).

### <a id="create-in-vs2017-rtm"></a> Visual Studio 2017 RTM'de, bir Windows Masaüstü projesi oluşturmak için

1. Üzerinde **dosya** menüsünde seçin **yeni** seçip **proje**.

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede, **yüklü** > **şablonları** > **Visual C++** ve ardından **Win32**. Orta bölmede seçin **Win32 projesi**.

   İçinde **adı** kutusunda, proje için bir ad yazın örneğin, *DesktopApp*. **Tamam**’ı seçin.

   ![DesktopApp projesini adlandırın](../build/media/desktop-app-new-project-name-150.png "DesktopApp projesini adlandırın")

1. Üzerinde **genel bakış** sayfasının **Win32 Uygulama Sihirbazı**, seçin **sonraki**.

   ![Win32 Uygulama Sihirbazı genel bakış DesktopApp oluşturma](../build/media/desktop-app-win32-wizard-overview-150.png "DesktopApp genel bakış Win32 Uygulama Sihirbazı oluştur")

1. Üzerinde **uygulama ayarları** sayfasındaki **uygulama türü**seçin **Windows uygulama**. Altında **ek seçenekler**seçin **boş proje**. Seçin **son** projeyi oluşturmak için.

   ![Win32 Uygulama Sihirbazı ayarlarında DesktopApp oluşturma](../build/media/desktop-app-win32-wizard-settings-150.png "DesktopApp Win32 Uygulama Sihirbazı ayarları oluşturma")

1. İçinde **Çözüm Gezgini**, DesktopApp projeye sağ tıklayın, seçin **Ekle**ve ardından **yeni öğe**.

   ![DesktopApp projesine yeni öğe Ekle](../build/media/desktop-app-project-add-new-item-150.gif "DesktopApp projesine yeni öğe Ekle")

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda **C++ dosyası (.cpp)**. İçinde **adı** kutusuna, dosya için bir ad yazın örneğin, *HelloWindowsDesktop.cpp*. Seçin **ekleme**.

   ![DesktopApp projesine Ekle .cpp dosyası](../build/media/desktop-app-add-cpp-file-150.png "DesktopApp projesine Ekle .cpp dosyası")

Projeniz oluşturuldu ve kaynak dosyanızı Düzenleyicisi'nde açılır.

## <a name="create-the-code"></a>Kod oluşturma

Ardından, Visual Studio'da bir Windows masaüstü uygulaması için kod oluşturulacağını öğreneceksiniz.

### <a name="to-start-a-windows-desktop-application"></a>Windows Masaüstü uygulamasını başlatmak için

1. Yalnızca her C uygulamasının ve C++ uygulamasının olmalıdır bir `main` işlev başlangıç noktası olarak her Windows masaüstü uygulaması olmalıdır bir `WinMain` işlevi. `WinMain` Aşağıdaki sözdizimine sahiptir.

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   Parametreler ve bu işlevin dönüş değeri hakkında daha fazla bilgi için bkz. [WinMain giriş noktası](/windows/desktop/api/winbase/nf-winbase-winmain).

   > [!NOTE]
   > Tüm bu ek sözcükler gibi nelerdir `CALLBACK`, veya `HINSTANCE`, veya `_In_`? Tür tanımları geleneksel Windows API kullanır ve kapsamlı bir şekilde hemen soyutlamak için Önişlemci makroları ayrıntılarını türleri ve platforma özgü bazı kod, çağırma kuralları, gibi **__declspec** bildirimler ve pragmalar derleyici. Visual Studio IntelliSense kullanabileceğiniz [hızlı bilgi](/visualstudio/ide/using-intellisense#quick-info) özelliği bu tür tanımlarının ve makroları tanımlayın görmek için. Fare, ilgilenilen sözcüğün üzerinde gelin veya görseli seçip **Ctrl**+**K**, **Ctrl**+**miyim** için bir tanımını içeren küçük açılır pencere. Daha fazla bilgi için [IntelliSense kullanarak](/visualstudio/ide/using-intellisense). Parametreler ve dönüş türleri, sık kullandığınız *SAL ek açıklamalarını* yardımcı olması için programlama hatalarını yakalama. Daha fazla bilgi için [C/C++ kod hatalarını azaltmak için SAL ek açıklamalarını kullanarak](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects).

1. Windows Masaüstü programları gerektiren &lt;windows.h >. &lt;Tchar.h > tanımlar `TCHAR` sonuçta çözümler makro için **wchar_t** UNICODE sembolü projenizde tanımlanmazsa, aksi takdirde, çözümler **char**.  Her zaman etkin UNICODE ile derleme yaparsanız TCHAR ihtiyacınız yoksa ve yalnızca kullanabilirsiniz **wchar_t** doğrudan.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. Ek olarak `WinMain` işlevi, her Windows masaüstü uygulaması, ayrıca bir pencere-yordamı fonksiyonuna sahip olmalıdır. Bu işlevin genellikle adlı `WndProc` ancak istediğiniz gibi adlandırabilirsiniz. `WndProc` Aşağıdaki sözdizimine sahiptir.

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hwnd,
      _In_ UINT   uMsg,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   Bu işlevde harcanan, işlemek için kod yazma *iletileri* Windows uygulamanın aldığı zaman *olayları* oluşur. Örneğin, bir kullanıcı uygulamanızda bir Tamam düğmesini seçerse, Windows bir ileti size gönderir ve içinde kod yazabilirsiniz, `WndProc` hangi iş uygun olduğunu mu işlevi. Çağrıldığı *işleme* bir olay. Yalnızca uygulamanız için uygun olan olayları işleyin.

   Daha fazla bilgi için [pencere yordamları](/windows/desktop/winmsg/window-procedures).

### <a name="to-add-functionality-to-the-winmain-function"></a>WinMain işlevine işlevsellik eklemek için

1. İçinde `WinMain` işlevi, bir yapı türünü doldurmak [WNDCLASSEX](/windows/desktop/api/winuser/ns-winuser-tagwndclassexa). Yapısı, örneğin, uygulama simgesi, pencerenin başlık çubuğunda ve da önemlisi, bir işlev işaretçisi, pencere yordamı için görüntülenecek ad arka plan rengi pencere hakkında bilgiler içerir. Aşağıdaki örnekte gösterilmektedir `WNDCLASSEX` yapısı.

   ```cpp
   WNDCLASSEX wcex;

   wcex.cbSize         = sizeof(WNDCLASSEX);
   wcex.style          = CS_HREDRAW | CS_VREDRAW;
   wcex.lpfnWndProc    = WndProc;
   wcex.cbClsExtra     = 0;
   wcex.cbWndExtra     = 0;
   wcex.hInstance      = hInstance;
   wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
   wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
   wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
   wcex.lpszMenuName   = NULL;
   wcex.lpszClassName  = szWindowClass;
   wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);
   ```

   Yukarıdaki yapının alanları hakkında daha fazla bilgi için bkz. [WNDCLASSEX](/windows/desktop/api/winuser/ns-winuser-tagwndclassexa).

1. Kayıt `WNDCLASSEX` BT'nin pencerenizin ve iletileri göndermek nasıl hakkında bilmesi için Windows ile. Kullanım [RegisterClassEx](/windows/desktop/api/winuser/nf-winuser-registerclassexa) işlev ve pencere sınıf yapısını bir bağımsız değişken olarak geçirin. `_T` Kullandığımızdan makrosu kullanılır `TCHAR` türü.

   ```cpp
   if (!RegisterClassEx(&wcex))
   {
      MessageBox(NULL,
         _T("Call to RegisterClassEx failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

1. Şimdi bir pencere oluşturabilirsiniz. Kullanım [CreateWindow](/windows/desktop/api/winuser/nf-winuser-createwindowa) işlevi.

   ```cpp
   static TCHAR szWindowClass[] = _T("DesktopApp");
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   // The parameters to CreateWindow explained:
   // szWindowClass: the name of the application
   // szTitle: the text that appears in the title bar
   // WS_OVERLAPPEDWINDOW: the type of window to create
   // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
   // 500, 100: initial size (width, length)
   // NULL: the parent of this window
   // NULL: this application does not have a menu bar
   // hInstance: the first parameter from WinMain
   // NULL: not used in this application
   HWND hWnd = CreateWindow(
      szWindowClass,
      szTitle,
      WS_OVERLAPPEDWINDOW,
      CW_USEDEFAULT, CW_USEDEFAULT,
      500, 100,
      NULL,
      NULL,
      hInstance,
      NULL
   );
   if (!hWnd)
   {
      MessageBox(NULL,
         _T("Call to CreateWindow failed!"),
         _T("Windows Desktop Guided Tour"),
         NULL);

      return 1;
   }
   ```

   Bu işlev döndürür bir `HWND`, bir pencere için işleme olduğu. Bir tanıtıcı bakıma Windows pencereler izlemek için kullandığı bir işaretçi değil. Daha fazla bilgi için [Windows veri türleri](/windows/desktop/WinProg/windows-data-types).

1. Bu noktada, pencerenin oluşturuldu ancak biz yine de görünür yapmak için Windows bilgi gerekir. Bu kodun yaptığı olmasıdır:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   Henüz uygulamadığınız için görüntülenen pencerede çok içerik sahip `WndProc` işlevi. Diğer bir deyişle, uygulama henüz Windows artık gönderdiğini iletileri işleme değil.

1. İletileri işlemek için biz öncelikle Windows gönderdiği iletileri dinlemek için bir ileti döngüsü ekleyin. Uygulama bir mesajı aldığında, bu döngü için gönderir, `WndProc` işlenecek işlevi. İleti döngüsü aşağıdaki koda benzer.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   Yapılar ve ileti döngüsü işlevler hakkında daha fazla bilgi için bkz: [MSG](/windows/desktop/api/winuser/ns-winuser-msg), [GetMessage](/windows/desktop/api/winuser/nf-winuser-getmessage), [TranslateMessage](/windows/desktop/api/winuser/nf-winuser-translatemessage), ve [DispatchMessage ](/windows/desktop/api/winuser/nf-winuser-dispatchmessage).

   Bu noktada, `WinMain` işlevi aşağıdaki kodu benzemesi gerekir.

   ```cpp
   int WINAPI WinMain(HINSTANCE hInstance,
                      HINSTANCE hPrevInstance,
                      LPSTR lpCmdLine,
                      int nCmdShow)
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application dows not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }
   ```

### <a name="to-add-functionality-to-the-wndproc-function"></a>WndProc işlevine işlevsellik eklemek için

1. Etkinleştirmek için `WndProc` işlevi uygulamanın aldığı iletileri işlemek için bir switch deyimi uygulayın.

   İşlemek için önemli bir ileti [WM_PAINT](/windows/desktop/gdi/wm-paint) ileti. Uygulamanın aldığı `WM_PAINT` iletiyi görüntülenen penceresinin parçası güncelleştirilmesi gerekir. Olay kullanıcı pencereniz önünde bir pencere taşır, sonra yeniden hemen taşır ve bu olaylar meydana geldiğinde uygulamanızı bilmez meydana gelebilir. Yalnızca Windows bilir, size bildirir, böylece `WM_PAINT`. Pencere ilk görüntülendiğinde tümünün güncelleştirilmiş olması gerekir.

   İşlenecek bir `WM_PAINT` ileti görüntülenirse, ilk çağrı [BeginPaint](/windows/desktop/api/winuser/nf-winuser-beginpaint)sonra metin, düğmeler ve diğer denetimleri penceresindeki yerleştirme sağlayan tüm mantığı işlemek ve sonra çağrı [EndPaint](/windows/desktop/api/winuser/nf-winuser-endpaint). Uygulama için başlangıç çağrısı ve bitiş çağrısı arasındaki mantık "Hello, Windows Masaüstü!" dizesi görüntülemektir penceresinde. Aşağıdaki kodda, dikkat [TextOut](/windows/desktop/api/wingdi/nf-wingdi-textouta) işlevi dizesini görüntülemek için kullanılır.

   ```cpp
   PAINTSTRUCT ps;
   HDC hdc;
   TCHAR greeting[] = _T("Hello, Windows desktop!");

   switch (message)
   {
   case WM_PAINT:
      hdc = BeginPaint(hWnd, &ps);

      // Here your application is laid out.
      // For this introduction, we just print out "Hello, Windows desktop!"
      // in the top left corner.
      TextOut(hdc,
         5, 5,
         greeting, _tcslen(greeting));
      // End application-specific layout section.

      EndPaint(hWnd, &ps);
      break;
   }
   ```

   `HDC` kodda bir Windows grafik alt sistemi ile iletişim kurmak uygulamanızı etkinleştirmek için kullandığı bir veri yapısıdır bir cihaz bağlamına işleyicisidir. `BeginPaint` Ve `EndPaint` işlevler uygulamanızı iyi vatandaşı gibi davranır ve cihaz bağlamı için gerekenden daha uzun süre kullanmaz. Grafik alt sistemi işlevleri yardımcı olur, diğer uygulamalar tarafından kullanılabilir.

1. Bir uygulama genellikle diğer birçok iletiyi gibi işler [WM_CREATE](/windows/desktop/winmsg/wm-create) pencere ilk oluşturulduğunda ve [WM_DESTROY](/windows/desktop/winmsg/wm-destroy) zaman penceresi kapatılır. Aşağıdaki kod temel gösterir ancak tamamlamak `WndProc` işlevi.

   ```cpp
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

## <a name="build-the-code"></a>Kod derleme

Söz verdiğimiz gibi çalışan bir uygulama için tam kod aşağıda verilmiştir.

### <a name="to-build-this-example"></a>Bu örneği oluşturmak için

1. Herhangi bir kod içinde girdiğiniz Sil *HelloWindowsDesktop.cpp* Düzenleyicisi. Bu örnek kodu kopyalayın ve ardından yapıştırın *HelloWindowsDesktop.cpp*:

   ```cpp
   // HelloWindowsDesktop.cpp
   // compile with: /D_UNICODE /DUNICODE /DWIN32 /D_WINDOWS /c

   #include <windows.h>
   #include <stdlib.h>
   #include <string.h>
   #include <tchar.h>

   // Global variables

   // The main window class name.
   static TCHAR szWindowClass[] = _T("DesktopApp");

   // The string that appears in the application's title bar.
   static TCHAR szTitle[] = _T("Windows Desktop Guided Tour Application");

   HINSTANCE hInst;

   // Forward declarations of functions included in this code module:
   LRESULT CALLBACK WndProc(HWND, UINT, WPARAM, LPARAM);

   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   )
   {
      WNDCLASSEX wcex;

      wcex.cbSize = sizeof(WNDCLASSEX);
      wcex.style          = CS_HREDRAW | CS_VREDRAW;
      wcex.lpfnWndProc    = WndProc;
      wcex.cbClsExtra     = 0;
      wcex.cbWndExtra     = 0;
      wcex.hInstance      = hInstance;
      wcex.hIcon          = LoadIcon(hInstance, IDI_APPLICATION);
      wcex.hCursor        = LoadCursor(NULL, IDC_ARROW);
      wcex.hbrBackground  = (HBRUSH)(COLOR_WINDOW+1);
      wcex.lpszMenuName   = NULL;
      wcex.lpszClassName  = szWindowClass;
      wcex.hIconSm        = LoadIcon(wcex.hInstance, IDI_APPLICATION);

      if (!RegisterClassEx(&wcex))
      {
         MessageBox(NULL,
            _T("Call to RegisterClassEx failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // Store instance handle in our global variable
      hInst = hInstance;

      // The parameters to CreateWindow explained:
      // szWindowClass: the name of the application
      // szTitle: the text that appears in the title bar
      // WS_OVERLAPPEDWINDOW: the type of window to create
      // CW_USEDEFAULT, CW_USEDEFAULT: initial position (x, y)
      // 500, 100: initial size (width, length)
      // NULL: the parent of this window
      // NULL: this application does not have a menu bar
      // hInstance: the first parameter from WinMain
      // NULL: not used in this application
      HWND hWnd = CreateWindow(
         szWindowClass,
         szTitle,
         WS_OVERLAPPEDWINDOW,
         CW_USEDEFAULT, CW_USEDEFAULT,
         500, 100,
         NULL,
         NULL,
         hInstance,
         NULL
      );

      if (!hWnd)
      {
         MessageBox(NULL,
            _T("Call to CreateWindow failed!"),
            _T("Windows Desktop Guided Tour"),
            NULL);

         return 1;
      }

      // The parameters to ShowWindow explained:
      // hWnd: the value returned from CreateWindow
      // nCmdShow: the fourth parameter from WinMain
      ShowWindow(hWnd,
         nCmdShow);
      UpdateWindow(hWnd);

      // Main message loop:
      MSG msg;
      while (GetMessage(&msg, NULL, 0, 0))
      {
         TranslateMessage(&msg);
         DispatchMessage(&msg);
      }

      return (int) msg.wParam;
   }

   //  FUNCTION: WndProc(HWND, UINT, WPARAM, LPARAM)
   //
   //  PURPOSE:  Processes messages for the main window.
   //
   //  WM_PAINT    - Paint the main window
   //  WM_DESTROY  - post a quit message and return
   LRESULT CALLBACK WndProc(HWND hWnd, UINT message, WPARAM wParam, LPARAM lParam)
   {
      PAINTSTRUCT ps;
      HDC hdc;
      TCHAR greeting[] = _T("Hello, Windows desktop!");

      switch (message)
      {
      case WM_PAINT:
         hdc = BeginPaint(hWnd, &ps);

         // Here your application is laid out.
         // For this introduction, we just print out "Hello, Windows desktop!"
         // in the top left corner.
         TextOut(hdc,
            5, 5,
            greeting, _tcslen(greeting));
         // End application-specific layout section.

         EndPaint(hWnd, &ps);
         break;
      case WM_DESTROY:
         PostQuitMessage(0);
         break;
      default:
         return DefWindowProc(hWnd, message, wParam, lParam);
         break;
      }

      return 0;
   }
   ```

1. Üzerinde **derleme** menüsünde seçin **Çözümü Derle**. Derleme sonuçlarını gözükeceğini **çıkış** Visual Studio'daki.

   ![DesktopApp projenizi](../build/media/desktop-app-project-build-150.gif "DesktopApp projeyi oluşturun")

1. Uygulamayı çalıştırmak için basın **F5**. "Hello, Windows Masaüstü!" metni içeren bir pencere ekranın sol üst köşesinde görüntülenir.

   ![DesktopApp projeyi Çalıştır](../build/media/desktop-app-project-run-157.png "DesktopApp projeyi Çalıştır")

Tebrikler! Siz bu kılavuzda tamamlayıp geleneksel Windows Masaüstü uygulamanızı oluşturdunuz.

## <a name="see-also"></a>Ayrıca Bkz.

[Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md)