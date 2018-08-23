---
title: 'İzlenecek yol: kullanarak yeni MFC Kabuk denetimlerini | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- shell controls (MFC)
ms.assetid: f0015caa-199d-4aaf-9501-5a239fce9095
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6fbf10ef749df0ce5e5984ac773e0d2c00106b82
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42464670"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>İzlenecek yol: Yeni MFC Kabuk Denetimlerini Kullanma

Bu kılavuzda, dosya Gezgini'ne benzeyen bir uygulama oluşturacaksınız. İki bölme içeren bir pencere oluşturur. Sol bölmede içerecek bir [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) Masaüstü hiyerarşik bir görünümde görüntüleyen bir nesne. Sağ bölmede içerecek bir [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) sol bölmede seçtiğiniz klasördeki dosyaların gösterir.

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yol, Visual Studio'yu kullanmak için ayarladığınız varsayılmaktadır **genel geliştirme ayarları**. Farklı geliştirme ayarı kullanıyorsanız, bu kılavuzda kullandığımız bazı Visual Studio windows varsayılan olarak görüntülenmeyebilir.

### <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazı'nı kullanarak yeni bir MFC uygulaması oluşturmak için

1. Kullanım **MFC Uygulama Sihirbazı** yeni bir MFC uygulaması oluşturmak için. Sihirbazı çalıştırmak **dosya** menüsünü seçin **yeni**ve ardından **proje**. **Yeni proje** iletişim kutusu görüntülenir.

2. İçinde **yeni proje** iletişim kutusunda **Visual C++** düğümünde **proje türleri** bölmesi ve select **MFC**. Ardından **şablonları** bölmesinde **MFC uygulaması**. Proje için bir ad yazın `MFCShellControls` tıklatıp **Tamam**. **MFC Uygulama Sihirbazı** görüntülenir.

3. İçinde **MFC Uygulama Sihirbazı** iletişim kutusu, tıklayın **sonraki**. **Uygulama türü** bölmesinde görüntülenir.

4. Üzerinde **uygulama türü** bölmesi altında **uygulama türü**temizleyin **belgeleri sekmeli** seçeneği. Ardından, **tek belge** seçip **belge/görünüm mimarisi desteği**. Altında **proje stili**seçin **Visual Studio**, gelen ve giden **görsel stil ve renkler** listesi seçin, açılan **Office 2007 (mavi tema)**. Diğer tüm seçenekler olduğu gibi bırakın. Tıklayın **sonraki** görüntülenecek **bileşik belge desteği** bölmesi.

5. Üzerinde **bileşik belge desteği** bölmesinde **hiçbiri**. Tıklayın **sonraki** görüntülenecek **belge şablonu dizeleri** bölmesi.

6. Herhangi bir değişiklik yapmayın **belge şablonu dizeleri** bölmesi. Tıklayın **sonraki** görüntülenecek **veritabanı desteği** bölmesi.

7. Üzerinde **veritabanı desteği** bölmesinde **hiçbiri** bu uygulama bir veritabanı kullanmadığı. Tıklayın **sonraki** görüntülenecek **kullanıcı arabirimi özellikleri** bölmesi.

8. Üzerinde **kullanıcı arabirimi özellikleri** bölmesinde emin olun **menü çubuğu ve araç çubuğu kullan** seçeneği belirlenir. Diğer tüm seçenekler olduğu gibi bırakın. Tıklayın **sonraki** görüntülenecek **Gelişmiş Özellikler** bölmesi.

9. Üzerinde **Gelişmiş Özellikler** bölmesi altında **Gelişmiş Özellikler**, yalnızca belirli **ActiveX denetimlerini** ve **ortak denetim bildirimi**. Altında **gelişmiş çerçeve bölmeleri**, yalnızca belirli **Gezinti bölmesinde** seçeneği. Bu Sihirbazı ile penceresinin sol bölmesinde neden olacak bir `CMFCShellTreeCtrl` zaten eklenmiş. Tıklayın **sonraki** görüntülenecek **oluşturulan sınıflar** bölmesi.

10. Değişiklik kullanacağız değil **oluşturulan sınıflar** bölmesi. Bu nedenle, tıklayın **son** yeni MFC projenizi oluşturmak için.

11. Oluşturma ve çalışan uygulamanın başarıyla oluşturulduğunu doğrulayın. Öğesinden, uygulamayı oluşturmak için **derleme** menüsünü seçin **Çözümü Derle**. Uygulama başarıyla derlenirse seçerek uygulamayı çalıştırmak **hata ayıklamayı Başlat** gelen **hata ayıklama** menüsü.

   Sihirbaz ile penceresinin sol tarafında için bir standart menü çubuğu, standart araç çubuğu, standart durum çubuğu ve bir Outlook çubuğu olan bir uygulama otomatik olarak oluşturur. bir **klasörleri** görünümü ve bir **Takvim** görüntüle .

### <a name="to-add-the-shell-list-control-to-the-document-view"></a>Belge Görünümü Kabuk liste denetimi eklemek için

