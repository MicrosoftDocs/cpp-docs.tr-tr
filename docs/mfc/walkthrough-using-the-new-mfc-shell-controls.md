---
title: 'İzlenecek yol: Yeni MFC Kabuk denetimlerini kullanma'
ms.date: 04/25/2019
helpviewer_keywords:
- shell controls (MFC)
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
ms.openlocfilehash: b75568c0207dc004bbdb919427e4f3f6860c4a81
ms.sourcegitcommit: 283cb64fd7958a6b7fbf0cd8534de99ac8d408eb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64558141"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>İzlenecek yol: Yeni MFC Kabuk denetimlerini kullanma

Bu kılavuzda, dosya Gezgini'ne benzeyen bir uygulama oluşturacaksınız. İki bölme içeren bir pencere oluşturacaksınız. Sol bölmede tutacak bir [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) Masaüstü hiyerarşik bir görünümde görüntüleyen bir nesne. Sağ bölmede tutacak bir [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) sol bölmede seçtiğiniz klasördeki dosyaların gösterir.

## <a name="prerequisites"></a>Önkoşullar

- Visual Studio 2017 ve sonraki sürümlerinde, MFC desteği isteğe bağlı bir bileşendir. Yüklemek için Windows Başlat menüsünde Visual Studio Yükleyicisi'ni açın. Kullanıyorsanız ve seçin Visual Studio sürümünü bulun **Değiştir** düğmesi. Emin **ile masaüstü geliştirme C++**  kutucuk denetlenir. Altında **isteğe bağlı bileşenler**, kontrol **MFC desteği** düğmesi.

- Bu izlenecek yol, Visual Studio'yu kullanmak için ayarladığınız varsayılmaktadır **genel geliştirme ayarları**. Farklı geliştirme ayarı kullanıyorsanız, bu kılavuzda kullandığımız bazı Visual Studio windows varsayılan olarak görüntülenmeyebilir.

## <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazı'nı kullanarak yeni bir MFC uygulaması oluşturmak için

Bu adımlar, kullandığınız Visual Studio'nun hangi sürümünün bağlı olarak farklılık gösterir. Bu sayfanın sol üst sürüm seçicisinde doğru ayarlandığından emin olun.

::: moniker range="vs-2019"

### <a name="to-create-an-mfc-project-in-visual-studio-2019"></a>Visual Studio 2019 içinde bir MFC projesi oluşturmak için

1. Ana menüden **dosya** > **yeni** > **proje** açmak için **yeni bir proje oluşturma** iletişim bir kutu.

1. Üstteki arama kutusuna yazın **MFC** seçip **MFC uygulaması** sonuçlar listesinden. 

1. **İleri**'ye tıklayın. Sonraki sayfada, proje için bir ad girin ve istenen proje konumu belirtin.

1. Seçin **Oluştur** projeyi oluşturmak için.

   Sonra **MFC Uygulama Sihirbazı** görüntüler, aşağıdaki seçenekleri kullanın:
 
   1. Seçin **uygulama türü** soldaki. Ardından **tek belge** seçip **belge/görünüm mimarisi desteği**. Altında **proje stili**seçin **Visual Studio**, gelen ve giden **görsel stil ve renkler** listesi seçin, açılan **Office 2007 (mavi tema)**.

   1. Üzerinde **bileşik belge desteği** bölmesinde **hiçbiri**.

   1. Herhangi bir değişiklik yapmayın **belge şablonu özellikleri** bölmesi.

   1. Üzerinde **kullanıcı arabirimi özellikleri** bölmesinde emin olun **menü çubuğu ve araç çubuğu kullan** seçeneği belirlenir. Diğer tüm seçenekler olduğu gibi bırakın.

   1. Üzerinde **Gelişmiş Özellikler** bölmesinde **ActiveX denetimlerini**, **ortak denetim bildirimi**, ve **Gezinti bölmesinde** seçeneği. Diğer her şey, olduğu gibi bırakın. **Gezinti bölmesinde** seçeneği ile penceresinin sol bölmesinde oluşturmak için Sihirbazı neden olacak bir `CMFCShellTreeCtrl` zaten eklenmiş.

   1. Değişiklik kullanacağız olmayan **oluşturulan sınıflar** bölmesinde, bunu **son** yeni MFC projenizi oluşturmak için.

::: moniker-end

::: moniker range="<=vs-2017"

### <a name="to-create-an-mfc-project-in-visual-studio-2017-or-earlier"></a>Visual Studio 2017 veya önceki bir MFC projesi oluşturmak için

