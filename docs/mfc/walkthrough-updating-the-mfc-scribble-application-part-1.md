---
title: 'İzlenecek yol: MFC karalama uygulamasını güncelleştirme (Bölüm 1)'
ms.date: 09/09/2019
helpviewer_keywords:
- examples [MFC], update existing application
- ribbon UI, porting to
- Office Fluent UI, porting to
- samples [MFC], update existing application
- MFC Feature Pack, update existing application
- walkthroughs [MFC], update existing application
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
ms.openlocfilehash: 2abcb509a3d7a0045ad33bedccdd61fd1e0e58f8
ms.sourcegitcommit: d8f65b1ddc9ea32e877c67e2c8f0ea7501183fc7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/03/2020
ms.locfileid: "93291080"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>İzlenecek yol: MFC karalama uygulamasını güncelleştirme (Bölüm 1)

Bu izlenecek yol, varolan bir MFC uygulamasının şerit kullanıcı arabirimini kullanmak üzere nasıl değiştirileceğini gösterir. Visual Studio hem Office 2007 şeridini hem de Windows 7 manzara şeridini destekler. Şerit kullanıcı arabirimi hakkında daha fazla bilgi için bkz. [şeritler](/windows/win32/uxguide/cmd-ribbons).

Bu izlenecek yol, fareyi kullanarak çizgi çizimleri oluşturmayı sağlayan Klasik karalama 1,0 MFC örneğini değiştirir. İzlenecek yolun bu bölümünde, karalama örneğinin bir şerit çubuğunu görüntüleyecek şekilde nasıl değiştirileceği gösterilmektedir. [2. Bölüm](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) , şerit çubuğuna daha fazla düğme ekler.

## <a name="prerequisites"></a>Önkoşullar

