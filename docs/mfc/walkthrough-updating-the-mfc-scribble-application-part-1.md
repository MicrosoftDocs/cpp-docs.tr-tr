---
title: 'İzlenecek yol: (Kısım 1) MFC karalama uygulamasını güncelleştirme'
ms.date: 09/20/2018
helpviewer_keywords:
- examples [MFC], update existing application
- ribbon UI, porting to
- Office Fluent UI, porting to
- samples [MFC], update existing application
- MFC Feature Pack, update existing application
- walkthroughs [MFC], update existing application
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
ms.openlocfilehash: 213bc8087b58eac232cc8fcfccc88e13785a807e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358300"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>İzlenecek yol: (Kısım 1) MFC karalama uygulamasını güncelleştirme

Bu yönerge Şerit kullanıcı arabirimini kullanarak varolan bir MFC uygulamasına değişiklik yapma gösterir. Visual Studio, hem Office 2007 Şerit hem de Windows 7, manzara Şerit destekler. Şerit kullanıcı arabirimini hakkında daha fazla bilgi için bkz: [şeritler](/windows/desktop/uxguide/cmd-ribbons).

Bu kılavuz satırı çizimler için fare kullanmanıza olanak sağlayan Klasik 1.0 MFC karalama örneği değiştirir. Kılavuzun bu bölümü, böylece bir Şerit çubuğuna görüntüler genişletilen Scribble örneğinin değiştirme işlemi gösterilmektedir. [2. bölüm](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) diğer düğmeleri Şerit çubuğuna ekler.

## <a name="prerequisites"></a>Önkoşullar

