---
title: 'İzlenecek yol: Yeni MFC Kabuk Denetimlerini Kullanma'
ms.date: 04/25/2019
helpviewer_keywords:
- shell controls (MFC)
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
ms.openlocfilehash: 5786fbbf7ec9f31e7d895a96dae27b8fc95abda1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360219"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>İzlenecek yol: Yeni MFC Kabuk Denetimlerini Kullanma

Bu izbarada, Dosya Gezgini'ne benzeyen bir uygulama oluşturursunuz. İki bölmeli bir pencere oluşturursunuz. Sol bölmede, Masaüstünüzü hiyerarşik bir görünümde görüntüleyen bir [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) nesnesi bulunur. Sağ bölmede, sol bölmede seçilen klasördeki dosyaları gösteren bir [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) bulunur.

## <a name="prerequisites"></a>Ön koşullar

- Visual Studio 2017 ve sonrası, MFC desteği isteğe bağlı bir bileşendir. Yüklemek için Windows Başlat menüsünden Visual Studio Yükleyici'yi açın. Kullandığınız Visual Studio sürümünü bulun ve **Değiştir** düğmesini seçin. **C++ döşemeli Masaüstü Geliştirme'nin** denetlendirildiğinden emin olun. **İsteğe Bağlı Bileşenler**altında **MFC Destek** düğmesini kontrol edin.

- Bu gözden geçirme, **Genel Geliştirme Ayarlarını**kullanmak üzere Visual Studio'yı kurduğunuzu varsayar. Farklı bir geliştirme ayarı kullanıyorsanız, bu izlenecek yol da kullandığımız bazı Visual Studio pencereleri varsayılan olarak görüntülenmeyebilir.

## <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazı'nı kullanarak yeni bir MFC uygulaması oluşturmak için

Bu adımlar Visual Studio'nun hangi sürümünü kullandığınıza bağlı olarak değişir. Visual Studio'nun tercih ettiğiniz sürümüiçin belgeleri görmek için **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="vs-2019"

### <a name="to-create-an-mfc-project-in-visual-studio-2019"></a>Visual Studio 2019'da bir MFC projesi oluşturmak için

1. Ana menüden, **Yeni Proje Oluştur** iletişim kutusunu açmak için **Yeni** > **Proje** **Dosyası'nı** > seçin.

1. Üstteki arama kutusunda **MFC** yazın ve sonuç listesinden **MFC Uygulamasını** seçin.

1. **İleri**’ye tıklayın. Sonraki sayfada, proje için bir ad girin ve istenirse proje konumunu belirtin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

   **MFC Application Wizard** görüntüledikten sonra aşağıdaki seçenekleri kullanın:

   1. Soldaki **Uygulama Türü'ni** seçin. Ardından **Tek belgeyi** seçin ve **Belge/Görünüm mimarisi desteği'ni**seçin. **Proje stili**altında, **Visual Studio**seçin ve Görsel stil ve **renkler** aşağı liste office **2007 (Mavi tema)** seçin bırakın.

   1. Bileşik **Belge Destek** bölmesine, **Yok'u**seçin.

   1. **Belge Şablon Özellikleri** bölmesinde değişiklik yapmayın.

   1. Kullanıcı **Arabirimi Özellikleri** bölmesinde, **menü çubuğu ve araç çubuğu seçeneğini kullan** seçeneğinin seçildiğinden emin olun. Diğer tüm seçenekleri olduğu gibi bırakın.

   1. Gelişmiş **Özellikler** bölmesinde **ActiveX denetimleri,** **Ortak Denetim Bildirimi**ve Gezinti **bölmesi** seçeneğini seçin. Diğer her şeyi olduğu gibi bırak. **Gezinti Bölmesi** seçeneği, sihirbazın pencerenin solundaki bölmeyi zaten `CMFCShellTreeCtrl` katıştırılmış bir bölmeyle oluşturmasına neden olur.

   1. **Oluşturulan Sınıflar** bölmesinde herhangi bir değişiklik yapmayacağız, bu nedenle yeni MFC projenizi oluşturmak için **Bitir'i** tıklatın.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-an-mfc-project-in-visual-studio-2017-or-earlier"></a>Visual Studio 2017 veya daha önce bir MFC projesi oluşturmak için

1. Yeni bir MFC uygulaması oluşturmak için **MFC Uygulama Sihirbazı'nı** kullanın. Sihirbazı çalıştırmak için **Dosya** menüsünden **Yeni'yi**seçin ve ardından **Project'i**seçin. **Yeni Proje** iletişim kutusu görüntülenir.

