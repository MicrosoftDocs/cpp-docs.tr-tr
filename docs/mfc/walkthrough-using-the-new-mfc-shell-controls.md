---
title: 'İzlenecek yol: yeni MFC kullanma Kabuk denetimleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: f349c955724b66ccc8cb1b19fc826ca0b8354258
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951955"
---
# <a name="walkthrough-using-the-new-mfc-shell-controls"></a>İzlenecek yol: Yeni MFC Kabuk Denetimlerini Kullanma
Bu kılavuzda, dosya Gezgini benzer bir uygulama oluşturacaksınız. İki bölme içerir bir pencere oluşturur. Sol bölmede içerecek bir [CMFCShellTreeCtrl](../mfc/reference/cmfcshelltreectrl-class.md) masaüstünüzü hiyerarşik bir görünümü görüntüler nesnesi. Sağ bölmede içerecek bir [CMFCShellListCtrl](../mfc/reference/cmfcshelllistctrl-class.md) , sol bölmede seçili klasördeki dosyaları gösterir.  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzda, ayarladığınız olduğunu varsayar [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] kullanmak için **genel geliştirme ayarları**. Bazı farklı geliştirme ayarı kullanıyorsanız [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] bu kılavuzda kullanırız windows varsayılan olarak değil görüntülenebilir.  
  
### <a name="to-create-a-new-mfc-application-by-using-the-mfc-application-wizard"></a>MFC Uygulama Sihirbazı'nı kullanarak yeni bir MFC uygulaması oluşturma  
  
1.  Kullanım **MFC Uygulama Sihirbazı'nı** yeni bir MFC uygulaması oluşturmak için. Gelen Sihirbazı'nı çalıştırmak için **dosya** menüsünü seçin **yeni**ve ardından **proje**. **Yeni proje** iletişim kutusu görüntülenir.  
  
2.  İçinde **yeni proje** iletişim kutusunda, genişletin **Visual C++** düğümünde **proje türleri** bölmesinde ve select **MFC**. Ardından **şablonları** bölmesinde, **MFC uygulaması**. Proje için bir ad yazın *MFCShellControls* tıklatıp **Tamam**. **MFC Uygulama Sihirbazı'nı** görüntülenir.  
  
3.  İçinde **MFC Uygulama Sihirbazı'nı** iletişim kutusu, tıklatın **sonraki**. **Uygulama türü** bölmesinde görüntülenir.  
  
4.  Üzerinde **uygulama türü** bölmesi altında **uygulama türü**, Temizle **belgeleri sekmeli** seçeneği. Ardından, **tek bir belge** seçip **belge/görünüm mimarisi desteği**. Altında **proje stili**seçin **Visual Studio**, gelen ve giden **görsel stil ve renkleri** listesi seçin bırakma **Office 2007 (mavi tema)**. Diğer tüm seçenekleri olduğu gibi bırakın. Tıklatın **sonraki** görüntülemek için **bileşik belge desteği** bölmesi.  
  
5.  Üzerinde **bileşik belge desteği** bölmesinde, **hiçbiri**. Tıklatın **sonraki** görüntülemek için **belge şablonu dizeleri** bölmesi.  
  
6.  Herhangi bir değişiklik yapmayın **belge şablonu dizeleri** bölmesi. Tıklatın **sonraki** görüntülemek için **veritabanı desteği** bölmesi.  
  
7.  Üzerinde **veritabanı desteği** bölmesinde, **hiçbiri** bu uygulama bir veritabanı kullanmadığından. Tıklatın **sonraki** görüntülemek için **kullanıcı arabirimi özellikleri** bölmesi.  
  
8.  Üzerinde **kullanıcı arabirimi özellikleri** bölmesinde olduğundan emin olun **menü çubuğu ve araç kullanın** seçeneği işaretlidir. Diğer tüm seçenekleri olduğu gibi bırakın. Tıklatın **sonraki** görüntülemek için **Gelişmiş Özellikler** bölmesi.  
  
9. Üzerinde **Gelişmiş Özellikler** bölmesi altında **Gelişmiş Özellikler**, yalnızca seçin **ActiveX denetimlerini** ve **ortak denetim bildirim**. Altında **çerçeve bölmeleri Gelişmiş**, yalnızca seçin **Gezinti Bölmesi** seçeneği. Bu ile penceresinin sol bölmesine oluşturmak için Sihirbazı neden olacak bir `CMFCShellTreeCtrl` zaten ekli. Tıklatın **sonraki** görüntülemek için **oluşturulan sınıflar** bölmesi.  
  
