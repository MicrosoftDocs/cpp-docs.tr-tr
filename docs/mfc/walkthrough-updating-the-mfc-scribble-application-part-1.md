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
ms.openlocfilehash: ce50d2c70107b4c88f223e32fdd8cc083df38840
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43685551"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>İzlenecek yol: MFC karalama uygulamasını (Kısım 1) güncelleştiriliyor

Bu yönerge Şerit kullanıcı arabirimini kullanarak varolan bir MFC uygulamasına değişiklik yapma gösterir. Visual Studio, hem Office 2007 Şerit hem de Windows 7, manzara Şerit destekler. Şerit kullanıcı arabirimini hakkında daha fazla bilgi için bkz: [şeritler](/windows/desktop/uxguide/cmd-ribbons).

Bu kılavuz satırı çizimler için fare kullanmanıza olanak sağlayan Klasik 1.0 MFC karalama örneği değiştirir. Kılavuzun bu bölümü, böylece bir Şerit çubuğuna görüntüler genişletilen Scribble örneğinin değiştirme işlemi gösterilmektedir. [2. bölüm](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) diğer düğmeleri Şerit çubuğuna ekler.

## <a name="prerequisites"></a>Önkoşullar

[Visual C++ Örnekleri](../visual-cpp-samples.md)

[Visual C++ Örnekleri](../visual-cpp-samples.md)

##  <a name="top"></a> Bölümleri

Kılavuzun bu bölümü aşağıdaki bölümleri içerir:

