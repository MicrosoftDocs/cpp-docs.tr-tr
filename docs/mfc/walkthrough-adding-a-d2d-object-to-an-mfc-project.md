---
title: 'İzlenecek yol: Bir MFC projesine D2D nesnesi ekleme'
ms.date: 09/20/2018
helpviewer_keywords:
- MFC, D2D
- D2D [MFC]
ms.assetid: dda36c33-c231-4da6-a62f-72d69a12b6dd
ms.openlocfilehash: 0793511f09be9dcb37732c4c16bfd2b3038a6cf4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62358623"
---
# <a name="walkthrough-adding-a-d2d-object-to-an-mfc-project"></a>İzlenecek yol: Bir MFC projesine D2D nesnesi ekleme

Bu izlenecek yol, temel bir Direct2D eklemek öğretir (D2D) nesne bir Visual C++ için Microsoft Foundation Class Kitaplığı'nı (MFC) projesi ve ardından Proje yazdıran bir uygulamaya "Hello, world" gradyan arka plan üzerinde.

İzlenecek yol aşağıdaki görevlerin nasıl gerçekleştirileceğini gösterir:

- Bir MFC uygulaması oluşturun.

- Düz renkli fırça ve doğrusal gradyan fırça oluşturun.

- Gradyan fırçası uygun zaman penceresi yeniden boyutlandırılırken değiştirecek şekilde değiştirin.

- D2D çizim işleyicisi uygulayın.

- Sonuçları doğrulayın.

[!INCLUDE[note_settings_general](../mfc/includes/note_settings_general_md.md)]

## <a name="prerequisites"></a>Önkoşullar

Bu izlenecek yolu tamamlamak için Visual Studio ile yüklü olmalıdır. **C++ ile masaüstü geliştirme** iş yükü ve isteğe bağlı **x86 ve x64 için Visual C++ MFC** bileşeni.

## <a name="to-create-an-mfc-application"></a>Bir MFC uygulaması oluşturmak için

1. Üzerinde **dosya** menüsünde **yeni** seçip **proje**.

1. İçinde **yeni proje** iletişim kutusunda, sol bölmede altında **yüklü şablonlar**, genişletme **Visual C++** seçip **MFC**. Orta bölmede seçin **MFC uygulaması**. İçinde **adı** kutusuna *MFCD2DWalkthrough*. **Tamam**’ı seçin.

1. İçinde **MFC Uygulama Sihirbazı**, seçin **son** herhangi bir ayarı değiştirmeden.

## <a name="to-create-a-solid-color-brush-and-a-linear-gradient-brush"></a>Düz renkli fırça ve doğrusal gradyan fırça oluşturma

1. İçinde **Çözüm Gezgini**, **MFCD2DWalkthrough** içinde proje **üst bilgi dosyaları** klasör, açık MFCD2DWalkthroughView.h. Bu kodu ekleyin `CMFCD2DWalkthroughView` üç veri değişkenleri oluşturma sınıfı:

   ```cpp
   CD2DTextFormat* m_pTextFormat;
   CD2DSolidColorBrush* m_pBlackBrush;
   CD2DLinearGradientBrush* m_pLinearGradientBrush;
   ```

   Dosyayı kaydedin ve kapatın.

1. İçinde **kaynak dosyaları** klasör, açık MFCD2DWalkthroughView.cpp. Oluşturucusunda `CMFCD2DWalkthroughView` sınıfı, bu kodu ekleyin:

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

## <a name="to-modify-the-gradient-brush-so-that-it-will-change-appropriately-when-the-window-is-resized"></a>Böylece uygun zaman penceresi yeniden boyutlandırılırken değişir gradyan fırçası değiştirmek için

1. Üzerinde **proje** menüsünde seçin **sınıf Sihirbazı**.

1. İçinde **MFC Sınıf Sihirbazı**altında **sınıf adı**seçin `CMFCD2DWalkthroughView`.

1. Üzerinde **iletileri** sekmesinde **iletileri** kutusunda `WM_SIZE` seçip **işleyici Ekle**. Bu eylem ekler `OnSize` ileti işleyicisi `CMFCD2DWalkthroughView` sınıfı.

1. İçinde **varolan işleyicileri** kutusunda `OnSize`. Seçin **kodunu Düzenle** görüntülenecek `CMFCD2DWalkthroughView::OnSize` yöntemi. Yönteminin sonunda, aşağıdaki kodu ekleyin.

   ```cpp
   m_pLinearGradientBrush->SetEndPoint(CPoint(cx, cy));
   ```

   Dosyayı kaydedin ve kapatın.

## <a name="to-implement-a-d2d-drawing-handler"></a>D2D çizim işleyicisi uygulamak için

1. Üzerinde **proje** menüsünde seçin **sınıf Sihirbazı**.

1. İçinde **MFC Sınıf Sihirbazı**altında **sınıf adı**seçin `CMFCD2DWalkthroughView`.

1. Üzerinde **iletileri** sekmesini, **özel ileti Ekle**.

1. İçinde **özel ileti Ekle** iletişim kutusundaki **özel Windows iletisi** kutusuna *AFX_WM_DRAW2D*. İçinde **ileti işleyicisi adı** kutusuna *OnDraw2D*. Seçin **kayıtlı ileti** seçeneğini ve ardından **Tamam**. Bu eylem için AFX_WM_DRAW2D ileti için ileti işleyicisi ekler `CMFCD2DWalkthroughView` sınıfı.

1. İçinde **varolan işleyicileri** kutusunda `OnDraw2D`. Seçin **kodunu Düzenle** görüntülenecek `CMFCD2DWalkthroughView::OnDraw2D` yöntemi. Bu kodu için `CMFCD2DWalkthroughView::OnDrawD2D` yöntemi:

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

Derleme ve uygulamayı çalıştırın. Pencereyi yeniden boyutlandırdığınızda değişir gradyan bir dikdörtgen sahip olması gerekir. "Hello World!" dikdörtgenin Merkezi'nde görüntülenmesi gerekir.

## <a name="see-also"></a>Ayrıca bkz.

[İzlenecek Yollar](../mfc/walkthroughs-mfc.md)
