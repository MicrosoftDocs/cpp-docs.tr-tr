---
title: 'İzim Süresi: Geleneksel bir Windows Masaüstü uygulaması oluşturma (C++)'
description: Visual Studio, C++ve Win32 API'sini kullanarak en az, geleneksel Windows Masaüstü uygulaması nasıl oluşturulur?
ms.custom: get-started-article
ms.date: 11/03/2019
helpviewer_keywords:
- Windows applications [C++], Win32
- Windows Desktop applications [C++]
- Windows API [C++]
ms.openlocfilehash: da74778e79a08dd3ed2b5be0675981425264bdc0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81351846"
---
# <a name="walkthrough-create-a-traditional-windows-desktop-application-c"></a>İzim Süresi: Geleneksel bir Windows Masaüstü uygulaması oluşturma (C++)

Bu walkthrough Visual Studio'da geleneksel bir Windows masaüstü uygulamasının nasıl oluşturulacagIni gösterir. Oluşturacağınız örnek uygulama, "Merhaba, Windows masaüstünü" görüntülemek için Windows API'sını kullanır. bir pencerede. Bu izbeden geliştirdiğiniz kodu, diğer Windows masaüstü uygulamaları oluşturmak için desen olarak kullanabilirsiniz.

Windows API (Win32 API, Windows Desktop API ve Windows Classic API olarak da bilinir) Windows uygulamaları oluşturmak için C dili tabanlı bir çerçevedir. 1980'lerden beri varlığını olmuştur ve yıllardır Windows uygulamaları oluşturmak için kullanılmıştır. Windows API'nın üzerine daha gelişmiş ve programa daha kolay çerçeveler oluşturulmuştür. Örneğin, MFC, ATL, .NET çerçeveleri. C++/WinRT'de yazılmış UWP ve Store uygulamaları için en modern Windows Runtime kodu bile altındaki Windows API'sını kullanır. Windows API hakkında daha fazla bilgi için [Windows API Dizini'ne](/windows/win32/apiindex/windows-api-list)bakın. Windows uygulamaları oluşturmanın birçok yolu vardır, ancak yukarıdaki işlem ilkidir.

> [!IMPORTANT]
> Kısalık adına, metinde bazı kod deyimleri atlanır. Bu [belgenin sonundaki kod](#build-the-code) oluşturma bölümü kodun tamamını gösterir.

## <a name="prerequisites"></a>Ön koşullar

- Microsoft Windows 7 veya sonraki sürümleri çalıştıran bir bilgisayar. En iyi geliştirme deneyimi için Windows 10'u öneririz.

- Visual Studio'nun bir kopyası. Visual Studio'u nasıl indirip yükleyin, [bkz.](/visualstudio/install/install-visual-studio) Yükleyiciyi çalıştırdığınızda, C++ iş yüküne **sahip Masaüstü geliştirmenin** denetlendiğinden emin olun. Visual Studio'yı yüklediğinizde bu iş yükünü yüklemediyseniz endişelenmeyin. Yükleyiciyi yeniden çalıştırıp şimdi yükleyebilirsiniz.

   ![C++ ile masaüstü geliştirme](../build/media/desktop-development-with-cpp.png "C++ ile masaüstü geliştirme")

- Visual Studio IDE kullanmanın temelleri hakkında bir anlayış. Windows masaüstü uygulamalarını daha önce kullandıysanız, büyük olasılıkla ayak uydurabilirsiniz. Giriş için [Visual Studio IDE özellik turuna](/visualstudio/ide/visual-studio-ide)bakın.

- C++ dilinin temellerinin yeterince anlaşılması. Merak etme, çok karmaşık bir şey yapmayız.

## <a name="create-a-windows-desktop-project"></a>Windows masaüstü projesi oluşturma

İlk Windows masaüstü projenizi oluşturmak için aşağıdaki adımları izleyin. Gittiğinizde, çalışan bir Windows masaüstü uygulamasının kodunu girersiniz. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2019"></a>Visual Studio 2019'da bir Windows masaüstü projesi oluşturmak için

1. Ana menüden, **Yeni Proje Oluştur** iletişim kutusunu açmak için **Yeni** > **Proje** **Dosyası'nı** > seçin.

1. İletişim kutusunun üst kısmında, **Dil'i** **C++** olarak ayarlayın, **Platform'u** **Windows'a**ayarlayın ve **Project türünü** **Masaüstüne**ayarlayın.

1. Filtre uygulanmış proje türleri listesinden **Windows Masaüstü Sihirbazı'nı** seçin ve **ardından İleri'yi**seçin. Bir sonraki sayfaya, örneğin *DesktopApp*gibi proje için bir ad girin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

1. **Windows Desktop Project** iletişim kutusu şimdi görüntülenir. **Uygulama türüaltında,** **Masaüstü uygulamasını (.exe)** seçin. **Ek seçenekler**altında, **Boş proje'yi**seçin. Projeyi oluşturmak için **Tamam'ı** seçin.

1. **Solution Explorer'da** **DesktopApp** projesine sağ tıklayın, **Ekle'yi**seçin ve ardından **Yeni Öğe'yi**seçin.

   ![DesktopApp Projesi'ne yeni öğe ekleme](../build/media/desktop-app-project-add-new-item-153.gif "DesktopApp Projesi'ne yeni öğe ekleme")

1. Yeni **Öğe Ekle** iletişim kutusunda **C++ Dosyası (.cpp)** seçeneğini belirleyin. **Ad** kutusuna, örneğin *HelloWindowsDesktop.cpp*gibi dosya için bir ad yazın. **Ekle'yi**seçin.

   ![DesktopApp Project'e .cpp dosyası ekle](../build/media/desktop-app-add-cpp-file-153.png "DesktopApp Project'e .cpp dosyası ekle")

Projeniz şimdi oluşturuldu ve kaynak dosyanız düzenleyicide açıldı. Devam etmek [için, kodu oluşturmak](#create-the-code)için ileri atlayın.

::: moniker-end

::: moniker range="vs-2017"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2017"></a>Visual Studio 2017'de bir Windows masaüstü projesi oluşturmak için

1. **Dosya** menüsünde **Yeni'yi** seçin ve ardından **Project'i**seçin.

1. Yeni **Proje** iletişim kutusunda, sol bölmede, **Yüklü** > **Visual C++** genişletin, ardından **Windows Desktop'ı**seçin. Orta bölmede Windows **Masaüstü Sihirbazı'nı**seçin.

   **Ad** kutusuna, örneğin *DesktopApp*gibi proje için bir ad yazın. **Tamam'ı**seçin.

   ![DesktopApp projesini adlandırın](../build/media/desktop-app-new-project-name-153.png "DesktopApp projesini adlandırın")

1. Windows **Desktop Project** iletişim kutusunda, **Uygulama türü**altında Windows **uygulamasını (.exe)** seçin. **Ek seçenekler**altında, **Boş proje'yi**seçin. Önceden **Derlenmiş Üstbilginin** seçilmediğinden emin olun. Projeyi oluşturmak için **Tamam'ı** seçin.

1. **Solution Explorer'da** **DesktopApp** projesine sağ tıklayın, **Ekle'yi**seçin ve ardından **Yeni Öğe'yi**seçin.

   ![DesktopApp Projesi'ne yeni öğe ekleme](../build/media/desktop-app-project-add-new-item-153.gif "DesktopApp Projesi'ne yeni öğe ekleme")

1. Yeni **Öğe Ekle** iletişim kutusunda **C++ Dosyası (.cpp)** seçeneğini belirleyin. **Ad** kutusuna, örneğin *HelloWindowsDesktop.cpp*gibi dosya için bir ad yazın. **Ekle'yi**seçin.

   ![DesktopApp Project'e .cpp dosyası ekle](../build/media/desktop-app-add-cpp-file-153.png "DesktopApp Project'e .cpp dosyası ekle")

Projeniz şimdi oluşturuldu ve kaynak dosyanız düzenleyicide açıldı. Devam etmek [için, kodu oluşturmak](#create-the-code)için ileri atlayın.

::: moniker-end

::: moniker range="vs-2015"

### <a name="to-create-a-windows-desktop-project-in-visual-studio-2015"></a>Visual Studio 2015'te bir Windows masaüstü projesi oluşturmak için

1. **Dosya** menüsünde **Yeni'yi** seçin ve ardından **Project'i**seçin.

1. Yeni **Proje** iletişim kutusunda, sol bölmede, **Yüklü** > **Şablonlar** > **Görsel C++** genişletmek ve sonra **Win32**seçin. Orta bölmede **Win32 Projesi'ni**seçin.

   **Ad** kutusuna, örneğin *DesktopApp*gibi proje için bir ad yazın. **Tamam'ı**seçin.

   ![DesktopApp projesini adlandırın](../build/media/desktop-app-new-project-name-150.png "DesktopApp projesini adlandırın")

1. **Win32 Uygulama Sihirbazı'nın** **Genel Bakış** sayfasında **İleri'yi**seçin.

   ![Win32 Uygulama Sihirbazına Genel Bakış'ta DesktopApp Oluşturun](../build/media/desktop-app-win32-wizard-overview-150.png "Win32 Uygulama Sihirbazına Genel Bakış'ta DesktopApp Oluşturun")

1. Uygulama **Ayarları** sayfasında, **Uygulama türü** **altında, Windows uygulamasını**seçin. **Ek seçenekler**altında, **Önceden Derlenmiş üstbilginin**işaretlerini kaldırın, ardından **Boş projeyi**seçin. Projeyi oluşturmak için **Finish'i** seçin.

1. **Solution Explorer'da**DesktopApp projesine sağ tıklayın, **Ekle'yi**seçin ve ardından **Yeni Öğe'yi**seçin.

   ![DesktopApp Projesi'ne yeni öğe ekleme](../build/media/desktop-app-project-add-new-item-150.gif "DesktopApp Projesi'ne yeni öğe ekleme")

1. Yeni **Öğe Ekle** iletişim kutusunda **C++ Dosyası (.cpp)** seçeneğini belirleyin. **Ad** kutusuna, örneğin *HelloWindowsDesktop.cpp*gibi dosya için bir ad yazın. **Ekle'yi**seçin.

   ![DesktopApp Project'e .cpp dosyası ekle](../build/media/desktop-app-add-cpp-file-150.png "DesktopApp Project'e .cpp dosyası ekle")

Projeniz şimdi oluşturuldu ve kaynak dosyanız düzenleyicide açıldı.

::: moniker-end

## <a name="create-the-code"></a>Kodu oluşturma

Ardından, Visual Studio'da bir Windows masaüstü uygulamasının kodunu nasıl oluşturacağınız öğrenilir.

### <a name="to-start-a-windows-desktop-application"></a>Windows masaüstü uygulamasını başlatmak için

1. Her C uygulaması ve C++ uygulamasının başlangıç noktası olarak bir `main` işlevi olması `WinMain` gerektiği gibi, her Windows masaüstü uygulamasının da bir işlevi olmalıdır. `WinMain`aşağıdaki sözdizimine sahiptir.

   ```cpp
   int CALLBACK WinMain(
      _In_ HINSTANCE hInstance,
      _In_opt_ HINSTANCE hPrevInstance,
      _In_ LPSTR     lpCmdLine,
      _In_ int       nCmdShow
   );
   ```

   Bu işlevin parametreleri ve geri dönüş değeri hakkında bilgi için [WinMain giriş noktasına](/windows/win32/api/winbase/nf-winbase-winmain)bakın.

   > [!NOTE]
   > Tüm bu ekstra kelimeler `CALLBACK` `HINSTANCE` `_In_`nedir? Geleneksel Windows API' stypedefs ve önişlemci makroları, çağrı kuralları, **__declspec** bildirimleri ve derleyici pragmas gibi tür ve platforma özgü kodun bazı ayrıntılarını özetlemek için kapsamlı olarak kullanır. Visual Studio'da, bu typedef'lerin ve makroların tanımladığını görmek için IntelliSense [Hızlı Bilgi](/visualstudio/ide/using-intellisense#quick-info) özelliğini kullanabilirsiniz. Farenizi ilgi alanı sözcüğünün üzerine tökezleveya seçin ve tanımı nı içeren küçük bir açılır pencere için **Ctrl**+**K**, **Ctrl**+**I** tuşuna basın. Daha fazla bilgi için [IntelliSense'i kullanma bilgisine](/visualstudio/ide/using-intellisense)bakın. Parametreler ve iade türleri genellikle programlama hatalarını yakalamanıza yardımcı olmak için *SAL Ek Açıklamalarını* kullanır. Daha fazla bilgi için [C/C++ Kod Hatalarını Azaltmak için SAL Ek Açıklamalarını Kullanma'ya](/cpp/code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects)bakın.

1. Windows masaüstü &lt;programları windows.h> gerektirir. &lt;tchar.h `TCHAR`>, projenizde UNICODE simgesi tanımlanmışsa, **sonuçta wchar_t** olarak çözen makroyu tanımlar, aksi takdirde **char**olarak çözülür.  HER ZAMAN UNICODE etkin bir şekilde inşa ederseniz, TCHAR'a ihtiyacınız yoktur ve **wchar_t** doğrudan kullanabilirsiniz.

   ```cpp
   #include <windows.h>
   #include <tchar.h>
   ```

1. `WinMain` İşlevle birlikte, her Windows masaüstü uygulamasının da bir pencere yordamı işlevi olmalıdır. Bu işlev genellikle `WndProc`adlandırılır, ancak istediğiniz adı alabilirsiniz. `WndProc`aşağıdaki sözdizimine sahiptir.

   ```cpp
   LRESULT CALLBACK WndProc(
      _In_ HWND   hWnd,
      _In_ UINT   message,
      _In_ WPARAM wParam,
      _In_ LPARAM lParam
   );
   ```

   Bu işlevde, *olaylar* oluştuğunda uygulamanın Windows'tan aldığı *iletileri* işlemek için kod yazarsınız. Örneğin, bir kullanıcı uygulamanızda tamam düğmesi seçerse, Windows size bir ileti gönderir `WndProc` ve işlevinizin içine uygun olan her işi yapan kod yazabilirsiniz. Buna bir olayı *ele alma* denir. Yalnızca uygulamanızla ilgili olayları ele alabilirsiniz.

   Daha fazla bilgi için [Bkz. Pencere Yordamları.](/windows/win32/winmsg/window-procedures)

### <a name="to-add-functionality-to-the-winmain-function"></a>WinMain işlevine işlevsellik eklemek için

1. İşlevolarak, `WinMain` [WNDCLASSEX](/windows/win32/api/winuser/ns-winuser-wndclassexw)türünden bir yapıyı dolduruyorsunuz. Yapı, pencere hakkında bilgi içerir: uygulama simgesi, pencerenin arka plan rengi, başlık çubuğunda görüntülenecek ad, diğer şeylerin yanı sıra. Daha da önemlisi, pencere yordamınız için bir işlev işaretçisi içerir. Aşağıdaki örnek, tipik `WNDCLASSEX` bir yapıyı gösterir.

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

   Yukarıdaki yapının alanları hakkında bilgi için [WNDCLASSEX'e](/windows/win32/api/winuser/ns-winuser-wndclassexw)bakın.

1. Pencerenizi `WNDCLASSEX` ve pencerenize nasıl ileti göndereceğinizi bilmesi için Windows'a kaydolun. [RegisterClassEx](/windows/win32/api/winuser/nf-winuser-registerclassexw) işlevini kullanın ve pencere sınıfı yapısını bağımsız değişken olarak geçirin. `TCHAR` Yazıyı `_T` kullandığımız için makro kullanılır.

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

1. Şimdi bir pencere oluşturabilirsiniz. [CreateWindow](/windows/win32/api/winuser/nf-winuser-createwindoww) işlevini kullanın.

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

   Bu işlev, `HWND`bir pencereye tutamaç olan bir , döndürür. Tutamacı, Windows'un açık pencereleri izlemek için kullandığı işaretçiye benzer. Daha fazla bilgi için [Windows Veri Türleri'ne](/windows/win32/WinProg/windows-data-types)bakın.

1. Bu noktada, pencere oluşturuldu, ancak yine de görünür hale getirmek için Windows'a söylememiz gerekir. Bu kod bunu yapar:

   ```cpp
   // The parameters to ShowWindow explained:
   // hWnd: the value returned from CreateWindow
   // nCmdShow: the fourth parameter from WinMain
   ShowWindow(hWnd,
      nCmdShow);
   UpdateWindow(hWnd);
   ```

   `WndProc` İşlevi henüz uygulamadığınız için görüntülenen pencerede fazla içerik yok. Başka bir deyişle, uygulama henüz Windows'un şu anda ona gönderdiği iletileri işleme değil.

1. İletileri işlemek için önce Windows'un gönderdiği iletileri dinlemek için bir ileti döngüsü ekleriz. Uygulama bir ileti aldığında, bu döngü onu `WndProc` işlenecek işlevinize gönderir. İleti döngüsü aşağıdaki kodu andırır.

   ```cpp
   MSG msg;
   while (GetMessage(&msg, NULL, 0, 0))
   {
      TranslateMessage(&msg);
      DispatchMessage(&msg);
   }

   return (int) msg.wParam;
   ```

   İleti döngüsündeki yapılar ve işlevler hakkında daha fazla bilgi için [MSG](/windows/win32/api/winuser/ns-winuser-msg), [GetMessage](/windows/win32/api/winuser/nf-winuser-getmessage), [TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)ve [DispatchMessage'a](/windows/win32/api/winuser/nf-winuser-dispatchmessage)bakın.

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

1. İşlevin `WndProc` uygulamanın aldığı iletileri işlemesini etkinleştirmek için bir geçiş deyimi uygulayın.

   İşletilen önemli bir ileti [WM_PAINT](/windows/win32/gdi/wm-paint) iletidir. Görüntülenen penceresinin `WM_PAINT` bir parçasının güncellenmesi gerektiğinde uygulama iletiyi alır. Olay, bir kullanıcı pencerenizin önündeki pencereyi hareket ettirdiğinde ve sonra yeniden uzaklaştırdığında oluşabilir. Başvurunuz bu olayların ne zaman meydana geldiğini bilmiyor. Yalnızca Windows bilir, bu nedenle uygulamanızı `WM_PAINT` bir mesajla birlikte not alabiliyor. Pencere ilk görüntülendiğinde, tümünün güncelleştirilmelidir.

   İletiyi `WM_PAINT` işlemek için önce [BeginPaint'i](/windows/win32/api/winuser/nf-winuser-beginpaint)arayın, ardından penceredeki metni, düğmeleri ve diğer denetimleri düzenlemek için tüm mantığı işleyin ve ardından [EndPaint'i](/windows/win32/api/winuser/nf-winuser-endpaint)arayın. Uygulama için, başlangıç çağrısı ile bitiş çağrısı arasındaki mantık "Merhaba, Windows masaüstü" dizesini görüntülemektir. Pencerede. Aşağıdaki kodda, String'i görüntülemek için [TextOut](/windows/win32/api/wingdi/nf-wingdi-textoutw) işlevinin kullanıldığına dikkat edin.

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

   `HDC`kodda, Windows'un uygulamanızın grafik alt sistemiyle iletişim kurmasını sağlamak için kullandığı bir veri yapısı olan aygıt bağlamına açılan bir tanıtıcı dır. Ve `BeginPaint` `EndPaint` işlevler, uygulamanızın iyi bir vatandaş gibi görünmesini sağlar ve cihaz bağlamını gerekenden daha uzun süre kullanmaz. Fonksiyonlar grafik alt sisteminin diğer uygulamalar tarafından kullanılabilmelerine yardımcı olur.

1. Bir uygulama genellikle diğer birçok iletileri işler. Örneğin, bir pencere ilk oluşturulduğunda [WM_CREATE](/windows/win32/winmsg/wm-create) ve pencere kapatıldığında [WM_DESTROY.](/windows/win32/winmsg/wm-destroy) Aşağıdaki kod temel ama `WndProc` tam bir işlev gösterir.

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

Söz verdiğim gibi, burada çalışma uygulaması için tam kodu.

### <a name="to-build-this-example"></a>Bu örneği oluşturmak için

1. *MerhabaWindowsDesktop.cpp'de* girdiğiniz tüm kodları düzenleyicide silin. Bu örnek kodu kopyalayın ve sonra *HelloWindowsDesktop.cpp*içine yapıştırın:

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

1. **Yapı** menüsünde **Çözüm Oluştur'u**seçin. Derlemenin sonuçları Visual Studio'daki **Çıktı** penceresinde görünmelidir.

   ![DesktopApp Projesini Oluşturun](../build/media/desktop-app-project-build-150.gif "DesktopApp Projesini Oluşturun")

1. Uygulamayı çalıştırmak için **F5**tuşuna basın. "Merhaba, Windows masaüstü!" metnini içeren bir pencere ekranın sol üst köşesinde görünmelidir.

   ![DesktopApp Projesini Yürütün](../build/media/desktop-app-project-run-157.PNG "DesktopApp Projesini Yürütün")

Tebrikler! Bu gözden geçirmeyi tamamladınız ve geleneksel bir Windows masaüstü uygulaması oluşturabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Windows Masaüstü Uygulamaları](../windows/windows-desktop-applications-cpp.md)
