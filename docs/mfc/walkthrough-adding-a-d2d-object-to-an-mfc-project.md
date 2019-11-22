---
title: 'İzlenecek Yol: Bir MFC Projesine D2D Nesnesi Ekleme'
ms.date: 04/25/2019
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
ms.openlocfilehash: 5e1c75e32899ef9697025d662eeec4a6a2482f2b
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74304304"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>İzlenecek Yol: Bir MFC Projesine D2D Nesnesi Ekleme

Bu izlenecek yol, Visual C++, MICROSOFT FOUNDATION Class KITAPLıĞı (MFC) projesine temel bir DIRECT2D (D2D) nesnesinin nasıl ekleneceğini ve sonra projeyi "Hello, World!" öğesini yazdıran bir uygulamada nasıl derleyeceğinizi öğretir bir gradyan arka planında.

İzlenecek yol, bu görevlerin nasıl gerçekleştirileceğini gösterir:

- MFC uygulaması oluşturun.

- Düz renk fırçası ve doğrusal gradyan fırçası oluşturun.

- Gradyan fırçayı, pencere yeniden boyutlandırılırken uygun şekilde değiştirecek şekilde değiştirin.

- Bir D2D çizim işleyicisi uygulayın.

- Sonuçları doğrulayın.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için, Visual Studio 'nun iş yükü **ile C++ masaüstü geliştirmesi** ve **x86 ve x64 bileşeni için isteğe C++ bağlı Visual MFC** ile yüklenmiş olması gerekir.

## <a name="to-create-an-mfc-application"></a>MFC uygulaması oluşturmak için

1. MFC uygulaması oluşturmak için **MFC Uygulama Sihirbazı 'nı** kullanın. Visual Studio sürümünüz için sihirbazın nasıl açılacağı hakkında yönergeler için bkz. [Izlenecek yol: yenı MFC kabuk denetimlerini kullanma](walkthrough-using-the-new-mfc-shell-controls.md) .

1. **Ad** kutusuna *MFCD2DWalkthrough*yazın. Seçin **Tamam**.

1. **MFC Uygulama Sihirbazı**'nda herhangi bir ayarı değiştirmeden **son** ' u seçin.

## <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>Düz renk fırçası ve doğrusal gradyan fırçası oluşturmak için

1. **Çözüm Gezgini**, **MFCD2DWalkthrough** projesinde, **üst bilgi dosyaları** klasöründe, MFCD2DWalkthroughView. h ' yi açın. Üç veri değişkeni oluşturmak için bu kodu `CMFCD2DWalkthroughView` sınıfına ekleyin:

   ```cpp
   CD2DTextFormat* m_pTextFormat;
   CD2DSolidColorBrush* m_pBlackBrush;
   CD2DLinearGradientBrush* m_pLinearGradientBrush;
   ```

   Dosyayı kaydedin ve kapatın.

1. **Kaynak dosyaları** klasöründe MFCD2DWalkthroughView. cpp dosyasını açın. `CMFCD2DWalkthroughView` sınıfına ilişkin oluşturucuda şu kodu ekleyin:

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

## <a name="to-modify-the-gradient-brush-so-that-it-will-change-appropriately-when-the-window-is-resized"></a>Pencere yeniden boyutlandırılırken uygun şekilde değişmeleri için gradyan fırçayı değiştirme

1. **Proje** menüsünde **sınıf Sihirbazı**' nı seçin.

1. **MFC sınıfı sihirbazında**, **sınıf adı**altında `CMFCD2DWalkthroughView`' yi seçin.

1. **İletiler** sekmesindeki **iletiler** kutusunda `WM_SIZE` ' ı seçin ve ardından **İşleyici Ekle**' yi seçin. Bu eylem, `OnSize` ileti işleyicisini `CMFCD2DWalkthroughView` sınıfına ekler.

1. **Varolan işleyiciler** kutusunda `OnSize`' yi seçin. `CMFCD2DWalkthroughView::OnSize` yöntemini göstermek için **kodu Düzenle** ' yi seçin. Yönteminin sonuna aşağıdaki kodu ekleyin.

   ```cpp
   m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));
   ```

   Dosyayı kaydedin ve kapatın.

## <a name="to-implement-a-d2d-drawing-handler"></a>Bir D2D çizim işleyicisi uygulamak için

1. **Proje** menüsünde **sınıf Sihirbazı**' nı seçin.

1. **MFC sınıfı sihirbazında**, **sınıf adı**altında `CMFCD2DWalkthroughView`' yi seçin.

1. **İletiler** sekmesinde **özel ileti Ekle**' yi seçin.

1. **Özel Ileti Ekle** iletişim kutusunda, **özel Windows ileti** kutusuna *AFX_WM_DRAW2D*yazın. **İleti işleyicisi adı** kutusuna *OnDraw2D*yazın. **Kayıtlı ileti** seçeneğini belirleyip **Tamam**' ı seçin. Bu eylem, `CMFCD2DWalkthroughView` sınıfına AFX_WM_DRAW2D ileti için bir ileti işleyicisi ekler.

1. **Varolan işleyiciler** kutusunda `OnDraw2D`' yi seçin. `CMFCD2DWalkthroughView::OnDraw2D` yöntemini göstermek için **kodu Düzenle** ' yi seçin. `CMFCD2DWalkthroughView::OnDrawD2D` yöntemi için bu kodu kullanın:

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

Uygulamayı derleyin ve çalıştırın. Pencereyi yeniden boyutlandırdığınızda değişen bir gradyan dikdörtgeni olmalıdır. "Merhaba Dünya!" dikdörtgenin ortasında görüntülenmelidir.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)
