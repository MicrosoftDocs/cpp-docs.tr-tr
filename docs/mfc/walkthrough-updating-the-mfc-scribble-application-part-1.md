---
title: 'İzlenecek yol: MFC karalama uygulamasını (Kısım 1) güncelleştirme | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- examples [MFC], update existing application
- ribbon UI, porting to
- Office Fluent UI, porting to
- samples [MFC], update existing application
- MFC Feature Pack, update existing application
- walkthroughs [MFC], update existing application
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 916c6ccbdaa9512f1ee0a23a59b866678005180a
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122859"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>İzlenecek yol: MFC karalama uygulamasını (Kısım 1) güncelleştirme

Bu anlatımda Şerit kullanıcı arabirimi kullanmak için varolan bir MFC uygulamasına değiştirme gösterilir. Visual Studio Office 2007 Şerit ve Windows 7 manzara Şerit destekler. Şerit kullanıcı arabirimi hakkında daha fazla bilgi için bkz: [Şerit](http://go.microsoft.com/fwlink/p/?linkid=129233) MSDN Web sitesinde.

Bu kılavuz çizgi çizimler için fare kullanmanıza olanak sağlayan Klasik 1.0 MFC karalama örnek değiştirir. Kılavuzun bu bölümü, böylece bir Şerit çubuğu görüntüler karalama örnek değiştirmek gösterilmiştir. [2. bölüm](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) daha fazla düğme Şerit çubuğuna ekler.

## <a name="prerequisites"></a>Önkoşullar

[Visual C++ Örnekleri](../visual-cpp-samples.md)

[Visual C++ Örnekleri](../visual-cpp-samples.md)

##  <a name="top"></a> Bölümler

Kılavuzun bu bölümü aşağıdaki bölümleri içerir:

- [Temel sınıflar değiştirme](#replaceclass)

- [Bit eşlemler projesine ekleniyor](#addbitmap)

- [Projeye Şerit kaynağı ekleme](#addribbon)

- [Şerit çubuğu örneği oluşturma](#createinstance)

- [Şerit kategorisi ekleme](#addcategory)

- [Uygulama görünümünü ayarlama](#setlook)

##  <a name="replaceclass"></a> Temel sınıflar değiştirme

Şerit destekleyen bir uygulama menüsüne destekleyen bir uygulama dönüştürmek için uygulama, çerçeve penceresi ve araç sınıfları güncelleştirilmiş temel sınıflarından türetilmesi gerekir. (, Değil özgün karalama örnek değiştirin; bunun yerine, karalama projeyi temizleyin, başka bir dizine kopyalayın ve kopyayı değiştirin, öneririz.)

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Karalama uygulamasını temel sınıflarda değiştirmek için

1. Scribble.cpp içinde doğrulayın `CScribbleApp::InitInstance` çağrısı içeriyor [Afxoleınit](../mfc/reference/ole-initialization.md#afxoleinit).

2. Stdafx.h dosyasına aşağıdaki kodu ekleyin.

    ```cpp
    #include <afxcontrolbars.h>
    ```

3. Scribble.h içinde tanımı değiştirmek `CScribbleApp` böylece öğesinden türetilmiş sınıf [CWinAppEx sınıfı](../mfc/reference/cwinappex-class.md).

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

4. Windows uygulamaları kullanıcı tercihi verileri kaydetmek için bir başlatma (.ini) dosyası kullanıldığında karalama 1.0 yazıldı. Bir başlatma dosyası yerine kullanıcı tercihleri kayıt defterine depolamak için karalama değiştirin. Kayıt defteri anahtarını ve temel ayarlamak için aşağıdaki kodu yazın `CScribbleApp::InitInstance` sonra `LoadStdProfileSettings()` deyimi.

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

5. Birden çok belge arabirimi (MDI) uygulaması için ana çerçeve artık türetilir `CMDIFrameWnd` sınıfı. Bunun yerine, onu türetildiği [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md) sınıfı.

     Tüm başvuruları mainfrm.h ve mainfrm.cpp dosyalarda Değiştir `CMDIFrameWnd` ile `CMDIFrameWndEx`.

6. Childfrm.h ve childfrm.cpp dosyalarda Değiştir `CMDIChildWnd` ile `CMDIChildWndEx`.

     Childfrm. h dosya Değiştir `CSplitterWnd` ile `CSplitterWndEx`.

7. Araç çubukları ve durum çubukları yeni MFC sınıfları kullanacak şekilde değiştirin.

     Mainfrm.h dosyasında:

    1. Değiştir `CToolBar` ile `CMFCToolBar`.

    2. Değiştir `CStatusBar` ile `CMFCStatusBar`.

8. Mainfrm.cpp dosyasında:

    1. Değiştir `m_wndToolBar.SetBarStyle` ile `m_wndToolBar.SetPaneStyle`

    2. Değiştir `m_wndToolBar.GetBarStyle` ile `m_wndToolBar.GetPaneStyle`

    3. Değiştir `DockControlBar(&m_wndToolBar)` ile `DockPane(&m_wndToolBar)`

9. İpframe.cpp dosyasında, aşağıdaki üç kod satırı açıklama.

    ```cpp
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->DockPane(&m_wndToolBar);
    ```

10. Uygulamanızı statik olarak bağlamak istiyorsanız, aşağıdaki kodu proje kaynak (.rc) dosyasının başlangıcına ekleyin.

    ```cpp
    #include "afxribbon.rc"
    ```

     Afxribbon.rc dosya çalışma zamanında gerekli kaynakları içerir. [MFC Uygulama Sihirbazı'nı](../mfc/reference/mfc-application-wizard.md) bir uygulama oluşturduğunuzda bu dosya otomatik olarak ekler.

11. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın.

[[Bölümleri](#top)]

##  <a name="addbitmap"></a> Bit eşlemler projesine ekleniyor

Bu kılavuzun sonraki dört adımları bit eşlem kaynakları gerektirir. Çeşitli şekillerde uygun bit eşlemler elde edebilirsiniz:

- Kullanım [kaynak düzenleyicileri](../windows/resource-editors.md) kendi bit eşlemler stok için. Veya kaynak düzenleyicileri dahil edilen Taşınabilir Ağ Grafikleri (.png) görüntülerden bit eşlemler derleyecek kullanmayı [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]. Bu görüntüleri bulunan `VS2008ImageLibrary` dizin.

     Ancak, Şerit kullanıcı arabirimi belirli bit eşlemler saydam görüntüler desteklemesini gerektirir. Saydam bit eşlemler kullanmak burada 24 bit rengi kırmızı, yeşil ve mavi bileşenlerinin belirtin ve 8 bit tanımlamak 32-bit piksel cinsinden bir *alfa kanal* rengi saydamlığını belirtir. Geçerli kaynak düzenleyicileri görüntüleyebilir, ancak 32-bit piksel bit eşlemler değiştiremez. Sonuç olarak, harici bir görüntü düzenleyicide yerine kaynak düzenleyicileri saydam bit eşlemler değiştirmek için kullanın.

- Projenize başka bir uygulamadan bir uygun kaynak dosyasını kopyalayın ve sonra bu dosyadan bit eşlemler aktarın.

Bu kılavuzda örnekler dizini uygulamada kaynak dosyalarını kopyalar.

### <a name="to-add-bitmaps-to-the-project"></a>Bit eşlemler projeye eklemek için

1. Kaynakları dizininden aşağıdaki .bmp dosyaları kopyalamak için dosya Gezgini'ni kullanın (`res`) RibbonGadgets örnek:

   1. Main.bmp karalama projenize kopyalayın.

   2. Filesmall.bmp ve filelarge.bmp karalama projenize kopyalayın.

   3. Filelarge.bmp ve filesmall.bmp dosyalarının yeni kopyalarını ancak kopyaları RibbonGadgets örnek kaydedin. Kopya homesmall.bmp ve homelarge.bmp yeniden adlandırın ve ardından kopya karalama projenize taşıyın.

   4. Toolbar.bmp dosyasının bir kopyası, ancak RibbonGadgets örnek kopyasını kaydedin. Kopyalama panelicons.bmp yeniden adlandırın ve ardından kopyalama karalama projenize taşıyın.

2. MFC uygulaması için bit eşlemde içeri aktarın. İçinde **kaynak görünümü**, çift tıklatın **scribble.rc** düğümü, çift **bit eşlem** düğümünü ve ardından **kaynak ekleyin**. Görüntülenen iletişim kutusunda tıklatın **alma**. Gözat `res` dizin main.bmp dosyasını seçin ve ardından **açık**.

   Main.bmp bit eşlem 26 x 26 görüntüsünü içerir. Bit eşlem Kimliğini IDB_RIBBON_MAIN için değiştirin.

3. Bit eşlemler uygulama düğmesi bağlı Dosya menüsü içeri aktarın.

   1. On 16 x 16 (16 x 160) içeren filesmall.bmp dosyasını içe görüntüler. Yalnızca sekiz 16 x 16 görüntü (16 x 128) ihtiyacımız olduğundan **kaynak görünümü** , bit eşlem genişliği 128 ' 160 değiştirmek için. Bit eşlem Kimliğini IDB_RIBBON_FILESMALL için değiştirin.

   2. Sekiz 32 x 32 (32 x 256) içeren filelarge.bmp alma görüntüler. Bit eşlem Kimliğini IDB_RIBBON_FILELARGE için değiştirin.

4. Bit eşlemler Şerit kategorileri ve paneller içeri aktarın. Her bir sekmede Şerit çubuğu bir kategori ve bir metin etiketi ve isteğe bağlı bir görüntü oluşur.

   1. Sekiz 16 x 16 görüntüler için küçük bir düğme bit eşlemler içeren homesmall.bmp bit eşlem içeri aktarın. Bit eşlem Kimliğini IDB_RIBBON_HOMESMALL için değiştirin.

   2. Sekiz 32 x 32 görüntüleri için büyük düğme bit eşlemler içeren homelarge.bmp bit eşlem içeri aktarın. Bit eşlem Kimliğini IDB_RIBBON_HOMELARGE için değiştirin.

5. Bit eşlemler yeniden boyutlandırılan Şerit paneller için içeri aktarın. Şerit tüm panelini görüntülemek için çok küçük ise bu bit eşlemler veya Masası simgeleri sonra bir yeniden boyutlandırma işlemi kullanılır.

   1. Sekiz 16 x 16 görüntü içeren panelicons.bmp bit eşlem içeri aktarın. İçinde **özellikleri** pencerenin **bit eşlem Düzenleyicisi**, bit eşlem 64 (16 x 64) için genişliğini ayarla. Bit eşlem Kimliğini IDB_PANEL_ICONS için değiştirin.

[[Bölümleri](#top)]

##  <a name="addribbon"></a> Projeye Şerit kaynağı ekleme

Şerit kullanan bir uygulama menüleri kullanan bir uygulamayı dönüştürürken kaldırın veya varolan menüleri devre dışı bırakma gerekmez. Bunun yerine, bir Şerit kaynağı oluşturun, Şerit düğmeleri ekleyin ve ardından yeni düğmeler varolan menü öğeleriyle ilişkilendirmek. Menüleri artık görünür olsa da, iletiler Şerit çubuğundan menülerde yönlendirilir. Ayrıca, menüsü kısayolları çalışmaya devam eder.

Şerit Şerit sol üst tarafındaki büyük düğme olan uygulama düğmesi ve bir veya daha fazla kategoriye sekmeleri oluşur. Her kategori sekme Şerit düğmeleri ve denetimler için kapsayıcı olarak davranan bir veya daha fazla paneller içerir. Aşağıdaki yordam, bir Şerit kaynak oluşturmak ve uygulama düğmesini özelleştirme gösterilmektedir.

### <a name="to-add-a-ribbon-resource-to-the-project"></a>Projeye Şerit kaynağına eklemek için

1. Üzerinde **proje** menüsünde tıklatın **kaynak ekleme**.

2. İçinde **kaynak ekleme** iletişim kutusunda **Şerit** ve ardından **yeni**.

   Visual Studio Şerit kaynağı oluşturur ve Tasarım görünümünde açılır. Görüntülenen IDR_RIBBON1 Şerit kaynak kimliğidir **kaynak görünümü**. Şerit bir kategori ve bir paneli içerir.

3. Uygulama düğmesi özelliklerini değiştirerek özelleştirebilirsiniz. Bu kod içinde kullanılan iletisi kimlikleri önceden menüde karalama 1.0 için tanımlanmış.

4. Tasarım görünümünde, özelliklerini görüntülemek için uygulama düğmesini tıklatın. Özellik değerleri aşağıdaki gibi değiştirin: **görüntü** için `IDB_RIBBON_MAIN`, **komut istemi** için `File`, **anahtarları** için `f`, **büyük görüntüleri** için `IDB_RIBBON_FILELARGE`, ve **küçük resimler** için `IDB_RIBBON_FILESMALL`.

5. Aşağıdaki değişiklikleri kullanıcı uygulama düğmesini tıklattığında görüntülenen menüde oluşturun. Üç nokta işaretine (**...** ) yanındaki **ana öğeleri** açmak için **öğeleri Düzenleyicisi**.

   1. Tıklatın **Ekle** düğme eklemek için. Değişiklik **resim yazısı** için `&New`, **kimliği** için `ID_FILE_NEW`, **görüntü** için `0`, **büyük görüntü** için`0`.

   2. Tıklatın **Ekle** ikinci düğme eklemek için. Değişiklik **resim yazısı** için `&Save`, **kimliği** için `ID_FILE_SAVE`, **görüntü** için `2`, ve **büyük görüntü** için`2`.

   3. Tıklatın **Ekle** üçüncü bir düğme eklemek için. Değişiklik **resim yazısı** için `Save &As`, **kimliği** için `ID_FILE_SAVE_AS`, **görüntü** için `3`, ve **büyük görüntü** için`3`.

   4. Tıklatın **Ekle** dördüncü bir düğme eklemek için. Değişiklik **resim yazısı** için `&Print`, **kimliği** için `ID_FILE_PRINT`, **görüntü** için `4`, ve **büyük görüntü** için`4`.

   5. Değişiklik **öğesi** için yazın **ayırıcı** ve ardından **Ekle**.

   6. Değişiklik **öğesi** için yazın **düğmesini**. Tıklatın **Ekle** beşinci düğme eklemek için. Değişiklik **resim yazısı** için `&Close`, **kimliği** için `ID_FILE_CLOSE`, **görüntü** için `5`, ve **büyük görüntü** için`5`.

6. Aşağıdaki değişiklikleri önceki adımda oluşturduğunuz Yazdır düğmesini altında bir alt oluşturun.

   1. Tıklatın **yazdırma** düğmesini tıklatın, değiştirmek **öğesi** için yazın **etiket**ve ardından **Ekle**. Değişiklik **resim yazısı** için `Preview and print the document`.

   2. Tıklatın **yazdırma** düğmesini tıklatın, değiştirmek **öğesi** için yazın **düğmesini**, tıklatıp **Ekle**. Değişiklik **resim yazısı** için `&Print`, **kimliği** için `ID_FILE_PRINT`, **görüntü** için `4`, ve **büyük görüntü** için`4`.

   3. Tıklatın **yazdırma** düğmesine tıklayın ve ardından **Ekle** düğme eklemek için. Değişiklik **resim yazısı** için `&Quick Print`, **kimliği** için `ID_FILE_PRINT_DIRECT`, **görüntü** için `7`, ve **büyük görüntü** için`7`.

   4. Tıklatın **yazdırma** düğmesine tıklayın ve ardından **Ekle** başka bir düğme eklemek için. Değişiklik **resim yazısı** için `Print Pre&view`, **kimliği** için `ID_FILE_PRINT_PREVIEW`, **görüntü** için `6`, ve **büyük görüntü** için`6`.

   5. Artık değiştirilmiş **ana öğeleri**. Tıklatın **Kapat** çıkmak için **öğeleri Düzenleyicisi**.

7. Aşağıdaki değişiklik uygulama düğmesi menüsünün alt kısmında görüntülenen bir çıkış düğmesi oluşturur.

   1. İçinde **özellikleri** penceresinde, üç nokta işaretine (**...** ) yanındaki **düğmesini** açmak için **öğeleri Düzenleyicisi**.

   2. Tıklatın **Ekle** düğme eklemek için. Değişiklik **resim yazısı** için `E&xit`, **kimliği** için `ID_APP_EXIT`, **görüntü** için `8`.

[[Bölümleri](#top)]

##  <a name="createinstance"></a> Şerit çubuğu örneği oluşturma

Aşağıdaki adımları uygulamanız başladığında Şerit çubuğu örneği oluşturmayı gösterir. Şerit çubuğu bir uygulama eklemek için mainfrm.h dosya Şerit çubuğunda bildirin. Ardından, mainfrm.cpp dosyasında Şerit kaynağı yüklemek için kod yazma.

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>Şerit çubuğundaki bir örneğini oluşturmak için

1. Mainfrm.h dosyasında veri üyesi korumalı bölümüne ekleyin `CMainFrame`, ana çerçeve sınıf tanımı. Bu üye Şerit çubuk temsil eder.

    ```cpp
    // Ribbon bar for the application
    CMFCRibbonBar m_wndRibbonBar;
    ```

2. Mainfrm.cpp dosyasında son önce aşağıdaki kodu ekleyin `return` deyimi sonunda `CMainFrame::OnCreate` işlevi. Şerit çubuğundaki bir örneğini oluşturur.

    ```cpp
    // Create the ribbon bar
    if (!m_wndRibbonBar.Create(this))
    {
        return -1;   //Failed to create ribbon bar
    }
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
    ```

[[Bölümleri](#top)]

##  <a name="addcategory"></a> Şerit kaynağı özelleştirme

Uygulama düğmesi oluşturduğunuza göre için Şerit öğeleri ekleyebilirsiniz.

> [!NOTE]
> Bu kılavuzda aynı Paneli simgesi tüm panelleri için kullanılır. Ancak, diğer simgeleri göstermek için diğer görüntü listesi dizinleri kullanabilirsiniz.

### <a name="to-add-a-home-category-and-edit-panel"></a>Giriş Kategori ekleme ve paneli düzenlemek için

1. Karalama programın yalnızca bir kategori gerektirir. Tasarım görünümü tıklatın **kategori** özelliklerini görüntülemek için. Özellik değerleri aşağıdaki gibi değiştirin: **resim yazısı** için `&Home`, **görüntülerin büyük** için `IDB_RIBBON_HOMELARGE`, **küçük resimler** için `IDB_RIBBON_HOMESMALL`.

2. Her Şerit kategori adlandırılmış bölmelere düzenlenmiştir. Her paneli ilgili işlemleri denetimleri kümesini içerir. Bu kategori bir paneli sahiptir. Tıklatın **Masası**ve ardından değiştirmek **resim yazısı** için `Edit` ve **görüntü dizini** için `0`.

3. İçin **Düzenle** paneli, belgesinin içeriğini temizlemek için sorumlu olduğu bir düğme ekleyin. Bu düğme için ileti kimliği IDR_SCRIBBTYPE menüsü kaynak zaten tanımlanmış. Belirtin `Clear All` düğme metni ve düğmesi süsler bit eşlem dizini olarak. Açık **araç**ve ardından sürükleyin bir **düğmesini** için **Düzenle** paneli. Düğmesini tıklatın ve sonra değiştirmek **resim yazısı** için `Clear All`, **kimliği** için `ID_EDIT_CLEAR_ALL`, **görüntü dizini** için `0`, **büyük görüntü dizini**  için `0`.

4. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Karalama uygulamasını görüntülenmesi gerekir ve bir menü çubuğu yerine penceresinin üst bir Şerit çubuğu olmalıdır. Şerit çubuğu bir kategori olmalıdır **giriş**, ve **giriş** bir paneli olmalıdır **Düzenle**. Eklediğiniz Şerit düğmeleri var olan olay işleyicileri ile ilişkili olmalıdır ve **açık**, **Kapat**, **kaydetmek**, **yazdırma**, ve **Tümünü Temizle** düğmeleri beklendiği gibi çalışmalıdır.

[[Bölümleri](#top)]

##  <a name="setlook"></a> Uygulama görünümünü ayarlama

A *visual Yöneticisi* bir uygulama için tüm çizim denetleyen genel bir nesnedir. Özgün karalama uygulamasını Office 2000 kullanıcı arabirimi (UI) stili kullandığından, uygulamanın eski moda görünebilir. Bir Office 2007 uygulama benzer şekilde, Office 2007 visual Yöneticisi'ni kullanmak için uygulamayı sıfırlayabilirsiniz.

### <a name="to-set-the-look-of-the-application"></a>Uygulama görünümünü ayarlamak için

1. İçinde `CMainFrame::OnCreate` işlev, varsayılan visual Yöneticisi ve stilini değiştirmek için aşağıdaki kodu yazın.

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

2. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Uygulama kullanıcı Arabirimi Office 2007 UI benzemelidir.

[[Bölümleri](#top)]

## <a name="next-steps"></a>Sonraki Adımlar

Şerit Tasarımcısını kullanmak için Klasik 1.0 MFC karalama örnek değiştirdiniz. Şimdi gidin [Kısım 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md).

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)  
[İzlenecek yol: MFC karalama uygulamasını güncelleştirme (Bölüm 2)] (.. / mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)  
