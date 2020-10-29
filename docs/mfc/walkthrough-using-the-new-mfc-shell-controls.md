---
title: 'İzlenecek yol: Yeni MFC Kabuk Denetimlerini Kullanma'
ms.date: 04/25/2019
helpviewer_keywords:
- shell controls (MFC)
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
ms.openlocfilehash: 0d8db9044a64305bd7bb9ef6fe10de9ecef1ce51
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924759"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>İzlenecek yol: Yeni MFC Kabuk Denetimlerini Kullanma

Bu kılavuzda, dosya Gezgini ile benzer bir uygulama oluşturacaksınız. İki bölme içeren bir pencere oluşturacaksınız. Sol bölme, masaüstünüzü hiyerarşik bir görünümde görüntüleyen bir [Cmfcshelltreeci](../mfc/reference/cmfcshelltreectrl-class.md) nesnesi tutar. Sağ bölmede, sol bölmede seçilen klasördeki dosyaları gösteren bir [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) kalır.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 2017 ve üzeri sürümlerde MFC desteği isteğe bağlı bir bileşendir. Yüklemek için, Windows Başlat menüsünden Visual Studio Yükleyicisi açın. Kullandığınız Visual Studio sürümünü bulun ve **Değiştir** düğmesini seçin. C++ kutucuğuna **sahip masaüstü geliştirmenin** seçili olduğundan emin olun. **Isteğe bağlı bileşenler** altında **MFC desteği** düğmesini işaretleyin.

- Bu izlenecek yolda, Visual Studio 'Yu **genel geliştirme ayarlarını** kullanacak şekilde ayarlamış olduğunuz varsayılmaktadır. Farklı bir geliştirme ayarı kullanıyorsanız, bu anlatımda kullandığımız bazı Visual Studio pencereleri varsayılan olarak görüntülenmeyebilir.

## <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazı 'Nı kullanarak yeni bir MFC uygulaması oluşturmak için

Bu adımlar, kullandığınız Visual Studio sürümüne bağlı olarak farklılık gösterir. Visual Studio 'nun tercih ettiğiniz sürümüne ilişkin belgeleri görmek için, **Sürüm** seçici denetimini kullanın. Bu sayfadaki içindekiler tablosunun üst kısmında bulunur.

::: moniker range="msvc-160"

### <a name="to-create-an-mfc-project-in-visual-studio-2019"></a>Visual Studio 2019 ' de MFC projesi oluşturmak için

1. **File** > **New** > **Yeni proje oluştur** iletişim kutusunu açmak için ana menüden dosya yeni **Proje** ' yi seçin.

1. Üstteki arama kutusuna **MFC** yazın ve ardından sonuçlar listesinden **MFC uygulaması** ' nı seçin.

1. **İleri** ’ye tıklayın. Sonraki sayfada, proje için bir ad girin ve isterseniz proje konumunu belirtin.

1. Projeyi oluşturmak için **Oluştur** düğmesini seçin.

   **MFC Uygulama Sihirbazı** görüntülendikten sonra, aşağıdaki seçenekleri kullanın:

   1. Sol tarafta **uygulama türü** ' nu seçin. Sonra **tek belge** ' yi seçin ve **belge/görünüm mimarisi desteği** ' ni seçin. **Proje stili** altında, **Visual Studio** ' yı seçin ve **görsel stil ve renkler** açılan listesinden **Office 2007 (mavi tema)** seçeneğini belirleyin.

   1. **Birleşik belge desteği** bölmesinde **hiçbiri** ' ni seçin.

   1. **Belge şablonu özellikleri** bölmesinde hiçbir değişiklik yapmayın.

   1. **Kullanıcı arabirimi özellikleri** bölmesinde, **bir menü çubuğu ve araç çubuğu kullan** seçeneğinin seçildiğinden emin olun. Diğer tüm seçenekleri olduğu gibi bırakın.

   1. **Gelişmiş Özellikler** bölmesinde, **ActiveX denetimleri** , **ortak denetim bildirimi** ve **Gezinti Bölmesi** seçeneğini belirleyin. Diğer her şeyi olduğu gibi bırakın. **Gezinti Bölmesi** seçeneği, sihirbazın pencerenin sol tarafında zaten eklenmiş olan bölmeyi oluşturmasına neden olur `CMFCShellTreeCtrl` .

   1. **Oluşturulan sınıflar** bölmesinde hiçbir değişiklik yapamıyoruz, bu nedenle yeni MFC projenizi oluşturmak için **son** ' a tıklayın.

::: moniker-end

::: moniker range="<=msvc-150"

### <a name="to-create-an-mfc-project-in-visual-studio-2017-or-earlier"></a>Visual Studio 2017 veya önceki sürümlerde MFC projesi oluşturmak için

