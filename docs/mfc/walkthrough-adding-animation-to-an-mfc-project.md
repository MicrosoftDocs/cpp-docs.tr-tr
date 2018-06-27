---
title: 'İzlenecek yol: Bir MFC projesine animasyon ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- animation [MFC]
- MFC, animation
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edc17f099a208e69242a51c1273b1bd11bb5353d
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36954575"
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>İzlenecek Yol: MFC Projesine Animasyon Ekleme
Bu kılavuz, bir Visual C++ için Microsoft Foundation Class Kitaplığı (MFC) proje temel bir animasyonlu nesne eklemek öğretir.  
  
 İzlenecek yol bu görevlerin nasıl gerçekleştirileceğini gösterir:  
  
-   MFC uygulaması oluşturun.  
  
-   Bir menüyü ekleyin ve sonra bir animasyon durdurmak ve başlatmak için komutları ekleyin.  
  
-   Başlatma ve durdurma komutları için işleyiciler oluşturun.  
  
-   Hareketli bir nesnenin projeye ekleyin.  
  
-   Merkezi penceresinde animasyonlu nesne.  
  
-   Sonuçları doğrulayın.  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzu tamamlamak için Visual Studio olması gerekir.  
  
### <a name="to-create-an-mfc-application"></a>MFC Uygulama oluşturmak için  
  
1.  Üzerinde **dosya** menüsündeki **yeni** ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, sol bölmede altında **yüklü şablonlar**, genişletin **Visual C++** ve ardından **MFC**. Orta bölmede seçin **MFC uygulaması**. İçinde **adı** kutusuna *MFCAnimationWalkthrough*. **Tamam**'ı tıklatın.  
  
3.  İçinde **MFC Uygulama Sihirbazı'nı** iletişim kutusunda, doğrulayın **uygulama türü** olan **birden çok belge**, **proje stili** olduğu **Visual Studio**ve **belge/görünüm mimarisi desteği** seçeneği işaretlidir. **Son**'a tıklayın.  
  
### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>Menü eklemek ve bir animasyon durdurmak ve başlatmak için komut eklemek için  
  
1.  Üzerinde **Görünüm** menüsündeki **diğer pencereler** ve ardından **kaynak görünümü**.  
  
2.  İçinde **kaynak görünümü**, gitmek **menü** klasörü ve açın. Çift `IDR_MFCAnimationWalTYPE` değiştirilmek üzere açmak için kaynak.  
  
3.  Menü çubuğunda, **burada türü** kutusuna *A & Meti* bir animasyon menü oluşturmak için.  
  
4.  Altında **animasyon**, **burada türü** kutusuna *Başlat & iletmek* İleri Başlat komutu oluşturmak için.  
  
5.  Altında **İleri Başlat**, **burada türü** kutusuna *başlangıç & Geri*.  
  
6.  Altında **Başlat geriye dönük**, **burada türü** kutusuna *ilk &* Durdur komutu oluşturmak için.  
  
7.  MFCAnimationWalkthrough.rc kaydedin ve kapatın.  
  
8.  İçinde **Çözüm Gezgini**, MainFrm.cpp değiştirilmek üzere açmak için çift tıklayın. İçinde `CMainFrame::OnCreate` yöntemi, birkaç çağrı olan bölümünü bulun `lstBasicCommands.AddTail`. Bu bölümde hemen sonra aşağıdaki kodu ekleyin.  
  
 ```  
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);

 lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);

    lstBasicCommands.AddTail(ID_ANIMATION_STOP);

 ```  
  
9. Dosyayı kaydedin ve kapatın.  
  
### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>Başlangıç için işleyiciler oluşturmak ve komutları durdurmak için  
  
1.  Üzerinde **proje** menüsünde tıklatın **sınıf Sihirbazı**.  
  
2.  İçinde **MFC Sınıf Sihirbazı**altında **sınıf adı**seçin `CMFCAnimationWalkthroughView`.  
  
3.  Üzerinde **komutları** sekmesinde **nesne kimlikleri** kutusunda `ID_ANIMATION_STARTFORWARD`ve ardından **iletileri** kutusunda `COMMAND`. Tıklatın **işleyici ekleme**.  
  