1. Yeni **Proje** iletişim kutusunda, **Proje türleri** bölmesinde **Visual C++** düğümünü genişletin ve **MFC'yi**seçin. Ardından, **Şablonlar** bölmesinde **MFC Uygulamasını**seçin. Proje için bir ad yazın, örneğin `MFCShellControls` ve **Tamam'ı**tıklatın.

   **MFC Application Wizard** görüntüledikten sonra aşağıdaki seçenekleri kullanın:

   1. Uygulama **Türü** bölmesinde, **Uygulama türü**altında **Sekmeli belgeler** seçeneğini temizleyin. Ardından, **Tek belgeyi** seçin ve **Belge/Görünüm mimarisi desteği'ni**seçin. **Proje stili**altında, **Visual Studio**seçin ve Görsel stil ve **renkler** aşağı liste office **2007 (Mavi tema)** seçin bırakın.

   1. Bileşik **Belge Destek** bölmesine, **Yok'u**seçin.

   1. **Belge Şablon Dizeleri** bölmesinde değişiklik yapmayın.

   1. Veritabanı **Destek** bölmesi (Visual Studio 2015 ve daha eski) üzerinde, uygulama veritabanı kullanmadığından **Yok'u** seçin.

   1. Kullanıcı **Arabirimi Özellikleri** bölmesinde, **menü çubuğu ve araç çubuğu seçeneğini kullan** seçeneğinin seçildiğinden emin olun. Diğer tüm seçenekleri olduğu gibi bırakın.

   1. Gelişmiş **Özellikler** bölmesinde, **Gelişmiş özellikler**altında yalnızca **ActiveX denetimlerini** ve **Ortak Denetim Bildirimi'ni**seçin. **Gelişmiş çerçeve bölmeleri**altında, yalnızca **Gezinti bölmesi** seçeneğini seçin. Sihirbazın pencerenin solundaki bölmeyi zaten katıştırılmış bir `CMFCShellTreeCtrl` bölmeyle oluşturmasına neden olur.

   1. **Oluşturulan Sınıflar** bölmesinde herhangi bir değişiklik yapmayacağız, bu nedenle yeni MFC projenizi oluşturmak için **Bitir'i** tıklatın.

::: moniker-end

Uygulamanın oluşturularak ve çalıştırılarak başarıyla oluşturulduğunu doğrulayın. Uygulamayı oluşturmak için **Yapı** menüsünden **Çözüm Oluştur'u**seçin. Uygulama başarılı bir şekilde yapılsa, **Hata Ayıklama** Menüsünden **Hata Ayıklama Başlat'ı** seçerek uygulamayı çalıştırın.

Sihirbaz, **klasörler** görünümü ve **Takvim** görünümü içeren pencerenin solunda standart menü çubuğu, standart araç çubuğu, standart durum çubuğu ve Outlook çubuğu olan bir uygulama otomatik olarak oluşturur.

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>Kabuk listesi denetimini belge görünümüne eklemek için

1. Bu bölümde, sihirbazın `CMFCShellListCtrl` oluşturduğu görünüme bir örnek eklersiniz. **Çözüm**Gezgini'nde **MFCShellControlsView.h'yi** çift tıklatarak görünüm üstbilgi dosyasını açın.

   `#pragma once` Yönergeleri üstbilgi dosyasının üst kısmında bulun. Hemen altında için üstbilgi dosyası eklemek için `CMFCShellListCtrl`bu kodu ekleyin:

   ```cpp
   #include <afxShellListCtrl.h>
   ```

   Şimdi türübir `CMFCShellListCtrl`üye değişken ekleyin. İlk olarak, üstbilgi dosyasında aşağıdaki yorumu bulun:

   ```cpp
   // Generated message map functions
   ```

   Bu yorumun hemen üzerine, bu kodu ekleyin:

   ```cpp
   private:
   CMFCShellListCtrl m_wndList;
   ```

1. **MFC Uygulama Sihirbazı** `CMFCShellTreeCtrl` `CMainFrame` zaten sınıfta bir nesne oluşturdu, ancak korunan bir üye. Nesneye daha sonra erişeceğiz, bu yüzden şimdi bir erişime erişim oluşturun. MainFrm.h üstbilgi dosyasını **Çözüm Gezgini'nde**çift tıklatarak açın. Aşağıdaki yorumu bulun:

   ```cpp
   // Attributes
   ```

   Hemen altında, aşağıdaki yöntem bildirimiekleyin:

   ```cpp
   public:
       CMFCShellTreeCtrl& GetShellTreeCtrl();
   ```

   Ardından, **Solution Explorer'da**çift tıklayarak MainFrm.cpp kaynak dosyasını açın. Bu dosyanın alt kısmında aşağıdaki yöntem tanımını ekleyin:

   ```cpp
   CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()
   {
        return m_wndTree;
   }
   ```

