---
title: 'İzlenecek yol: Bir MFC projesine animasyon ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
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
ms.openlocfilehash: dfcab237070b401d78c3fc52fc765930272832da
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439282"
---
# <a name="walkthrough-adding-animation-to-an-mfc-project"></a>İzlenecek Yol: MFC Projesine Animasyon Ekleme

Bu izlenecek yol, temel bir animasyonlu nesne bir Visual C++ için Microsoft Foundation Class Kitaplığı'nı (MFC) projesi eklemek öğretir.

İzlenecek yol aşağıdaki görevlerin nasıl gerçekleştirileceğini gösterir:

- Bir MFC uygulaması oluşturun.

- Menü eklemek ve ardından bir animasyon durdurmak ve başlatmak komutları ekleyin.

- Başlatma ve durdurma komutlar için işleyicileri oluşturun.

- Bir animasyonlu nesne projeye ekleyin.

- Merkezi penceresinde animasyonlu nesne.

- Sonuçları doğrulayın.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için Visual Studio olması gerekir.

### <a name="to-create-an-mfc-application"></a>Bir MFC uygulaması oluşturmak için

1. Üzerinde **dosya** menüsünde **yeni** ve ardından **proje**.

2. İçinde **yeni proje** iletişim kutusunda, sol bölmede altında **yüklü şablonlar**, genişletme **Visual C++** seçip **MFC**. Orta bölmede seçin **MFC uygulaması**. İçinde **adı** kutusuna *MFCAnimationWalkthrough*. **Tamam**'ı tıklatın.

3. İçinde **MFC Uygulama Sihirbazı** iletişim kutusunda, doğrulayın **uygulama türü** olduğu **birden çok belge**, **proje stili** olduğu **Visual Studio**ve **belge/görünüm mimarisi desteği** seçeneği belirlenir. **Son**'a tıklayın.

### <a name="to-add-a-menu-and-then-add-commands-to-start-and-stop-an-animation"></a>Menü eklemek ve ardından başlatma ve durdurma animasyon için kullanılabilecek komutlar eklendi

1. Üzerinde **görünümü** menüsünde **diğer Windows** ve ardından **kaynak görünümü**.

2. İçinde **kaynak görünümü**, gitmek **menü** klasörü açın. Çift `IDR_MFCAnimationWalTYPE` değiştirilmek üzere açmak için kaynak.

3. Menü çubuğunda, **türü burada** kutusuna *A & Meti* animasyon menü oluşturmak için.

4. Altında **animasyon**, **türü burada** kutusuna *başlatın & İleri* İleri Başlat komutu oluşturmak için.

5. Altında **İleri Başlat**, **türü burada** kutusuna *başlangıç & Geri*.

6. Altında **Başlat geriye dönük**, **türü burada** kutusuna *& Durdur* Durdur komutu oluşturmak için.

7. MFCAnimationWalkthrough.rc kaydedin ve kapatın.

8. İçinde **Çözüm Gezgini**, MainFrm.cpp değiştirilmek üzere açmak için çift tıklayın. İçinde `CMainFrame::OnCreate` yöntemi için çeşitli çağrılar olan bölümünü bulun `lstBasicCommands.AddTail`. Bu bölümde hemen sonra aşağıdaki kodu ekleyin.

    ```cpp
    lstBasicCommands.AddTail(ID_ANIMATION_STARTFORWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STARTBACKWARD);
    lstBasicCommands.AddTail(ID_ANIMATION_STOP);
    ```

9. Dosyayı kaydedin ve kapatın.

### <a name="to-create-handlers-for-the-start-and-stop-commands"></a>Başlangıç işleyicileri ve komutları durdurmak için

1. Üzerinde **proje** menüsünü tıklatın **sınıf Sihirbazı**.

2. İçinde **MFC Sınıf Sihirbazı**altında **sınıf adı**seçin `CMFCAnimationWalkthroughView`.

3. Üzerinde **komutları** sekmesinde **nesne kimlikleri** kutusunda `ID_ANIMATION_STARTFORWARD`ve ardından **iletileri** kutusunda `COMMAND`. Tıklayın **işleyici Ekle**.

4. İçinde **üye işlevi ekleme** iletişim kutusu, tıklayın **Tamam**.

5. İçinde **nesne kimlikleri** kutusunda `ID_ANIMATION_STARTBACKWARD`ve ardından **iletileri** kutusunda `COMMAND`. Tıklayın **işleyici Ekle**.

6. İçinde **üye işlevi ekleme** iletişim kutusu, tıklayın **Tamam**.

7. İçinde **nesne kimlikleri** kutusunda `ID_ANIMATION_STOP`ve ardından **iletileri** kutusunda `COMMAND`. Tıklayın **işleyici Ekle** ve ardından **Tamam**.

8. İçinde **üye işlevi ekleme** iletişim kutusu, tıklayın **Tamam**.

9. İçinde **MFC Sınıf Sihirbazı**, tıklayın **Tamam**.

10. Düzenleyicide açık olan MFCAnimationWalkthroughView.cpp kaydedebilir, ancak bunu kapatmayın.

### <a name="to-add-an-animated-object-to-the-project"></a>Animasyonlu nesne projeye eklemek için

1. Çözüm Gezgini'nde MFCAnimationWalkthroughView.h değiştirilmek üzere açmak için çift tıklayın. Hemen önce tanımını `CMFCAnimationWalkthroughView` sınıfı, animasyon nesnesi zamanlama çakışıyor işleyecek bir özel animasyon denetleyicisi oluşturmak için aşağıdaki kodu ekleyin.

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