4.  İçinde **üye işlevi ekleme** iletişim kutusu, tıklatın **Tamam**.  
  
5.  İçinde **nesne kimlikleri** kutusunda `ID_ANIMATION_STARTBACKWARD`ve ardından **iletileri** kutusunda `COMMAND`. Tıklatın **işleyici ekleme**.  
  
6.  İçinde **üye işlevi ekleme** iletişim kutusu, tıklatın **Tamam**.  
  
7.  İçinde **nesne kimlikleri** kutusunda `ID_ANIMATION_STOP`ve ardından **iletileri** kutusunda `COMMAND`. Tıklatın **işleyici Ekle** ve ardından **Tamam**.  
  
8.  İçinde **üye işlevi ekleme** iletişim kutusu, tıklatın **Tamam**.  
  
9. İçinde **MFC Sınıf Sihirbazı**, tıklatın **Tamam**.  
  
10. Düzenleyicide açık olduğundan, MFCAnimationWalkthroughView.cpp kaydedin, ancak bunu kapatmayın.  
  
### <a name="to-add-an-animated-object-to-the-project"></a>Hareketli bir nesnenin projeye eklemek için  
  
1.  Çözüm Gezgini'nde MFCAnimationWalkthroughView.h değiştirilmek üzere açmak için çift tıklayın. Tanımından hemen önce `CMFCAnimationWalkthroughView` sınıfı, animasyon nesne zamanlama çakışıyor işleyecek bir özel animasyon denetleyicisi oluşturmak için aşağıdaki kodu ekleyin.  
  
 ```  
    class CCustomAnimationController : public CAnimationController  
 {  
    public: 
    CCustomAnimationController() 
 {  
 }  
 
    virtual BOOL OnHasPriorityTrim(CAnimationGroup* pGroupScheduled,
    CAnimationGroup* pGroupNew,
    UI_ANIMATION_PRIORITY_EFFECT priorityEffect)  
 {  
    return TRUE;  
 }  
 };  
 ```  
  
2.  Sonunda `CMFCAnimationWalkthroughView` sınıfında, aşağıdaki kodu ekleyin.  
  
 ```  
    CCustomAnimationController m_animationController;  
    CAnimationColor m_animationColor;   
    CAnimationRect m_animationRect;  
 ```  
  
3.  Sonra `DECLARE_MESSAGE_MAP()` satır, aşağıdaki kodu ekleyin.  
  
 ```  
    void Animate(BOOL bDirection);

 ```  
  
4.  Dosyayı kaydedin ve kapatın.  
  
5.  Dosyanın üst kısmındaki sonra MFCAnimationWalkthroughView.cpp içinde `#include` deyimleri ancak herhangi bir yöntem, sınıf önce aşağıdaki kodu ekleyin.  
  
 ```  
    static int nAnimationGroup = 0;  
    static int nInfoAreaHeight = 40;  
 ```  
  
6.  Oluşturucusu sonunda `CMFCAnimationWalkthroughView`, aşağıdaki kodu ekleyin.  
  
 ```  
    m_animationController.EnableAnimationTimerEventHandler();
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);

    m_animationColor = RGB(255, 255, 255);

    m_animationRect = CRect(0, 0, 0, 0);

    m_animationColor.SetID(-1, nAnimationGroup);

    m_animationRect.SetID(-1, nAnimationGroup);

    m_animationController.AddAnimationObject(&m_animationColor);

    m_animationController.AddAnimationObject(&m_animationRect);
 ```  
  
7.  Bulun `CAnimationWalthroughView::PreCreateWindow` yöntemi ve aşağıdaki kod ile değiştirin.  
  
 ```  
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)  
     { *// TODO: Modify the Window class or styles here by modifying *//  the CREATESTRUCT cs  
 
    m_animationController.SetRelatedWnd(this);

     return CView::PreCreateWindow(cs);

     }  
 ```  
  
