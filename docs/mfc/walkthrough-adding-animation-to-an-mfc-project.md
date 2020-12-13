---
description: 'Daha fazla bilgi edinin: Izlenecek yol: MFC projesine animasyon ekleme'
title: 'İzlenecek Yol: MFC Projesine Animasyon Ekleme'
ms.date: 04/25/2019
helpviewer_keywords:
- animation [MFC]
- MFC, animation
ms.assetid: 004f832c-9fd5-4f88-9ca9-ae65dececdc2
ms.openlocfilehash: ef6d6fc8e17c8e6dc4c6f0f4e8d7407f2690927f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143123"
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>İzlenecek Yol: MFC Projesine Animasyon Ekleme

Bu izlenecek yol, bir Visual C++, Microsoft Foundation Class Kitaplığı (MFC) projesine temel bir animasyonlu nesnenin nasıl ekleneceğini öğretir.

İzlenecek yol, bu görevlerin nasıl gerçekleştirileceğini gösterir:

- MFC uygulaması oluşturun.

- Bir menü ekleyin ve ardından bir animasyonu başlatmak ve durdurmak için komutlar ekleyin.

- Start ve stop komutları için işleyiciler oluşturun.

- Projeye animasyon eklenmiş bir nesne ekleyin.

- Penceredeki animasyonlu nesneyi ortalayın.

- Sonuçları doğrulayın.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Önkoşullar

Bu yönergeyi tamamlamak için, Visual Studio 'ya sahip olmanız gerekir.

### <a name="to-create-an-mfc-application"></a>MFC uygulaması oluşturmak için

1. MFC uygulaması oluşturmak için **MFC Uygulama Sihirbazı 'nı** kullanın. Visual Studio sürümünüz için sihirbazın nasıl açılacağı hakkında yönergeler için bkz. [Izlenecek yol: yenı MFC kabuk denetimlerini kullanma](walkthrough-using-the-new-mfc-shell-controls.md) .

1. **Ad** kutusuna *MFCAnimationWalkthrough* yazın. **Tamam** düğmesine tıklayın.

1. **MFC Uygulama Sihirbazı** iletişim kutusunda, **uygulama türünün** **birden çok belge** olduğunu, **Proje stilinin** **Visual Studio** olduğunu ve **belge/görünüm mimarisi desteği** seçeneğinin seçildiğini doğrulayın. **Finish (Son)** düğmesine tıklayın.

### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>Bir menü eklemek ve ardından bir animasyonu başlatmak ve durdurmak için komutlar eklemek

1. **Görünüm** menüsünde **diğer pencereler** ' in üzerine gelin ve **kaynak görünümü**' ye tıklayın.

1. **Kaynak görünümü** **menüsünde, menü** klasörüne gidin ve açın. **IDR_MFCAnimationWalkthroughTYPE** kaynağına çift tıklayarak değişiklik için açın.

1. Menü çubuğunda, **buraya yazın** kutusuna bir animasyon menüsü oluşturmak için *bir&nimation* yazın.

1. **Animasyon**' ın altında, **buraya yazın** kutusuna *ilet &başla* yazın.

1. Ileri ' yi **Başlat**' ın altında, **buraya yazın** kutusuna *geriye &başla* yazın.

1. **Geri başla**' nın altında, **buraya yazın** kutusuna bir durdur komutu oluşturmak için *S&üst* yazın.

1. MFCAnimationWalkthrough. RC ' i kaydedin ve kapatın.

1. **Çözüm Gezgini**, MainFrm. cpp öğesine çift tıklayarak değişiklik için açın. `CMainFrame::OnCreate`Yönteminde, için birkaç çağrıya sahip olan bölümünü bulun `lstBasicCommands.AddTail` . Bu bölümden hemen sonra aşağıdaki kodu ekleyin.

    ```cpp
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);
    ```

1. Dosyayı kaydedin ve kapatın.

### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>Start ve stop komutlarına yönelik işleyiciler oluşturmak için

1. **Proje** menüsünde, **sınıf Sihirbazı**' na tıklayın.

1. **MFC sınıfı sihirbazında** **sınıf adı** altında **CMFCAnimationWalkthroughView** öğesini seçin.

1. **Komutlar** sekmesinde, **nesne kimlikleri** kutusunda **ID_ANIMATION_STARTFORWARD**' yi seçin ve sonra **iletiler** kutusunda **komut**' yi seçin. **Işleyici Ekle**' ye tıklayın.

1. **Üye Işlevi Ekle** Iletişim kutusunda **Tamam**' a tıklayın.

1. **Nesne kimlikleri** kutusunda **ID_ANIMATION_STARTBACKWARD**' yi seçin ve sonra **iletiler** kutusunda **komut**' i seçin. **Işleyici Ekle**' ye tıklayın.