2. Sonunda `CMFCAnimationWalkthroughView` sınıfında, aşağıdaki kodu ekleyin.

    ```cpp
    CCustomAnimationController m_animationController;
    CAnimationColor m_animationColor;
    CAnimationRect m_animationRect;
    ```

3. Sonra `DECLARE_MESSAGE_MAP()` satır, aşağıdaki kodu ekleyin.

    ```cpp
    void Animate(BOOL bDirection);
    ```

4. Dosyayı kaydedin ve kapatın.

5. İçinde sonra dosyayı üst kısmındaki MFCAnimationWalkthroughView.cpp `#include` deyimleri ancak tüm yöntemler, sınıf önce aşağıdaki kodu ekleyin.

    ```cpp
    static int nAnimationGroup = 0;
    static int nInfoAreaHeight = 40;
    ```

6. Oluşturucusu sonunda `CMFCAnimationWalkthroughView`, aşağıdaki kodu ekleyin.

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

7. Bulun `CAnimationWalthroughView::PreCreateWindow` yöntemini aşağıdaki kodla değiştirin.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::PreCreateWindow(CREATESTRUCT& cs)
    {
        // TODO: Modify the Window class or styles here by modifying
        //       the CREATESTRUCT cs
        m_animationController.SetRelatedWnd(this);

        return CView::PreCreateWindow(cs);
    }
    ```

8. Bulun `CAnimationWalkthroughView::OnDraw` yöntemini aşağıdaki kodla değiştirin.

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

9. Dosyanın sonunda aşağıdaki kodu ekleyin.

    ```cpp
    void CMFCAnimationWalkthroughView::Animate(BOOL bDirection)
    {
        static UI_ANIMATION_SECONDS duration = 3;
        static DOUBLE dblSpeed = 35.;
        static BYTE nStartColor = 50;
        static BYTE nEndColor = 255;

        BYTE nRedColorFinal = bDirection  nStartColor : nEndColor;
        BYTE nGreenColorFinal = bDirection  nStartColor : nEndColor;
        BYTE nBlueColorFinal = bDirection  nStartColor : nEndColor;

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

10. Üzerinde **proje** menüsünü tıklatın **sınıf Sihirbazı**.

11. İçinde **MFC Sınıf Sihirbazı**altında **sınıf adı**seçin `CMFCAnimationWalkthroughView`.

12. Üzerinde **iletileri** sekmesinde **iletileri** kutusunda `WM_ERASEBKGND`, tıklayın **işleyici Ekle**ve ardından **Tamam**.

13. Uygulamasını MFCAnimationWalkthroughView.cpp içinde değiştirin `OnEraseBkgnd` onu yeniden çizildiğinde animasyonlu nesne titremeyi azaltmak için aşağıdaki kod ile.

    ```cpp
    BOOL CMFCAnimationWalkthroughView::OnEraseBkgnd(CDC* /*pDC*/)
    {
        return TRUE;
    }
    ```

14. Uygulamaları değiştirin `CMFCAnimationWalkthroughView::OnAnimationStartforward`, `CMFCAnimationWalkthroughView::OnAnimationStartbackward`, ve `CMFCAnimationWalkthroughView::OnAnimationStop` aşağıdaki kod ile.

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

15. Dosyayı kaydedin ve kapatın.

### <a name="to-center-the-animated-object-in-the-window"></a>Animasyonlu nesne penceresinde ortalamak için

1. İçinde **Çözüm Gezgini**, MFCAnimationWalkthroughView.h değiştirilmek üzere açmak için çift tıklayın. Sonunda `CMFCAnimationWalkthroughView` tanımını hemen ardına bir sınıf `m_animationRect`, aşağıdaki kodu ekleyin.

    ```cpp
    BOOL m_bCurrentDirection;
    ```

2. Dosyayı kaydedin ve kapatın.

3. Üzerinde **proje** menüsünü tıklatın **sınıf Sihirbazı**.

4. İçinde **MFC Sınıf Sihirbazı**altında **sınıf adı**seçin `CMFCAnimationWalkthroughView`.

5. Üzerinde **iletileri** sekmesinde **iletileri** kutusunda `WM_SIZE`, tıklayın **işleyici Ekle**ve ardından **Tamam**.

6. MFCAnimationWalkthroughView.cpp içinde için kodu değiştirin `CMFCAnimationWalkthroughView::OnSize` aşağıdaki kod ile.

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

7. Oluşturucusu başındaki `CMFCAnimationWalkthroughView`, aşağıdaki kodu ekleyin.

    ```cpp
    m_bCurrentDirection = TRUE;
    ```

8. Başında `CMFCAnimationWalkthroughView::Animate` yöntemine aşağıdaki kodu ekleyin.

    ```cpp
    m_bCurrentDirection = bDirection;
    ```

9. Dosyayı kaydedin ve kapatın.

### <a name="to-verify-the-results"></a>Sonuçları doğrulamak için

1. Derleme ve uygulamayı çalıştırın. Üzerinde **animasyon** menüsünde tıklatın **İleri Başlat**. Bir dikdörtgen, görünür ve daha sonra orta alanı doldurun. Tıkladığınızda **Başlat geriye dönük**animasyon dönmelidir ve tıkladığınızda **Durdur**, durdurmanız gerekir. Dikdörtgenin dolgu rengi Animasyon ilerledikçe değiştirmeniz ve geçerli renk animasyon penceresinin en üstünde görüntülenmesi gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)
