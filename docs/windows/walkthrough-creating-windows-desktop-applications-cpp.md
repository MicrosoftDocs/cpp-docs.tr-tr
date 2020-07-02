---
title: 'İzlenecek yol: geleneksel Windows masaüstü uygulaması oluşturma (C++)'
description: Visual Studio, C++ ve Win32 API kullanarak en düşük, geleneksel Windows masaüstü uygulaması oluşturma
ms.custom: get-started-article
ms.date: 05/28/2020
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.openlocfilehash: 1b084cab0e985f9ab8c593e22d972913130e4380
ms.sourcegitcommit: 83ea5df40917885e261089b103d5de3660314104
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85813615"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>İzlenecek yol: geleneksel Windows masaüstü uygulaması oluşturma (C++)

Bu izlenecek yol, Visual Studio 'da geleneksel bir Windows masaüstü uygulaması oluşturmayı gösterir. Oluşturacağınız örnek uygulama, "Merhaba, Windows Desktop!" öğesini göstermek için Windows API 'sini kullanır. bir pencerede. Bu kılavuzda geliştirdiğiniz kodu, diğer Windows Masaüstü uygulamaları oluşturmak için bir model olarak kullanabilirsiniz.

Windows API (Win32 API, Windows Masaüstü API 'SI ve Windows Classic API olarak da bilinir), Windows uygulamaları oluşturmak için C dili tabanlı bir çerçevedir. 1980 ' den bu yana mevcut ve Decades için Windows uygulamaları oluşturmak üzere kullanılmıştır. Windows API 'nin üzerine daha gelişmiş ve daha kolay program çerçeveleri oluşturulmuştur. Örneğin, MFC, ATL, .NET Framework. UWP ve C++/Wınrt 'de yazılan uygulamalar için en modern Windows Çalışma Zamanı Kodu bile, altında Windows API kullanır. Windows API 'SI hakkında daha fazla bilgi için bkz. [WINDOWS API dizini](/windows/win32/apiindex/windows-api-list). Windows uygulamaları oluşturmanın birçok yolu vardır, ancak yukarıdaki işlem ilk ilkiydi.

> [!IMPORTANT]
> Kısaltma açısından, bazı kod deyimleri metinde atlanır. Bu belgenin sonundaki [kod oluştur](#build-the-code) bölümünde kodun tamamı gösterilmektedir.

## <a name="prerequisites"></a>Ön koşullar

- Microsoft Windows 7 veya sonraki sürümlerini çalıştıran bir bilgisayar. En iyi geliştirme deneyimi için Windows 10 ' un kullanılması önerilir.

- Visual Studio 'nun bir kopyası. Visual Studio 'Yu indirme ve yükleme hakkında daha fazla bilgi için bkz. [Visual Studio 'Yu yükleme](/visualstudio/install/install-visual-studio). Yükleyiciyi çalıştırdığınızda, C++ iş yüküyle **masaüstü geliştirme** 'nın işaretli olduğundan emin olun. Visual Studio 'Yu yüklerken bu iş yükünü yüklemediyseniz endişelenmeyin. Yükleyiciyi yeniden çalıştırabilir ve şimdi yükleyebilirsiniz.

   ![C++ ile masaüstü geliştirme](../build/media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

- Visual Studio IDE kullanmanın temellerini anlama. Daha önce Windows Masaüstü uygulamaları kullandıysanız muhtemelen izleyebilirsiniz. Giriş için bkz. [Visual STUDIO IDE Özellik turu](/visualstudio/ide/visual-studio-ide).

- C++ dilinin takip etmek için temel sayısının yeterince anlaşılmasıdır. Endişelenmeyin, çok karmaşık bir şey yapmadık.

## <a name="create-a-windows-desktop-project"></a>Windows Masaüstü projesi oluşturma

İlk Windows Masaüstü projenizi oluşturmak için bu adımları izleyin. Hareket halindeyken, çalışan bir Windows masaüstü uygulaması için kodu girersiniz. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de bir Windows Masaüstü projesi oluşturmak için

1. **File** > **New** > **Yeni proje oluştur** iletişim kutusunu açmak için ana menüden dosya yeni **Proje** ' yi seçin.

1. İletişim kutusunun üst kısmında, **dili** **C++** olarak ayarlayın, **platformu** **Windows**'a ayarlayın ve **proje türünü** **Masaüstü**olarak ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **Windows Masaüstü Sihirbazı** ' nı seçin ve ardından **İleri**' yi seçin. Sonraki sayfada, proje için bir ad girin, örneğin, *Desktopapp*.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

1. **Windows Masaüstü projesi** iletişim kutusu artık görüntülenir. **Uygulama türü**altında **Masaüstü uygulaması (. exe)** seçeneğini belirleyin. **Ek seçenekler**altında **boş proje**' yi seçin. Projeyi oluşturmak için **Tamam ' ı** seçin.

1. **Çözüm Gezgini**, **Desktopapp** projesine sağ tıklayın, **Ekle**' yi ve ardından **Yeni öğe**' yi seçin.

   ![DesktopApp projesine yeni öğe Ekle](../build/media/desktop-app-project-add-new-item-153.gif "DesktopApp projesine yeni öğe Ekle")

1. **Yeni öğe Ekle** iletişim kutusunda, **C++ dosyası (. cpp)** öğesini seçin. **Ad** kutusuna dosya için bir ad yazın, örneğin, *hellowindowsdesktop. cpp*. **Ekle**' yi seçin.

   ![. Cpp dosyasını DesktopApp projesine ekleyin](../build/media/desktop-app-add-cpp-file-153.png ". Cpp dosyasını DesktopApp projesine ekleyin")

Projeniz artık oluşturulur ve kaynak dosyanız düzenleyicide açılır. Devam etmek için, [kodu oluşturma](#create-the-code)bölümüne atlayın.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017"></a>Visual Studio 2017 ' de bir Windows Masaüstü projesi oluşturmak için

1. **Dosya** menüsünde **Yeni** ' yi ve ardından **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunda, sol bölmede, **yüklü**  >  **Visual C++**' i genişletin ve ardından **Windows Masaüstü**' nü seçin. Orta bölmede **Windows Masaüstü Sihirbazı**' nı seçin.

   **Ad** kutusuna proje için bir ad yazın, örneğin, *Desktopapp*. **Tamam ' ı**seçin.

   ![DesktopApp projesini adlandırın](../build/media/desktop-app-new-project-name-153.png "DesktopApp projesini adlandırın")

1. **Windows Masaüstü projesi** iletişim kutusunda, **uygulama türü**altında **Windows uygulaması (. exe)** öğesini seçin. **Ek seçenekler**altında **boş proje**' yi seçin. **Önceden derlenmiş üstbilginin** seçili olmadığından emin olun. Projeyi oluşturmak için **Tamam ' ı** seçin.

1. **Çözüm Gezgini**, **Desktopapp** projesine sağ tıklayın, **Ekle**' yi ve ardından **Yeni öğe**' yi seçin.

   ![DesktopApp projesine yeni öğe Ekle](../build/media/desktop-app-project-add-new-item-153.gif "DesktopApp projesine yeni öğe Ekle")

1. **Yeni öğe Ekle** iletişim kutusunda, **C++ dosyası (. cpp)** öğesini seçin. **Ad** kutusuna dosya için bir ad yazın, örneğin, *hellowindowsdesktop. cpp*. **Ekle**' yi seçin.

   ![. Cpp dosyasını DesktopApp projesine ekleyin](../build/media/desktop-app-add-cpp-file-153.png ". Cpp dosyasını DesktopApp projesine ekleyin")

Projeniz artık oluşturulur ve kaynak dosyanız düzenleyicide açılır. Devam etmek için, [kodu oluşturma](#create-the-code)bölümüne atlayın.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2015"></a>Visual Studio 2015 ' de bir Windows Masaüstü projesi oluşturmak için

1. **Dosya** menüsünde **Yeni** ' yi ve ardından **Proje**' yi seçin.

1. **Yeni proje** iletişim kutusunda, sol bölmede, **yüklü**  >  **Şablonlar**  >  **Visual C++**' ı genişletin ve ardından **Win32**' yi seçin. Orta bölmede **Win32 projesi**' ni seçin.

   **Ad** kutusuna proje için bir ad yazın, örneğin, *Desktopapp*. **Tamam ' ı**seçin.

   ![DesktopApp projesini adlandırın](../build/media/desktop-app-new-project-name-150.png "DesktopApp projesini adlandırın")

1. **Win32 uygulama Sihirbazı**' nın **genel bakış** sayfasında **İleri**' yi seçin.

   ![Win32 uygulama Sihirbazına Genel Bakış 'da DesktopApp oluşturma](../build/media/desktop-app-win32-wizard-overview-150.png "Win32 uygulama Sihirbazına Genel Bakış 'da DesktopApp oluşturma")

1. **Uygulama ayarları** sayfasında, **uygulama türü**altında **Windows uygulaması**' nı seçin. **Ek seçenekler**altında, **önceden derlenmiş üstbilginin**Işaretini kaldırın, sonra **boş proje**' yi seçin. Projeyi oluşturmak için **son** ' a tıklayın.

1. **Çözüm Gezgini**, DesktopApp projesine sağ tıklayın, **Ekle**' yi ve ardından **Yeni öğe**' yi seçin.

   ![DesktopApp projesine yeni öğe Ekle](../build/media/desktop-app-project-add-new-item-150.gif "DesktopApp projesine yeni öğe Ekle")

1. **Yeni öğe Ekle** iletişim kutusunda, **C++ dosyası (. cpp)** öğesini seçin. **Ad** kutusuna dosya için bir ad yazın, örneğin, *hellowindowsdesktop. cpp*. **Ekle**' yi seçin.

   ![. Cpp dosyasını DesktopApp projesine ekleyin](../build/media/desktop-app-add-cpp-file-150.png ". Cpp dosyasını DesktopApp projesine ekleyin")

Projeniz artık oluşturulur ve kaynak dosyanız düzenleyicide açılır.

::: moniker-end

## <a name="create-the-code"></a>Kodu oluşturma

Daha sonra, Visual Studio 'da bir Windows masaüstü uygulaması için kod oluşturmayı öğreneceksiniz.

### <a name="to-start-a-windows-desktop-application"></a>Bir Windows masaüstü uygulamasını başlatmak için

1. Her C uygulamasının ve C++ uygulamasının `main` Başlangıç noktası olarak bir işlevi olması gerektiği gibi, her Windows masaüstü uygulamasında bir işlev olması gerekir `WinMain` . `WinMain`aşağıdaki sözdizimine sahiptir.

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_opt_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   Bu işlevin parametreleri ve dönüş değeri hakkında daha fazla bilgi için bkz. [WinMain giriş noktası](/windows/win32/api/winbase/nf-winbase-winmain).

   > [!NOTE]
   > Ya da veya gibi tüm ek sözcükler nelerdir `CALLBACK` `HINSTANCE` `_In_` ? Geleneksel Windows API 'si, tür ayrıntılarının ve platforma özgü kodun, çağırma kuralları, **__declspec** bildirimleri ve derleyici pragmaları gibi ayrıntıların bazılarını soyutlamak için kapsamlı olarak tür tanımları ve Önişlemci makrolarını kullanır. Visual Studio 'da, bu tür tanımları ve makroların neleri tanımlacağınızı görmek için IntelliSense [hızlı bilgi](/visualstudio/ide/using-intellisense#quick-info) özelliğini kullanabilirsiniz. Farenizi ilgilendiğiniz sözcüğün üzerine getirin veya seçin ve **Ctrl** + **K** **Ctrl** + tanımı içeren küçük bir açılır pencere için CTRL K, CTRL**i** tuşlarına basın. Daha fazla bilgi için bkz. [IntelliSense kullanma](/visualstudio/ide/using-intellisense). Parametreler ve dönüş türleri, programlama hatalarını yakalayabilmeniz için genellikle *sal ek açıklamalarını* kullanır. Daha fazla bilgi için bkz. [C/C++ kod hatalarını azaltmak IÇIN sal ek açıklamalarını kullanma](/cpp/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects).

1. Windows masaüstü programları için &lt; Windows. h> gerekir. &lt;Tchar. h>, `TCHAR` UNICODE sembolü projenizde tanımlandıysa, aksi takdirde **char**olarak çözümlenirse, sonunda **wchar_t** için sonuç olarak çözümlenen makroyu tanımlar.  Her zaman UNICODE 'u etkin olarak oluşturursanız, TCHAR 'a ihtiyacınız yoktur ve yalnızca **wchar_t** doğrudan kullanabilirsiniz.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. İşlevin yanı sıra `WinMain` , her Windows masaüstü uygulaması da bir pencere yordamı işlevine sahip olmalıdır. Bu işlev genellikle adlandırılır `WndProc` , ancak istediğiniz gibi adlandırabilirsiniz. `WndProc`aşağıdaki sözdizimine sahiptir.

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hWnd,
      _In_ UINT   message,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   Bu işlevde, *Olaylar* gerçekleştiğinde uygulamanın Windows 'dan aldığı *iletileri* işlemek için kod yazarsınız. Örneğin, bir Kullanıcı uygulamanızda bir Tamam düğmesi seçerse, Windows size bir ileti gönderir ve `WndProc` işlevinizin içinde herhangi bir işi uygun hale gelen kodu yazabilirsiniz. Bu, bir olayı *işleme* olarak adlandırılır. Yalnızca uygulamanız için uygun olan olayları işleyebilirsiniz.

   Daha fazla bilgi için bkz. [pencere yordamları](/windows/win32/winmsg/window-procedures).

### <a name="to-add-functionality-to-the-winmain-function"></a>WinMain işlevine işlevsellik eklemek için

1. `WinMain`İşlevinde, [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw)türünde bir yapıyı doldurursunuz. Yapı, pencere hakkında bilgiler içerir: uygulama simgesi, pencerenin arka plan rengi, başlık çubuğunda görüntülenecek ad, diğer şeyler. Önemlisi, pencere yordamınıza bir işlev işaretçisi içerir. Aşağıdaki örnekte tipik bir yapı gösterilmektedir `WNDCLASSEX` .

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

   Yukarıdaki yapının alanları hakkında daha fazla bilgi için bkz. [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw).

1. `WNDCLASSEX`Pencerenizi ve ileti gönderme şeklini öğrenmek Için Windows 'a kaydolun. [RegisterClassEx](/windows/win32/api/winuser/nf-winuser-registerclassexw) işlevini kullanın ve pencere sınıfı yapısını bir bağımsız değişken olarak geçirin. `_T`Türü kullandığımız için makro kullanılır `TCHAR` .

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

1. Artık bir pencere oluşturabilirsiniz. [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) işlevini kullanın.

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

   Bu işlev, bir `HWND` pencerenin tanıtıcısı olan bir döndürür. Bir tanıtıcı, Windows 'un açık pencereleri izlemek için kullandığı bir işaretçiye benzer. Daha fazla bilgi için bkz. [Windows veri türleri](/windows/win32/WinProg/windows-data-types).

1. Bu noktada pencere oluşturulmuştur, ancak yine de Windows 'un görünür hale getirmek için söylememiz gerekir. Bu kod şu şekilde yapılır:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   İşlevi henüz uygulamamış olduğunuzdan, görüntülenmiş pencerenin içeriği çok fazla içeriğe sahip değil `WndProc` . Diğer bir deyişle, uygulama henüz Windows 'un buraya gönderdiği iletileri işlememiştir.

1. İletileri işlemek için ilk olarak Windows 'un gönderdiği iletileri dinlemek üzere bir ileti döngüsü ekleyeceğiz. Uygulama bir ileti aldığında, bu döngü onu `WndProc` işlenecek işlevinizde gönderir. İleti döngüsü aşağıdaki koda benzer.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   İleti döngüsündeki yapılar ve işlevler hakkında daha fazla bilgi için bkz. [msg](/windows/win32/api/winuser/ns-winuser-msg), [GetMessage](/windows/win32/api/winuser/nf-winuser-getmessage), [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)ve [DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage).

   Bu noktada, `WinMain` işlev aşağıdaki koda benzemelidir.

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

1. `WndProc`İşlevin, uygulamanın aldığı iletileri işlemesini sağlamak için bir switch ifadesini uygulayın.

   İşlemek için önemli bir ileti [WM_PAINT](/windows/win32/gdi/wm-paint) iletisidir. Uygulama, `WM_PAINT` görüntülenmiş pencerenin bir kısmı güncelleştirilirken iletiyi alır. Olay, bir Kullanıcı pencerenize bir pencere taşıdığı zaman meydana gelebilir ve sonra yeniden gider. Uygulamanız bu olayların ne zaman gerçekleşeceğini bilmez. Yalnızca Windows biliyor, bu nedenle uygulamanıza bir `WM_PAINT` ileti bildirir. Pencere ilk görüntülendiğinde, tümünün güncellenmesi gerekir.

   Bir iletiyi işlemek için `WM_PAINT` önce [BeginPaint](/windows/win32/api/winuser/nf-winuser-beginpaint)'i çağırın, ardından penceredeki metni, düğmeleri ve diğer denetimleri düzenlemek için tüm mantığı Işleyin ve ardından [EndPaint](/windows/win32/api/winuser/nf-winuser-endpaint)'i çağırın. Uygulama için, başlangıç çağrısıyla bitiş çağrısı arasındaki mantık "Merhaba, Windows Desktop!" dizesini görüntüler. penceresinde. Aşağıdaki kodda, [TextOut](/windows/win32/api/wingdi/nf-wingdi-textoutw) işlevi dizeyi göstermek için kullanılır.

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

   `HDC`kodda, pencerenin istemci alanında çizmek için kullanılan bir cihaz bağlamı tanıtıcıdır. `BeginPaint`Ve işlevlerini kullanarak, `EndPaint` istemci alanında çizimi hazırlayın ve doldurun. `BeginPaint`istemci alanında çizim için kullanılan görüntüleme cihazı bağlamına yönelik bir tanıtıcı döndürür; `EndPaint`boyama isteğini sonlandırır ve cihaz bağlamını yayınlar.

1. Bir uygulama genellikle diğer birçok iletiyi işler. Örneğin, bir pencere ilk oluşturulduğunda [WM_CREATE](/windows/win32/winmsg/wm-create) ve pencere kapatıldığında [WM_DESTROY](/windows/win32/winmsg/wm-destroy) . Aşağıdaki kod, temel ancak tamamlanmış bir `WndProc` işlevi gösterir.

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

## <a name="build-the-code"></a>Kodu oluşturma

Taahhüt edilen şekilde, çalışma uygulaması için kodun tamamı aşağıda verilmiştir.

### <a name="to-build-this-example"></a>Bu örneği oluşturmak için

1. Düzenleyicideki *Merhaba Windowsdesktop. cpp* ' de girdiğiniz tüm kodları silin. Bu örnek kodu kopyalayın ve ardından *Merhaba Windowsdesktop. cpp*dosyasına yapıştırın:

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
      _In_opt_ HINSTANCE hPrevInstance,
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

1. **Build** menüsünde **Build Solution**öğesini seçin. Derlemenin sonuçları, Visual Studio 'daki **Çıkış** penceresinde görünmelidir.

   ![DesktopApp projesini oluşturma](../build/media/desktop-app-project-build-150.gif "DesktopApp projesini oluşturma")

1. Uygulamayı çalıştırmak için **F5**'e basın. "Merhaba, Windows Masaüstü!" metnini içeren pencere , ekranın sol üst köşesinde görünmelidir.

   ![DesktopApp projesini çalıştırma](../build/media/desktop-app-project-run-157.PNG "DesktopApp projesini çalıştırma")

Tebrikler! Bu yönergeyi tamamladınız ve geleneksel bir Windows masaüstü uygulaması oluşturdunuz.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Masaüstü uygulamaları](../windows/windows-desktop-applications-cpp.md)