1. **Üye Işlevi Ekle** Iletişim kutusunda **Tamam**' a tıklayın.

1. **Nesne kimlikleri** kutusunda **ID_ANIMATION_STOP**' yi seçin ve sonra **iletiler** kutusunda **komut**' i seçin. **Işleyici Ekle** ' ye tıklayın ve ardından **Tamam**' a tıklayın.

1. **Üye Işlevi Ekle** Iletişim kutusunda **Tamam**' a tıklayın.

1. **MFC sınıfı sihirbazında**, **Tamam**' a tıklayın.

1. Düzenleyicide açık olan MFCAnimationWalkthroughView. cpp ' yi kaydedin, ancak kapatmayın.

### <a name="to-add-an-animated-object-to-the-project"></a>Projeye animasyon eklenmiş bir nesne eklemek için

1. **Çözüm Gezgini**, MFCAnimationWalkthroughView. h ' ye çift tıklayarak değişiklik için açın. Sınıfın tanımından hemen önce `CMFCAnimationWalkthroughView` , animasyon nesnesiyle zamanlama çakışmalarını işleyecek özel bir animasyon denetleyicisi oluşturmak için aşağıdaki kodu ekleyin.

    ```cpp
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

1. `CMFCAnimationWalkthroughView`Sınıfının sonuna aşağıdaki kodu ekleyin.

    ```cpp
    CCustomAnimationController m_animationController;
    CAnimationColor m_animationColor;
    CAnimationRect m_animationRect;
    ```

1. Satırdan sonra `DECLARE_MESSAGE_MAP()` aşağıdaki kodu ekleyin.

    ```cpp
    void Animate(BOOL bDirection);
    ```

1. Dosyayı kaydedin ve kapatın.

1. MFCAnimationWalkthroughView. cpp içinde, `#include` deyimlerden sonra, ancak herhangi bir sınıf yönteminden önce, aşağıdaki kodu ekleyin.

    ```cpp
    static int nAnimationGroup = 0;
    static int nInfoAreaHeight = 40;
    ```

1. Oluşturucusunun sonunda `CMFCAnimationWalkthroughView` aşağıdaki kodu ekleyin.

    ```cpp
    m_animationController.EnableAnimationTimerEventHandler();
    m_animationController.EnablePriorityComparisonHandler(UI_ANIMATION_PHT_TRIM);
    m_animationColor = RGB(255, 255, 255);
    m_animationRect = CRect(0, 0, 0, 0);
    m_animationColor.SetID(-1, nAnimationGroup);
    m_animationRect.SetID(-1, nAnimationGroup);
    m_animationController.AddAnimationObject(&m_animationColor);
    m_animationController.AddAnimationObject(&m_animationRect);
    ```

1. Yöntemini bulun `CAnimationWalthroughView::PreCreateWindow` ve aşağıdaki kodla değiştirin.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)
    {
        // TODO: Modify the Window class or styles here by modifying
        //       the CREATESTRUCT cs
        m_animationController.SetRelatedWnd(this);

        return CView::PreCreateWindow(cs);
    }
    ```

1. Yöntemini bulun `CAnimationWalkthroughView::OnDraw` ve aşağıdaki kodla değiştirin.

    ```cpp
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

        dc.FillSolidRect(rect, GetSysColor(COLOR_WINDOW));

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

1. Dosyanın sonuna aşağıdaki kodu ekleyin.

    ```cpp
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)
    {
        static UI_ANIMATION_SECONDS duration = 3;
        static DOUBLE dblSpeed = 35.;
        static BYTE nStartColor = 50;
        static BYTE nEndColor = 255;

        BYTE nRedColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nGreenColorFinal = bDirection ? nStartColor : nEndColor;
        BYTE nBlueColorFinal = bDirection ? nStartColor : nEndColor;

        CLinearTransition* pRedTransition =
            new CLinearTransition(duration, (DOUBLE)nRedColorFinal);

        CSmoothStopTransition* pGreenTransition =
            new CSmoothStopTransition(duration, (DOUBLE)nGreenColorFinal);

        CLinearTransitionFromSpeed* pBlueTransition =
            new CLinearTransitionFromSpeed(dblSpeed, (DOUBLE)nBlueColorFinal);

        m_animationColor.AddTransition(pRedTransition,
            pGreenTransition,
            pBlueTransition);

        CRect rectClient;
        GetClientRect(rectClient);

        rectClient.top += nInfoAreaHeight;

        int nLeftFinal = bDirection ? rectClient.left : rectClient.CenterPoint().x;
        int nTopFinal = bDirection ? rectClient.top : rectClient.CenterPoint().y;
        int nRightFinal = bDirection ? rectClient.right : rectClient.CenterPoint().x;
        int nBottomFinal = bDirection ? rectClient.bottom : rectClient.CenterPoint().y;

        CLinearTransition* pLeftTransition =
            new CLinearTransition(duration, nLeftFinal);

        CLinearTransition* pTopTransition =
            new CLinearTransition(duration, nTopFinal);

        CLinearTransition* pRightTransition =
            new CLinearTransition(duration, nRightFinal);

        CLinearTransition* pBottomTransition =
            new CLinearTransition(duration, nBottomFinal);

        m_animationRect.AddTransition(pLeftTransition,
            pTopTransition,
            pRightTransition,
            pBottomTransition);

        CBaseKeyFrame* pKeyframeStart =
            CAnimationController::GetKeyframeStoryboardStart();
        CKeyFrame* pKeyFrameEnd =
            m_animationController.CreateKeyframe(nAnimationGroup,
                pBlueTransition);

        pLeftTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pTopTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pRightTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);
        pBottomTransition->SetKeyframes(pKeyframeStart, pKeyFrameEnd);

        m_animationController.AnimateGroup(nAnimationGroup);
    }
    ```

