---
title: 'İzlenecek yol: MFC karalama uygulamasını güncelleştirme (Bölüm 1)'
ms.date: 04/25/2019
helpviewer_keywords:
- examples [MFC], update existing application
- ribbon UI, porting to
- Office Fluent UI, porting to
- samples [MFC], update existing application
- MFC Feature Pack, update existing application
- walkthroughs [MFC], update existing application
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
ms.openlocfilehash: 71abf84e4c2afd75b0da88c261c78aa04ae08309
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69512929"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>İzlenecek yol: MFC karalama uygulamasını güncelleştirme (Bölüm 1)

Bu izlenecek yol, varolan bir MFC uygulamasının şerit kullanıcı arabirimini kullanmak üzere nasıl değiştirileceğini gösterir. Visual Studio hem Office 2007 şeridini hem de Windows 7 manzara şeridini destekler. Şerit kullanıcı arabirimi hakkında daha fazla bilgi için bkz. [şeritler](/windows/win32/uxguide/cmd-ribbons).

Bu izlenecek yol, fareyi kullanarak çizgi çizimleri oluşturmayı sağlayan Klasik karalama 1,0 MFC örneğini değiştirir. İzlenecek yolun bu bölümünde, karalama örneğinin bir şerit çubuğunu görüntüleyecek şekilde nasıl değiştirileceği gösterilmektedir. [2. Bölüm](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) , şerit çubuğuna daha fazla düğme ekler.

## <a name="prerequisites"></a>Önkoşullar

