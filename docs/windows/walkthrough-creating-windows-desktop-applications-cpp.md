---
title: "İzlenecek yol: Geleneksel Windows Masaüstü uygulama (C++) oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 1/11/2018
ms.reviewer: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce3c18abbace2181b2d31e0621b6e376021be68a
ms.sourcegitcommit: c2e990450ccd528d85b2783fbc63042612987cfd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/16/2018
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>İzlenecek yol: Geleneksel Windows Masaüstü uygulama (C++) oluşturma

Bu kılavuzda, Visual Studio'da geleneksel bir Windows masaüstü uygulaması oluşturulacağını gösterir. Oluşturacağınız örnek uygulama, "Hello, Windows Masaüstü!" görüntülemek için Windows API kullanır. bir pencerede. Bu kılavuzda diğer Windows Masaüstü uygulamaları oluşturmak için bir desen geliştirmek kodu kullanabilirsiniz.

Windows API (olarak da bilinen Win32 API, Windows Masaüstü API ve Windows Klasik API), Windows uygulamaları oluşturma bir C dili tabanlı çerçevedir. Varlığı 1980 lerin bu yana bırakıldı ve Windows uygulamaları için on yılları oluşturmak için kullanılır. Daha gelişmiş ve daha kolay program çerçeveleri MFC ve ATL .NET Framework gibi bu API üstünde oluşturulmuş. C + yazılmış UWP ve mağazası uygulamaları için bile en modern kod +/ WinRT altında bu API kullanır. Windows API'si hakkında daha fazla bilgi için bkz: [Windows API dizini](https://msdn.microsoft.com/library/windows/desktop/ff818516.aspx). Windows uygulamaları oluşturmak için birçok yolu vardır, ancak bu ilk değil.

