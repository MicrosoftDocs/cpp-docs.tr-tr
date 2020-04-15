---
title: 'İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (1. Bölüm)'
ms.date: 09/09/2019
helpviewer_keywords:
- examples [MFC], update existing application
- ribbon UI, porting to
- Office Fluent UI, porting to
- samples [MFC], update existing application
- MFC Feature Pack, update existing application
- walkthroughs [MFC], update existing application
ms.assetid: aa6330d3-6cfc-4c79-8fcb-0282263025f7
ms.openlocfilehash: 18803d2222c80b80ac2b1fde75b442ea1e9a89bb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360254"
---
# <a name="walkthrough-updating-the-mfc-scribble-application-part-1"></a>İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (1. Bölüm)

Bu gözden geçirme, Varolan bir MFC uygulamasını Şerit kullanıcı arabirimini kullanmak için nasıl değiştirilebildiğini gösterir. Visual Studio hem Office 2007 Şeridini hem de Windows 7 Scenic Ribbon'u destekler. Şerit kullanıcı arabirimi hakkında daha fazla bilgi için [Şeritler'e](/windows/win32/uxguide/cmd-ribbons)bakın.

Bu izbis, çizgi çizimleri oluşturmak için fareyi kullanmanıza olanak tanıyan klasik Karalama 1.0 MFC örneğini değiştirir. Gözden geçirme nin bu bölümü, Karalama örneğinin şerit çubuğunu görüntüleyecek şekilde nasıl değiştirilebildiğini gösterir. [Bölüm 2](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md) şerit çubuğuna daha fazla düğme ekler.

## <a name="prerequisites"></a>Ön koşullar