1. **Proje** menüsünde, **sınıf Sihirbazı**' na tıklayın.

1. **MFC sınıfı sihirbazında** **sınıf adı** altında **CMFCAnimationWalkthroughView** öğesini seçin.

1. **İletiler** sekmesindeki **iletiler** kutusunda **WM_ERASEBKGND**' ı seçin, **İşleyici Ekle**' ye ve ardından **Tamam**' a tıklayın.

1. MFCAnimationWalkthroughView. cpp ' de, `OnEraseBkgnd` yeniden çizilme sırasında animasyon nesnesindeki titreşmeyi azaltmak için uygulamasının uygulamasını aşağıdaki kodla değiştirin.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)
    {
        return TRUE;
    }
    ```

1. `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward` , Ve uygulamalarını `CMFCAnimationWalkthroughView::OnAnimationStop` aşağıdaki kodla değiştirin.

    ```cpp
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

1. Dosyayı kaydedin ve kapatın.

### <a name="to-center-the-animated-object-in-the-window"></a>Penceredeki hareketli nesneyi ortalamak için

1. **Çözüm Gezgini**, MFCAnimationWalkthroughView. h ' ye çift tıklayarak değişiklik için açın. `CMFCAnimationWalkthroughView`Sınıfının sonunda, öğesinin tanımından hemen sonra `m_animationRect` aşağıdaki kodu ekleyin.

    ```cpp
    BOOL m_bCurrentDirection;
    ```

1. Dosyayı kaydedin ve kapatın.

1. **Proje** menüsünde, **sınıf Sihirbazı**' na tıklayın.

1. **MFC sınıfı sihirbazında** **sınıf adı** altında **CMFCAnimationWalkthroughView** öğesini seçin.

1. **İletiler** sekmesindeki **iletiler** kutusunda **WM_SIZE**' ı seçin, **İşleyici Ekle**' ye ve ardından **Tamam**' a tıklayın.

1. MFCAnimationWalkthroughView. cpp içinde, kodunu `CMFCAnimationWalkthroughView::OnSize` aşağıdaki kodla değiştirin.

    ```cpp
    void CMFCAnimationWalkthroughView::OnSize(UINT nType, int cx, int cy)
    {
        CView::OnSize(nType, cx, cy);
        CRect rect;
        GetClientRect(rect);

        rect.top += nInfoAreaHeight;

        CRect rectAnim = m_animationRect;
        m_animationRect = CRect(CPoint(rect.CenterPoint().x - rectAnim.Width() / 2,
        rect.CenterPoint().y - rectAnim.Height() / 2),
        rectAnim.Size());

        if (m_animationController.IsAnimationInProgress())
        {
            Animate(m_bCurrentDirection);
        }
    }
    ```

1. Oluşturucusunun başlangıcında `CMFCAnimationWalkthroughView` , aşağıdaki kodu ekleyin.

    ```cpp
    m_bCurrentDirection = TRUE;
    ```

1. `CMFCAnimationWalkthroughView::Animate`Yönteminin başlangıcında aşağıdaki kodu ekleyin.

    ```cpp
    m_bCurrentDirection = bDirection;
    ```

1. Dosyayı kaydedin ve kapatın.

### <a name="to-verify-the-results"></a>Sonuçları doğrulamak için

1. Uygulamayı derleyin ve çalıştırın. **Animasyon** menüsünde **İleri 'yi Başlat**' a tıklayın. Bir dikdörtgen görünmelidir ve ardından orta alanı doldurur. **Geriye doğru Başlat**' a tıkladığınızda animasyon ters alınmalıdır ve **Durdur**' a tıkladığınızda durdurulmalıdır. Animasyon ilerledikçe dikdörtgenin Fill Color değişiklik göstermelidir ve geçerli renk animasyon penceresinin en üstünde görüntülenmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)