[Karalama 1,0 MFC örneği](https://download.microsoft.com/download/4/0/9/40946FEC-EE5C-48C2-8750-B0F8DA1C99A8/MFC/general/Scribble.zip.exe). Visual Studio 2017 veya sonraki bir sürüme dönüştürme hakkında yardım için bkz [. taşıma Kılavuzu: MFC Karalama](../porting/porting-guide-mfc-scribble.md).

##  <a name="top"></a>Başlıklı

İzlenecek yolun bu bölümü aşağıdaki bölümlere sahiptir:

- [Taban sınıfları değiştirme](#replaceclass)

- [Projeye bit eşlemler ekleme](#addbitmap)

- [Projeye şerit kaynağı ekleme](#addribbon)

- [Şerit çubuğunun bir örneğini oluşturma](#createinstance)

- [Şerit kategorisi ekleme](#addcategory)

- [Uygulamanın görünümünü ayarlama](#setlook)

##  <a name="replaceclass"></a>Taban sınıfları değiştirme

Bir menüyü destekleyen bir uygulamayı bir şeridi destekleyen bir uygulamaya dönüştürmek için, güncelleştirilmiş temel sınıflardan uygulamayı, çerçeve penceresini ve araç çubuğu sınıflarını türetmeniz gerekir. (Orijinal karalama örneğinizi değiştirmemenizi öneririz. Bunun yerine, karalama projesini temizleyin, başka bir dizine kopyalayın ve sonra kopyayı değiştirin.)

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Karalama uygulamasındaki temel sınıfları değiştirmek için

1. Karalama. cpp içinde, `CScribbleApp::InitInstance` [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)çağrısı içerdiğini doğrulayın.

1. Aşağıdaki kodu stbafx. h dosyasına ekleyin.

    ```cpp
    #include <afxcontrolbars.h>
    ```

1. Karalama. h içinde, `CScribbleApp` sınıfın tanımını [CWinAppEx sınıfından](../mfc/reference/cwinappex-class.md)türetilmiş olacak şekilde değiştirin.

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

1. Windows uygulamaları Kullanıcı tercihi verilerini kaydetmek için bir başlatma (. ini) dosyası kullandıysa karalama 1,0 yazıldı. Bir başlatma dosyası yerine, Kullanıcı tercihlerini kayıt defterine depolamak için karalama 'yı değiştirin. Kayıt defteri anahtarını ve temelini ayarlamak için, ' `CScribbleApp::InitInstance` `LoadStdProfileSettings()` den sonra aşağıdaki kodu yazın.

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

1. Birden çok belge arabirimi (MDI) uygulaması için ana çerçeve artık `CMDIFrameWnd` sınıftan türetilmemektedir. Bunun yerine, [Cmdiframewndex](../mfc/reference/cmdiframewndex-class.md) sınıfından türetilir.

    MainFrm. h ve MainFrm. cpp dosyalarında, tüm başvurularını `CMDIFrameWnd` ile `CMDIFrameWndEx`değiştirin.

1. Childfrm. h ve childfrm. cpp dosyalarında ile `CMDIChildWnd` `CMDIChildWndEx`değiştirin.

    Yazın. h dosyası, ile `CSplitterWnd` `CSplitterWndEx`değiştirin.

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

##  <a name="addbitmap"></a>Projeye bit eşlemler ekleme

Bu izlenecek yolun sonraki dört adımı için bit eşlem kaynakları gerekir. Uygun bit eşlemleri çeşitli yollarla edinebilirsiniz:

- Kendi bit eşlemlerinizi stok için [kaynak düzenleyicilerini](../windows/resource-editors.md) kullanın. Ya da Visual Studio 'da bulunan Taşınabilir Ağ Grafikleri (. png) görüntülerinden bitmapleri birleştirmek için kaynak düzenleyicilerini kullanın ve [Visual Studio görüntü kitaplığından](https://docs.microsoft.com/visualstudio/designers/the-visual-studio-image-library)indirebilirsiniz.

    Ancak, **Şerit** Kullanıcı arabirimi belirli Bit eşlemlerin saydam görüntüleri desteklemesini gerektirir. Saydam bit eşlemler 32 bitlik pikselleri kullanır; burada 24 bit rengin kırmızı, yeşil ve mavi bileşenlerini belirtir ve 8 bit rengin saydamlığını belirten bir *Alfa kanalını* tanımlar. Geçerli kaynak düzenleyicileri, 32 bit pikselle bit eşlemleri görüntüleyebilir, ancak değiştiremez. Sonuç olarak, saydam bit eşlemleri işlemek için kaynak düzenleyicileri yerine bir dış görüntü düzenleyicisi kullanın.

- Başka bir uygulamadaki uygun bir kaynak dosyasını projenize kopyalayın ve ardından bu dosyadaki bit eşlemleri içeri aktarın.

Bu izlenecek yol, kaynak dosyalarını [izlenecek yolda oluşturulan örnekteki kopyalar: MFC](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md)kullanarak şerit uygulaması oluşturma.

### <a name="to-add-bitmaps-to-the-project"></a>Projeye bit eşlemler eklemek için

1. Aşağıdaki. bmp dosyalarını, şerit örneği (`res`) kaynak dizininden karalama projesinin kaynak dizinine (`res`) kopyalamak için dosya Gezgini 'ni kullanın:

   1. Main. bmp 'yi karalama projenize kopyalayın.

   1. Filesmall. bmp ve filelarge. bmp ' i karalama projenize kopyalayın.

   1. Filelarge. bmp ve filesmall. bmp dosyalarının yeni kopyalarını oluşturun, ancak kopyayı şerit örneğine kaydedin. Unmesküçük. bmp ve homelarge. bmp kopyalarını yeniden adlandırıp kopyaları karalama projenize taşıyın.

   1. ToolBar. bmp dosyasının bir kopyasını oluşturun, ancak kopyayı şerit örneğine kaydedin. Copy panelicons. bmp öğesini yeniden adlandırıp kopyayı karalama projenize taşıyın.

1. MFC uygulaması için bit eşlemi içeri aktarın. **Kaynak görünümü**, **karalama. RC** düğümüne çift tıklayın, **bit eşlem** düğümüne çift tıklayın ve ardından **Kaynak Ekle**' ye tıklayın. Görüntülenen iletişim kutusunda **Içeri aktar**' a tıklayın. Dizine gidin, Main. bmp dosyasını seçin ve ardından Aç ' a tıklayın. `res`

   Main. bmp bit eşlemi bir 26x26 görüntüsü içerir. Bit eşlemin KIMLIĞINI olarak `IDB_RIBBON_MAIN`değiştirin.

1. **Uygulama** düğmesine eklenen dosya menüsünün bit eşlemlerini içeri aktarın.

   1. On bir 16x16 (16x176) görüntüleri içeren filesmall. bmp dosyasını içeri aktarın. Bit eşlemin KIMLIĞINI olarak `IDB_RIBBON_FILESMALL`değiştirin.

   > [!NOTE]
   > Yalnızca ilk sekiz 16x16 görüntü (16x128) gerektiğinden, bu bit eşlemin sağ tarafı genişliğini 176 ' den 128 ' e kırpabilirsiniz.

   1. Dokuz 32x32 (32x288) görüntü içeren filelarge. bmp dosyası içeri aktarın. Bit eşlemin KIMLIĞINI olarak `IDB_RIBBON_FILELARGE`değiştirin.

1. Şerit kategorileri ve panellerinin bit eşlemlerini içeri aktarın. Şerit çubuğundaki her sekme bir kategorisidir ve bir metin etiketinden ve isteğe bağlı görüntüden oluşur.

   1. Küçük düğme bit eşlemler için on bir 16x16 görüntü içeren homesküçük. bmp bit eşlemini içeri aktarın. Bit eşlemin KIMLIĞINI olarak `IDB_RIBBON_HOMESMALL`değiştirin.

   1. Büyük düğme bit eşlemler için dokuz 32x32 görüntü içeren homelarge. bmp bit eşlemini içeri aktarın. Bit eşlemin KIMLIĞINI olarak `IDB_RIBBON_HOMELARGE`değiştirin.

1. Yeniden boyutlandırılan şerit panelleri için bit eşlemleri içeri aktarın. Bu bit eşlemler veya panel simgeleri, şerit 'in tüm paneli görüntülemesi için çok küçük olması halinde bir yeniden boyutlandırma işleminden sonra kullanılır.

   1. Sekiz 16x16 görüntü içeren panelicons. bmp bit eşlemini içeri aktarın. **Bit eşlem düzenleyicisinin** **Özellikler** penceresinde, bit eşlemin genişliğini 64 (16x64) olarak ayarlayın. Bit eşlemin KIMLIĞINI olarak `IDB_PANEL_ICONS`değiştirin.

   > [!NOTE]
   > Yalnızca ilk dört 16x16 görüntüsünü (16x64) ihtiyacımız olduğundan, bu bit eşlemin sağ tarafındaki genişliğini 128 ' dan 64 ' e kırpabilirsiniz.

##  <a name="addribbon"></a>Projeye şerit kaynağı ekleme

Menüler kullanan bir uygulamayı şerit kullanan bir uygulamaya dönüştürdüğünüzde, var olan menüleri kaldırmanız veya devre dışı bırakmanız gerekmez. Yalnızca bir şerit kaynağı oluşturun, Şerit düğmeleri ekleyin ve ardından yeni düğmeleri mevcut menü öğeleriyle ilişkilendirin. Menüler artık görünmeyebilir, ancak Şerit çubuğundaki iletiler, menüler ve menü kısayolları aracılığıyla yönlendirilir.

Şerit, şeridin sol üst tarafındaki büyük düğme ve bir veya daha fazla kategori sekmesi olan **uygulama** düğmesinden oluşur. Her kategori sekmesi, Şerit düğmeleri ve denetimleri için kapsayıcılar olarak davranan bir veya daha fazla panel içerir. Aşağıdaki yordamda, bir şerit kaynağı oluşturma ve ardından **uygulama** düğmesini özelleştirme gösterilmektedir.

### <a name="to-add-a-ribbon-resource-to-the-project"></a>Projeye şerit kaynağı eklemek için

1. **Çözüm Gezgini**' de karalama projesi seçiliyken, **Proje** menüsünde **Kaynak Ekle**' ye tıklayın.

1. **Kaynak Ekle** iletişim kutusunda, **Şerit** ' i seçin ve ardından **Yeni**' ye tıklayın.

   Visual Studio bir şerit kaynağı oluşturur ve Tasarım görünümünde açar. Şerit kaynak kimliği `IDR_RIBBON1`, **kaynak görünümü**' de görüntülenir. Şeritte bir kategori ve bir panel bulunur.

1. Özelliklerini değiştirerek **uygulama** düğmesini özelleştirebilirsiniz. Bu kodda kullanılan ileti kimlikleri, karalama 1,0 için menüde zaten tanımlanmıştır.

1. Tasarım görünümünde, özelliklerini görüntülemek için **uygulama** düğmesine tıklayın. Özellik değerlerini aşağıdaki gibi değiştirin: **Görüntüye görüntü** , **komut istemi** `File`, **anahtarlar** , büyük görüntüler`IDB_RIBBON_FILELARGE`ve küçük görüntüler `IDB_RIBBON_FILESMALL`. `f` `IDB_RIBBON_MAIN`

1. Aşağıdaki değişiklikler Kullanıcı **uygulama** düğmesine tıkladığında görüntülenen menüyü oluşturur. **Ana öğeler** ' in yanındaki üç nokta ( **...** ) simgesine tıklayarak **öğeler düzenleyicisini**açın.

   1. **Öğe** türü **düğmesi** seçili olduğunda, düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı** alt yazı `&New`, **ID** to `ID_FILE_NEW`, **Image** to `0`, **Image Large** `0`.

   1. Düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı** alt yazı `&Save` `ID_FILE_SAVE`, **kimlik-** , **resim** `2` ve görüntü büyük olarak değiştirin `2`.

   1. Düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı** alt yazı `Save &As` `ID_FILE_SAVE_AS`, **kimlik-** , **resim** `3` ve görüntü büyük olarak değiştirin `3`.

   1. Düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı** alt yazı `&Print` `ID_FILE_PRINT`, **kimlik-** , **resim** `4` ve görüntü büyük olarak değiştirin `4`.

   1. **Öğe** türünü **ayırıcı** olarak değiştirin ve ardından **Ekle**' ye tıklayın.

   1. **Öğe** türünü **düğme**olarak değiştirin. Beşinci düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı** alt yazı `&Close` `ID_FILE_CLOSE`, **kimlik-** , **resim** `5` ve görüntü büyük olarak değiştirin `5`.

1. Aşağıdaki değişiklikler, önceki adımda oluşturduğunuz **Yazdır** düğmesinin altında bir alt menü oluşturur.

   1. **Yazdır** düğmesine tıklayın, **öğe** türünü **etiket**olarak değiştirin ve ardından **Ekle**' ye tıklayın. **Açıklamalı** alt yazı `Preview and print the document`değiştirin.

   1. **Yazdır** düğmesine tıklayın, **öğe** türünü **düğme**olarak değiştirin ve **Ekle**' ye tıklayın. **Açıklamalı** alt yazı `&Print` `ID_FILE_PRINT`, **kimlik-** , **resim** `4` ve görüntü büyük olarak değiştirin `4`.

   1. **Yazdır** düğmesine tıklayın ve sonra düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı** alt yazı `&Quick Print` `ID_FILE_PRINT_DIRECT`, **kimlik-** , **resim** `7` ve görüntü büyük olarak değiştirin `7`.

   1. **Yazdır** düğmesine tıklayın ve ardından başka bir düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı** alt yazı `Print Pre&view` `ID_FILE_PRINT_PREVIEW`, **kimlik-** , **resim** `6` ve görüntü büyük olarak değiştirin `6`.

   1. Artık **ana öğeleri**değiştirdiniz. **Öğe düzenleyicisinden**çıkmak için **Kapat** ' a tıklayın.

1. Aşağıdaki değişiklik, **uygulama** düğmesi menüsünün altında görüntülenen bir çıkış düğmesi oluşturur.

   1. **Özellikler** penceresinde, **düğme** ' nin yanındaki üç nokta ( **...** ) simgesine tıklayarak **öğeler düzenleyicisini**açın.

   1. **Öğe** türü **düğmesi** seçili olduğunda, düğme eklemek için **Ekle** ' ye tıklayın. **Açıklamalı** alt yazı `E&xit` `ID_APP_EXIT`, **ID,** görüntü olarak değiştirin. `8`

   1. **Düğmeleri**değiştirdiniz. **Öğe düzenleyicisinden**çıkmak için **Kapat** ' a tıklayın.

##  <a name="createinstance"></a>Şerit çubuğunun bir örneğini oluşturma

Aşağıdaki adımlarda, uygulamanız başlatıldığında şerit çubuğunun bir örneğinin nasıl oluşturulacağı gösterilmektedir. Bir uygulamaya şerit çubuğu eklemek için MainFrm. h dosyasında Şerit çubuğunu bildirin. Ardından, MainFrm. cpp dosyasında, şerit kaynağını yüklemek için kod yazın.

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>Şerit çubuğunun bir örneğini oluşturmak için

1. MainFrm. h dosyasında, öğesinin `CMainFrame`korumalı bölümüne, ana çerçeveye ait sınıf tanımına bir veri üyesi ekleyin. Bu üye şerit çubuğu içindir.

    ```cpp
    // Ribbon bar for the application
    CMFCRibbonBar m_wndRibbonBar;
    ```

2. MainFrm. cpp dosyasında, `return` `CMainFrame::OnCreate` işlevin sonundaki son deyimden önce aşağıdaki kodu ekleyin. Şerit çubuğunun bir örneğini oluşturur.

    ```cpp
    // Create the ribbon bar
    if (!m_wndRibbonBar.Create(this))
    {
        return -1;   //Failed to create ribbon bar
    }
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
    ```

##  <a name="addcategory"></a>Şerit kaynağını özelleştirme

Artık **uygulama** düğmesini oluşturduğunuza göre, şerit 'e öğe ekleyebilirsiniz.

> [!NOTE]
> Bu izlenecek yol, tüm panolar için aynı panel simgesini kullanır. Bununla birlikte, diğer simgeleri göstermek için diğer resim listesi dizinlerini de kullanabilirsiniz.

### <a name="to-add-a-home-category-and-edit-panel"></a>Bir giriş kategorisi ve düzenleme paneli eklemek için

1. Karalama programı yalnızca bir kategori gerektirir. Tasarım görünümünde, **araç kutusunda** **Kategori** ' ye çift tıklayarak bir tane ekleyin ve özelliklerini görüntüleyin. Özellik değerlerini aşağıdaki gibi değiştirin: **Açıklamalı alt yazı** `IDB_RIBBON_HOMESMALL`,büyük **görüntü** , küçük resim `IDB_RIBBON_HOMELARGE`. `&Home`

1. Her Şerit kategorisi adlandırılmış panellerde düzenlenir. Her panel ilgili işlemleri tamamlamaya yönelik bir denetim kümesi içerir. Bu kategoride bir panel vardır. **Panel**' e `Edit`tıklayın ve ardından **başlık** ' ı değiştirin.

1. **Düzenleme** paneline, belgenin içeriğini temizlemeden sorumlu bir düğme ekleyin. Bu düğmenin ileti kimliği, `IDR_SCRIBBTYPE` menü kaynağında zaten tanımlanmış. Düğme `Clear All` metni ve düğmeyi süsleyecek bit eşlemin dizini olarak belirtin. **Araç kutusunu**açın ve sonra bir **düğmeyi** **düzenleme** paneline sürükleyin. Düğmeye tıklayın ve ardından **başlık** `Clear All`' ı, **kimlik** `ID_EDIT_CLEAR_ALL`' i `0`, **görüntü dizini** `0`' ni, **büyük görüntü dizini** ' ni değiştirin.

1. Değişiklikleri kaydedin ve uygulamayı derleyin ve çalıştırın. Karalama uygulamasının görüntülenmesi gerekir ve bir menü çubuğu yerine pencerenin üst kısmında bir şerit çubuğu olmalıdır. Şerit çubuğunda bir kategori, **giriş**ve **giriş** bir panel, **düzenleme**olmalıdır. Eklediğiniz Şerit düğmelerinin mevcut olay işleyicileriyle ilişkilendirilmesi gerekir ve **Açık**, **kapalı**, **Kaydet**, **Yazdır**ve **Tümünü Temizle** düğmeleri beklendiği gibi çalışmalıdır.

##  <a name="setlook"></a>Uygulamanın görünümünü ayarlama

*Görsel yönetici* , bir uygulamanın tüm çizimini denetleyen genel bir nesnedir. Özgün karalama uygulaması Office 2000 kullanıcı arabirimi (UI) stilini kullandığından, uygulama eski-Fashioned görünebilir. Office 2007 uygulamasına benzer şekilde uygulamayı Office 2007 Visual Manager 'ı kullanacak şekilde sıfırlayabilirsiniz.

### <a name="to-set-the-look-of-the-application"></a>Uygulamanın görünümünü ayarlamak için

1. İşlevinde, varsayılan görsel Yöneticisi ve stilini değiştirmek için `return 0;` ifadesinden önce aşağıdaki kodu yazın. `CMainFrame::OnCreate`

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

1. Değişiklikleri kaydedin ve uygulamayı derleyin ve çalıştırın. Uygulama kullanıcı arabirimi Office 2007 kullanıcı arabirimine benzemelidir.

## <a name="next-steps"></a>Sonraki Adımlar

Klasik karalama 1,0 MFC örneğini, **Şerit Tasarımcısını**kullanacak şekilde değiştirdiniz. Şimdi [Bölüm 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)' ye gidin.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)<br/>
[İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (2. Bölüm)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)