10. Biz herhangi bir değişiklik yapmak için yapmayacağınız **oluşturulan sınıflar** bölmesi. Bu nedenle, tıklatarak **son** yeni MFC projesi oluşturmak için.  
  
11. Derleme ve çalışan uygulamanın başarıyla oluşturulduğunu doğrulayın. Gelen uygulama oluşturmak için **yapı** menüsünü seçin **yapı çözümü**. Uygulama başarıyla oluşturursa, uygulamayı seçerek çalıştırın **hata ayıklamayı Başlat** gelen **hata ayıklama** menüsü.  
  
     Sihirbaz otomatik olarak penceresiyle solundaki standart menü çubuğunda, standart araç, standart durum çubuğu ve Outlook çubuğu olan bir uygulama oluşturur bir **klasörleri** görünümü ve bir **Takvim** görünümü .  
  
### <a name="to-add-the-shell-list-control-to-the-document-view"></a>Kabuk liste denetimi belge görünümüne eklemek için  
  
1.  Bu bölümde, bir örneğini ekleyeceksiniz `CMFCShellListCtrl` sihirbaz oluşturulan görüntülemek için. Görünüm üstbilgi dosyası içinde MFCShellControlsView.h çift tıklatarak açın **Çözüm Gezgini**.  
  
     Bulun `#pragma once` üstbilgi dosyanın en üstüne yakın yönergesi. Altındaki eklemek hemen için üst bilgi dosyasını dahil etmek için bu kodu `CMFCShellListCtrl`:  
  
 ```  
    #include <afxShellListCtrl.h>  
 ```  
  
     Şimdi türündeki üye değişkeni ekleme `CMFCShellListCtrl`. İlk olarak, aşağıdaki açıklama üst bilgi dosyasını bulun:  
  
 ``` 
    // Generated message map functions  
 ```  
  
     Hemen açıklamanın bu kodu ekleyin:  
  
 ```  
    private: 
    CMFCShellListCtrl m_wndList;  
 ```  
  
2.  **MFC Uygulama Sihirbazı'nı** önceden oluşturulmuş bir `CMFCShellTreeCtrl` nesnesinde `CMainFrame` sınıfı, ancak bir üyesidir korumalı. Biz bu nesne daha sonra erişir. Bu nedenle, bunun için bir erişimci şimdi oluşturun. MainFrm.h üst bilgi dosyasını çift tıklatarak açın **Çözüm Gezgini**. Aşağıdaki açıklama bulun:  
  
 ``` 
    // Attributes  
 ```  
  
     Hemen altında aşağıdaki yöntem bildirimi ekleyin:  
  
 ```  
    public: 
    CMFCShellTreeCtrl& GetShellTreeCtrl();
 ```  
  
     Ardından, MainFrm.cpp kaynak dosyasını çift tıklatarak açın **Çözüm Gezgini**. Bu dosyayı alt kısmındaki aşağıdaki yöntem tanımını ekleyin:  
  
 ```  
    CMFCShellTreeCtrl& CMainFrame::GetShellTreeCtrl()  
    {  
        return m_wndTree;  
    }  
 ```  
  
3.  Güncelleştiriyoruz artık `CMFCShellControlsView` WM_CREATE windows iletiyi işlemek için sınıf. MFCShellControlsView.h üst bilgi dosyasını açın ve bu kodu satırda tıklatın:  
  
 ```  
    class CMFCShellControlsView : public CView  
 ```  
  
     İleri ' **özellikleri** penceresinde tıklatın **iletileri** simgesi. WM_CREATE ileti bulana kadar aşağıya kaydırın. Açılan listeden WM_CREATE yanında, seçin  *\<Ekle > OnCreate*. Bu ileti işleyicisi bize oluşturur ve MFC ileti eşlemesi otomatik olarak güncelleştirir.  
  
     İçinde `OnCreate` biz şimdi oluşturacak yöntemi bizim `CMFCShellListCtrl` nesnesi. Bul `OnCreate` MFCShellControlsView.cpp yöntemi tanımında kaynak dosyası ve kendi uygulama aşağıdaki kodla değiştirin:  
  
 ```  
    int CMFCShellControlsView::OnCreate(LPCREATESTRUCT lpCreateStruct)  
    {  
        if (CView::OnCreate(lpCreateStruct) == -1)  
            return -1;  
     
        CRect rectDummy (0, 0, 0, 0);
    
        m_wndList.Create(WS_CHILD | WS_VISIBLE | LVS_REPORT, rectDummy, this, 1);
    
        return 0;  
    }  
 ```  
  