8.  Bulun `CAnimationWalkthroughView::OnDraw` yöntemi ve aşağıdaki kod ile değiştirin.  
  
 ```  
    void CMFCAnimationWalkthroughView::OnDraw(CDC* pDC)  
    {  
        CMFCAnimationWalkthroughDoc* pDoc = GetDocument();
        ASSERT_VALID(pDoc);
    
        if (!pDoc)  
           return; 
        // TODO: add draw code for native data here  
        CMemDC dcMem(*pDC, this);
    
        CDC& dc = dcMem.GetDC();
    
        CRect rect;  
        GetClientRect(rect);
    
        dc.FillSolidRect(rect,
        GetSysColor(COLOR_WINDOW));
    
        CString strRGB;  
        strRGB.Format(_T("Fill Color is: %d; %d; %d"),
        GetRValue(m_animationColor),
        GetGValue(m_animationColor),
        GetBValue(m_animationColor));
    
        dc.DrawText(strRGB, rect, DT_CENTER);
    
        rect.top += nInfoAreaHeight;  
     
        CBrush br;  
     
        br.CreateSolidBrush(m_animationColor);
    
        CBrush* pBrushOld = dc.SelectObject(&br);
    
        dc.Rectangle((CRect)m_animationRect);
    
        dc.SelectObject(pBrushOld);
    }  
 ```  
  
9. Dosya sonuna aşağıdaki kodu ekleyin.  
  
 ```  
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)  
    {  
        static UI_ANIMATION_SECONDS duration = 3;  
        static DOUBLE dblSpeed = 35.;  
        static BYTE nStartColor = 50;  
        static BYTE nEndColor = 255;  
     
        BYTE nRedColorFinal = bDirection  nStartColor : nEndColor;  
        BYTE nGreenColorFinal = bDirection  nStartColor : nEndColor;  
        BYTE nBlueColorFinal = bDirection  nStartColor : nEndColor;  
     
        CLinearTransition* pRedTransition = new CLinearTransition(duration, (DOUBLE)nRedColorFinal);
    
        CSmoothStopTransition* pGreenTransition = new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);
    
        CLinearTransitionFromSpeed* pBlueTransition = new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);
    
        m_animationColor.AddTransition(pRedTransition, pGreenTransition, pBlueTransition);
    
        CRect rectClient;  
        GetClientRect(rectClient);
    
        rectClient.top += nInfoAreaHeight;  
     
        int nLeftFinal = bDirection  rectClient.left : rectClient.CenterPoint().x;  
        int nTopFinal = bDirection  rectClient.top : rectClient.CenterPoint().y;  
        int nRightFinal = bDirection  rectClient.right : rectClient.CenterPoint().x;  
        int nBottomFinal = bDirection  rectClient.bottom : rectClient.CenterPoint().y;  
     
        CLinearTransition* pLeftTransition = new CLinearTransition(duration, nLeftFinal);
    
        CLinearTransition* pTopTransition = new CLinearTransition(duration, nTopFinal);
    
        CLinearTransition* pRightTransition = new CLinearTransition(duration, nRightFinal);
    
        CLinearTransition* pBottomTransition = new CLinearTransition(duration, nBottomFinal);
    
        m_animationRect.AddTransition(pLeftTransition, pTopTransition, pRightTransition, pBottomTransition);
    
        CBaseKeyFrame* pKeyframeStart = CAnimationController::GetKeyframeStoryboardStart();
        CKeyFrame* pKeyFrameEnd = m_animationController.CreateKeyframe(nAnimationGroup, pBlueTransition);
    
        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
    
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
    
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
    
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
    
        m_animationController.AnimateGroup(nAnimationGroup);
    }  
 ```  
  
10. Üzerinde **proje** menüsünde tıklatın **sınıf Sihirbazı**.  
  
11. İçinde **MFC Sınıf Sihirbazı**altında **sınıf adı**seçin `CMFCAnimationWalkthroughView`.  
  
12. Üzerinde **iletileri** sekmesinde **iletileri** kutusunda `WM_ERASEBKGND`, tıklatın **işleyici Ekle**ve ardından **Tamam**.  
  