1. Kullanım **MFC Uygulama Sihirbazı** yeni bir MFC uygulaması oluşturmak için. Sihirbazı çalıştırmak **dosya** menüsünü seçin **yeni**ve ardından **proje**. **Yeni proje** iletişim kutusu görüntülenir.

1. İçinde **yeni proje** iletişim kutusunda **Visual C++** düğümünde **proje türleri** bölmesi ve select **MFC**. Ardından **şablonları** bölmesinde **MFC uygulaması**. Proje için bir ad yazın `MFCShellControls` tıklatıp **Tamam**. 

   Sonra **MFC Uygulama Sihirbazı** görüntüler, aşağıdaki seçenekleri kullanın:

   1. Üzerinde **uygulama türü** bölmesi altında **uygulama türü**temizleyin **belgeleri sekmeli** seçeneği. Ardından, **tek belge** seçip **belge/görünüm mimarisi desteği**. Altında **proje stili**seçin **Visual Studio**, gelen ve giden **görsel stil ve renkler** listesi seçin, açılan **Office 2007 (mavi tema)**.

   1. Üzerinde **bileşik belge desteği** bölmesinde **hiçbiri**.

   1. Herhangi bir değişiklik yapmayın **belge şablonu dizeleri** bölmesi.

   1. Üzerinde **veritabanı desteği** bölmesinde (Visual Studio 2015 veya daha eski), seçin **hiçbiri** uygulama bir veritabanı kullanmadığı.

   1. Üzerinde **kullanıcı arabirimi özellikleri** bölmesinde emin olun **menü çubuğu ve araç çubuğu kullan** seçeneği belirlenir. Diğer tüm seçenekler olduğu gibi bırakın.

   1. Üzerinde **Gelişmiş Özellikler** bölmesi altında **Gelişmiş Özellikler**, yalnızca belirli **ActiveX denetimlerini** ve **ortak denetim bildirimi**. Altında **gelişmiş çerçeve bölmeleri**, yalnızca belirli **Gezinti bölmesinde** seçeneği. Penceresinin sol bölmesinde oluşturmak için Sihirbazı neden olacak bir `CMFCShellTreeCtrl` zaten eklenmiş.

   1. Değişiklik kullanacağız olmayan **oluşturulan sınıflar** bölmesinde, bunu **son** yeni MFC projenizi oluşturmak için.

::: moniker-end

Oluşturma ve çalışan uygulamanın başarıyla oluşturulduğunu doğrulayın. Öğesinden, uygulamayı oluşturmak için **derleme** menüsünü seçin **Çözümü Derle**. Uygulama başarıyla derlenirse seçerek uygulamayı çalıştırmak **hata ayıklamayı Başlat** gelen **hata ayıklama** menüsü.

Sihirbaz ile penceresinin sol tarafında için bir standart menü çubuğu, standart araç çubuğu, standart durum çubuğu ve bir Outlook çubuğu olan bir uygulama otomatik olarak oluşturur. bir **klasörleri** görünümü ve bir **Takvim** görüntüle .

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>Belge Görünümü Kabuk liste denetimi eklemek için

1. Bu bölümde, bir örneğini ekleyeceksiniz `CMFCShellListCtrl` sihirbaz oluşturulan görünümü. Görünüm başlık dosyasını çift tıklayarak açın **MFCShellControlsView.h** içinde **Çözüm Gezgini**.

   Bulun `#pragma once` üstbilgi dosyasının en üstüne yakın yönergesi. Altındaki ekleme hemen için üstbilgi dosyasını eklemek için bu kodu `CMFCShellListCtrl`:

   ```cpp
   #include <afxShellListCtrl.h>
   ```

   Artık türündeki üye değişkeni ekleme `CMFCShellListCtrl`. İlk olarak, aşağıdaki açıklama başlık dosyasında bulun:

   ```cpp
   // Generated message map functions
   ```

   Hemen açıklamanın, bu kodu ekleyin:

   ```cpp
   private:
   CMFCShellListCtrl m_wndList;
   ```

1. **MFC Uygulama Sihirbazı** önceden oluşturulmuş bir `CMFCShellTreeCtrl` nesnesine `CMainFrame` sınıfı, ancak kullanıcının korumalı bir üye. Biz nesnesi daha sonra erişmek, bu nedenle, bir erişimci şimdi oluşturmak gerekir. MainFrm.h üstbilgi dosyasını çift tıklayarak açın **Çözüm Gezgini**. Aşağıdaki açıklamayı bulun:

   ```cpp
   // Attributes
   ```

   Hemen altında aşağıdaki yöntemi bildirimi ekleyin:

   ```cpp
   public:
       CMFCShellTreeCtrl& GetShellTreeCtrl();
   ```

   Ardından, MainFrm.cpp kaynak dosyasını çift tıklayarak açın **Çözüm Gezgini**. Bu dosyanın sonunda aşağıdaki yöntemi ekleyin:

   ```cpp
   CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()
   {
        return m_wndTree;
   }
   ```