1. **MFC Uygulama Sihirbazı 'nı** kullanarak yenı bir MFC uygulaması oluşturun. Sihirbazı çalıştırmak için, **Dosya** menüsünden **Yeni** ' yi seçin ve ardından **Proje** ' yi seçin. **Yeni proje** iletişim kutusu görüntülenir.

1. **Yeni proje** iletişim kutusunda, **proje türleri** bölmesinde **Visual C++** düğümünü genişletin ve **MFC** ' yi seçin. Ardından, **Şablonlar** bölmesinde **MFC uygulaması** ' nı seçin. Proje için bir ad yazın (gibi) `MFCShellControls` ve **Tamam** ' a tıklayın.

   **MFC Uygulama Sihirbazı** görüntülendikten sonra, aşağıdaki seçenekleri kullanın:

   1. **Uygulama türü** bölmesinde, **uygulama türü** altında **sekmeli belgeler** seçeneğini temizleyin. Sonra, **tek belge** ' yi seçin ve **belge/görünüm mimarisi desteği** ' ni seçin. **Proje stili** altında, **Visual Studio** ' yı seçin ve **görsel stil ve renkler** açılan listesinden **Office 2007 (mavi tema)** seçeneğini belirleyin.

   1. **Birleşik belge desteği** bölmesinde **hiçbiri** ' ni seçin.

   1. **Belge şablonu dizeleri** bölmesinde hiçbir değişiklik yapmayın.

   1. **Veritabanı destek** bölmesinde (Visual Studio 2015 ve üzeri), uygulama bir veritabanı kullanmadığından **yok** ' u seçin.

   1. **Kullanıcı arabirimi özellikleri** bölmesinde, **bir menü çubuğu ve araç çubuğu kullan** seçeneğinin seçildiğinden emin olun. Diğer tüm seçenekleri olduğu gibi bırakın.

   1. **Gelişmiş Özellikler** bölmesinde, **Gelişmiş Özellikler** altında yalnızca **ActiveX denetimleri** ve **ortak denetim bildirimi** ' ni seçin. **Gelişmiş çerçeve bölmeleri** altında yalnızca **Gezinti Bölmesi** seçeneğini belirleyin. Sihirbazın pencerenin sol tarafında zaten eklenmiş olan bölmeyi oluşturmasına neden olur `CMFCShellTreeCtrl` .

   1. **Oluşturulan sınıflar** bölmesinde hiçbir değişiklik yapamıyoruz, bu nedenle yeni MFC projenizi oluşturmak için **son** ' a tıklayın.

::: moniker-end

Uygulamanın oluşturup çalıştırarak başarıyla oluşturulduğunu doğrulayın. Uygulamayı derlemek için **Build** menüsünden **Build Solution** ' ı seçin. Uygulama başarıyla yapılıyorsanız **Hata Ayıkla** menüsünden **hata ayıklamayı Başlat** ' ı seçerek uygulamayı çalıştırın.

Sihirbaz, standart bir menü çubuğu, standart bir araç çubuğu, standart bir durum çubuğu ve bir **klasör** görünümü ve **Takvim** görünümü Içeren pencerenin solunda bir Outlook çubuğu olan bir uygulamayı otomatik olarak oluşturur.

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>Kabuk listesi denetimini belge görünümüne eklemek için

1. Bu bölümde, `CMFCShellListCtrl` Sihirbazın oluşturduğu görünüme bir örneği ekleyeceksiniz. **Çözüm Gezgini** Için **MFCShellControlsView. h** öğesine çift tıklayarak görünüm üst bilgisini açın.

   `#pragma once`Üst bilgi dosyasının üst kısmına yakın olan yönergeyi bulun. Hemen altındaki bu kodu, için üst bilgi dosyasını içerecek şekilde ekleyin `CMFCShellListCtrl` :

   ```cpp
   #include <afxShellListCtrl.h>
   ```

   Şimdi türünde bir üye değişkeni ekleyin `CMFCShellListCtrl` . İlk olarak, üstbilgi dosyasında aşağıdaki yorumu bulun:

   ```cpp
   // Generated message map functions
   ```

   Bu açıklamanın hemen üstünde şu kodu ekleyin:

   ```cpp
   private:
   CMFCShellListCtrl m_wndList;
   ```

1. **MFC Uygulama Sihirbazı** sınıfta zaten bir `CMFCShellTreeCtrl` nesne oluşturmuş `CMainFrame` , ancak korumalı bir üye. Daha sonra nesneye erişeceğiz, bu nedenle şimdi bir erişimci oluşturun. MainFrm. h üstbilgi dosyasını **Çözüm Gezgini** açın. Aşağıdaki yorumu bulun:

   ```cpp
   // Attributes
   ```

   Hemen altında, aşağıdaki yöntem bildirimini ekleyin:

   ```cpp
   public:
       CMFCShellTreeCtrl& GetShellTreeCtrl();
   ```

   Sonra, **Çözüm Gezgini** MainFrm. cpp kaynak dosyasını açın. Bu dosyanın en altında, aşağıdaki yöntem tanımını ekleyin:

   ```cpp
   CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()
   {
        return m_wndTree;
   }
   ```

