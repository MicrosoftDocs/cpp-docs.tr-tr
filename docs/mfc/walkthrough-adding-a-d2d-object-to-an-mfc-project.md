---
title: "İzlenecek yol: bir MFC projesine D2D nesnesi ekleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 98c14611bbca828f6264c3fcfa66462c02320432
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>İzlenecek Yol: Bir MFC Projesine D2D Nesnesi Ekleme
Bu kılavuz temel Direct2D eklemek öğretir (D2D) nesne bir Visual C++ için Microsoft Foundation Class Kitaplığı (MFC) projesi ve ardından yazdırır bir uygulamaya Projeyi derlemek "Hello, world" gradyan arka plan üzerinde.  
  
 İzlenecek yol bu görevlerin nasıl gerçekleştirileceğini gösterir:  
  
-   MFC uygulaması oluşturun.  
  
-   Düz renkli fırça ve doğrusal gradyan fırçası oluşturun.  
  
-   Gradyan fırçası pencere ne zaman yeniden boyutlandırılır uygun şekilde değiştirecek şekilde değiştirin.  
  
-   D2D çizim işleyicisi uygulayın.  
  
-   Sonuçları doğrulayın.  
  
 [!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]  
  
## <a name="prerequisites"></a>Önkoşullar  
 Bu kılavuzu tamamlamak için Visual Studio olması gerekir.  
  
### <a name="to-create-an-mfc-application"></a>MFC Uygulama oluşturmak için  
  
1.  Üzerinde **dosya** menüsündeki **yeni** ve ardından **proje**.  
  
2.  İçinde **yeni proje** iletişim kutusunda, sol bölmede altında **yüklü şablonlar**, genişletin **Visual C++** ve ardından **MFC**. Orta bölmede seçin **MFC uygulaması**. İçinde **adı** kutusuna `MFCD2DWalkthrough`. **Tamam**'ı tıklatın.  
  
3.  İçinde **MFC Uygulama Sihirbazı'nı**, tıklatın **son** ayarlarda herhangi bir değişiklik olmadan.  
  
### <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>Düz renkli fırça ve doğrusal gradyan fırçası oluşturmak için  
  
1.  İçinde **Çözüm Gezgini**, **MFCD2DWalkthrough** içinde proje **üstbilgi dosyaları** klasörü, açık MFCD2DWalkthroughView.h. Aşağıdaki kodu ekleyin `CMFCD2DWalkthroughView` üç veri değişkenleri oluşturmak üzere sınıfı.  
  
 ```  
    CD2DTextFormat* m_pTextFormat;  
    CD2DSolidColorBrush* m_pBlackBrush;  
    CD2DLinearGradientBrush* m_pLinearGradientBrush;  
 ```  
  
     Dosyayı kaydedin ve kapatın.  
  
2.  İçinde **kaynak dosyaları** klasörü, açık MFCD2DWalkthroughView.cpp. Oluşturucuda `CMFCD2DWalkthroughView` sınıfında, aşağıdaki kodu ekleyin.  
  
 ''' * / / Bu pencereyi D2D desteğini etkinleştir:  
    EnableD2DSupport();

 * / / D2D kaynakları başlatılamadı:  
    m_pBlackBrush yeni CD2DSolidColorBrush(GetRenderTarget(), D2D1::ColorF(D2D1::ColorF::Black)); =

 
    m_pTextFormat yeni CD2DTextFormat(GetRenderTarget(), _T("Verdana"), 50 =);

    m_pTextFormat -> Get() SetTextAlignment(DWRITE_TEXT_ALIGNMENT_CENTER); ->

 m_pTextFormat -> Get() SetParagraphAlignment(DWRITE_PARAGRAPH_ALIGNMENT_CENTER); ->

 
    D2D1_GRADIENT_STOP gradientStops [2];  
 
    gradientStops [0] .color D2D1::ColorF(D2D1::ColorF::White); =

    gradientStops [0] .position 0.f; =  
    [1] gradientStops .color D2D1::ColorF(D2D1::ColorF::Indigo); =

    [1] gradientStops .position 1.f; =  
 
    m_pLinearGradientBrush yeni CD2DLinearGradientBrush(GetRenderTarget() =   
    gradientStops, ARRAYSIZE(gradientStops),  
    D2D1::LinearGradientBrushProperties (D2D1::Point2F (0, 0), D2D1::Point2F (0, 0)));

 ```  
  
     Save the file and close it.  
  
### To modify the gradient brush so that it will change appropriately when the window is resized  
  
1.  On the **Project** menu, click **Class Wizard**.  
  
2.  In the **MFC Class Wizard**, under **Class name**, select `CMFCD2DWalkthroughView`.  
  
3.  On the **Messages** tab, in the **Messages** box, select `WM_SIZE` and then click **Add Handler**. This action adds the `OnSize` message handler to the `CMFCD2DWalkthroughView` class.  
  
4.  In the **Existing handlers** box, select `OnSize`. Click **Edit Code** to display the `CMFCD2DWalkthroughView::OnSize` method. At the end of the method, add the following code.  
  
 ```  
    m_pLinearGradientBrush -> SetEndPoint (CPoint (cx, cy));

 ```  
  
     Save the file and close it.  
  
### To implement a D2D drawing handler  
  
1.  On the **Project** menu, click **Class Wizard**.  
  
2.  In the **MFC Class Wizard**, under **Class name**, select `CMFCD2DWalkthroughView`.  
  
3.  On the **Messages** tab, click **Add Custom Message**.  
  
4.  In the **Add Custom Message** dialog box, in the **Custom Windows Message** box, type `AFX_WM_DRAW2D`. In the **Message handler name** box, type `OnDraw2D`. Select the **Registered Message** option and then click **OK**. This action adds a message handler for the `AFX_WM_DRAW2D` message to the `CMFCD2DWalkthroughView` class.  
  
5.  In the **Existing handlers** box, select `OnDraw2D`. Click **Edit Code** to display the `CMFCD2DWalkthroughView::OnDraw2D` method. Use the following code for the `CMFCD2DWalkthroughView::OnDrawD2D` method.  
  
 ```  
    afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(WPARAM wParam, LPARAM lParam)  
    {  
 CHwndRenderTarget * pRenderTarget (CHwndRenderTarget *) lParam; =  
    ASSERT_VALID(pRenderTarget);

 
    CRect rect;  
    GetClientRect(rect);

 
    pRenderTarget -> FillRectangle (rect, m_pLinearGradientBrush);

    pRenderTarget -> DrawText (_T ("Hello, World!"), rect, m_pBlackBrush, m_pTextFormat);

 
    TRUE döndürür;  
 }  
 ```  
  
     Save the file and close it.  
  
### To verify the results  
  
1.  Build and run the application. It should have a gradient rectangle that changes when you resize the window. “Hello World!” should be displayed in the center of the rectangle.  
  
## See Also  
 [Walkthroughs](../mfc/walkthroughs-mfc.md)

