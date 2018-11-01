---
title: MFC Tarafından Oluşturulan Pencerenin Stillerini Değiştirme
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- WS_OVERLAPPEDWINDOW macro [MFC]
- single document interface (SDI), changing window attributes
- MDI [MFC], window styles
- windows [MFC], MFC
- child windows [MFC], styles
- MFC, windows
- CFrameWnd class [MFC], window styles
- CREATESTRUCT macro [MFC]
- CMDIChildWnd class [MFC], changing window styles
- multidocument interface style
- PreCreateWindow method [MFC], window styles
- single document interface (SDI), style
- default window style
- defaults [MFC], window style
- PreCreateWindow method [MFC], changing window styles
- CMainFrame class [MFC]
- styles [MFC], windows
ms.assetid: 77fa4f03-96b4-4687-9ade-41e46f7e4b0a
ms.openlocfilehash: 8ee18cd311d9ab304a3096f8e8dcbb2c7edf42f0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508002"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC Tarafından Oluşturulan Pencerenin Stillerini Değiştirme

Kendi sürümünde `WinMain` işlevi, MFC, birkaç standart pencere sınıfları kaydeder. MFC'nin normalde düzenlemeyin çünkü `WinMain`, işlevi, MFC varsayılan pencere stilleri değiştirme için bir fırsat sağlar. Bu makalede, mevcut bir uygulamada gibi önceden kaydettiğiniz pencere sınıfı stillerini nasıl değiştirebileceğiniz açıklanır.

##  <a name="_core_changing_styles_in_a_new_mfc_application"></a> Yeni bir MFC uygulamasında stillerini değiştirme

Visual C++ 2.0 veya sonraki bir sürümü kullanıyorsanız, uygulamanızı oluşturduğunuzda, uygulama sihirbazında varsayılan pencere stilleri değiştirebilirsiniz. Uygulama Sihirbazı'nın kullanıcı arabirimi özellikleri sayfasında ana çerçeve penceresi ve MDI alt pencereleri stillerini değiştirebilirsiniz. Her iki pencere türü için çerçeve kalınlığını (kalın veya basit) belirtebilirsiniz ve aşağıdakilerden biri:

- Pencereyi simge durumuna küçült ya da Ekranı Kapla denetimleri olup olmadığı.

- Pencerenin ekranı, başlangıçta simge durumuna küçültülmüş, görüntülenip ya da hiçbiri.

Ana çerçeve pencereleri için pencereyi bir sistem menüsünü olup olmadığını belirtebilirsiniz. MDI alt pencereleri için pencerenin Bölümlendirici bölmeleri destekleyip desteklemediğini belirtebilirsiniz.

##  <a name="_core_changing_styles_in_an_existing_application"></a> Mevcut bir uygulamada stillerini değiştirme

Mevcut bir uygulamada pencere özniteliklerini değiştiriyorsanız, bu makalenin geri kalanında yönergeleri yerine izleyin.

Uygulama Sihirbazı ile oluşturulan bir framework uygulaması tarafından kullanılan varsayılan pencere özniteliklerini değiştirmek için pencerenin geçersiz kılma [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) sanal üye işlevi. `PreCreateWindow` bir uygulama oluşturma işlemini normalde tarafından dahili olarak yönetilen erişim sağlayan [CDocTemplate](../mfc/reference/cdoctemplate-class.md) sınıfı. Framework çağrıları `PreCreateWindow` penceresi oluşturma önce. Değiştirerek [CREATESTRUCT](../mfc/reference/createstruct-structure.md) yapısı geçirilen `PreCreateWindow`, uygulamanızın pencere oluşturmak için kullanılan öznitelikleri değiştirebilirsiniz. Örneğin, bir pencere bir başlık kullanmadığından emin olmak için aşağıdaki bit düzeyinde işlem kullanın:

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

[CTRLBARS](../visual-cpp-samples.md) örnek uygulaması, pencere özniteliklerini değiştirmek için bu tekniği göstermektedir. Uygulamanızı, değişiklikleri bağlı olarak `PreCreateWindow`, işlevin temel sınıf uygulamasını çağıracak şekilde gerekli olabilir.

SDI çalışması aşağıdaki tartışma kapsar ve [MDI çalışması](#_core_the_mdi_case).

##  <a name="_core_the_sdi_case"></a> SDI çalışması

Bir tek Belgeli Arabirim (SDI) uygulamasında varsayılan pencere stili Framework birleşimidir **ws_overlappedwındow** ve **fws_addtotıtle** stilleri. **Fws_addtotıtle** pencerenin başlık belge başlık eklemek için framework yönlendiren bir MFC özgü stili. SDI uygulamasında pencere özniteliklerini değiştirmek için geçersiz kılma `PreCreateWindow` işlevi sınıfınızdaki türetilen `CFrameWnd` (hangi uygulama Sihirbazı adları `CMainFrame`). Örneğin:

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

Bu kod, bir ana çerçeve penceresi simge durumuna küçült ve Ekranı Kapla düğmeleri hacimle kenarlık olmadan ve oluşturur. Pencerenin ilk ekranda ortalanır.

##  <a name="_core_the_mdi_case"></a> MDI çalışması

Alt pencere birden çok belge arabirimi (MDI) uygulamasında pencere stilini değiştirmek için biraz daha fazla çalışma gerekir. Varsayılan olarak, varsayılan uygulama Sihirbazı ile oluşturulan bir MDI uygulaması kullanan [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) MFC'de tanımlanmış sınıf. Bir MDI alt penceresi pencere stilini değiştirmek için yeni bir sınıftan türetilmelidir `CMDIChildWnd` ve tüm başvuruları değiştirin `CMDIChildWnd` projenizde yeni bir sınıf başvuruları. Büyük olasılıkla yalnızca başvuru `CMDIChildWnd` uygulamanızın uygulamada bulunan `InitInstance` üye işlevi.

Bir MDI uygulamasında kullanılan varsayılan pencere stili birleşimidir **WS_CHILD**, **ws_overlappedwındow**, ve **fws_addtotıtle** stilleri. Uygulama MDI alt pencereleri pencere özniteliklerini değiştirmek için geçersiz kılma [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) işlevi sınıfınızdaki türetilen `CMDIChildWnd`. Örneğin:

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

Bu kod, Ekranı Kapla düğmesini olmadan windows MDI alt oluşturur.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Windows stilleri](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)

- [Pencere stilleri](https://msdn.microsoft.com/library/windows/desktop/ms632600)

## <a name="see-also"></a>Ayrıca Bkz.

[Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)