13. MFCAnimationWalkthroughView.cpp içinde uygulanması Değiştir `OnEraseBkgnd` yeniden çizilir zaman animasyonlu nesnesinde titremeyi azaltmak için aşağıdaki kod ile.  
  
 ```  
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)  
    {  
        return TRUE;  
    }  
 ```  
  
14. Uygulamaları Değiştir `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward`, ve `CMFCAnimationWalkthroughView::OnAnimationStop` aşağıdaki kod ile.  
  
 ```  
    void CMFCAnimationWalkthroughView::OnAnimationStartforward()  
    {  
        Animate(TRUE);
    }  
 
    void CMFCAnimationWalkthroughView::OnAnimationStartbackward()  
    {  
        Animate(FALSE);
    }  
 
    void CMFCAnimationWalkthroughView::OnAnimationStop()  
    {  
        IUIAnimationManager* pManager = m_animationController.GetUIAnimationManager();
        if (pManager != NULL)  
        {  
            pManager->AbandonAllStoryboards();
        }  
    }  
 ```  
  
15. Dosyayı kaydedin ve kapatın.  
  
### <a name="to-center-the-animated-object-in-the-window"></a>Merkezi penceresinde animasyonlu nesnesi  
  
1.  İçinde **Çözüm Gezgini**, MFCAnimationWalkthroughView.h değiştirilmek üzere açmak için çift tıklayın. Sonunda `CMFCAnimationWalkthroughView` tanımından hemen sonra sınıfı `m_animationRect`, aşağıdaki kodu ekleyin.  
  
 ```  
    BOOL m_bCurrentDirection;  
 ```  
  
2.  Dosyayı kaydedin ve kapatın.  
  
3.  Üzerinde **proje** menüsünde tıklatın **sınıf Sihirbazı**.  
  
4.  İçinde **MFC Sınıf Sihirbazı**altında **sınıf adı**seçin `CMFCAnimationWalkthroughView`.  
  
5.  Üzerinde **iletileri** sekmesinde **iletileri** kutusunda `WM_SIZE`, tıklatın **işleyici Ekle**ve ardından **Tamam**.  
  
6.  MFCAnimationWalkthroughView.cpp içinde kodunu değiştir `CMFCAnimationWalkthroughView::OnSize` aşağıdaki kod ile.  
  
 ```  
    void CMFCAnimationWalkthroughView::OnSize(UINT nType, int cx, int cy)  
    {  
        CView::OnSize(nType, cx, cy);

        CRect rect;  
        GetClientRect(rect);
    
        rect.top += nInfoAreaHeight;  
     
        CRect rectAnim = m_animationRect;  
        m_animationRect = CRect(CPoint(rect.CenterPoint().x - rectAnim.Width() / 2, rect.CenterPoint().y - rectAnim.Height() / 2), rectAnim.Size());
    
        if (m_animationController.IsAnimationInProgress())  
        {  
            Animate(m_bCurrentDirection);
        }  
    }  
 ```  
  
7.  Oluşturucusu başında `CMFCAnimationWalkthroughView`, aşağıdaki kodu ekleyin.  
  
 ```  
    m_bCurrentDirection = TRUE;  
 ```  
  
8.  Başında `CMFCAnimationWalkthroughView::Animate` yöntemi, aşağıdaki kodu ekleyin.  
  
 ```  
    m_bCurrentDirection = bDirection;  
 ```  
  
9. Dosyayı kaydedin ve kapatın.  
  
### <a name="to-verify-the-results"></a>Sonuçları doğrulamak için  
  
1.  Derleme ve uygulamayı çalıştırın. Üzerinde **animasyon** menüsünde tıklatın **İleri Başlat**. Dikdörtgene görünür ve merkezi alanını doldurun. Tıkladığınızda **Başlat geriye dönük**, animasyonun dönmelidir ve tıkladığınızda **durdurmak**, durdurmanız gerekir. Dikdörtgen dolgu rengini Animasyon ilerledikçe değiştirmeniz ve geçerli rengini animasyon penceresinin en üstünde görüntülenmesi gerekir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzlenecek Yollar](../mfc/walkthroughs-mfc.md)