- [Temel sınıflar değiştirme](#replaceclass)

- [Bit eşlemler projeye ekleniyor](#addbitmap)

- [Projeye bir Şerit kaynağı ekleme](#addribbon)

- [Bir Şerit çubuğuna örneğini oluşturma](#createinstance)

- [Bir Şerit kategorisi ekleme](#addcategory)

- [Uygulama görünümünü ayarlama](#setlook)

##  <a name="replaceclass"></a> Temel sınıflar değiştirme

Bir Şerit destekleyen bir uygulama için bir menü destekleyen bir uygulamaya dönüştürmek için uygulama, çerçeve ve araç sınıfları güncelleştirilmiş temel sınıfların türetilmesi gerekir. (, Değil özgün genişletilen Scribble örneğinin değiştirin; bunun yerine, karalama projeyi temizleyin, başka bir dizine kopyalayın ve kopyayı değiştirin, öneririz.)

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Karalama uygulamasını taban sınıflardaki değiştirmek için

1. Scribble.cpp içinde doğrulayın `CScribbleApp::InitInstance` bir çağrı içerdiğine [Afxoleınit](../mfc/reference/ole-initialization.md#afxoleinit).

2. Stdafx.h dosyaya aşağıdaki kodu ekleyin.

    ```cpp
    #include <afxcontrolbars.h>
    ```

3. Scribble.h içinde tanımını değiştirme `CScribbleApp` böylece, türetilmiş sınıf [CWinAppEx sınıfı](../mfc/reference/cwinappex-class.md).

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

4. Windows uygulamaları, kullanıcı tercihi verileri kaydetmek için bir başlatma (.ini) dosyası kullanıldığında karalama 1.0 yazılmıştır. Karalama kullanıcı tercihlerini kayıt defterine depolamak için bir başlatma dosyası yerine değiştirin. Temel ve kayıt defteri anahtarını ayarlamak için aşağıdaki kodu yazın `CScribbleApp::InitInstance` sonra `LoadStdProfileSettings()` deyimi.

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

5. Birden çok belge arabirimi (MDI) uygulaması için ana çerçeve artık türetilir `CMDIFrameWnd` sınıfı. Bunun yerine, öğesinden türetilir [Cmdıframewndex](../mfc/reference/cmdiframewndex-class.md) sınıfı.

     Tüm başvuruları mainfrm.h ve mainfrm.cpp dosyaları değiştirin `CMDIFrameWnd` ile `CMDIFrameWndEx`.

6. Childfrm.h ve childfrm.cpp dosyalarda Değiştir `CMDIChildWnd` ile `CMDIChildWndEx`.

     İçinde childfrm. h dosya değiştirin `CSplitterWnd` ile `CSplitterWndEx`.

7. Araç çubuklarını ve durum çubukları yeni MFC sınıflarını kullanmak için değiştirin.

     Mainfrm.h dosyasında:

    1. Değiştirin `CToolBar` ile `CMFCToolBar`.

    2. Değiştirin `CStatusBar` ile `CMFCStatusBar`.

8. Mainfrm.cpp dosyasında:

    1. Değiştirin `m_wndToolBar.SetBarStyle` ile `m_wndToolBar.SetPaneStyle`

    2. Değiştirin `m_wndToolBar.GetBarStyle` ile `m_wndToolBar.GetPaneStyle`

    3. Değiştirin `DockControlBar(&m_wndToolBar)` ile `DockPane(&m_wndToolBar)`

9. İpframe.cpp dosyasında kod aşağıdaki üç satırları açıklama satırı yapar.

    ```cpp
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->DockPane(&m_wndToolBar);
    ```

10. Kullanarak statik olarak bağlantı istiyorsanız, proje kaynak (.rc) dosyasının başına aşağıdaki kodu ekleyin.

    ```cpp
    #include "afxribbon.rc"
    ```

     Afxribbon.rc dosyanın çalışma zamanında gerekli olan kaynakları içerir. [MFC Uygulama Sihirbazı](../mfc/reference/mfc-application-wizard.md) bir uygulama oluşturduğunuzda bu dosya otomatik olarak içerir.

11. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın.

[[Bölümleri](#top)]

##  <a name="addbitmap"></a> Bit eşlemler projeye ekleniyor

Bu kılavuzun sonraki dört adımları, bit eşlem kaynakları gerektirir. Çeşitli şekillerde uygun bit eşlemler elde edebilirsiniz:

- Kullanım [kaynak düzenleyicileri](../windows/resource-editors.md) kendi bit eşlemler imkan. Veya Visual Studio ile birlikte gelen Taşınabilir Ağ Grafikleri (.png) görüntülerinden bit eşlemler derlemek için kaynak düzenleyicileri kullanın. Bu görüntüleri bulunan `VS2008ImageLibrary` dizin.

     Ancak, Şerit kullanıcı arabirimini, belirli bir bit eşlemler saydam görüntüler desteklemesini gerektirir. Saydam bit eşlemler kullanın. burada 24 bit rengin kırmızı, yeşil ve mavi bileşenlerinin belirtin ve 8 bit tanımlamak 32-bit piksel bir *alfa kanalı* rengini, saydamlığını belirtir. Geçerli kaynak düzenleyicileri görüntüleyebilir, ancak bit eşlemler 32-bit piksel ile değiştiremez. Sonuç olarak, dış görüntü düzenleyici saydam bit eşlemler işlemek için yerine kaynak düzenleyicileri kullanın.

- Projeniz başka bir uygulamadan bir uygun kaynak dosyasını buraya kopyalayın ve ardından bit eşlemler bu dosyadan içeri aktarın.

Bu izlenecek yolda kaynak dosyalarını örnekler dizini uygulamada kopyalar.

### <a name="to-add-bitmaps-to-the-project"></a>Bit eşlemler projeye eklemek için

1. Kaynakları dizininden aşağıdaki .bmp dosyaları kopyalamak için dosya Gezgini'ni kullanın (`res`), RibbonGadgets örneği:

   1. Main.bmp karalama projenize kopyalayın.

   2. Filesmall.bmp ve filelarge.bmp karalama projenize kopyalayın.

   3. Filelarge.bmp ve filesmall.bmp dosyalarının yeni kopyalarını ancak RibbonGadgets örneği kopya kaydedin. Kopya homesmall.bmp ve homelarge.bmp yeniden adlandırın ve ardından kopya karalama projenize taşıyabilirsiniz.

   4. Toolbar.bmp dosyanın bir kopyasını, ancak RibbonGadgets örneği kopyasını kaydedin. Kopyalama panelicons.bmp yeniden adlandırın ve ardından kopya karalama projenize taşıyabilirsiniz.

2. Bir MFC uygulaması için bit eşlem olarak içeri aktarın. İçinde **kaynak görünümü**, çift **scribble.rc** düğümünü çift tıklayın **bit eşlem** düğümünü ve ardından **kaynak ekleme**. Görüntülenen iletişim kutusuna tıklayın **alma**. Gözat `res` dizin main.bmp dosyasını seçin ve ardından **açık**.

   Main.bmp bit eşlem 26 x 26 görüntü içerir. Bit eşlem kimliği için IDB_RIBBON_MAIN değiştirin.

3. Bit eşlemler uygulama düğmesine bağlı Dosya menüsü için içeri aktarın.

   1. On 16 x 16 (16 x 160) içeren filesmall.bmp dosyasını içeri aktarma görüntüler. Yalnızca sekiz 16 x 16 görüntü (16 x 128) ihtiyacımız çünkü **kaynak görünümü** , bit eşlem genişliği 128 ' 160 değiştirmek için. Bit eşlem kimliği için IDB_RIBBON_FILESMALL değiştirin.

   2. Sekiz 32 x 32 (32 x 256) içeren filelarge.bmp alma görüntüler. Bit eşlem kimliği için IDB_RIBBON_FILELARGE değiştirin.

4. Bit eşlemler Şerit kategori ve panel için içeri aktarın. Her sekme Şerit çubuğundaki bir kategori ve bir metin etiketi ve isteğe bağlı görüntü oluşur.

   1. Sekiz 16 x 16 görüntüler için küçük bir düğme bit eşlemler içeren homesmall.bmp bit eşlem olarak içeri aktarın. Bit eşlem kimliği için IDB_RIBBON_HOMESMALL değiştirin.

   2. Sekiz 32 x 32 görüntüleri için büyük düğme bit eşlemler içeren homelarge.bmp bit eşlem olarak içeri aktarın. Bit eşlem kimliği için IDB_RIBBON_HOMELARGE değiştirin.

5. Bit eşlemleri yeniden boyutlandırılan Şerit paneli için içeri aktarın. Şerit paneli tamamını görüntülemek için çok küçük olduğunda bu bit eşlemler veya paneli simgeler, sonra yeniden boyutlandırma işlemi kullanılır.

   1. Sekiz 16 x 16 görüntü içeren panelicons.bmp bit eşlem olarak içeri aktarın. İçinde **özellikleri** pencerenin **bit eşlem Düzenleyicisi**, (16 x 64) 64 bit eşlem genişliğini ayarla. Bit eşlem kimliği için IDB_PANEL_ICONS değiştirin.

[[Bölümleri](#top)]

##  <a name="addribbon"></a> Projeye bir Şerit kaynağı ekleme

Menülere Şerit kullanan bir uygulamayı kullanan bir uygulamayı dönüştürdüğünüzde, kaldırın veya var olan menüleri devre dışı gerekmez. Bunun yerine, bir Şerit kaynağı oluşturabilir, Şerit düğmeleri eklemek ve ardından yeni düğmeler var olan menü öğeleriyle ilişkilendirmek. Menüler artık görünür olmasına rağmen Şerit çubuğunda iletiler menüleri yönlendirilir. Ayrıca, menüsü kısayolları çalışmaya devam eder.

Şerit büyük düğmesidir Şeridin sol üst tarafında, uygulama düğmesini ve bir veya daha fazla kategori sekmeden oluşur. Her kategori sekme Şerit düğmeleri ve denetimler için kapsayıcı olarak davranan bir veya daha fazla panel içerir. Aşağıdaki yordam nasıl bir Şerit kaynağı oluşturabilir ve ardından uygulama düğmesini özelleştirme gösterir.

### <a name="to-add-a-ribbon-resource-to-the-project"></a>Projeye bir Şerit kaynağı eklemek için

1. Üzerinde **proje** menüsünü tıklatın **kaynak Ekle**.

2. İçinde **kaynak Ekle** iletişim kutusunda **Şerit** ve ardından **yeni**.

   Visual Studio, bir Şerit kaynağı oluşturur ve Tasarım görünümünde açılır. Görüntülenen IDR_RIBBON1, Şerit kaynak kimliğidir **kaynak görünümü**. Şerit, bir kategori ve tek bir panel içerir.

3. Uygulama düğmesi özelliklerini değiştirerek özelleştirebilirsiniz. Bu kodda kullanılan iletisi kimlikleri, menüde karalama 1.0 için önceden tanımlanmıştır.

4. Tasarım görünümünde, özelliklerini görüntülemek için uygulama düğmesini tıklatın. Özellik değerleri aşağıdaki gibi değiştirin: **görüntü** için `IDB_RIBBON_MAIN`, **istemi** için `File`, **anahtarları** için `f`, **büyük resimler** için `IDB_RIBBON_FILELARGE`, ve **küçük resimler** için `IDB_RIBBON_FILESMALL`.

5. Aşağıdaki değişiklikler, kullanıcı uygulama düğmesini tıkladığında açılan menüden oluşturun. Üç nokta simgesine tıklayın (**...** ) yanındaki **ana öğeler** açmak için **öğe düzenleyici**.

   1. Tıklayın **Ekle** bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `&New`, **kimliği** için `ID_FILE_NEW`, **görüntü** için `0`, **büyük görüntü** için`0`.

   2. Tıklayın **Ekle** ikinci bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `&Save`, **kimliği** için `ID_FILE_SAVE`, **görüntü** için `2`, ve **büyük görüntü** için`2`.

   3. Tıklayın **Ekle** üçüncü bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `Save &As`, **kimliği** için `ID_FILE_SAVE_AS`, **görüntü** için `3`, ve **büyük görüntü** için`3`.

   4. Tıklayın **Ekle** dördüncü bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `&Print`, **kimliği** için `ID_FILE_PRINT`, **görüntü** için `4`, ve **büyük görüntü** için`4`.

   5. Değişiklik **öğesi** için yazın **ayırıcı** ve ardından **Ekle**.

   6. Değişiklik **öğesi** için yazın **düğmesi**. Tıklayın **Ekle** beşinci bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `&Close`, **kimliği** için `ID_FILE_CLOSE`, **görüntü** için `5`, ve **büyük görüntü** için`5`.

6. Aşağıdaki değişiklikler, önceki adımda oluşturduğunuz Yazdır düğmesini altında bir alt oluşturun.

   1. Tıklayın **yazdırma** düğmesi, değişiklik **öğesi** için yazın **etiket**ve ardından **Ekle**. Değişiklik **açıklamalı alt yazı** için `Preview and print the document`.

   2. Tıklayın **yazdırma** düğmesi, değişiklik **öğesi** için yazın **düğmesi**, tıklatıp **Ekle**. Değişiklik **açıklamalı alt yazı** için `&Print`, **kimliği** için `ID_FILE_PRINT`, **görüntü** için `4`, ve **büyük görüntü** için`4`.

   3. Tıklayın **yazdırma** düğmesine ve ardından **Ekle** bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `&Quick Print`, **kimliği** için `ID_FILE_PRINT_DIRECT`, **görüntü** için `7`, ve **büyük görüntü** için`7`.

   4. Tıklayın **yazdırma** düğmesine ve ardından **Ekle** başka bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `Print Pre&view`, **kimliği** için `ID_FILE_PRINT_PREVIEW`, **görüntü** için `6`, ve **büyük görüntü** için`6`.

   5. Artık değiştirilmiş **ana öğeler**. Tıklayın **Kapat** çıkmak için **öğe düzenleyici**.

7. Aşağıdaki değişiklik uygulama düğmesini menüsünün alt kısmında görüntülenen bir çıkış düğmesi oluşturur.

   1. İçinde **özellikleri** penceresinde üç noktaya tıklayın (**...** ) yanındaki **düğmesi** açmak için **öğe düzenleyici**.

   2. Tıklayın **Ekle** bir düğme eklemek için. Değişiklik **açıklamalı alt yazı** için `E&xit`, **kimliği** için `ID_APP_EXIT`, **görüntü** için `8`.

[[Bölümleri](#top)]

##  <a name="createinstance"></a> Bir Şerit çubuğuna örneğini oluşturma

Aşağıdaki adımları, uygulamanız başlatıldığında bir Şerit çubuğuna örneğini oluşturma işlemi gösterilmektedir. Bir Şerit çubuğuna bir uygulamaya eklemek için Şerit çubuğuna mainfrm.h dosyasındaki bildirin. Ardından, mainfrm.cpp dosyasında Şerit kaynağı yükleme için kod yazın.

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>Bir Şerit çubuğuna örneğini oluşturmak için

1. Mainfrm.h dosyanın korumalı bölümüne veri üyesi ekleyin `CMainFrame`, ana çerçeve için sınıf tanımının. Bu üye, Şerit çubuğunu temsil eder.

    ```cpp
    // Ribbon bar for the application
    CMFCRibbonBar m_wndRibbonBar;
    ```

2. Mainfrm.cpp dosyanın en son önce aşağıdaki kodu ekleyin `return` deyimi, sonunda `CMainFrame::OnCreate` işlevi. Bu Şerit çubuğundaki bir örneğini oluşturur.

    ```cpp
    // Create the ribbon bar
    if (!m_wndRibbonBar.Create(this))
    {
        return -1;   //Failed to create ribbon bar
    }
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
    ```

[[Bölümleri](#top)]

##  <a name="addcategory"></a> Şerit kaynağını özelleştirme

Uygulama düğmesi oluşturduğunuza göre Şerit öğeleri ekleyebilirsiniz.

> [!NOTE]
> Bu izlenecek yol aynı Paneli simgesi tüm bölmeleri için kullanır. Ancak, diğer görüntü listesi dizinleri diğer simgeleri göstermek için kullanabilirsiniz.

### <a name="to-add-a-home-category-and-edit-panel"></a>Giriş Kategori ekleme ve panel düzenlemek için

1. Karalama programın yalnızca bir kategori gerektirir. Tasarım görünümünde tıklayın **kategori** özelliklerini görüntülemek için. Özellik değerleri aşağıdaki gibi değiştirin: **açıklamalı alt yazı** için `&Home`, **büyük resimler** için `IDB_RIBBON_HOMELARGE`, **küçük resimler** için `IDB_RIBBON_HOMESMALL`.

2. Her Şerit kategorisi adlandırılmış bölmelere düzenlenmiştir. Her paneli ilgili işlemleri denetimleri kümesini içerir. Bu kategori, tek bir panel sahiptir. Tıklayın **paneli**ve ardından değiştirmek **açıklamalı alt yazı** için `Edit` ve **görüntü dizini** için `0`.

3. İçin **Düzenle** panelinde, belge içeriğini temizlemek için sorumlu olduğu bir düğme ekleyin. Bu düğme için ileti kimliği IDR_SCRIBBTYPE menü kaynakta zaten tanımlandı. Belirtin `Clear All` düğme metni ve düğmeyi düzenler bit eşlem dizini. Açık **araç kutusu**ve ardından bir **düğmesi** için **Düzenle** paneli. Düğmesine tıklayın ve ardından değiştirmek **açıklamalı alt yazı** için `Clear All`, **kimliği** için `ID_EDIT_CLEAR_ALL`, **görüntü dizini** için `0`, **büyük görüntü dizini**  için `0`.

4. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Karalama uygulamasını görüntülenmesi gerekir ve bir menü çubuğu yerine pencerenin üstünde bir Şerit çubuğuna olmalıdır. Şerit çubuğuna bir kategoriye sahip olmalıdır **giriş**, ve **giriş** tek bir panel olmalıdır **Düzenle**. Eklediğiniz Şerit düğmeleri mevcut olay işleyicileri ile ilişkilendirilmesi gereken ve **açık**, **Kapat**, **Kaydet**, **yazdırma**, ve **Tümünü Temizle** düğmeler, beklendiği gibi çalışmalıdır.

[[Bölümleri](#top)]

##  <a name="setlook"></a> Uygulama görünümünü ayarlama

A *görsel yöneticiyi* denetleyen bir uygulama için tüm çizim genel bir nesnedir. Özgün karalama uygulamasını, Office 2000 kullanıcı arabirimi (UI) stili kullandığından, uygulamanın eski moda görünebilir. Office 2007 uygulamasına benzer olacak şekilde, Office 2007 görsel yöneticiyi kullanmak için uygulamayı sıfırlayabilirsiniz.

### <a name="to-set-the-look-of-the-application"></a>Uygulamanın görünümü ayarlamak için

1. İçinde `CMainFrame::OnCreate` işlev, varsayılan görsel yöneticiyi ve stili değiştirmek için aşağıdaki kodu yazın.

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

2. Değişiklikleri kaydetmek ve oluşturmak ve uygulamayı çalıştırın. Uygulama kullanıcı Arabirimi, Office 2007 UI benzemelidir.

[[Bölümleri](#top)]

## <a name="next-steps"></a>Sonraki Adımlar

Şerit Tasarımcısını kullanmak için Klasik 1.0 MFC karalama örneğinin değiştirdiniz. Artık Git [2. bölüm](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md).

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)  
[İzlenecek yol: MFC karalama uygulamasını (Bölüm 2) güncelleştirme] (.. / mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)  