1. Şimdi `CMFCShellControlsView` Windows iletisini işleyecek olan sınıfı güncelleştiririz `WM_CREATE` . **Sınıf görünümü** penceresini açın ve `CMFCShellControlsView` sınıfı seçin. Sağ tıklayın ve **Özellikler** ' i seçin.

   Sonra, [sınıf Sihirbazı](reference/mfc-class-wizard.md)'nda **iletiler** sekmesine tıklayın. İletiyi bulana kadar aşağı kaydırın `WM_CREATE` . Yanındaki aşağı açılan listeden `WM_CREATE` **\<Add> onoluştur** ' u seçin. Komut, ABD için bir ileti işleyicisi oluşturur ve MFC ileti haritasını otomatik olarak güncelleştirir.

   `OnCreate`Yönteminde, şimdi `CMFCShellListCtrl` nesnemizi oluşturacağız. `OnCreate`MFCShellControlsView. cpp kaynak dosyasında yöntem tanımını bulun ve uygulamasını aşağıdaki kodla değiştirin:

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

1. İleti için önceki adımı tekrarlayın `WM_SIZE` . Kullanıcı uygulama penceresinin boyutunu değiştirdiğinde, uygulamalar görünümlerinizin yeniden çizilmesini sağlar. Yöntemi için tanımı `OnSize` aşağıdaki kodla değiştirin:

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

1. Son adım, `CMFCShellTreeCtrl` `CMFCShellListCtrl` [Cmfcshelltreeci:: SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) yöntemini kullanarak ve nesnelerini bağlamak olur. Öğesini çağırdıktan sonra, `CMFCShellTreeCtrl::SetRelatedList` `CMFCShellListCtrl` içinde seçilen öğenin içeriğini otomatik olarak görüntüler `CMFCShellTreeCtrl` . `OnActivateView` [CView:: OnActivateView](../mfc/reference/cview-class.md#onactivateview)öğesinden geçersiz kılınan yöntemdeki nesneleri bağlayacağız.

   MFCShellControlsView. h üstbilgi dosyasında, `CMFCShellControlsView` sınıf bildiriminde, aşağıdaki yöntem bildirimini ekleyin:

    ```cpp
    protected:
    virtual void OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView);
    ```

   Daha sonra, yönteminin tanımını MFCShellControlsView. cpp kaynak dosyasına ekleyin:

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

   Sınıfından Yöntemler çağırırken `CMainFrame` `#include` MFCShellControlsView. cpp kaynak dosyasının en üstüne bir yönerge eklememiz gerekir:

    ```cpp
    #include "MainFrm.h"
    ```

1. Uygulamanın oluşturup çalıştırarak başarıyla oluşturulduğunu doğrulayın. Uygulamayı derlemek için **Build** menüsünden **Build Solution** ' ı seçin. Uygulama başarıyla yapılıyorsanız **Hata Ayıkla** menüsünden **hata ayıklamayı Başlat** ' ı seçerek çalıştırın.

   Artık görünüm bölmesinde seçilen öğenin ayrıntılarını görmeniz gerekir `CMFCShellTreeCtrl` . İçindeki bir düğüme tıkladığınızda, `CMFCShellTreeCtrl` `CMFCShellListCtrl` otomatik olarak güncelleştirilir. Benzer şekilde, içindeki bir klasörü çift tıklattığınızda, `CMFCShellListCtrl` `CMFCShellTreeCtrl` otomatik olarak güncelleştirilmeleri gerekir.

   Ağaç denetimindeki veya liste denetimindeki herhangi bir öğeye sağ tıklayın. Aynı bağlam menüsünü, gerçek **dosya gezginini** kullanmakta olduğunuz gibi alırsınız.

## <a name="next-steps"></a>Sonraki adımlar

- Sihirbaz hem **Klasörler** bölmesi hem de **Takvim** bölmesi olan bir Outlook çubuğu oluşturdu. **Gezgin** penceresinde **Takvim** bölmesi olması mantıklı değildir, bu nedenle bu bölmeyi Şimdi kaldırın.

- , `CMFCShellListCtrl` Dosyaların **büyük simgeler** , **küçük simgeler** , **liste** ve **Ayrıntılar** gibi farklı modlarda görüntülenmesini destekler. Uygulamanızı bu işlevselliği uygulamak için güncelleştirin. İpucu: [Visual C++ örneklerine](../overview/visual-cpp-samples.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)