1. Şimdi windows `CMFCShellControlsView` iletisini `WM_CREATE` işlemek için sınıfı güncelliyoruz. Sınıf **Görünümü** penceresini açın `CMFCShellControlsView` ve sınıfı seçin. Sağ tıklatın ve **Özellikler**seçin.

   Ardından, [Sınıf Sihirbazı'nda](reference/mfc-class-wizard.md) **İletiler** sekmesini tıklatın. `WM_CREATE` Yanındaki açılır `WM_CREATE`listeden,> ** \<OnCreate ekle'yi**seçin. Komut bizim için bir ileti işleyicisi oluşturur ve MFC ileti eşlemi otomatik olarak güncelleştirir.

   Yöntemde, `OnCreate` şimdi nesnemizi `CMFCShellListCtrl` oluşturacağız. MFCShellControlsView.cpp kaynak dosyasındaki `OnCreate` yöntem tanımını bulun ve uygulanmasını aşağıdaki kodla değiştirin:

    ```cpp
    int CMFCShellControlsView::OnCreate(LPCREATESTRUCT lpCreateStruct)
    {
        if (CView::OnCreate(lpCreateStruct) == -1)
            return -1;

        CRect rectDummy (0, 0, 0, 0);

        m_wndList.Create(WS_CHILD | WS_VISIBLE | LVS_REPORT,
            rectDummy, this, 1);

        return 0;
    }
    ```

1. Önceki adımı ancak ileti `WM_SIZE` için yineleyin. Bir kullanıcı uygulama penceresinin boyutunu değiştirdiğinde uygulama görünümünün yeniden çizilmesine neden olur. Yöntemin tanımını `OnSize` aşağıdaki kodla değiştirin:

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

1. Son adım CMFCShellTreeCtrl kullanarak `CMFCShellTreeCtrl` ve `CMFCShellListCtrl` nesneleri bağlamak [için::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) yöntemi. Aradıktan `CMFCShellTreeCtrl::SetRelatedList`sonra, `CMFCShellListCtrl` 'de seçilen öğenin içeriğini otomatik `CMFCShellTreeCtrl`olarak görüntüler. `OnActivateView` [CView::OnActivateView'dan](../mfc/reference/cview-class.md#onactivateview)geçersiz kılınan yöntemdeki nesneleri bağlıyız.

   MFCShellControlsView.h üstbilgi dosyasında, `CMFCShellControlsView` sınıf bildiriminin içinde aşağıdaki yöntem bildirimini ekleyin:

    ```cpp
    protected:
    virtual void OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView);
    ```

   Ardından, yöntemin tanımını MFCShellControlsView.cpp kaynak dosyasına ekleyin:

    ```cpp
    void CMFCShellControlsView::OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView)
    {
        if (bActivate&& AfxGetMainWnd() != NULL)
        {
            ((CMainFrame*)AfxGetMainWnd())->GetShellTreeCtrl().SetRelatedList(&m_wndList);
        }

        CView::OnActivateView(bActivate,
            pActivateView,
            pDeactiveView);
    }
    ```

   Sınıftan `CMainFrame` yöntemleri aradığımız için, MFCShellControlsView.cpp kaynak dosyasının üst kısmındaki bir `#include` yönerge eklememiz gerekir:

    ```cpp
    #include "MainFrm.h"
    ```

1. Uygulamanın oluşturularak ve çalıştırılarak başarıyla oluşturulduğunu doğrulayın. Uygulamayı oluşturmak için **Yapı** menüsünden **Çözüm Oluştur'u**seçin. Uygulama başarılı bir şekilde yapılsa, **Hata Ayıklama** Menüsünden **Hata Ayıklama Başlat'ı** seçerek çalıştırın.

   Şimdi görünüm bölmesinde `CMFCShellTreeCtrl` seçilen öğenin ayrıntılarını görmeniz gerekir. Bir düğümü `CMFCShellTreeCtrl`tıklattığınızda, düğüm `CMFCShellListCtrl` otomatik olarak güncelleştirilir. Aynı şekilde, bir klasörü çift `CMFCShellListCtrl`tıklattığınızda, otomatik `CMFCShellTreeCtrl` olarak güncelleştirilmelidir.

   Ağaç denetiminde veya liste denetiminde herhangi bir öğeyi sağ tıklatın. Gerçek **Dosya Gezgini'ni**kullanıyormuş gibi aynı bağlam menüsünü alırsınız.

## <a name="next-steps"></a>Sonraki adımlar

- Sihirbaz, hem **Klasörler** bölmesi hem de **Takvim** bölmesini içeren bir Outlook çubuğu oluşturdu. **Explorer** penceresinde **takvim** bölmesi olması muhtemelen mantıklı değildir, bu nedenle bölmeyi şimdi kaldırın.

- Büyük `CMFCShellListCtrl` **Simgeler,** Küçük **Simgeler,** **Liste**ve **Ayrıntılar**gibi farklı modlarda dosyaları görüntülemeyi destekler. Bu işlevselliği uygulamak için uygulamanızı güncelleştirin. İpucu: [bkz. Görsel C++ Örnekleri](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)
