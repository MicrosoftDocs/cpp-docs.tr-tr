---
title: Çerçeve Penceresi Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- frame window classes [MFC], about frame window classes
- frame window classes [MFC]
- windows [MFC], MDI
- document frame windows [MFC], classes
- single document interface (SDI), frame windows
- window classes [MFC], frame
- MFC, frame windows
- MDI [MFC], frame windows
- classes [MFC], window
ms.assetid: c27e43a7-8ad0-4759-b1b7-43f4725f4132
ms.openlocfilehash: d42fa475fca7c92e4ba46b164a9beda9869231c4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57279178"
---
# <a name="frame-window-classes"></a>Çerçeve Penceresi Sınıfları

Her uygulamanın bir "ana çerçeve penceresinin", genellikle kendi yazısında uygulama adı olan bir masaüstü pencere vardır. Her belge genellikle bir "Belge çerçevesi penceresinin." sahiptir Bir belge çerçevesi penceresinin belgenin verilerini sunan en az bir görünüm içerir.

## <a name="frame-windows-in-sdi-and-mdi-applications"></a>SDI ve MDI uygulamaları çerçeve Windows

Bir SDI uygulaması için sınıfından türetilen bir çerçeve penceresi yok [CFrameWnd](../mfc/reference/cframewnd-class.md). Bu, hem ana çerçeve penceresi ve belge çerçeve penceresi penceredir. Bir MDI uygulaması için ana çerçeve penceresinin sınıfından türetilir [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md), ve MDI alt pencereleri olan belge çerçeve pencereleri sınıfından türetilen [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md).

## <a name="use-the-frame-window-class-or-derive-from-it"></a>Çerçeve pencere sınıfını kullanın veya bundan türetilmiş

Bu sınıfların çoğu uygulamalarınız için ihtiyacınız olan çerçeve pencere işlevleri sağlar. Normal koşullar altında varsayılan davranış ve görünümünü sağladıkları ihtiyaçlarınıza en uygun. Ek işlevler gerekiyorsa, bu sınıflardan türetilir.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Uygulama Sihirbazı tarafından oluşturulan çerçeve pencere sınıfları](../mfc/frame-window-classes-created-by-the-application-wizard.md)

- [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)

- [MFC tarafından oluşturulan pencerenin stillerini değiştirme](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve Pencereleri](../mfc/frame-windows.md)