4.  Önceki adımı yineleyin, ancak WM_SIZE için ileti. Bu, bir kullanıcı uygulama penceresi boyutunu değiştiğinde çizilmesi için uygulamaları görünümünüzü neden olur. Tanımı Değiştir `OnSize` aşağıdaki kod ile yöntemi:  
  
 ```  
    void CMFCShellControlsView::OnSize(UINT nType, int cx, int cy)  
    {  
        CView::OnSize(nType, cx, cy);
    
        m_wndList.SetWindowPos(NULL, -1, -1, cx, cy, SWP_NOMOVE | SWP_NOZORDER | SWP_NOACTIVATE);
    }  
 ```  
  
5.  Bağlanmak için son adımdır `CMFCShellTreeCtrl` ve `CMFCShellListCtrl` kullanarak nesneleri [CMFCShellTreeCtrl::SetRelatedList](../mfc/reference/cmfcshelltreectrl-class.md#setrelatedlist) yöntemi. Bu yöntem çağırdıktan sonra `CMFCShellListCtrl` otomatik olarak seçili öğenin içeriğini görüntüler `CMFCShellTreeCtrl`. Bu gerçekleştiririz `OnActivateView` gelen kılınmadığı yöntemi [CView::OnActivateView](../mfc/reference/cview-class.md#onactivateview).  
  
     MFCShellControlsView.h üstbilgi dosyasında içinde `CMFCShellControlsView` sınıf bildiriminin, aşağıdaki yöntemi ekleyin:  
  
 ```  
    protected: 
    virtual void OnActivateView(BOOL bActivate, CView* pActivateView, CView* pDeactiveView);
 ```  
  
     Ardından, bu yöntem için tanım MFCShellControlsView.cpp kaynak dosyaya ekleyin:  
  
 ```  
    void CMFCShellControlsView::OnActivateView(BOOL bActivate, CView* pActivateView, CView* pDeactiveView)   
    {  
        if (bActivate&& AfxGetMainWnd() != NULL)  
        {  
            ((CMainFrame*)AfxGetMainWnd())->GetShellTreeCtrl().SetRelatedList(&m_wndList);
        }  
     
        CView::OnActivateView(bActivate, pActivateView, pDeactiveView);
    }  
 ```  
  
     Yöntemleri çağırma için `CMainFrame` sınıfı, biz eklemelisiniz bir `#include` MFCShellControlsView.cpp kaynak dosyasının üst yönerge:  
  
 ```  
    #include "MainFrm.h"  
 ```  
  
6.  Derleme ve çalışan uygulamanın başarıyla oluşturulduğunu doğrulayın. Gelen uygulama oluşturmak için **yapı** menüsünü seçin **yapı çözümü**. Uygulama başarıyla oluşturursa çalıştırın seçerek **hata ayıklamayı Başlat** gelen **hata ayıklama** menüsü.  
  
     Seçili öğenin ayrıntılarını görmelisiniz `CMFCShellTreeCtrl` görünümü bölmesinde. Bir düğüme tıkladığınızda `CMFCShellTreeCtrl`, `CMFCShellListCtrl` otomatik olarak güncelleştirilir. Benzer şekilde, bir klasörde çift tıklarsanız `CMFCShellListCtrl`, `CMFCShellTreeCtrl` otomatik olarak güncelleştirilmesi.  
  
     Ağaç denetimi veya liste denetimi herhangi bir öğeyi sağ tıklayın. Gerçek dosya Gezgini kullanıyormuş gibi aynı bağlam menüsü aldığını unutmayın.  
  
## <a name="next-steps"></a>Sonraki Adımlar  
  
-   Sihirbaz oluşturulan bir Outlook Çubuğu ikisi ile bir **klasörleri** bölmesinde ve **Takvim** bölmesi. Bu büyük olasılıkla olmasını anlamsız bir **Takvim** Gezgini penceresi bölmesinde. Bu nedenle, bu bölme şimdi kaldırın.  
  
-   `CMFCShellListCtrl` Dosyaları gibi farklı modda görüntülemeyi destekler **büyük simgeler**, **küçük simgeler**, **listesi**, ve **ayrıntıları**. Bu işlev uygulamak için uygulamanızın güncelleştirin. İpucu: bkz [Visual C++ örnekleri](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yollar](../mfc/walkthroughs-mfc.md)