1. Güncelleştiriyoruz artık `CMFCShellControlsView` işlemek için sınıfın `WM_CREATE` windows iletisi. Açık **sınıf görünümü** penceresi ve select `CMFCShellControlsView` sınıfı. Sağ tıklayıp **özellikleri**.

   Ardından **özellikleri** penceresinde tıklayın **iletileri** simgesi. Bulana kadar aşağıya kaydırın `WM_CREATE` ileti. Açılan listeden listesinde yanındaki `WM_CREATE`seçin  **\<Ekle > OnCreate**. Komut için bize bir ileti işleyicisi oluşturur ve MFC ileti eşlemesi otomatik olarak güncelleştirir.

   İçinde `OnCreate` yöntemi, artık oluşturacağımız bizim `CMFCShellListCtrl` nesne. Bulma `OnCreate` MFCShellControlsView.cpp yöntem tanımında, kaynak dosyası ve uygulanması şu kodla değiştirin:

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

1. Önceki adımı yineleyin ancak `WM_SIZE` ileti. Bir kullanıcı uygulama penceresinin boyutu değiştiğinde çizilmesini uygulamaları görünümünüzü neden olur. İlişkin tanımı değiştirin `OnSize` yöntemini aşağıdaki kod ile:

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

1. Bağlanmak için son adımdır `CMFCShellTreeCtrl` ve `CMFCShellListCtrl` kullanarak nesneleri [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) yöntemi. Çağırdıktan sonra `CMFCShellTreeCtrl::SetRelatedList`, `CMFCShellListCtrl` otomatik olarak seçilen öğenin içeriğini görüntüler `CMFCShellTreeCtrl`. Biz nesneleri bağlama `OnActivateView` gelen geçersiz kılınan yöntemi [CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview).

   MFCShellControlsView.h üstbilgi dosyasında içinde `CMFCShellControlsView` sınıf bildiriminin, aşağıdaki yöntemi ekleyin:

    ```cpp
    protected:
    virtual void OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView);
    ```

   Ardından, yöntem için MFCShellControlsView.cpp kaynak dosyaya ekleyin:

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

   Biz yöntemlerinden arıyoruz çünkü `CMainFrame` sınıfı, biz eklemelisiniz bir `#include` MFCShellControlsView.cpp kaynak dosyasının üst yönerge:

    ```cpp
    #include "MainFrm.h"
    ```

1. Oluşturma ve çalışan uygulamanın başarıyla oluşturulduğunu doğrulayın. Öğesinden, uygulamayı oluşturmak için **derleme** menüsünü seçin **Çözümü Derle**. Uygulama başarıyla derlenirse çalıştırın seçerek **hata ayıklamayı Başlat** gelen **hata ayıklama** menüsü.

   Seçilen öğenin ayrıntılarını görmelisiniz `CMFCShellTreeCtrl` Görünüm bölmesinde. Bir düğüme tıkladığınızda `CMFCShellTreeCtrl`, `CMFCShellListCtrl` otomatik olarak güncelleştirilir. Benzer şekilde, bir klasörde çift tıklarsanız `CMFCShellListCtrl`, `CMFCShellTreeCtrl` otomatik olarak güncelleştirilmelidir.

   Ağaç denetimi veya liste denetimi herhangi bir öğeyi sağ tıklayın. Gerçek kullanıyormuş gibi aynı bağlam menüsü alma **dosya Gezgini**.

## <a name="next-steps"></a>Sonraki adımlar

- Sihirbaz oluşturulan bir Outlook çubuğu olan bir **klasörleri** bölmesi ve **Takvim** bölmesi. Bu büyük olasılıkla için anlam ifade etmez bir **Takvim** bölmesinde bir **Gezgini** penceresinde, bu nedenle bu bölme artık kaldırın.

- `CMFCShellListCtrl` Dosyaları gibi farklı modlarda görüntülemeyi destekler **büyük simgeler**, **küçük simgeleri**, **listesi**, ve **ayrıntıları**. Bu işlevselliği uygulamak için uygulamanızı güncelleştirin. İpucu: bkz [Visual C++ örnekleri](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)
