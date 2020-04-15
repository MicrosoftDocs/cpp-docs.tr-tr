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
ms.openlocfilehash: 221092eb25a4f044cda5b379d6774659d9e9d2d1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374587"
---
# <a name="changing-the-styles-of-a-window-created-by-mfc"></a>MFC Tarafından Oluşturulan Pencerenin Stillerini Değiştirme

`WinMain` Fonksiyonun kendi sürümünde, MFC sizin için birkaç standart pencere sınıfları kaydeder. Normalde MFC'yi `WinMain`değiştirmediğiniz için, bu işlev size MFC varsayılan pencere stillerini değiştirme fırsatı vermez. Bu makalede, varolan bir uygulamada böyle bir önceden kaydedilmiş pencere sınıfının stilleri nasıl değiştirebilirsiniz açıklar.

## <a name="changing-styles-in-a-new-mfc-application"></a><a name="_core_changing_styles_in_a_new_mfc_application"></a>Yeni Bir MFC Uygulamasında Stilleri Değiştirme

Visual C++ 2.0 veya daha yeni bir şekilde kullanıyorsanız, uygulamanızı oluştururken Uygulama Sihirbazı'ndaki varsayılan pencere stillerini değiştirebilirsiniz. Uygulama Sihirbazı'nın Kullanıcı Arabirimi Özellikleri sayfasında, ana çerçeve pencereniz ve MDI alt pencerenizin stillerini değiştirebilirsiniz. Pencere türünden biri için çerçeve kalınlığını (kalın veya ince) ve aşağıdakilerden herhangi birini belirtebilirsiniz:

- Pencerede Simge durumuna Küçültme veya Üst Düzeye Çıkarma denetimleri olup olmadığı.

- Pencerenin başlangıçta en aza indirgenmiş, en üst düzeye çıkarılıp çıkarılmadığı veya görünmediği.

Ana çerçeve pencereleri için, pencerenin Sistem Menüsü olup olmadığını da belirtebilirsiniz. MDI alt pencereleriçin, pencerenin ayırıcı bölmelerini destekleyip desteklemediğini belirtebilirsiniz.

## <a name="changing-styles-in-an-existing-application"></a><a name="_core_changing_styles_in_an_existing_application"></a>Varolan Bir Uygulamada Stilleri Değiştirme

Varolan bir uygulamada pencere özniteliklerini değiştiriyorsanız, bunun yerine bu makalenin geri kalanındaki yönergeleri izleyin.

Uygulama Sihirbazı ile oluşturulan bir çerçeve uygulaması tarafından kullanılan varsayılan pencere özniteliklerini değiştirmek için, pencerenin [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) sanal üye işlevini geçersiz kılın. `PreCreateWindow`bir uygulamanın [normalde CDocTemplate](../mfc/reference/cdoctemplate-class.md) sınıfı tarafından dahili olarak yönetilen oluşturma işlemine erişmesine izin verir. Çerçeve, `PreCreateWindow` pencereyi oluşturmadan hemen önce çağırır. Geçirilen [CREATESTRUCT](/windows/win32/api/winuser/ns-winuser-createstructw) yapısını `PreCreateWindow`değiştirerek, uygulamanız pencereoluşturmak için kullanılan öznitelikleri değiştirebilir. Örneğin, bir pencerenin resim yazısı kullanmadığından emin olmak için aşağıdaki bit yönünde işlemi kullanın:

[!code-cpp[NVC_MFCDocView#15](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_1.cpp)]

[CTRLBARS](../overview/visual-cpp-samples.md) örnek uygulaması, pencere özniteliklerini değiştirmek için bu tekniği gösterir. Uygulamanızın ne degistirdiğine bağlı `PreCreateWindow`olarak, iþlevin taban sınıf uygulamasını aramak gerekebilir.

Aşağıdaki tartışma SDI durumda ve [MDI durumda](#_core_the_mdi_case)kapsar.

## <a name="the-sdi-case"></a><a name="_core_the_sdi_case"></a>SDİ Davası

Tek bir belge arabirimi (SDI) uygulamasında, çerçevedeki varsayılan pencere stili **WS_OVERLAPPEDWINDOW** ve **FWS_ADDTOTITLE** stillerinin bir birleşimidir. **FWS_ADDTOTITLE,** çerçeveye belge başlığını pencerenin alt yazısına eklemesini söyleyen MFC'ye özgü bir stildir. Bir SDI uygulamasındaki pencere özniteliklerini `PreCreateWindow` değiştirmek için, sınıfınızdaki `CFrameWnd` (Uygulama Sihirbazı adları) işlevi geçersiz kılın. `CMainFrame` Örneğin:

[!code-cpp[NVC_MFCDocViewSDI#11](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_2.cpp)]

Bu kod, Simge Durumuna Küçült ve Üst Düzeye Çıkarma düğmeleri olmadan ve büyükçe kenarlık olmadan bir ana çerçeve penceresi oluşturur. Pencere başlangıçta ekranda ortalanır.

## <a name="the-mdi-case"></a><a name="_core_the_mdi_case"></a>MDI Davası

Birden çok belge arabirimi (MDI) uygulamasında bir alt pencerenin pencere stilini değiştirmek için biraz daha fazla çalışma gerekir. Varsayılan olarak, Uygulama Sihirbazı ile oluşturulan bir MDI uygulaması, MFC'de tanımlanan varsayılan [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) sınıfını kullanır. Bir MDI alt penceresinin pencere stilini değiştirmek için, `CMDIChildWnd` projenizdeki tüm `CMDIChildWnd` başvuruları yeni sınıfa yapılan başvurularla değiştirmeniz ve yeni bir sınıfa ait yeni bir sınıf türetmeniz gerekir. Büyük olasılıkla, uygulamada `CMDIChildWnd` tek başvuru uygulamanızın `InitInstance` üye işlevinde yer alır.

Bir MDI uygulamasında kullanılan varsayılan pencere stili, **WS_CHILD,** **WS_OVERLAPPEDWINDOW**ve **FWS_ADDTOTITLE** stillerinin bir birleşimidir. Bir MDI uygulamasının alt pencerelerinin pencere özniteliklerini değiştirmek için, sınıfınızda `CMDIChildWnd`türetilen [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow) işlevini geçersiz kılın. Örneğin:

[!code-cpp[NVC_MFCDocView#16](../mfc/codesnippet/cpp/changing-the-styles-of-a-window-created-by-mfc_3.cpp)]

Bu kod, MDI alt pencerelerini Üst düzeye çıkarma düğmesi olmadan oluşturur.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Windows stilleri](../mfc/reference/styles-used-by-mfc.md#window-styles)

- [Çerçeve penceresi stilleri](../mfc/frame-window-styles-cpp.md)

- [Pencere stilleri](/windows/win32/winmsg/window-styles)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve-Pencere Stilleri](../mfc/frame-window-styles-cpp.md)