> [!IMPORTANT]
> Konuyu uzatmamak amacıyla bazı kod deyimleri metin göz ardı edilir. [Kod derleme](#build-the-code) bölümünde bu belgenin sonundaki tam kod gösterilir.

## <a name="prerequisites"></a>Önkoşullar

- Microsoft Windows 7 veya sonraki sürümlerini çalıştıran bir bilgisayar. En iyi geliştirme deneyimi için Windows 10 öneririz.

- Visual Studio 2017 kopyası. Visual Studio yükleyip konusunda daha fazla bilgi için bkz: [yükleme Visual Studio 2017](/visualstudio/install/install-visual-studio). Yükleyiciyi çalıştırdığınızda emin olun **C++ ile masaüstü geliştirme** iş yükü denetlenir. Visual Studio yüklendiğinde bu iş yükü yüklenmediyse, endişelenmeyin. Yükleyiciyi yeniden çalıştırın ve şimdi yükleyin.

   ![C++ ile masaüstü geliştirme](../build/media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

- Visual Studio IDE kullanarak, temel bir anlayış. Windows Masaüstü uygulamaları önce kullandıysanız, büyük olasılıkla tutabilirsiniz. Giriş için bkz [Visual Studio IDE özelliği Turu](/visualstudio/ide/visual-studio-ide).

- Bir anlayış yeterli izlemek için C++ dili ile ilgili temel bilgileri. Endişelenmeyin, biz çok karmaşık hiçbir şey yapmayın.

## <a name="create-a-windows-desktop-project"></a>Windows Masaüstü projesi oluşturma

İlk Windows Masaüstü projenizi oluşturmak ve Windows masaüstü uygulaması için bir çalışma kodu girmek için şu adımları izleyin. Visual Studio sürümü 15.3 Visual Studio 2017'den daha eski bir sürümünü kullanıyorsanız, İleri için atlayabilirsiniz [Visual Studio 2017 RTM ile bir Windows Masaüstü projesi oluşturmak için](#create-in-vs2017-rtm).

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017-update-153-and-later"></a>Visual Studio 2017 güncelleştirme 15.3 ve daha sonra Windows Masaüstü projesi oluşturmak için

1. Üzerinde **dosya** menüsünde seçin **yeni** ve ardından **proje**.

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede, genişletin **yüklü**, **Visual C++**seçeneğini belirleyip **Windows Masaüstü**. Orta bölmede seçin **Windows Masaüstü Sihirbazı'nı**.

   İçinde **adı** kutusunda, proje için bir ad yazın, örneğin, *DesktopApp*. Seçin **Tamam**.

   ![DesktopApp proje adı](../build/media/desktop-app-new-project-name-153.png "DesktopApp proje adı")

1. İçinde **Windows Masaüstü projesi** iletişim altında **uygulama türü**seçin **Windows uygulaması (.exe)**. Altında **ek seçenekler**seçin **boş proje**. Seçin **Tamam** projesi oluşturmak için.

   ![Windows Masaüstü projesi Sihirbazı'nda DesktopApp oluşturma](../build/media/desktop-app-new-project-wizard-153.png "DesktopApp Windows Masaüstü projesi Sihirbazı'nda oluşturma")

1. İçinde **Çözüm Gezgini**, sağ **DesktopApp** seçin, proje **Ekle**ve ardından **yeni öğe**.

   ![DesktopApp projesine yeni öğe Ekle](../build/media/desktop-app-project-add-new-item-153.gif "DesktopApp projesine yeni öğe Ekle")

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda **C++ dosyasına (.cpp)**. İçinde **adı** kutusuna, dosya için bir ad yazın, örneğin, *HelloWindowsDesktop.cpp*. Seçin **eklemek**.

   ![DesktopApp projesine Ekle .cpp dosyasını](../build/media/desktop-app-add-cpp-file-153.png "DesktopApp projesine .cpp Dosya Ekle")

Projeniz şimdi oluşturulur ve kaynak dosyanızı Düzenleyicisi'nde açılır. Devam etmek için İleri atlayabilirsiniz [kod oluşturma](#create-the-code).

### <a id="create-in-vs2017-rtm"></a>Visual Studio 2017 RTM ile bir Windows Masaüstü projesi oluşturmak için

1. Üzerinde **dosya** menüsünde seçin **yeni** ve ardından **proje**.

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede, genişletin **yüklü**, **şablonları**, **Visual C++**ve ardından **Win32**. Orta bölmede seçin **Win32 Proje**.

   İçinde **adı** kutusunda, proje için bir ad yazın, örneğin, *DesktopApp*. Seçin **Tamam**.

   ![DesktopApp proje adı](../build/media/desktop-app-new-project-name-150.png "DesktopApp proje adı")

1. Üzerinde **genel bakış** sayfasında **Win32 Uygulama Sihirbazı'nı**, seçin **sonraki**.

   ![Win32 Uygulama Sihirbazı genel bakış DesktopApp oluşturma](../build/media/desktop-app-win32-wizard-overview-150.png "DesktopApp genel bakış Win32 Uygulama Sihirbazı oluştur")

1. Üzerinde **uygulama ayarları** sayfasında **uygulama türü**seçin **Windows uygulaması**. Altında **ek seçenekler**seçin **boş proje**. Seçin **son** projesi oluşturmak için.

   ![Win32 Uygulama Sihirbazı ayarlarında DesktopApp oluşturma](../build/media/desktop-app-win32-wizard-settings-150.png "DesktopApp Win32 Uygulama Sihirbazı ayarları oluşturma")

1. İçinde **Çözüm Gezgini**, DesktopApp projesine sağ tıklayın, seçin **Ekle**ve ardından **yeni öğe**.

   ![DesktopApp projesine yeni öğe Ekle](../build/media/desktop-app-project-add-new-item-150.gif "DesktopApp projesine yeni öğe Ekle")

1. İçinde **Yeni Öğe Ekle** iletişim kutusunda **C++ dosyasına (.cpp)**. İçinde **adı** kutusuna, dosya için bir ad yazın, örneğin, *HelloWindowsDesktop.cpp*. Seçin **eklemek**.

   ![DesktopApp projesine Ekle .cpp dosyasını](../build/media/desktop-app-add-cpp-file-150.png "DesktopApp projesine .cpp Dosya Ekle")

Projeniz şimdi oluşturulur ve kaynak dosyanızı Düzenleyicisi'nde açılır.

## <a name="create-the-code"></a>Kod oluşturma

Ardından, Visual Studio'da bir Windows masaüstü uygulaması için kod oluşturmak nasıl öğreneceksiniz.

### <a name="to-start-a-windows-desktop-application"></a>Bir Windows masaüstü uygulaması başlatmak için

1. Yalnızca her C uygulama ve C++ uygulaması olmalıdır bir `main` işlev başlangıç noktası olarak her Windows masaüstü uygulaması olmalıdır bir `WinMain` işlevi. `WinMain`sözdizimi aşağıdaki gibidir.

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   Bu işlevin dönüş değeri ve parametreleri hakkında daha fazla bilgi için bkz: [WinMain giriş noktası](https://msdn.microsoft.com/library/windows/desktop/ms633559).

   > [!NOTE]
   > Tüm ek sözcükleri, gibi nelerdir **geri ÇAĞIRMA**, veya **HINSTANCE**, veya  **\_içinde\_**? Tür tanımları geleneksel Windows API kullanır ve yaygın hemen soyut Önişlemci makroları bazı ayrıntılar türleri ve platforma özgü kod, çağırma kuralları, gibi **__declspec** bildirimler ve derleyici pragmaları. Visual Studio'da IntelliSense kullanabilirsiniz [hızlı bilgi](/visualstudio/ide/using-intellisense#quick-info) bu tür tanımları ve makrolar tanımlayın görmek için özellik. Farenizi ilgi, word getirin veya seçin ve ctrl-K, ctrl tuşuna basın-ı tanımını içeren küçük bir açılır pencere için. Daha fazla bilgi için bkz: [kullanarak IntelliSense](/visualstudio/ide/using-intellisense). Parametreler ve dönüş türleri sık kullandığınız *SAL ek açıklamaları* yardımcı olması için programlama hatalarını yakalama. Daha fazla bilgi için bkz: [C/C++ kod hatalarını azaltmak için SAL ek açıklamaları kullanılarak](/visualstudio/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects).

1. Windows Masaüstü programları gerektiren &lt;windows.h >. &lt;Tchar.h > tanımlar `TCHAR` sonuçta çözümler makrosu için `wchar_t` UNICODE simge projenizde tanımlanırsa, aksi takdirde bu çözümler `char`.  UNICODE etkin her zaman olarak oluşturursanız TCHAR gerek yoktur ve yalnızca wchar_t doğrudan kullanabilirsiniz.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. Ek olarak `WinMain` işlevi, her Windows masaüstü uygulaması penceresini yordamı işlevi olması gerekir. Bu işlev genellikle adlı `WndProc` ancak istediğiniz gibi adlandırabilirsiniz. `WndProc`sözdizimi aşağıdaki gibidir.

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hwnd,
      _In_ UINT   uMsg,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   Bu işlevde işlemek için kod yazma *iletileri* uygulama Windows'dan alan zaman *olayları* oluşur. Örneğin, bir kullanıcı, uygulamanızda Tamam düğmesine seçerse, Windows bir ileti size gönderir ve içinde kod yazabilirsiniz, `WndProc` hangi iş uygun yapar işlevi. Bu adlı *işleme* bir olay. Yalnızca uygulamanız için uygun olan olayları idare eder.

   Daha fazla bilgi için bkz: [pencere yordamları](https://msdn.microsoft.com/library/windows/desktop/ms632593).

### <a name="to-add-functionality-to-the-winmain-function"></a>WinMain işlevi işlevselliği eklemek için

1. İçinde `WinMain` işlevi türü yapısını doldurmak [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577). Bu yapı penceresi, örneğin, uygulama simgesi, penceresinin başlık çubuğunda ve çok da önemlisi, bir işlev işaretçisi pencere yordamı için görüntülenecek adı arka plan rengini hakkında bilgi içerir. Aşağıdaki örnek gösterilmektedir `WNDCLASSEX` yapısı.

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

   Bu yapı alanları hakkında daha fazla bilgi için bkz: [WNDCLASSEX](https://msdn.microsoft.com/library/windows/desktop/ms633577).

1. Kaydetmeniz gerekir `WNDCLASSEX` pencerenizi ve iletileri göndermeye nasıl hakkında BT'nin bilmesi için Windows ile. Kullanım [RegisterClassEx](https://msdn.microsoft.com/library/windows/desktop/ms633587) işlev ve pencere sınıfı yapısı bağımsız değişken olarak geçirin. `_T` Makrosu kullandığımız için kullanılan `TCHAR` türü.

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

1. Artık bir pencere oluşturabilirsiniz. Kullanım [CreateWindow'u](https://msdn.microsoft.com/library/windows/desktop/ms632679) işlevi.

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

   Bu işlev döndüren bir `HWND`, bir pencere için bir tanıtıcı olduğu. Bir tanıtıcı bakıma Windows açık windows izlemek için kullandığı bir işaretçi değil. Daha fazla bilgi için bkz: [Windows veri türleri](https://msdn.microsoft.com/library/windows/desktop/aa383751).

1. Bu noktada penceresi oluşturuldu ancak biz yine görünür hale getirmek için Windows bildirmeniz gerekir. Bu kodun yaptığı olmasıdır:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   Henüz uygulamaya olduğundan görüntülenen penceresi kadar içerik yok `WndProc` işlevi. Diğer bir deyişle, uygulama henüz Windows şimdi kendisine gönderdiği iletileri işleyen değil.

1. İletileri işlemek için öncelikle Windows gönderdiği iletilerini dinlemek için bir ileti döngüsü ekleriz. Uygulama bir ileti aldığında, bu döngü için gönderir, `WndProc` işlenecek işlevi. İleti döngüsü aşağıdaki kodu benzer.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   Yapılar ve ileti döngüsü işlevleri hakkında daha fazla bilgi için bkz: [MSG](https://msdn.microsoft.com/library/windows/desktop/ms644958), [GetMessage](https://msdn.microsoft.com/library/windows/desktop/ms644936), [TranslateMessage](https://msdn.microsoft.com/library/windows/desktop/ms644955), ve [DispatchMessage ](https://msdn.microsoft.com/library/windows/desktop/ms644934).

   Bu noktada, `WinMain` işlevi aşağıdaki kodu benzer.

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

### <a name="to-add-functionality-to-the-wndproc-function"></a>WndProc işlevi işlevselliği eklemek için

1. Etkinleştirmek için `WndProc` uygulama aldığı iletileri işlemek, switch deyimi uygulamak için işlev.

   İşlemek için önemli bir ileti [WM_PAINT](https://msdn.microsoft.com/library/windows/desktop/dd145213) ileti. Uygulama görüntülenen onun penceresi parçası güncelleştirilmelidir bu iletiyi alır. Bu olay, bir kullanıcı bir pencere pencerenizi önünde taşır ve ardından yeniden uzağa taşınıp ortaya çıkabilir. Uygulamanız bu gibi olaylar ortaya çıktığında bilmiyor; yalnızca Windows bilir, sizinle bildirir şekilde `WM_PAINT`. Pencere ilk görüntülendiğinde tamamını güncelleştirilmesi gerekir.

   İşlemek için bir `WM_PAINT` iletisi, ilk çağrıda [BeginPaint](https://msdn.microsoft.com/library/windows/desktop/dd183362), metin, düğmelerin ve diğer denetimlerin penceresinde yerleştirme mantığı işlemek ve ardından çağrısı [EndPaint](https://msdn.microsoft.com/library/windows/desktop/dd162598). Bu uygulama için bitiş çağrı başına çağrı arasındaki mantığı "Hello, Windows Masaüstü!" dize görüntülemektir penceresinde. Aşağıdaki kodda dikkat [TextOut](https://msdn.microsoft.com/library/windows/desktop/dd145133) işlevi dizesini görüntülemek için kullanılır.

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

   `HDC`Bu kodda grafik alt sistemi ile iletişim kurmak uygulamanızı etkinleştirmek için Windows kullanan bir veri yapısıdır bir cihaz bağlamı için bir tanıtıcı değil. `BeginPaint` Ve `EndPaint` İşlevler, uygulamanızın iyi vatandaşı gibi davranır ve cihaz bağlamı için gerekenden daha uzun süre kullanmayan emin olun. Bu grafik alt sistemi diğer uygulamalar tarafından kullanılabilir olduğundan emin olun yardımcı olur.

1. Örneğin, genellikle işleme diğer birçok iletileri bir uygulama [WM_CREATE](https://msdn.microsoft.com/library/windows/desktop/ms632619) bir pencere ilk oluşturulduğunda ve [WM_DESTROY](https://msdn.microsoft.com/library/windows/desktop/ms632620) zaman penceresi kapatıldığında. Aşağıdaki kod temel gösterir ancak tamamlamak `WndProc` işlevi.

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

Taahhüt olarak çalışan bir uygulama için tam kod aşağıda verilmiştir.

### <a name="to-build-this-example"></a>Bu örnek oluşturmak için

1. Düzenleyicide HelloWindowsDesktop.cpp içinde girmiş olduğunuz herhangi bir kod silin. Bu örnek kodu kopyalayın ve ardından HelloWindowsDesktop.cpp yapıştırın:

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

1. Üzerinde **yapı** menüsünde seçin **yapı çözümü**. Derleme işleminin sonucunu görüntülenmelidir **çıkış** Visual Studio'daki.

   ![DesktopApp projeyi](../build/media/desktop-app-project-build-150.gif "DesktopApp projeyi derleme")

1. Uygulamayı çalıştırmak için basın **F5**. "Hello, Windows Masaüstü!" metin içeren bir pencere ekranın sol üst köşesindeki görünmesi gerekir.

   ![DesktopApp projeyi](../build/media/desktop-app-project-run-150.gif "DesktopApp projesi çalıştırma")

Tebrikler! Bu kılavuzda tamamlandı ve geleneksel bir Windows masaüstü uygulaması yerleşik.

## <a name="see-also"></a>Ayrıca Bkz.

[Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md)
