---
description: 'Hakkında daha fazla bilgi edinin: Frame-Window sınıfları'
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
ms.openlocfilehash: 888fae71bef2dd2e30e10c645e78ab981a30c6af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154961"
---
# <a name="frame-window-classes"></a>Çerçeve Penceresi Sınıfları

Her uygulamanın bir "ana çerçeve penceresi" vardır, genellikle başlık başlığında uygulama adı bulunan bir masaüstü penceresidir. Her belgenin genellikle bir "belge çerçevesi penceresi" vardır. Belge çerçevesi penceresi, belgenin verilerini sunan en az bir görünüm içerir.

## <a name="frame-windows-in-sdi-and-mdi-applications"></a>SDI ve MDI uygulamalarında çerçeve pencereleri

SDI uygulaması için [CFrameWnd](reference/cframewnd-class.md)sınıfından türetilmiş bir çerçeve penceresi vardır. Bu pencere hem ana çerçeve penceresi hem de belge çerçevesi penceresidir. Bir MDI uygulaması için, ana çerçeve penceresi [Cmdiframewnd](reference/cmdiframewnd-class.md)sınıfından TÜRETILIR ve MDI alt pencereleri olan belge çerçevesi pencereleri [Cmdictepdwnd](reference/cmdichildwnd-class.md)sınıfından türetilir.

## <a name="use-the-frame-window-class-or-derive-from-it"></a>Frame-Window sınıfını kullanın veya bu sınıftan türetebilirsiniz

Bu sınıflar, uygulamalarınız için ihtiyaç duyduğunuz çerçeve pencere işlevselliğinin çoğunu sağlar. Normal koşullarda, sağladığı varsayılan davranış ve görünüm ihtiyaçlarınıza göre değişir. Ek işlevselliğe ihtiyacınız varsa, bu sınıflardan türetebilirsiniz.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Uygulama Sihirbazı tarafından oluşturulan çerçeve pencere sınıfları](frame-window-classes-created-by-the-application-wizard.md)

- [Çerçeve pencere stilleri](frame-window-styles-cpp.md)

- [MFC tarafından oluşturulan pencerenin stillerini değiştirme](changing-the-styles-of-a-window-created-by-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Çerçeve pencereleri](frame-windows.md)
