---
title: "MFC tarafından oluşturulan pencerenin stillerini değiştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
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
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7745054066a928c414360a215605cf343971ddf4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC Tarafından Oluşturulan Pencerenin Stillerini Değiştirme
Kendi sürümünde `WinMain` işlevi, MFC sizin için birkaç standart pencere sınıfları kaydeder. MFC'nin normalde Düzenle yoktur çünkü `WinMain`, işlev, MFC varsayılan pencere stilleri değiştirme fırsatı verir. Bu makalede, bu tür bir preregistered pencere sınıfı var olan bir uygulamada stillerini nasıl değiştirebileceğiniz açıklanır.  
  
##  <a name="_core_changing_styles_in_a_new_mfc_application"></a>Yeni bir MFC uygulamasında stillerini değiştirme  
 Visual C++ 2.0 veya sonraki sürümünü kullanıyorsanız, uygulamanızı oluşturduğunuzda, Uygulama Sihirbazı'nda varsayılan pencere stilleri değiştirebilirsiniz. Uygulama Sihirbazı'nın kullanıcı arabirimi özellikleri sayfasında MDI alt pencereleri ve ana çerçeve pencere stilleri değiştirebilirsiniz. Her iki pencere türü için çerçeve kalınlığını (kalın veya ince) belirtebilirsiniz ve aşağıdakilerden herhangi birini:  
  
-   Pencereyi simge durumuna küçült veya Ekranı Kapla denetimleri olup olmadığı.  
  
-   Pencereyi tam ekran, başlangıçta küçültülmüş görüntülenip veya hiçbiri.  
  
 Ana çerçeve pencereleri için pencereyi System menü sahip olup olmadığını belirtebilirsiniz. MDI alt pencereleri için pencereyi Bölümlendirici bölmeleri destekleyip desteklemediğini belirtebilirsiniz.  
  
##  <a name="_core_changing_styles_in_an_existing_application"></a>Varolan bir uygulamada stillerini değiştirme  
 Pencere özniteliklerini var olan bir uygulamada değiştiriyorsanız, bunun yerine, bu makalenin kalanında'ndaki yönergeleri izleyin.  
  
 Uygulama Sihirbazı'yla oluşturulmuş bir framework uygulaması tarafından kullanılan varsayılan pencere özniteliklerini değiştirmek için pencerenin geçersiz kılma [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) sanal üye işlevi. `PreCreateWindow`Normalde tarafından dahili olarak yönetilen oluşturma işlemi erişmek bir uygulama sağlar [CDocTemplate](../mfc/reference/cdoctemplate-class.md) sınıfı. Framework çağrıları `PreCreateWindow` pencere önce. Değiştirerek [CREATESTRUCT](../mfc/reference/createstruct-structure.md) yapısı geçirilen `PreCreateWindow`, uygulamanızın penceresini oluşturmak için kullanılan özniteliklerini değiştirebilirsiniz. Örneğin, bir pencere resim yazısı kullanmaz emin olmak için aşağıdaki Bitsel işlemi kullanın:  
  
 [!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]  
  
 [CTRLBARS](../visual-cpp-samples.md) örnek uygulaması pencere özniteliklerini değiştirme için bu tekniği gösterir. Uygulamanızın ne değişiklikleri bağlı olarak `PreCreateWindow`, işlevi temel sınıf uygulamasını çağırmak gerekli olabilir.  
  
 SDI durumda aşağıdaki tartışma kapsar ve [MDI durumda](#_core_the_mdi_case).  
  
##  <a name="_core_the_sdi_case"></a>SDI durumu  
 Tek belge arabirimi (SDI) uygulamasında Framework'te varsayılan pencere stili birleşimidir **ws_overlappedwındow** ve **fws_addtotıtle** stilleri. **Fws_addtotıtle** pencerenin resim yazısı belge başlık eklemek için framework yönlendiren bir MFC özgü stili. SDI uygulamada penceresi özniteliklerini değiştirmek için geçersiz kılma `PreCreateWindow` sınıfınızda işlevi türetilen `CFrameWnd` (hangi uygulama Sihirbazı adları `CMainFrame`). Örneğin:  
  
 [!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]  
  
 Bu kod bir ana çerçeve penceresi simge durumuna küçült ve Ekranı Kapla düğmeleri ve boyutlandırılabilir kenarlık olmadan oluşturur. Pencerenin başlangıçta ekranda ortalanır.  
  
##  <a name="_core_the_mdi_case"></a>MDI durumu  
 Biraz daha fazla iş birden çok belge arabirimi (MDI) uygulaması içindeki bir alt pencerenin pencere stili değiştirmek için gereklidir. Varsayılan olarak, varsayılan uygulama Sihirbazı'yla oluşturulmuş MDI uygulama kullanan [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md) MFC'de tanımlanmış sınıf. MDI alt penceresinin pencere stili değiştirmek için yeni bir sınıf türetin `CMDIChildWnd` ve tüm başvuruları değiştirin `CMDIChildWnd` projenize yeni sınıf başvuruları. Büyük olasılıkla yalnızca başvuru `CMDIChildWnd` uygulamanızın uygulamada bulunan `InitInstance` üye işlevi.  
  
 MDI uygulamada kullanılan varsayılan pencere stili birleşimidir **WS_CHILD**, **ws_overlappedwındow**, ve **fws_addtotıtle** stilleri. MDI uygulamanın alt windows penceresi özniteliklerini değiştirmek için geçersiz kılma [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) sınıfınızda işlevi türetilen `CMDIChildWnd`. Örneğin:  
  
 [!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]  
  
 Bu kod, Ekranı Kapla düğmesi olmadan windows MDI alt oluşturur.  
  
### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz  
  
-   [Windows stilleri](../mfc/reference/styles-used-by-mfc.md#window-styles)  
  
-   [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)  
  
-   [Pencere stilleri](http://msdn.microsoft.com/library/windows/desktop/ms632600)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)