[Karalama 1.0 MFC örneği.](https://download.microsoft.com/download/4/0/9/40946FEC-EE5C-48C2-8750-B0F8DA1C99A8/MFC/general/Scribble.zip.exe) Visual Studio 2017 veya sonraki lere dönüştürme konusunda yardım için [Porting Guide: MFC Scribble](../porting/porting-guide-mfc-scribble.md)' a bakın.

## <a name="sections"></a><a name="top"></a>Bölüm

Bu bölümün bu bölümü aşağıdaki bölümlere sahiptir:

- [Temel Sınıfların Değiştirilmesi](#replaceclass)

- [Projeye Bit Eş ekleme](#addbitmap)

- [Projeye Şerit Kaynağı Ekleme](#addribbon)

- [Şerit Çubuğu Örneği Oluşturma](#createinstance)

- [Şerit Kategorisi Ekleme](#addcategory)

- [Uygulamanın Görünümünü Ayarlama](#setlook)

## <a name="replacing-the-base-classes"></a><a name="replaceclass"></a>Temel Sınıfların Değiştirilmesi

Menüyü destekleyen bir uygulamayı şeridi destekleyen bir uygulamaya dönüştürmek için, uygulama, çerçeve penceresi ve araç çubuğu sınıflarını güncelleştirilmiş taban sınıflardan türemelisiniz. (Orijinal Karalama örneğini değiştirmemenizi öneririz. Bunun yerine, Karalama projesini temizleyin, başka bir dizine kopyalayın ve ardından kopyayı değiştirin.)

### <a name="to-replace-the-base-classes-in-the-scribble-application"></a>Karalama uygulamasındaki temel sınıfları değiştirmek için

1. Scribble.cpp olarak, `CScribbleApp::InitInstance` [AfxOleInit](../mfc/reference/ole-initialization.md#afxoleinit)bir çağrı içerir doğrulayın.

1. *Pch.h* dosyasına aşağıdaki kodu ekleyin (Visual Studio 2017 ve önceki*stdafx.h):*

    ```cpp
    #include <afxcontrolbars.h>
    ```

1. Scribble.h olarak, `CScribbleApp` [cWinAppEx Sınıf](../mfc/reference/cwinappex-class.md)türetilmiş olacak şekilde sınıf için tanımı değiştirin.

    ```cpp
    class CScribbleApp: public CWinAppEx
    ```

1. Windows uygulamaları kullanıcı tercihi verilerini kaydetmek için bir başlatma (.ini) dosyası kullandığında Karalama 1.0 yazılmıştır. Bir başlatma dosyası yerine, Scribble'ı kullanıcı tercihlerini kayıt defterinde depolamak için değiştirin. Kayıt defteri anahtarını ve tabanını ayarlamak `CScribbleApp::InitInstance` için, `LoadStdProfileSettings()` deyimden sonra aşağıdaki kodu yazın.

    ```cpp
    SetRegistryKey(_T("MFCNext\\Samples\\Scribble2"));
    SetRegistryBase(_T("Settings"));
    ```

1. Birden çok belge arabirimi (MDI) uygulamasının ana `CMDIFrameWnd` çerçevesi artık sınıftan türetilmiş değil. Bunun yerine, [CMDIFrameWndEx](../mfc/reference/cmdiframewndex-class.md) sınıfından türetilmiştir.

    mainfrm.h ve mainfrm.cpp dosyalarında, tüm `CMDIFrameWnd` `CMDIFrameWndEx`başvuruları .

1. childfrm.h ve childfrm.cpp `CMDIChildWnd` dosyalarında, `CMDIChildWndEx`değiştirin.

    Çocuk frm'inde. h dosyası, `CSplitterWnd` `CSplitterWndEx`değiştirin.

1. Yeni MFC sınıflarını kullanmak için araç çubuklarını ve durum çubuklarını değiştirin.

    mainfrm.h dosyasında:

    1. `CToolBar` yerine `CMFCToolBar` yazın.

    1. `CStatusBar` yerine `CMFCStatusBar` yazın.

1. mainfrm.cpp dosyasında:

    1. Değiştir `m_wndToolBar.SetBarStyle``m_wndToolBar.SetPaneStyle`

    1. Değiştir `m_wndToolBar.GetBarStyle``m_wndToolBar.GetPaneStyle`

    1. Değiştir `DockControlBar(&m_wndToolBar)``DockPane(&m_wndToolBar)`

1. ipframe.cpp dosyasında, aşağıdaki üç kod satırına yorum yapın.

    ```cpp
    m_wndToolBar.EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->EnableDocking(CBRS_ALIGN_ANY);
    pWndFrame->DockPane(&m_wndToolBar);
    ```

1. Değişiklikleri kaydedin ve uygulamayı oluşturun ve çalıştırın.

## <a name="adding-bitmaps-to-the-project"></a><a name="addbitmap"></a>Projeye Bit Eş ekleme

Bu izlenecek yoldaki sonraki dört adım bit eşlemi kaynakları gerektirir. Uygun bit eşlemlerini çeşitli şekillerde alabilirsiniz:

- Kendi bit eşlerinizi icat etmek için [Kaynak Düzenleyicileri'ni](../windows/resource-editors.md) kullanın. Veya Visual Studio ile birlikte olan ve [Visual Studio görüntü kitaplığından](https://docs.microsoft.com/visualstudio/designers/the-visual-studio-image-library)indirilebilen taşınabilir ağ grafikleri (.png) görüntülerinden bit eşlemlerini bir araya getirmek için kaynak editörlerini kullanın.

    Ancak, **Şerit** kullanıcı arabirimi, belirli bit eşlemlerin saydam görüntüleri desteklemesini gerektirir. Saydam bit eşlemler, 24 bitin rengin kırmızı, yeşil ve mavi bileşenlerini, 8 bitin ise rengin saydamlıkını belirten bir *alfa kanalını* tanımladığı 32 bitlik pikseller kullanır. Geçerli kaynak düzenleyicileri, bit eşlemlerini 32 bit pikselle görüntüleyebilir, ancak değiştiremez. Sonuç olarak, saydam bit eşlemlerini işlemek için kaynak düzenleyicileri yerine harici bir görüntü düzenleyicisi kullanın.

- Başka bir uygulamadan projenize uygun bir kaynak dosyasını kopyalayın ve ardından bu dosyadan bit eşlemleri alın.

Bu gözden geçirme, Kaynak dosyalarını [Walkthrough: MFC kullanarak şerit uygulaması oluşturma'da](../mfc/walkthrough-creating-a-ribbon-application-by-using-mfc.md)oluşturulan örnekten kopyalar.

### <a name="to-add-bitmaps-to-the-project"></a>Projeye bit eşlemeklemek için

1. Şerit örneğinin kaynak dizininden (`res`) karalama projesinin kaynak dizinine (`res`) aşağıdaki .bmp dosyalarını kopyalamak için Dosya Gezgini'ni kullanın:

   1. Scribble projenize main.bmp kopyalayın.

   1. Scribble projenize filesmall.bmp ve filelarge.bmp kopyalayın.

   1. Filelarge.bmp ve filesmall.bmp dosyalarının yeni kopyalarını yapın, ancak kopyaları Şerit örneğine kaydedin. Kopyaları homesmall.bmp ve homelarge.bmp olarak yeniden adlandırın ve kopyaları Karalama projenize taşıyın.

   1. Araç çubuğu.bmp dosyasının bir kopyasını yapın, ancak kopyayı Şerit örneğine kaydedin. Kopya panelicons.bmp'yi yeniden adlandırın ve kopyayı Karalama projenize taşıyın.

1. Bir MFC uygulaması için bit eşlemi aktarın. **Kaynak Görünümü'nde**, **karalama.rc** düğümüne çift tıklayın, **Bitmap** düğüme çift tıklayın ve ardından **kaynak ekle'yi**tıklatın. Görünen iletişim kutusunda, **İçe Aktar'ı**tıklatın. Dizine `res` göz atın, main.bmp dosyasını seçin ve sonra **Aç'ı**tıklatın.

   Main.bmp bitmap 26x26 görüntü içerir. Bit haritasının kimliğini `IDB_RIBBON_MAIN`' olarak değiştirin

1. **Uygulama** düğmesine bağlı dosya menüsüiçin bit eşlemlerini içeri aktarın.

   1. On bir 16x16 (16x176) görüntü içeren filesmall.bmp dosyasını içeri aktarın. Bit haritasının kimliğini `IDB_RIBBON_FILESMALL`' olarak değiştirin

   > [!NOTE]
   > Sadece ilk sekiz 16x16 görüntüye (16x128) ihtiyacımız olduğundan, isteğe bağlı olarak bu bit eşleminin sağ kenar genişliğini 176'dan 128'e çıkarabilirsiniz.

   1. Dokuz 32x32 (32x288) görüntü içeren filelarge.bmp'yi içeri aktarın. Bit haritasının kimliğini `IDB_RIBBON_FILELARGE`' olarak değiştirin

1. Şerit kategorileri ve panelleri için bit eşlemlerini içeri aktarın. Şerit çubuğundaki her sekme bir kategoridir ve bir metin etiketi ve isteğe bağlı bir resimden oluşur.

   1. Küçük düğme bit eşlemleri için on bir 16x16 görüntü içeren homesmall.bmp bitmap'i içe aktarın. Bit haritasının kimliğini `IDB_RIBBON_HOMESMALL`' olarak değiştirin

   1. Büyük düğme bit eşlemleri için dokuz 32x32 görüntü içeren homelarge.bmp bitmap'i içe aktarın. Bit haritasının kimliğini `IDB_RIBBON_HOMELARGE`' olarak değiştirin

1. Yeniden boyutlandırılmış şerit panelleri için bit eşlemlerini içe aktarın. Bu bit eşlemler veya panel simgeleri, şeridin tamamını görüntülemek için çok küçükse, yeniden boyutlandırma işleminden sonra kullanılır.

   1. Sekiz 16x16 görüntü içeren panelicons.bmp bitmap, içe aktarın. **Bitmap**Düzenleyicisi'nin **Özellikler** penceresinde bit eşleminin genişliğini 64 (16x64) olarak ayarlayın. Bit haritasının kimliğini `IDB_PANEL_ICONS`' olarak değiştirin

   > [!NOTE]
   > Sadece ilk dört 16x16 görüntüye (16x64) ihtiyacımız olduğundan, isteğe bağlı olarak bu bit eşleminin sağ yan genişliğini 128'den 64'e çıkarabilirsiniz.

## <a name="adding-a-ribbon-resource-to-the-project"></a><a name="addribbon"></a>Projeye Şerit Kaynağı Ekleme

Menüleri kullanan bir uygulamayı şerit kullanan bir uygulamaya dönüştürdüğünüzde, varolan menüleri kaldırmanız veya devre dışı kaldırmanız gerekmez. Bir şerit kaynağı oluşturun, şerit düğmeleri ekleyin ve ardından yeni düğmeleri varolan menü öğeleriyle ilişkilendirin. Menüler artık görünür olmasa da, şerit çubuğundan gelen iletiler menüler aracılığıyla yönlendirilir ve menü kısayolları çalışmaya devam eder.

Şerit, şeridin sol üst tarafındaki büyük düğme olan **Uygulama** düğmesinden ve bir veya daha fazla kategori sekmesinden oluşur. Her kategori sekmesi, şerit düğmeleri ve denetimleri için kapsayıcı görevi yapan bir veya daha fazla panel içerir. Aşağıdaki yordam, şerit kaynağının nasıl oluşturulup ardından **Uygulama** düğmesini nasıl özelleştirileştirilebildiğini gösterir.

### <a name="to-add-a-ribbon-resource-to-the-project"></a>Projeye şerit kaynağı eklemek için

1. **Çözüm Gezgini'nde**seçilen Karalama projesiyle, **Proje** menüsünde **Kaynak Ekle'yi**tıklatın.

1. Kaynak **Ekle** iletişim kutusunda **Şerit'i** seçin ve ardından **Yeni'yi**tıklatın.

   Visual Studio bir şerit kaynağı oluşturur ve tasarım görünümünde açar. Şerit kaynak `IDR_RIBBON1`kimliği, Kaynak **Görünümü'nde**görüntülenir. Şerit bir kategori ve bir panel içerir.

1. Özelliklerini değiştirerek **Uygulama** düğmesini özelleştirebilirsiniz. Bu kodda kullanılan ileti işlemi, Karalama 1.0' ın menüsünde zaten tanımlanmıştır.

1. Tasarım görünümünde, özelliklerini görüntülemek için **Uygulama** düğmesini tıklatın. Özellik değerlerini aşağıdaki gibi `IDB_RIBBON_MAIN`değiştirin: **Görüntü** `f`, **İstem** `File`, **Anahtarlar** , **Büyük Görüntüler** `IDB_RIBBON_FILELARGE`ve **Küçük Görüntüler** için `IDB_RIBBON_FILESMALL`.

1. Aşağıdaki değişiklikler, kullanıcı **Uygulama** düğmesini tıklattığında görünen menüyü oluşturur. Öğeler Düzenleyicisi'ni açmak için **Ana Öğeler'in** yanındaki elips (**...**) öğesini tıklatın. **Items Editor**

   1. **Öğe** türü **Düğmesi** seçilise, düğme eklemek için **Ekle'yi** tıklatın. Resim Yazı `&New`resim **yazısını** `0`, **Id** `ID_FILE_NEW`için , **Resim** için, **Resim Büyük** ' e `0`değiştirin.

   1. Düğme eklemek için **Ekle'yi** tıklatın. Resim Yazı `&Save`Resim **Yazısını** `2`, **Id** 'de `ID_FILE_SAVE`, **Görüntü'ye** ve **Resim Büyük** 'e `2`değiştirin.

   1. Düğme eklemek için **Ekle'yi** tıklatın. Resim Yazı `Save &As`Resim **Yazısını** `3`, **Id** 'de `ID_FILE_SAVE_AS`, **Görüntü'ye** ve **Resim Büyük** 'e `3`değiştirin.

   1. Düğme eklemek için **Ekle'yi** tıklatın. Resim Yazı `&Print`Resim **Yazısını** `4`, **Id** 'de `ID_FILE_PRINT`, **Görüntü'ye** ve **Resim Büyük** 'e `4`değiştirin.

   1. **Öğe** türünü **Ayırıcı** olarak değiştirin ve sonra **Ekle'yi**tıklatın.

   1. **Öğe** türünü **Düğme**olarak değiştirin. Beşinci düğme eklemek için **Ekle'yi** tıklatın. Resim Yazı `&Close`Resim **Yazısını** `5`, **Id** 'de `ID_FILE_CLOSE`, **Görüntü'ye** ve **Resim Büyük** 'e `5`değiştirin.

1. Aşağıdaki değişiklikler, önceki adımda oluşturduğunuz **Yazdır** düğmesinin altında bir alt menü oluşturur.

   1. **Yazdır** düğmesini tıklatın, **Öğe** türünü **Etiket**olarak değiştirin ve ardından **Ekle'yi**tıklatın. **Resim Yazısını** ' ile `Preview and print the document`değiştir

   1. **Yazdır** düğmesini tıklatın, **Öğe** türünü **Düğme'ye**değiştirin ve **Ekle'yi**tıklatın. Resim Yazı `&Print`Resim **Yazısını** `4`, **Id** 'de `ID_FILE_PRINT`, **Görüntü'ye** ve **Resim Büyük** 'e `4`değiştirin.

   1. **Yazdır** düğmesini tıklatın ve ardından bir düğme eklemek için **Ekle'yi** tıklatın. Resim Yazı `&Quick Print`Resim **Yazısını** `7`, **Id** 'de `ID_FILE_PRINT_DIRECT`, **Görüntü'ye** ve **Resim Büyük** 'e `7`değiştirin.

   1. **Yazdır** düğmesini tıklatın ve sonra başka bir düğme eklemek için **Ekle'yi** tıklatın. Resim Yazı `Print Pre&view`Resim **Yazısını** `6`, **Id** 'de `ID_FILE_PRINT_PREVIEW`, **Görüntü'ye** ve **Resim Büyük** 'e `6`değiştirin.

   1. **Şimdi Ana Öğeleri**değiştirdiniz. **Öğeler**Düzenleyicisi'nden çıkmak için **Kapat'ı** tıklatın.

1. Aşağıdaki **değişiklik, Uygulama** düğmesi menüsünün alt kısmında görünen bir çıkış düğmesi oluşturur.

   1. **Çözüm Gezgini'nde** **Kaynak Görünümü** sekmesini seçin.
   1. **Özellikler** penceresinde, Öğeler Düzenleyicisi'ni açmak için **Düğme'nin** yanındaki elipsis (**...**) düğmesini tıklatın. **Items Editor**

   1. **Öğe** türü **Düğmesi** seçilise, düğme eklemek için **Ekle'yi** tıklatın. **Resim Yazıresim'i** `E&xit`, `8` **Id** 'de `ID_APP_EXIT`, **Resim** 'e değiştirin.

   1. **Düğmeleri**değiştirdiniz. **Öğeler**Düzenleyicisi'nden çıkmak için **Kapat'ı** tıklatın.

## <a name="creating-an-instance-of-the-ribbon-bar"></a><a name="createinstance"></a>Şerit Çubuğu Örneği Oluşturma

Aşağıdaki adımlar, uygulamanız başladığında şerit çubuğunun bir örneğinin nasıl oluşturulbekleyeceğini gösterir. Bir uygulamaya şerit çubuğu eklemek için mainfrm.h dosyasındaki şerit çubuğunu bildirin. Ardından, mainfrm.cpp dosyasında, şerit kaynağını yüklemek için kod yazın.

### <a name="to-create-an-instance-of-the-ribbon-bar"></a>Şerit çubuğunun bir örneğini oluşturmak için

1. mainfrm.h dosyasında, ana çerçevenin sınıf tanımı `CMainFrame`olan korumalı bölümüne bir veri üyesi ekleyin. Bu üye şerit çubuğu içindir.

    ```cpp
    // Ribbon bar for the application
    CMFCRibbonBar m_wndRibbonBar;
    ```

2. mainfrm.cpp dosyasında, `return` `CMainFrame::OnCreate` işlevin sonundaki son ifadeden önce aşağıdaki kodu ekleyin. Şerit çubuğunun bir örneğini oluşturur.

    ```cpp
    // Create the ribbon bar
    if (!m_wndRibbonBar.Create(this))
    {
        return -1;   //Failed to create ribbon bar
    }
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);
    ```

## <a name="customizing-the-ribbon-resource"></a><a name="addcategory"></a>Şerit Kaynağını Özelleştirme

**Uygulama** düğmesini oluşturduğunuza göre, şerite öğeler ekleyebilirsiniz.

> [!NOTE]
> Bu walkthrough tüm paneller için aynı panel simgesini kullanır. Ancak, diğer simgeleri görüntülemek için diğer resim listesi dizinlerini kullanabilirsiniz.

### <a name="to-add-a-home-category-and-edit-panel"></a>Ana Sayfa kategorisi ve Panel'i Edit eklemek için

1. Karalama programı yalnızca bir kategori gerektirir. Tasarım görünümünde, **Araç Kutusu'nda,** kategoriyi çift tıklatın ve bir tane ekleyin ve özelliklerini görüntüleyin. **Category** Özellik değerlerini aşağıdaki gibi `&Home`değiştirin: Resim **yazısı** `IDB_RIBBON_HOMESMALL`, Büyük **Görüntüler** için `IDB_RIBBON_HOMELARGE`, Küçük **Görüntüler** için .

1. Her şerit kategorisi adlandırılmış paneller halinde düzenlenir. Her panel, ilgili işlemleri tamamlayan bir denetim kümesi içerir. Bu kategoride bir panel vardır. **Panel'i**tıklatın ve `Edit`ardından **Resim Yazısı'nı** ' olarak değiştirin.

1. **Edit** paneline, belgenin içeriğini temizlemekten sorumlu bir düğme ekleyin. Bu düğmenin ileti kimliği `IDR_SCRIBBTYPE` menü kaynağında zaten tanımlanmıştır. Düğme `Clear All` metni ni ve düğmeyi süsleyen bit eşlemi dizini olarak belirtin. Araç **Kutusunu**açın ve ardından **düğmeyi** **Düzenleme** paneline sürükleyin. Düğmeyi tıklatın ve ardından `Clear All`Resim `ID_EDIT_CLEAR_ALL` **Yazısı'nı** `0`, **Kimlik** için `0`, **Resim Dizini** için , Büyük **Görüntü Dizini'ne** ' olarak değiştirin.

1. Değişiklikleri kaydedin ve uygulamayı oluşturun ve çalıştırın. Karalama uygulaması görüntülenmeli ve pencerenin üst kısmında menü çubuğu yerine bir şerit çubuğu olmalıdır. Şerit çubuğunda bir kategori olmalı, **Ana Sayfa**ve **Ev** bir panel esahip olmalıdır, **Edit**. Eklediğiniz şerit düğmeleri varolan olay işleyicileri ile ilişkili olmalıdır ve **Açık**, **Kapat**, **Kaydet,** **Yazdır**ve **Tüm düğmeleri temizle** düğmeleri beklendiği gibi çalışmalıdır.

## <a name="setting-the-look-of-the-application"></a><a name="setlook"></a>Uygulamanın Görünümünü Ayarlama

*Görsel yönetici,* bir uygulama için tüm çizimleri denetleyen genel bir nesnedir. Özgün Karalama uygulaması Office 2000 kullanıcı arabirimi (UI) stilini kullandığından, uygulama eski moda görünebilir. Office 2007 görsel yöneticisini kullanmak için uygulamayı sıfırlayabilirsiniz, böylece Office 2007 uygulamasına benzer.

### <a name="to-set-the-look-of-the-application"></a>Uygulamanın görünümünü ayarlamak için

1. İşlevde, `CMainFrame::OnCreate` varsayılan görsel yönetici `return 0;` ve stili değiştirmek için deyimden önce aşağıdaki kodu yazın.

    ```cpp
    // Set the default manager to Office 2007
    CMFCVisualManager::SetDefaultManager(RUNTIME_CLASS(CMFCVisualManagerOffice2007));
    CMFCVisualManagerOffice2007::SetStyle(CMFCVisualManagerOffice2007::Office2007_LunaBlue);
    ```

1. Değişiklikleri kaydedin ve uygulamayı oluşturun ve çalıştırın. Uygulama Kullanıcı GIçini Office 2007 Kullanıcı Yı'na benzemelidir.

## <a name="next-steps"></a>Sonraki Adımlar

**Şerit Tasarımcısı'nı**kullanmak için klasik Karalama 1.0 MFC örneğini değiştirdiniz. Şimdi [Bölüm 2'ye](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)git.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)<br/>
[İzlenecek yol: MFC Karalama Uygulamasını Güncelleştirme (2. Bölüm)](../mfc/walkthrough-updating-the-mfc-scribble-application-part-2.md)
