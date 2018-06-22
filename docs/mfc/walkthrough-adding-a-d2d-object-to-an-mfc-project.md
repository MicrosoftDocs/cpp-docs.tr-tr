---
title: 'İzlenecek yol: bir MFC projesine D2D nesnesi ekleme | Microsoft Docs'
ms.custom: ''
ms.date: 06/19/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 68a6d5a0cda8c4d7fd06cf7bb6b9c1b60e50374b
ms.sourcegitcommit: 301bb19056e5bae84ff50f7d1df1e546efe225ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/21/2018
ms.locfileid: "36306014"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>İzlenecek Yol: Bir MFC Projesine D2D Nesnesi Ekleme

Bu kılavuz temel Direct2D eklemek öğretir (D2D) nesne bir Visual C++ için Microsoft Foundation Class Kitaplığı (MFC) projesi ve ardından yazdırır bir uygulamaya Projeyi derlemek "Hello, world" gradyan arka plan üzerinde.

İzlenecek yol bu görevlerin nasıl gerçekleştirileceğini gösterir:

- MFC uygulaması oluşturun.

- Düz renkli fırça ve doğrusal gradyan fırçası oluşturun.

- Gradyan fırçası pencere ne zaman yeniden boyutlandırılır uygun şekilde değiştirecek şekilde değiştirin.

- D2D çizim işleyicisi uygulayın.

- Sonuçları doğrulayın.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Önkoşullar

Bu kılavuzda tamamlamak için Visual Studio yüklenmiş olması **C++ ile masaüstü geliştirme** iş yükü ve isteğe bağlı **x86 hem x64 için Visual C++ MFC** bileşeni.

## <a name="to-create-an-mfc-application"></a>MFC Uygulama oluşturmak için

1. Üzerinde **dosya** menüsündeki **yeni** ve ardından **proje**.

2. İçinde **yeni proje** iletişim kutusunda, sol bölmede altında **yüklü şablonlar**, genişletin **Visual C++** ve ardından **MFC**. Orta bölmede seçin **MFC uygulaması**. İçinde **adı** kutusuna `MFCD2DWalkthrough`. Seçin **Tamam**.

3. İçinde **MFC Uygulama Sihirbazı'nı**, seçin **son** ayarlarda herhangi bir değişiklik olmadan.

## <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>Düz renkli fırça ve doğrusal gradyan fırçası oluşturmak için

1. İçinde **Çözüm Gezgini**, **MFCD2DWalkthrough** içinde proje **üstbilgi dosyaları** klasörü, açık MFCD2DWalkthroughView.h. Bu kodu ekleyin `CMFCD2DWalkthroughView` üç veri değişkenleri oluşturmak üzere sınıfı:

   ```cpp
   CD2DTextFormat* m_pTextFormat;
   CD2DSolidColorBrush* m_pBlackBrush;
   CD2DLinearGradientBrush* m_pLinearGradientBrush;
   ```

   Dosyayı kaydedin ve kapatın.

2. İçinde **kaynak dosyaları** klasörü, açık MFCD2DWalkthroughView.cpp. Oluşturucuda `CMFCD2DWalkthroughView` sınıfı, bu kodu ekleyin:

   ```cpp
   // Enable D2D support for this window:
   EnableD2DSupport();

   // Initialize D2D resources:
   m_pBlackBrush = new CD2DSolidColorBrush(
       GetRenderTarget(),
       D2D1::ColorF(D2D1::ColorF::Black));

   m_pTextFormat = new CD2DTextFormat(
       GetRenderTarget(),
       _T("Verdana"),
       50);

   m_pTextFormat->Get()->SetTextAlignment(
       DWRITE_TEXT_ALIGNMENT_CENTER);

   m_pTextFormat->Get()->SetParagraphAlignment(
       DWRITE_PARAGRAPH_ALIGNMENT_CENTER);

   D2D1_GRADIENT_STOP gradientStops[2];

   gradientStops[0].color =
       D2D1::ColorF(D2D1::ColorF::White);

   gradientStops[0].position = 0.f;
   gradientStops[1].color =
       D2D1::ColorF(D2D1::ColorF::Indigo);

   gradientStops[1].position = 1.f;

   m_pLinearGradientBrush = new CD2DLinearGradientBrush(
       GetRenderTarget(),
       gradientStops,
       ARRAYSIZE(gradientStops),
       D2D1::LinearGradientBrushProperties(
           D2D1::Point2F(0,0),
           D2D1::Point2F(0,0)));
   ```

   Dosyayı kaydedin ve kapatın.

