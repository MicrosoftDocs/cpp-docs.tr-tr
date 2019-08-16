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
ms.openlocfilehash: ef79fc88604d565a942fdb0ae07d5fc5a2e0ebeb
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509007"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC Tarafından Oluşturulan Pencerenin Stillerini Değiştirme

`WinMain` İşlevin sürümünde MFC, sizin için birkaç standart pencere sınıfı kaydeder. MFC 'nin `WinMain`normalde düzenlenmediği için, bu işlev mfc varsayılan pencere stillerini değiştirme fırsatına sahip olmanızı sağlar. Bu makalede, var olan bir uygulamada böyle bir önkoşul olan pencere sınıfının stillerinin nasıl değiştirileceği açıklanmaktadır.

##  <a name="_core_changing_styles_in_a_new_mfc_application"></a>Yeni bir MFC uygulamasındaki stilleri değiştirme

Visual C++ 2,0 veya sonraki bir sürümünü kullanıyorsanız, uygulamanızı oluştururken uygulama Sihirbazı 'ndaki varsayılan pencere stillerini değiştirebilirsiniz. Uygulama Sihirbazının Kullanıcı arabirimi özellikleri sayfasında, ana çerçeve pencerenizin ve MDI alt pencerelerinin stillerini değiştirebilirsiniz. Her iki pencere türü için, çerçeve kalınlığını (kalın veya ince) ve aşağıdakilerden herhangi birini belirtebilirsiniz:

- Pencerenin denetimleri en aza Indirdiğini veya ekranı kaplamadığını belirtir.

- Pencerenin başlangıçta simge durumuna küçültülmüş, büyütülmüş veya hiçbirini değiştirmediği.

Ana çerçeve pencereleri için pencerenin bir sistem menüsü olup olmadığını da belirtebilirsiniz. MDI alt pencereleri için pencerenin Bölümlendirici bölmeleri destekleyip desteklemediğini belirtebilirsiniz.

##  <a name="_core_changing_styles_in_an_existing_application"></a>Mevcut bir uygulamadaki stilleri değiştirme

Mevcut bir uygulamadaki pencere özniteliklerini değiştiriyorsanız, bunun yerine bu makalenin geri kalanında bulunan yönergeleri izleyin.

Uygulama Sihirbazıyla oluşturulmuş bir Framework uygulaması tarafından kullanılan varsayılan pencere özniteliklerini değiştirmek için, pencerenin önceden [Reatewindow](../mfc/reference/cwnd-class.md#precreatewindow) sanal üye işlevini geçersiz kılın. `PreCreateWindow`bir uygulamanın, normal olarak [CDocTemplate](../mfc/reference/cdoctemplate-class.md) sınıfı tarafından yönetilen oluşturma işlemine erişmesine izin verir. Framework, pencereyi `PreCreateWindow` oluşturmadan hemen önce çağırır. Uygulamasına geçirilen `PreCreateWindow` [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) yapısını değiştirerek, uygulamanız pencereyi oluşturmak için kullanılan öznitelikleri değiştirebilir. Örneğin, bir pencerenin açıklamalı alt yazı kullandığından emin olmak için aşağıdaki bit düzeyinde işlemi kullanın:

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

[CTRLBARS](../overview/visual-cpp-samples.md) örnek uygulaması, pencere özniteliklerini değiştirmek için bu tekniği gösterir. Uygulamanızın ' de `PreCreateWindow`değiştiği seçeneğe bağlı olarak, işlevin temel sınıf uygulamasını çağırmak gerekebilir.

Aşağıdaki tartışmada SDI ve [MDI büyük/](#_core_the_mdi_case)küçük harf konuları ele alınmaktadır.

##  <a name="_core_the_sdi_case"></a>SDI durumu

Tek bir belge arabirimi (SDI) uygulamasında, Framework içindeki varsayılan pencere stili **WS_OVERLAPPEDWINDOW** ve **FWS_ADDTOTITLE** stillerinin bir birleşimidir. **FWS_ADDTOTITLE** , çerçeveye belge başlığını pencerenin açıklamalı alt başlığına EKLEMESINI sağlayan MFC 'ye özgü bir stildir. Bir SDI uygulamasındaki pencere özniteliklerini değiştirmek için, sınıfınızdan `PreCreateWindow` `CFrameWnd` türetilmiş (uygulama Sihirbazı adları `CMainFrame`) işlevini geçersiz kılın. Örneğin:

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

Bu kod, simge durumuna küçültmek ve en üst düzeye çıkarmadan ve boyutlandırılabilir kenarlık olmadan bir ana çerçeve penceresi oluşturur. Pencere başlangıçta ekranda ortalanır.

##  <a name="_core_the_mdi_case"></a>MDI durumu

Birden çok belge arabirimi (MDI) uygulamasında bir alt pencerenin pencere stilini değiştirmek için biraz daha fazla çalışma gerekir. Varsayılan olarak, uygulama sihirbazıyla oluşturulan bir MDI uygulaması MFC 'de tanımlanan varsayılan [Cmdicchild Dwnd](../mfc/reference/cmdichildwnd-class.md) sınıfını kullanır. MDI alt penceresinin pencere stilini değiştirmek için, ' dan `CMDIChildWnd` yeni bir sınıf türemeli ve projenizdeki tüm `CMDIChildWnd` başvuruları yeni sınıfa başvurularla değiştirmelisiniz. Büyük olasılıkla, uygulamada yapılan `CMDIChildWnd` tek başvuru `InitInstance` uygulamanızın üye işlevinde bulunur.

MDI uygulamasında kullanılan varsayılan pencere stili, **WS_CHILD**, **WS_OVERLAPPEDWINDOW**ve **FWS_ADDTOTITLE** stillerinin bir birleşimidir. Bir MDI uygulamasının alt pencerelerinin pencere özniteliklerini değiştirmek için, sınıfınızın sınıfından türetilmiş, [ön](../mfc/reference/cwnd-class.md#precreatewindow) planda olan `CMDIChildWnd`işlevini geçersiz kılın. Örneğin:

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

Bu kod, EkranıKapla düğmesi olmadan MDI alt pencereleri oluşturur.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Windows stilleri](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)

- [Pencere stilleri](/windows/win32/winmsg/window-styles)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)