[Karalama 1,0 MFC örneği](https://github.com/microsoft/VCSamples/tree/master/VC2010Samples/MFC/general/Scribble). Visual Studio 2017 veya sonraki bir sürüme dönüştürme hakkında yardım için bkz. [taşıma Kılavuzu: MFC karalama](../porting/porting-guide-mfc-scribble.md).

## <a name="sections"></a><a name="top"></a> Başlıklı

İzlenecek yolun bu bölümü aşağıdaki bölümlere sahiptir:

- [Taban sınıfları değiştirme](#replaceclass)

- [Projeye bit eşlemler ekleme](#addbitmap)

- [Projeye şerit kaynağı ekleme](#addribbon)

- [Şerit çubuğunun bir örneğini oluşturma](#createinstance)

- [Şerit kategorisi ekleme](#addcategory)

- [Uygulamanın görünümünü ayarlama](#setlook)

## <a name="replacing-the-base-classes"></a><a name="replaceclass"></a> Taban sınıfları değiştirme

Bir menüyü destekleyen bir uygulamayı bir şeridi destekleyen bir uygulamaya dönüştürmek için, güncelleştirilmiş temel sınıflardan uygulamayı, çerçeve penceresini ve araç çubuğu sınıflarını türetmeniz gerekir. (Orijinal karalama örneğinizi değiştirmemenizi öneririz. Bunun yerine, karalama projesini temizleyin, başka bir dizine kopyalayın ve sonra kopyayı değiştirin.)

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Karalama uygulamasındaki temel sınıfları değiştirmek için

1. Karalama. cpp içinde, `CScribbleApp::InitInstance` [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)çağrısı içerdiğini doğrulayın.

1. Aşağıdaki kodu, *pch. h* dosyasına (Visual Studio 2017 ve önceki sürümlerde *stdadfx. h* ) ekleyin:

    ```cpp
    #include <afxcontrolbars.h>
    ```

1. Karalama. h içinde, `CScribbleApp` sınıfın tanımını [CWinAppEx sınıfından](../mfc/reference/cwinappex-class.md)türetilmiş olacak şekilde değiştirin.

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

1. Windows uygulamaları Kullanıcı tercihi verilerini kaydetmek için bir başlatma (. ini) dosyası kullandıysa karalama 1,0 yazıldı. Bir başlatma dosyası yerine, Kullanıcı tercihlerini kayıt defterine depolamak için karalama 'yı değiştirin. Kayıt defteri anahtarını ve temelini ayarlamak için, ' den sonra aşağıdaki kodu yazın `CScribbleApp::InitInstance` `LoadStdProfileSettings()` .

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

1. Birden çok belge arabirimi (MDI) uygulaması için ana çerçeve artık sınıftan türetilmemektedir `CMDIFrameWnd` . Bunun yerine, [Cmdiframewndex](../mfc/reference/cmdiframewndex-class.md) sınıfından türetilir.

    MainFrm. h ve MainFrm. cpp dosyalarında, tüm başvurularını `CMDIFrameWnd` ile değiştirin `CMDIFrameWndEx` .

1. Childfrm. h ve childfrm. cpp dosyalarında `CMDIChildWnd` ile değiştirin `CMDIChildWndEx` .

    Yazın. h dosyası, `CSplitterWnd` ile değiştirin `CSplitterWndEx` .

1. Yeni MFC sınıflarını kullanmak için araç çubuklarını ve durum çubuklarını değiştirin.

    MainFrm. h dosyasında:

    1. `CToolBar` yerine `CMFCToolBar` yazın.

    1. `CStatusBar` yerine `CMFCStatusBar` yazın.

1. MainFrm. cpp dosyasında:

    1. Değiştir `m_wndToolBar.SetBarStyle``m_wndToolBar.SetPaneStyle`

    1. Değiştir `m_wndToolBar.GetBarStyle``m_wndToolBar.GetPaneStyle`

    1. Değiştir `DockControlBar(&m_wndToolBar)``DockPane(&m_wndToolBar)`

1. IPFRAME. cpp dosyasında, aşağıdaki üç kod satırını açıklama olarak kodlayın.

    ```cpp
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->DockPane(&m_wndToolBar);
    ```

1. Değişiklikleri kaydedin ve uygulamayı derleyin ve çalıştırın.

## <a name="adding-bitmaps-to-the-project"></a><a name="addbitmap"></a> Projeye bit eşlemler ekleme

Bu izlenecek yolun sonraki dört adımı için bit eşlem kaynakları gerekir. Uygun bit eşlemleri çeşitli yollarla edinebilirsiniz:

- Kendi bit eşlemlerinizi stok için [kaynak düzenleyicilerini](../windows/resource-editors.md) kullanın. Ya da Visual Studio 'da bulunan Taşınabilir Ağ Grafikleri (. png) görüntülerinden bitmapleri birleştirmek için kaynak düzenleyicilerini kullanın ve [Visual Studio görüntü kitaplığından](/visualstudio/designers/the-visual-studio-image-library)indirebilirsiniz.

    Ancak, **Şerit** Kullanıcı arabirimi belirli Bit eşlemlerin saydam görüntüleri desteklemesini gerektirir. Saydam bit eşlemler 32 bitlik pikselleri kullanır; burada 24 bit rengin kırmızı, yeşil ve mavi bileşenlerini belirtir ve 8 bit rengin saydamlığını belirten bir *Alfa kanalını* tanımlar. Geçerli kaynak düzenleyicileri, 32 bit pikselle bit eşlemleri görüntüleyebilir, ancak değiştiremez. Sonuç olarak, saydam bit eşlemleri işlemek için kaynak düzenleyicileri yerine bir dış görüntü düzenleyicisi kullanın.

- Başka bir uygulamadaki uygun bir kaynak dosyasını projenize kopyalayın ve ardından bu dosyadaki bit eşlemleri içeri aktarın.

Bu izlenecek yol, kaynak dosyalarını [Izlenecek yol: MFC kullanarak şerit uygulaması oluşturma](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md)bölümünde oluşturulan örnekte kopyalar.

### <a name="to-add-bitmaps-to-the-project"></a>Projeye bit eşlemler eklemek için

1. Aşağıdaki. bmp dosyalarını, `res` Şerit örneği () kaynak dizininden karalama projesinin kaynak dizinine () kopyalamak Için dosya Gezgini 'ni kullanın `res` :

   1. main.bmp karalama projenize kopyalayın.

   1. filesmall.bmp ve filelarge.bmp karalama projenize kopyalayın.

   1. filelarge.bmp ve filesmall.bmp dosyalarının yeni kopyalarını oluşturun, ancak kopyayı şerit örneğine kaydedin. homesmall.bmp kopyaları yeniden adlandırıp homelarge.bmp ve ardından kopyaları karalama projenize taşıyın.

   1. toolbar.bmp dosyanın bir kopyasını oluşturun, ancak kopyayı şerit örneğine kaydedin. Kopya panelicons.bmp yeniden adlandırın ve sonra kopyayı karalama projenize taşıyın.

1. MFC uygulaması için bit eşlemi içeri aktarın. **Kaynak görünümü** , **karalama. RC** düğümüne çift tıklayın, **bit eşlem** düğümüne çift tıklayın ve ardından **Kaynak Ekle** ' ye tıklayın. Görüntülenen iletişim kutusunda **Içeri aktar** ' a tıklayın. `res`Dizine gidin, main.bmp dosyasını seçin ve ardından **Aç** ' a tıklayın.

   main.bmp bit eşlem bir 26x26 görüntüsü içerir. Bit eşlemin KIMLIĞINI olarak değiştirin `IDB_RIBBON_MAIN` .

1. **Uygulama** düğmesine eklenen dosya menüsünün bit eşlemlerini içeri aktarın.

   1. On bir 16x16 (16x176) görüntüleri içeren filesmall.bmp dosyasını içeri aktarın. Bit eşlemin KIMLIĞINI olarak değiştirin `IDB_RIBBON_FILESMALL` .

   > [!NOTE]
   > Yalnızca ilk sekiz 16x16 görüntü (16x128) gerektiğinden, bu bit eşlemin sağ tarafı genişliğini 176 ' den 128 ' e kırpabilirsiniz.

   1. Dokuz 32x32 (32x288) görüntü içeren filelarge.bmp içeri aktarın. Bit eşlemin KIMLIĞINI olarak değiştirin `IDB_RIBBON_FILELARGE` .

1. Şerit kategorileri ve panellerinin bit eşlemlerini içeri aktarın. Şerit çubuğundaki her sekme bir kategorisidir ve bir metin etiketinden ve isteğe bağlı görüntüden oluşur.

   1. Küçük düğme bit eşlemler için on bir 16x16 görüntü içeren homesmall.bmp bit eşlemini içeri aktarın. Bit eşlemin KIMLIĞINI olarak değiştirin `IDB_RIBBON_HOMESMALL` .

   1. Büyük düğme bit eşlemler için dokuz 32x32 görüntü içeren homelarge.bmp bit eşlemini içeri aktarın. Bit eşlemin KIMLIĞINI olarak değiştirin `IDB_RIBBON_HOMELARGE` .

1. Yeniden boyutlandırılan şerit panelleri için bit eşlemleri içeri aktarın. Bu bit eşlemler veya panel simgeleri, şerit 'in tüm paneli görüntülemesi için çok küçük olması halinde bir yeniden boyutlandırma işleminden sonra kullanılır.

   1. Sekiz 16x16 görüntü içeren panelicons.bmp bit eşlemini içeri aktarın. **Bit eşlem düzenleyicisinin** **Özellikler** penceresinde, bit eşlemin genişliğini 64 (16x64) olarak ayarlayın. Bit eşlemin KIMLIĞINI olarak değiştirin `IDB_PANEL_ICONS` .

   > [!NOTE]
   > Yalnızca ilk dört 16x16 görüntüsünü (16x64) ihtiyacımız olduğundan, bu bit eşlemin sağ tarafındaki genişliğini 128 ' dan 64 ' e kırpabilirsiniz.

## <a name="adding-a-ribbon-resource-to-the-project"></a><a name="addribbon"></a> Projeye şerit kaynağı ekleme

Menüler kullanan bir uygulamayı şerit kullanan bir uygulamaya dönüştürdüğünüzde, var olan menüleri kaldırmanız veya devre dışı bırakmanız gerekmez. Yalnızca bir şerit kaynağı oluşturun, Şerit düğmeleri ekleyin ve ardından yeni düğmeleri mevcut menü öğeleriyle ilişkilendirin. Menüler artık görünmeyebilir, ancak Şerit çubuğundaki iletiler, menüler ve menü kısayolları aracılığıyla yönlendirilir.

Şerit, şeridin sol üst tarafındaki büyük düğme ve bir veya daha fazla kategori sekmesi olan **uygulama** düğmesinden oluşur. Her kategori sekmesi, Şerit düğmeleri ve denetimleri için kapsayıcılar olarak davranan bir veya daha fazla panel içerir. Aşağıdaki yordamda, bir şerit kaynağı oluşturma ve ardından **uygulama** düğmesini özelleştirme gösterilmektedir.

### <a name="to-add-a-ribbon-resource-to-the-project"></a>Projeye şerit kaynağı eklemek için

1. **Çözüm Gezgini** ' de karalama projesi seçiliyken, **Proje** menüsünde **Kaynak Ekle** ' ye tıklayın.

1. **Kaynak Ekle** iletişim kutusunda, **Şerit** ' i seçin ve ardından **Yeni** ' ye tıklayın.

   Visual Studio bir şerit kaynağı oluşturur ve Tasarım görünümünde açar. Şerit kaynak KIMLIĞI, `IDR_RIBBON1` **kaynak görünümü** ' de görüntülenir. Şeritte bir kategori ve bir panel bulunur.

1. Özelliklerini değiştirerek **uygulama** düğmesini özelleştirebilirsiniz. Bu kodda kullanılan ileti kimlikleri, karalama 1,0 için menüde zaten tanımlanmıştır.

1. Tasarım görünümünde, özelliklerini görüntülemek için **uygulama** düğmesine tıklayın. Özellik değerlerini şu şekilde değiştirin: **görüntü** `IDB_RIBBON_MAIN` , **komut istemi** `File` , **anahtarlar** , `f` **büyük görüntüler** `IDB_RIBBON_FILELARGE` ve **küçük görüntüler** `IDB_RIBBON_FILESMALL` .

1. Aşağıdaki değişiklikler Kullanıcı **uygulama** düğmesine tıkladığında görüntülenen menüyü oluşturur. **Ana öğeler** ' in yanındaki üç nokta ( **...** ) simgesine tıklayarak **öğeler düzenleyicisini** açın.

   1. **Öğe** türü **düğmesi** seçili olduğunda, düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı alt yazı** , `&New` **ID** to `ID_FILE_NEW` , **Image** to `0` , **Image Large** `0` .

   1. Düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı alt yazı** , `&Save` **kimlik** - `ID_FILE_SAVE` , **resim** `2` ve **görüntü büyük** olarak değiştirin `2` .

   1. Düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı alt yazı** , `Save &As` **kimlik** - `ID_FILE_SAVE_AS` , **resim** `3` ve **görüntü büyük** olarak değiştirin `3` .

   1. Düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı alt yazı** , `&Print` **kimlik** - `ID_FILE_PRINT` , **resim** `4` ve **görüntü büyük** olarak değiştirin `4` .

   1. **Öğe** türünü **ayırıcı** olarak değiştirin ve ardından **Ekle** ' ye tıklayın.

   1. **Öğe** türünü **düğme** olarak değiştirin. Beşinci düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı alt yazı** , `&Close` **kimlik** - `ID_FILE_CLOSE` , **resim** `5` ve **görüntü büyük** olarak değiştirin `5` .

1. Aşağıdaki değişiklikler, önceki adımda oluşturduğunuz **Yazdır** düğmesinin altında bir alt menü oluşturur.

   1. **Yazdır** düğmesine tıklayın, **öğe** türünü **etiket** olarak değiştirin ve ardından **Ekle** ' ye tıklayın. **Açıklamalı alt yazı** değiştirin `Preview and print the document` .

   1. **Yazdır** düğmesine tıklayın, **öğe** türünü **düğme** olarak değiştirin ve **Ekle** ' ye tıklayın. **Açıklamalı alt yazı** , `&Print` **kimlik** - `ID_FILE_PRINT` , **resim** `4` ve **görüntü büyük** olarak değiştirin `4` .

   1. **Yazdır** düğmesine tıklayın ve sonra düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı alt yazı** , `&Quick Print` **kimlik** - `ID_FILE_PRINT_DIRECT` , **resim** `7` ve **görüntü büyük** olarak değiştirin `7` .

   1. **Yazdır** düğmesine tıklayın ve ardından başka bir düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı alt yazı** , `Print Pre&view` **kimlik** - `ID_FILE_PRINT_PREVIEW` , **resim** `6` ve **görüntü büyük** olarak değiştirin `6` .

   1. Artık **ana öğeleri** değiştirdiniz. **Öğe düzenleyicisinden** çıkmak için **Kapat** ' a tıklayın.

1. Aşağıdaki değişiklik, **uygulama** düğmesi menüsünün altında görüntülenen bir çıkış düğmesi oluşturur.

   1. **Çözüm Gezgini** **kaynak görünümü** sekmesini seçin.
   1. **Özellikler** penceresinde, **düğme** ' nin yanındaki üç nokta ( **...** ) simgesine tıklayarak **öğeler düzenleyicisini** açın.

   1. **Öğe** türü **düğmesi** seçili olduğunda, düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı** alt yazı `E&xit` , **ID** `ID_APP_EXIT` , **görüntü** olarak değiştirin `8` .

   1. **Düğmeleri** değiştirdiniz. **Öğe düzenleyicisinden** çıkmak için **Kapat** ' a tıklayın.

## <a name="creating-an-instance-of-the-ribbon-bar"></a><a name="createinstance"></a> Şerit çubuğunun bir örneğini oluşturma

Aşağıdaki adımlarda, uygulamanız başlatıldığında şerit çubuğunun bir örneğinin nasıl oluşturulacağı gösterilmektedir. Bir uygulamaya şerit çubuğu eklemek için MainFrm. h dosyasında Şerit çubuğunu bildirin. Ardından, MainFrm. cpp dosyasında, şerit kaynağını yüklemek için kod yazın.

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>Şerit çubuğunun bir örneğini oluşturmak için

1. MainFrm. h dosyasında, öğesinin korumalı bölümüne `CMainFrame` , ana çerçeveye ait sınıf tanımına bir veri üyesi ekleyin. Bu üye şerit çubuğu içindir.

    ```cpp
    // Ribbon bar for the application
    CMFCRibbonBar m_wndRibbonBar;
    ```

2. MainFrm. cpp dosyasında, işlevin sonundaki son deyimden önce aşağıdaki kodu ekleyin **`return`** `CMainFrame::OnCreate` . Şerit çubuğunun bir örneğini oluşturur.

    ```cpp
    // Create the ribbon bar
    if (!m_wndRibbonBar.Create(this))
    {
        return -1;   //Failed to create ribbon bar
    }
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
    ```

## <a name="customizing-the-ribbon-resource"></a><a name="addcategory"></a> Şerit kaynağını özelleştirme

Artık **uygulama** düğmesini oluşturduğunuza göre, şerit 'e öğe ekleyebilirsiniz.

> [!NOTE]
> Bu izlenecek yol, tüm panolar için aynı panel simgesini kullanır. Bununla birlikte, diğer simgeleri göstermek için diğer resim listesi dizinlerini de kullanabilirsiniz.

### <a name="to-add-a-home-category-and-edit-panel"></a>Bir giriş kategorisi ve düzenleme paneli eklemek için

1. Karalama programı yalnızca bir kategori gerektirir. Tasarım görünümünde, **araç kutusunda** **Kategori** ' ye çift tıklayarak bir tane ekleyin ve özelliklerini görüntüleyin. Özellik değerlerini şu şekilde değiştirin: **açıklamalı alt yazı** `&Home` , **büyük görüntüler** `IDB_RIBBON_HOMELARGE` , **küçük görüntüler** `IDB_RIBBON_HOMESMALL` .

1. Her Şerit kategorisi adlandırılmış panellerde düzenlenir. Her panel ilgili işlemleri tamamlamaya yönelik bir denetim kümesi içerir. Bu kategoride bir panel vardır. **Panel** ' e tıklayın ve ardından **başlık** ' ı değiştirin `Edit` .

1. **Düzenleme** paneline, belgenin içeriğini temizlemeden sorumlu bir düğme ekleyin. Bu düğmenin ileti KIMLIĞI, `IDR_SCRIBBTYPE` menü kaynağında zaten tanımlanmış. Düğme `Clear All` metni ve düğmeyi süsleyecek bit eşlemin dizini olarak belirtin. **Araç kutusunu** açın ve sonra bir **düğmeyi** **düzenleme** paneline sürükleyin. Düğmeye tıklayın ve ardından **başlık** ' ı `Clear All` , **kimlik** ' i `ID_EDIT_CLEAR_ALL` , **görüntü dizini** ' `0` ni, **büyük görüntü dizini** `0` ' ni değiştirin.

1. Değişiklikleri kaydedin ve uygulamayı derleyin ve çalıştırın. Karalama uygulamasının görüntülenmesi gerekir ve bir menü çubuğu yerine pencerenin üst kısmında bir şerit çubuğu olmalıdır. Şerit çubuğunda bir kategori, **giriş** ve **giriş** bir panel, **düzenleme** olmalıdır. Eklediğiniz Şerit düğmelerinin mevcut olay işleyicileriyle ilişkilendirilmesi gerekir ve **Açık** , **kapalı** , **Kaydet** , **Yazdır** ve **Tümünü Temizle** düğmeleri beklendiği gibi çalışmalıdır.

## <a name="setting-the-look-of-the-application"></a><a name="setlook"></a> Uygulamanın görünümünü ayarlama

*Görsel yönetici* , bir uygulamanın tüm çizimini denetleyen genel bir nesnedir. Özgün karalama uygulaması Office 2000 kullanıcı arabirimi (UI) stilini kullandığından, uygulama eski-Fashioned görünebilir. Office 2007 uygulamasına benzer şekilde uygulamayı Office 2007 Visual Manager 'ı kullanacak şekilde sıfırlayabilirsiniz.

### <a name="to-set-the-look-of-the-application"></a>Uygulamanın görünümünü ayarlamak için

1. `CMainFrame::OnCreate`İşlevinde, `return 0;` varsayılan görsel Yöneticisi ve stilini değiştirmek için ifadesinden önce aşağıdaki kodu yazın.

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

1. Değişiklikleri kaydedin ve uygulamayı derleyin ve çalıştırın. Uygulama kullanıcı arabirimi Office 2007 kullanıcı arabirimine benzemelidir.

## <a name="next-steps"></a>Sonraki Adımlar

Klasik karalama 1,0 MFC örneğini, **Şerit Tasarımcısını** kullanacak şekilde değiştirdiniz. Şimdi [Bölüm 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)' ye gidin.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)<br/>
[İzlenecek yol: MFC karalama uygulamasını güncelleştirme (2. bölüm)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)