## <a name="to-modify-the-gradient-brush-so-that-it-will-change-appropriately-when-the-window-is-resized"></a>Böylece zaman penceresi boyutlandırılır uygun şekilde değişir gradyan fırçası değiştirmek için

1. Üzerinde **proje** menüsünde seçin **sınıf Sihirbazı**.

2. İçinde **MFC Sınıf Sihirbazı**altında **sınıf adı**seçin `CMFCD2DWalkthroughView`.

3. Üzerinde **iletileri** sekmesinde **iletileri** kutusunda `WM_SIZE` ve ardından **işleyici Ekle**. Bu eylem ekler `OnSize` ileti işleyicisi `CMFCD2DWalkthroughView` sınıfı.

4. İçinde **varolan işleyicileri** kutusunda `OnSize`. Seçin **kodu Düzenle** görüntülemek için `CMFCD2DWalkthroughView::OnSize` yöntemi. Yöntemi sonuna aşağıdaki kodu ekleyin.

   ```cpp
   m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));
   ```

   Dosyayı kaydedin ve kapatın.

## <a name="to-implement-a-d2d-drawing-handler"></a>D2D çizim işleyicisi uygulamak için

1. Üzerinde **proje** menüsünde seçin **sınıf Sihirbazı**.

2. İçinde **MFC Sınıf Sihirbazı**altında **sınıf adı**seçin `CMFCD2DWalkthroughView`.

3. Üzerinde **iletileri** sekmesinde, seçin **eklemek özel ileti**.

4. İçinde **eklemek özel ileti** iletişim kutusunda **özel Windows ileti** kutusuna `AFX_WM_DRAW2D`. İçinde **ileti işleyicisi adı** kutusuna `OnDraw2D`. Seçin **kayıtlı ileti** seçeneğini ve ardından **Tamam**. Bu eylem için bir ileti işleyicisini ekler `AFX_WM_DRAW2D` için ileti `CMFCD2DWalkthroughView` sınıfı.

5. İçinde **varolan işleyicileri** kutusunda `OnDraw2D`. Seçin **kodu Düzenle** görüntülemek için `CMFCD2DWalkthroughView::OnDraw2D` yöntemi. Bu kodu kullanın `CMFCD2DWalkthroughView::OnDrawD2D` yöntemi:

   ```cpp
   afx_msg LRESULT CMFCD2DWalkthroughView::OnDraw2D(
       WPARAM wParam,
       LPARAM lParam)
   {
       CHwndRenderTarget* pRenderTarget = (CHwndRenderTarget*)lParam;
       ASSERT_VALID(pRenderTarget);

       CRect rect;
       GetClientRect(rect);

       pRenderTarget->FillRectangle(rect, m_pLinearGradientBrush);

       pRenderTarget->DrawText(
           _T("Hello, World!"),
           rect,
           m_pBlackBrush,
           m_pTextFormat);

       return TRUE;
   }
   ```

   Dosyayı kaydedin ve kapatın.

## <a name="to-verify-the-results"></a>Sonuçları doğrulamak için

- Derleme ve uygulamayı çalıştırın. Pencereyi yeniden boyutlandırdığınızda değişiklikleri bir gradyan dikdörtgen olmalıdır. "Hello World!" Dikdörtgen Merkezi'nde görüntülenmesi gerekir.

## <a name="see-also"></a>Ayrıca bkz.

- [İzlenecek Yollar](../mfc/walkthroughs-mfc.md)