1. Bu bölümde, bir örneğini ekleyeceksiniz `CMFCShellListCtrl` sihirbaz oluşturulan görünümü. Görünüm üstbilgi dosyası içinde MFCShellControlsView.h çift tıklayarak açın **Çözüm Gezgini**.

   Bulun `#pragma once` üstbilgi dosyasının en üstüne yakın yönergesi. Altındaki ekleme hemen için üstbilgi dosyasını eklemek için bu kodu `CMFCShellListCtrl`:

   ```cpp
   #include <afxShellListCtrl.h>
   ```

   Artık türündeki üye değişkeni ekleme `CMFCShellListCtrl`. İlk olarak, aşağıdaki açıklama başlık dosyasında bulun:

   ```cpp
   // Generated message map functions
   ```

   Hemen açıklamanın bu kodu ekleyin:

   ```cpp
   private:
   CMFCShellListCtrl m_wndList;
   ```

2. **MFC Uygulama Sihirbazı** önceden oluşturulmuş bir `CMFCShellTreeCtrl` nesnesine `CMainFrame` sınıfı, ancak olduğu korumalı bir üye. Biz bu nesne daha sonra erişir. Bu nedenle, bir erişimci şimdi oluşturun. MainFrm.h üstbilgi dosyasını çift tıklayarak açın **Çözüm Gezgini**. Aşağıdaki açıklamayı bulun:

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

3. Güncelleştiriyoruz artık `CMFCShellControlsView` işlemek için sınıfın **WM_CREATE** windows iletisi. MFCShellControlsView.h üstbilgi dosyasını açın ve bu kod satırı tıklatın:

    ```cpp
    class CMFCShellControlsView : public CView
    ```

   Ardından **özellikleri** penceresinde tıklayın **iletileri** simgesi. Bulana kadar aşağıya kaydırın **WM_CREATE** ileti. Açılır listeden yanındaki **WM_CREATE**seçin  **\<Ekle > OnCreate**. Bu bizim için ileti işleyicisi oluşturur ve MFC ileti eşlemesi otomatik olarak güncelleştirir.

   İçinde `OnCreate` artık oluştururuz yöntemi bizim `CMFCShellListCtrl` nesne. Bulma `OnCreate` MFCShellControlsView.cpp yöntem tanımında, kaynak dosyası ve uygulanması şu kodla değiştirin:

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

4. Önceki adımı yineleyin ancak **WM_SIZE** ileti. Bu, bir kullanıcı uygulama penceresinin boyutu değiştiğinde çizilmesini uygulamaları görünümünüzü neden olur. İlişkin tanımı değiştirin `OnSize` yöntemini aşağıdaki kod ile:

    ```cpp
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);

        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy,
            SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }
    ```

5. Bağlanmak için son adımdır `CMFCShellTreeCtrl` ve `CMFCShellListCtrl` kullanarak nesneleri [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) yöntemi. Bu yöntem çağrısından sonra `CMFCShellListCtrl` otomatik olarak seçilen öğenin içeriğini görüntüler `CMFCShellTreeCtrl`. Bunu yapacağız `OnActivateView` gelen geçersiz kılınan yöntemi [CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview).

   MFCShellControlsView.h üstbilgi dosyasında içinde `CMFCShellControlsView` sınıf bildiriminin, aşağıdaki yöntemi ekleyin:

    ```cpp
    protected:
    virtual void OnActivateView(BOOL bActivate,
        CView* pActivateView,
        CView* pDeactiveView);
    ```

   Ardından, bu yöntemin MFCShellControlsView.cpp kaynak dosyaya ekleyin:

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

   Biz yöntemleri çağırmak için `CMainFrame` sınıfı, biz eklemelisiniz bir `#include` MFCShellControlsView.cpp kaynak dosyasının üst yönergesi:

    ```cpp
    #include "MainFrm.h"
    ```

6. Oluşturma ve çalışan uygulamanın başarıyla oluşturulduğunu doğrulayın. Öğesinden, uygulamayı oluşturmak için **derleme** menüsünü seçin **Çözümü Derle**. Uygulama başarıyla derlenirse çalıştırın seçerek **hata ayıklamayı Başlat** gelen **hata ayıklama** menüsü.

   Seçilen öğenin ayrıntılarını görmelisiniz `CMFCShellTreeCtrl` Görünüm bölmesinde. Bir düğüme tıkladığınızda `CMFCShellTreeCtrl`, `CMFCShellListCtrl` otomatik olarak güncelleştirilir. Benzer şekilde, bir klasörde çift tıklarsanız `CMFCShellListCtrl`, `CMFCShellTreeCtrl` otomatik olarak güncelleştirilmelidir.

   Sağ ağaç denetimi veya liste denetimi herhangi bir öğeyi tıklatın. Gerçek dosya Gezgini kullanıyormuş gibi aynı bağlam menüsü aldığını unutmayın.

## <a name="next-steps"></a>Sonraki Adımlar

- Sihirbaz oluşturulan bir Outlook çubuğu olan bir **klasörleri** bölmesi ve **Takvim** bölmesi. Bu büyük olasılıkla olmasını anlamsız bir **Takvim** bölmesinde bir Gezgin penceresi. Bu nedenle, artık bu bölmesini kaldırın.

- `CMFCShellListCtrl` Dosyaları gibi farklı modlarda görüntülemeyi destekler **büyük simgeler**, **küçük simgeleri**, **listesi**, ve **ayrıntıları**. Bu işlevselliği uygulamak için uygulamanızı güncelleştirin. İpucu: bkz [Visual C++ örnekleri](../visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)  