[1.0 MFC karalama örnek](http://download.microsoft.com/download/4/0/9/40946FEC-EE5C-48C2-8750-B0F8DA1C99A8/MFC/general/Scribble.zip.exe). Visual Studio 2017'ye dönüştürme hakkında daha fazla yardım için bkz: [Taşıma Kılavuzu: MFC Scribble](../porting/porting-guide-mfc-scribble.md).

##  <a name="top"></a> Bölümleri

Kılavuzun bu bölümü aşağıdaki bölümleri içerir:

- [Temel sınıflar değiştirme](#replaceclass)

- [Bit eşlemler projeye ekleniyor](#addbitmap)

- [Projeye bir Şerit kaynağı ekleme](#addribbon)

- [Bir Şerit çubuğuna örneğini oluşturma](#createinstance)

- [Bir Şerit kategorisi ekleme](#addcategory)

- [Uygulama görünümünü ayarlama](#setlook)

##  <a name="replaceclass"></a> Temel sınıflar değiştirme

Bir Şerit destekleyen bir uygulama için bir menü destekleyen bir uygulamaya dönüştürmek için uygulama, çerçeve ve araç sınıfları güncelleştirilmiş temel sınıfların türetilmesi gerekir. (Özgün genişletilen Scribble örneğinin değiştirmemeniniz öneririz. Bunun yerine, karalama projeyi temizleyin, başka bir dizine kopyalayın ve kopyayı değiştirin.)

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Karalama uygulamasını taban sınıflardaki değiştirmek için

1. Scribble.cpp içinde doğrulayın `CScribbleApp::InitInstance` bir çağrı içerdiğine [Afxoleınit](../mfc/reference/ole-initialization.md#afxoleinit).

1. Stdafx.h dosyaya aşağıdaki kodu ekleyin.

    ```cpp
    #include <afxcontrolbars.h>
    ```

1. Scribble.h içinde tanımını değiştirme `CScribbleApp` böylece, türetilmiş sınıf [CWinAppEx sınıfı](../mfc/reference/cwinappex-class.md).

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

1. Windows uygulamaları, kullanıcı tercihi verileri kaydetmek için bir başlatma (.ini) dosyası kullanıldığında karalama 1.0 yazılmıştır. Karalama kullanıcı tercihlerini kayıt defterine depolamak için bir başlatma dosyası yerine değiştirin. Temel ve kayıt defteri anahtarını ayarlamak için aşağıdaki kodu yazın `CScribbleApp::InitInstance` sonra `LoadStdProfileSettings()` deyimi.

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

1. Birden çok belge arabirimi (MDI) uygulaması için ana çerçeve artık türetilir `CMDIFrameWnd` sınıfı. Bunun yerine, öğesinden türetilir [Cmdıframewndex](../mfc/reference/cmdiframewndex-class.md) sınıfı.

    Tüm başvuruları mainfrm.h ve mainfrm.cpp dosyaları değiştirin `CMDIFrameWnd` ile `CMDIFrameWndEx`.

1. Childfrm.h ve childfrm.cpp dosyalarda Değiştir `CMDIChildWnd` ile `CMDIChildWndEx`.

    İçinde childfrm. h dosya değiştirin `CSplitterWnd` ile `CSplitterWndEx`.

1. Araç çubuklarını ve durum çubukları yeni MFC sınıflarını kullanmak için değiştirin.

    Mainfrm.h dosyasında:

    1. `CToolBar` yerine `CMFCToolBar` yazın.

    1. `CStatusBar` yerine `CMFCStatusBar` yazın.

1. Mainfrm.cpp dosyasında:

    1. Değiştirin `m_wndToolBar.SetBarStyle` ile `m_wndToolBar.SetPaneStyle`

    1. Değiştirin `m_wndToolBar.GetBarStyle` ile `m_wndToolBar.GetPaneStyle`

    1. Değiştirin `DockControlBar(&m_wndToolBar)` ile `DockPane(&m_wndToolBar)`

1. İpframe.cpp dosyasında kod aşağıdaki üç satırları açıklama satırı yapar.

    ```cpp
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->DockPane(&m_wndToolBar);
    ```

1. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın.

##  <a name="addbitmap"></a> Bit eşlemler projeye ekleniyor

Bu kılavuzun sonraki dört adımları, bit eşlem kaynakları gerektirir. Çeşitli şekillerde uygun bit eşlemler alabilirsiniz:

- Kullanım [kaynak düzenleyicileri](../windows/resource-editors.md) kendi bit eşlemler imkan. Veya Visual Studio ile birlikte gelir ve indirilebileceğini Taşınabilir Ağ Grafikleri (.png) görüntülerinden bit eşlemler derlemek için kaynak düzenleyicileri kullanma [Visual Studio görüntü kitaplığı](https://docs.microsoft.com/visualstudio/designers/the-visual-studio-image-library).

    Ancak, **Şerit** kullanıcı arabirimi, belirli bir bit eşlemler'ın saydam görüntüler desteklemesini gerektirir. Saydam bit eşlemler kullanın. burada 24 bit rengin kırmızı, yeşil ve mavi bileşenlerinin belirtin ve 8 bit tanımlamak 32-bit piksel bir *alfa kanalı* rengini, saydamlığını belirtir. Geçerli kaynak düzenleyicileri görüntüleyebilir, ancak bit eşlemler 32-bit piksel ile değiştiremez. Sonuç olarak, dış görüntü düzenleyici saydam bit eşlemler işlemek için yerine kaynak düzenleyicileri kullanın.

- Projeniz başka bir uygulamadan bir uygun kaynak dosyasını buraya kopyalayın ve ardından bit eşlemler bu dosyadan içeri aktarın.

Bu izlenecek yolda oluşturulan örnek kaynak dosyalarını kopyalar [izlenecek yol: MFC kullanarak Şerit uygulaması oluşturma](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md).

### <a name="to-add-bitmaps-to-the-project"></a>Bit eşlemler projeye eklemek için

1. Kaynakları dizininden aşağıdaki .bmp dosyaları kopyalamak için dosya Gezgini'ni kullanın (`res`) Şerit Örneğin kaynak dizinine (`res`) karalama proje:

   1. Main.bmp karalama projenize kopyalayın.

   1. Filesmall.bmp ve filelarge.bmp karalama projenize kopyalayın.

   1. Filelarge.bmp ve filesmall.bmp dosyalarının yeni kopyalarını ancak Şerit örnekte kopya kaydedin. Kopya homesmall.bmp ve homelarge.bmp yeniden adlandırın ve ardından kopya karalama projenize taşıyabilirsiniz.

   1. Toolbar.bmp dosyanın bir kopyasını, ancak Şerit örnekte kopyasını kaydedin. Kopyalama panelicons.bmp yeniden adlandırın ve ardından kopya karalama projenize taşıyabilirsiniz.

1. Bir MFC uygulaması için bit eşlem olarak içeri aktarın. İçinde **kaynak görünümü**, çift **scribble.rc** düğümünü çift tıklayın **bit eşlem** düğümünü ve ardından **kaynak ekleme**. Görüntülenen iletişim kutusuna tıklayın **alma**. Gözat `res` dizin main.bmp dosyasını seçin ve ardından **açık**.

   Main.bmp bit eşlem 26 x 26 görüntü içerir. Bit eşleme Kimliğini değiştirme `IDB_RIBBON_MAIN`.

1. Bit eşlemler bağlı Dosya menüsü için içeri aktarma **uygulama** düğmesi.

   1. On 16 x 16 (16 x 176) içeren filesmall.bmp dosyasını içeri aktarma görüntüler. Bit eşleme Kimliğini değiştirme `IDB_RIBBON_FILESMALL`.

   > [!NOTE]
   > Biz yalnızca ilk sekiz 16 x 16 görüntü (16 x 128) gerektiğinden, isteğe bağlı olarak bu 176 bit eşlem 128 için sağ taraftaki genişliğini kırpma.

   1. Dokuz 32 x 32 (32 x 288) içeren filelarge.bmp alma görüntüler. Bit eşleme Kimliğini değiştirme `IDB_RIBBON_FILELARGE`.

1. Bit eşlemler Şerit kategori ve panel için içeri aktarın. Her sekme Şerit çubuğundaki bir kategori ve bir metin etiketi ve isteğe bağlı görüntü oluşur.

   1. On 16 x 16 görüntüler için küçük bir düğme bit eşlemler içeren homesmall.bmp bit eşlem olarak içeri aktarın. Bit eşleme Kimliğini değiştirme `IDB_RIBBON_HOMESMALL`.

   1. Dokuz 32 x 32 görüntüleri için büyük düğme bit eşlemler içeren homelarge.bmp bit eşlem olarak içeri aktarın. Bit eşleme Kimliğini değiştirme `IDB_RIBBON_HOMELARGE`.

1. Bit eşlemleri yeniden boyutlandırılan Şerit paneli için içeri aktarın. Şerit paneli tamamını görüntülemek için çok küçük olduğunda bu bit eşlemler veya paneli simgeler, sonra yeniden boyutlandırma işlemi kullanılır.

   1. Sekiz 16 x 16 görüntü içeren panelicons.bmp bit eşlem olarak içeri aktarın. İçinde **özellikleri** pencerenin **bit eşlem Düzenleyicisi**, (16 x 64) 64 bit eşlem genişliğini ayarla. Bit eşleme Kimliğini değiştirme `IDB_PANEL_ICONS`.

   > [!NOTE]
   > Biz yalnızca ilk dört 16 x 16 görüntü (16 x 64) gerektiğinden, isteğe bağlı olarak bu 128 bit eşlem 64 sağ taraftaki genişliğini kırpma.

##  <a name="addribbon"></a> Projeye bir Şerit kaynağı ekleme

Menülere Şerit kullanan bir uygulamayı kullanan bir uygulamayı dönüştürdüğünüzde, kaldırın veya var olan menüleri devre dışı gerekmez. Yalnızca bir Şerit kaynağı oluşturabilir, Şerit düğmeleri ekleyin ve ardından yeni düğmeler var olan menü öğeleriyle ilişkilendirmek. Menüler artık görünür olmasına rağmen Şerit çubuğunda iletiler Menüler yoluyla yönlendirilir ve menüsü kısayolları çalışmaya devam eder.

Bir Şerit oluşan **uygulama** düğmesi, Şeridin sol tarafındaki büyük düğme olan ve bir veya daha fazla kategori sekmeler. Her kategori sekme Şerit düğmeleri ve denetimler için kapsayıcı olarak davranan bir veya daha fazla panel içerir. Aşağıdaki yordamda, bir Şerit kaynağı oluşturabilir ve ardından özelleştirmek gösterilmiştir **uygulama** düğmesi.

### <a name="to-add-a-ribbon-resource-to-the-project"></a>Projeye bir Şerit kaynağı eklemek için

1. Seçili karalama proje **Çözüm Gezgini**, **proje** menüsünde tıklatın **kaynak Ekle**.

1. İçinde **kaynak Ekle** iletişim kutusunda **Şerit** ve ardından **yeni**.

   Visual Studio, bir Şerit kaynağı oluşturur ve Tasarım görünümünde açılır. Şerit kaynak kimliği `IDR_RIBBON1`, içinde görüntülenen **kaynak görünümü**. Şerit, bir kategori ve tek bir panel içerir.

1. Özelleştirebileceğiniz **uygulama** özelliklerini değiştirerek düğmesi. Bu kodda kullanılan iletisi kimlikleri, menüde karalama 1.0 için önceden tanımlanmıştır.

1. Tasarım görünümünde tıklayın **uygulama** özelliklerini görüntülemek için düğme. Özellik değerleri aşağıdaki gibi değiştirin: **Görüntü** için `IDB_RIBBON_MAIN`, **istemi** için `File`, **anahtarları** için `f`, **büyük resimler** için `IDB_RIBBON_FILELARGE`ve **Küçük resimler** için `IDB_RIBBON_FILESMALL`.

1. Kullanıcı tıkladığında açılan menüden aşağıdaki değişiklikleri oluşturma **uygulama** düğmesi. Üç nokta simgesine tıklayın (**...** ) yanındaki **ana öğeler** açmak için **öğe düzenleyici**.

   1. İle **öğesi** türü **düğmesi** seçili tıklayın **Ekle** bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `&New`, **kimliği** için `ID_FILE_NEW`, **görüntü** için `0`, **büyük görüntü** için`0`.

   1. Tıklayın **Ekle** bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `&Save`, **kimliği** için `ID_FILE_SAVE`, **görüntü** için `2`, ve **büyük görüntü** için`2`.

   1. Tıklayın **Ekle** bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `Save &As`, **kimliği** için `ID_FILE_SAVE_AS`, **görüntü** için `3`, ve **büyük görüntü** için`3`.

   1. Tıklayın **Ekle** bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `&Print`, **kimliği** için `ID_FILE_PRINT`, **görüntü** için `4`, ve **büyük görüntü** için`4`.

   1. Değişiklik **öğesi** için yazın **ayırıcı** ve ardından **Ekle**.

   1. Değişiklik **öğesi** için yazın **düğmesi**. Tıklayın **Ekle** beşinci bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `&Close`, **kimliği** için `ID_FILE_CLOSE`, **görüntü** için `5`, ve **büyük görüntü** için`5`.

1. Aşağıdaki değişiklikler altında bir alt menü oluşturma **yazdırma** , önceki adımda oluşturduğunuz düğmesi.

   1. Tıklayın **yazdırma** düğmesi, değişiklik **öğesi** için yazın **etiket**ve ardından **Ekle**. Değişiklik **açıklamalı alt yazı** için `Preview and print the document`.

   1. Tıklayın **yazdırma** düğmesi, değişiklik **öğesi** için yazın **düğmesi**, tıklatıp **Ekle**. Değişiklik **açıklamalı alt yazı** için `&Print`, **kimliği** için `ID_FILE_PRINT`, **görüntü** için `4`, ve **büyük görüntü** için`4`.

   1. Tıklayın **yazdırma** düğmesine ve ardından **Ekle** bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `&Quick Print`, **kimliği** için `ID_FILE_PRINT_DIRECT`, **görüntü** için `7`, ve **büyük görüntü** için`7`.

   1. Tıklayın **yazdırma** düğmesine ve ardından **Ekle** başka bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `Print Pre&view`, **kimliği** için `ID_FILE_PRINT_PREVIEW`, **görüntü** için `6`, ve **büyük görüntü** için`6`.

   1. Artık değiştirilmiş **ana öğeler**. Tıklayın **Kapat** çıkmak için **öğe düzenleyici**.

1. Aşağıdaki değişiklik alt kısmında görüntülenen bir çıkış düğmesi oluşturur **uygulama** düğmesi menüsü.

   1. İçinde **özellikleri** penceresinde üç noktaya tıklayın (**...** ) yanındaki **düğmesi** açmak için **öğe düzenleyici**.

   1. İle **öğesi** türü **düğmesi** seçili tıklayın **Ekle** bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `E&xit`, **kimliği** için `ID_APP_EXIT`, **görüntü** için `8`.

   1. Değiştirdiğiniz **düğmeleri**. Tıklayın **Kapat** çıkmak için **öğe düzenleyici**.

##  <a name="createinstance"></a> Bir Şerit çubuğuna örneğini oluşturma

Aşağıdaki adımları, uygulamanız başlatıldığında bir Şerit çubuğuna örneğini oluşturma işlemi gösterilmektedir. Bir Şerit çubuğuna bir uygulamaya eklemek için Şerit çubuğuna mainfrm.h dosyasındaki bildirin. Ardından, mainfrm.cpp dosyasında Şerit kaynağı yükleme için kod yazın.

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>Bir Şerit çubuğuna örneğini oluşturmak için

1. Mainfrm.h dosyanın korumalı bölümüne veri üyesi ekleyin `CMainFrame`, ana çerçeve için sınıf tanımının. Şerit çubuğunu üyesidir.

    ```cpp
    // Ribbon bar for the application
    CMFCRibbonBar m_wndRibbonBar;
    ```

2. Mainfrm.cpp dosyanın en son önce aşağıdaki kodu ekleyin `return` deyimi, sonunda `CMainFrame::OnCreate` işlevi. Şerit çubuğuna bir örneğini oluşturur.

    ```cpp
    // Create the ribbon bar
    if (!m_wndRibbonBar.Create(this))
    {
        return -1;   //Failed to create ribbon bar
    }
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
    ```

##  <a name="addcategory"></a> Şerit kaynağını özelleştirme

Oluşturduğunuz göre **uygulama** düğmesi, Şerit öğeleri ekleyebilirsiniz.

> [!NOTE]
> Bu izlenecek yol aynı Paneli simgesi tüm bölmeleri için kullanır. Ancak, diğer görüntü listesi dizinleri diğer simgeleri göstermek için kullanabilirsiniz.

### <a name="to-add-a-home-category-and-edit-panel"></a>Giriş Kategori ekleme ve panel düzenlemek için

1. Karalama programın yalnızca bir kategori gerektirir. Tasarım görünümünde, **araç kutusu**, çift **kategori** ekleyin ve özelliklerini görüntülemek için. Özellik değerleri aşağıdaki gibi değiştirin: **Açıklamalı alt yazı** için `&Home`, **büyük resimler** için `IDB_RIBBON_HOMELARGE`, **küçük resimler** için `IDB_RIBBON_HOMESMALL`.

1. Her Şerit kategorisi adlandırılmış bölmelere düzenlenmiştir. Her paneli, tam ilgili operations denetimleri kümesini içerir. Bu kategori, tek bir panel sahiptir. Tıklayın **paneli**ve ardından değiştirmek **açıklamalı alt yazı** için `Edit`.

1. İçin **Düzenle** panelinde, belge içeriğini temizlemek için sorumlu bir düğme ekleyin. Bu düğme için ileti kimliği, önceden tanımlanmış `IDR_SCRIBBTYPE` menü kaynağı. Belirtin `Clear All` düğme metni ve düğmeyi düzenler bit eşlem dizini. Açık **araç kutusu**ve ardından bir **düğmesi** için **Düzenle** paneli. Düğmesine tıklayın ve ardından değiştirmek **açıklamalı alt yazı** için `Clear All`, **kimliği** için `ID_EDIT_CLEAR_ALL`, **görüntü dizini** için `0`, **büyük görüntü dizini**  için `0`.

1. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Karalama uygulamasını görüntülenmesi gerekir ve bir menü çubuğu yerine pencerenin üstünde bir Şerit çubuğuna olmalıdır. Şerit çubuğuna bir kategoriye sahip olmalıdır **giriş**, ve **giriş** tek bir panel olmalıdır **Düzenle**. Eklediğiniz Şerit düğmeleri mevcut olay işleyicileri ile ilişkilendirilmesi gereken ve **açık**, **Kapat**, **Kaydet**, **yazdırma**, ve **Tümünü Temizle** düğmeler, beklendiği gibi çalışmalıdır.

##  <a name="setlook"></a> Uygulama görünümünü ayarlama

A *görsel yöneticiyi* denetleyen bir uygulama için tüm çizim genel bir nesnedir. Özgün karalama uygulamasını, Office 2000 kullanıcı arabirimi (UI) stili kullandığından, uygulamanın eski moda görünebilir. Office 2007 uygulamasına benzer olacak şekilde, Office 2007 görsel yöneticiyi kullanmak için uygulamayı sıfırlayabilirsiniz.

### <a name="to-set-the-look-of-the-application"></a>Uygulamanın görünümü ayarlamak için

1. İçinde `CMainFrame::OnCreate` işlev, önce aşağıdaki kodu yazın `return 0;` varsayılan görsel yöneticiyi ve stili değiştirmek için deyimi.

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

1. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Uygulama kullanıcı Arabirimi, Office 2007 UI benzemelidir.

## <a name="next-steps"></a>Sonraki Adımlar

Kullanılacak Klasik 1.0 MFC karalama örneğinin değiştirdiğiniz **Şerit Tasarımcısı**. Artık Git [2. bölüm](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md).

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)<br/>
[İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (2. Bölüm)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)
