---
title: Çerçeve Windows | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document frame windows [MFC]
- windows [MFC], MDI
- window classes [MFC], frame
- single document interface (SDI) [MFC]
- single document interface (SDI) [MFC], frame windows
- views [MFC], and frame windows
- CFrameWnd class [MFC], frame windows
- frame windows [MFC]
- frame windows [MFC], about frame widows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77035b50070478f5117635738f13c7bfd43edec2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46431027"
---
# <a name="frame-windows"></a>Çerçeve Pencereleri

Bir uygulama Windows altında çalışırken, kullanıcı çerçeve pencerelerinde görüntülenen belgeleri ile etkileşim kurar. Bir belge çerçevesi penceresinin iki önemli bileşeni vardır: çerçeve ve bu çerçeve içeriği. Bir belge çerçevesi penceresinin olabilir bir [tek Belgeli Arabirim](../mfc/sdi-and-mdi.md) (SDI) çerçeve penceresi veya [birden çok belge arabirimi](../mfc/sdi-and-mdi.md) (MDI) alt penceresi. Windows, birçok çerçeve penceresi ile kullanıcı etkileşimi yönetir: taşıma ve pencereyi yeniden boyutlandırma, kapatma ve en aza indirmek ve bunu en üst düzeye. İçeriği çerçevesindeki yönettiğiniz.

## <a name="frame-windows-and-views"></a>Çerçeve Windows ve görünümleri

MFC çerçevesi çerçeve pencereleri görünümler içermesi için kullanır. İki bileşeni — çerçeve ve içeriği — temsil ve MFC'de iki farklı sınıflar tarafından yönetilir. Çerçeve çerçeve-pencere sınıfı yönetir ve bir görünüm sınıfı içeriği yönetir. Görünüm penceresine çerçeve penceresinin alt öğesidir. Çizim ve başka bir kullanıcı etkileşimi belgeyle görünümün istemci alanı, çerçeve penceresinin istemci alanına gerçekleşir. Çerçeve penceresi etrafında bir görünümü, tam bir başlık çubuğu ve standart penceresi denetimleriyle denetimi menüsü, en aza indirmek ve, pencerenin en üst düzeye çıkarmak için düğmeler gibi görünür bir çerçeve sağlar ve pencereyi yeniden boyutlandırmak için denetler. Tam olarak bir alt pencere tarafından kullanılıyor pencerenin istemci alanının "İçerik" oluşur; görünümü. Aşağıdaki şekilde bir çerçeve penceresi ve bir görünüm arasındaki ilişki gösterilmektedir.

![Çerçeve penceresi görünümü](../mfc/media/vc37fx1.gif "vc37fx1") çerçeve penceresi ve görünümü

## <a name="frame-windows-and-splitter-windows"></a>Çerçeve Windows ve Windows Bölümlendirici

Başka bir ortak kullanımı genellikle birden çok görünüm çerçeve çerçeve penceresi için düzenlemesidir bir [ayırıcı penceresi](../mfc/multiple-document-types-views-and-frame-windows.md). Ayırıcı penceresi içinde çerçeve penceresinin istemci alanına sırayla görünümleridir bölmeleri, adında birden çok alt öğe pencerelerini sahip bir ayırıcı penceresi tarafından kullanılıyor.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

**Çerçeve penceresi genel konular**

- [Pencere nesneleri](../mfc/window-objects.md)

- [Çerçeve penceresi sınıfları](../mfc/frame-window-classes.md)

- [Uygulama Sihirbazı tarafından oluşturulan çerçeve pencere sınıfları](../mfc/frame-window-classes-created-by-the-application-wizard.md)

- [Çerçeve pencere stilleri](../mfc/frame-window-styles-cpp.md)

- [Çerçeve pencerelerinin görevi](../mfc/what-frame-windows-do.md)

**Çerçeve Windows kullanma konuları**

- [Çerçeve pencerelerini kullanma](../mfc/using-frame-windows.md)

- [Belge çerçeve pencereleri oluşturma](../mfc/creating-document-frame-windows.md)

- [Çerçeve pencerelerini yok etme](../mfc/destroying-frame-windows.md)

- [MDI alt öğe pencerelerini yönetme](../mfc/managing-mdi-child-windows.md)

- [Geçerli görünümü yönetme](../mfc/managing-the-current-view.md) bir çerçeve penceresinde birden fazla görünümü içerir

- [Menüleri, Denetim çubuklarını ve Hızlandırıcıları (Çerçeve penceresinin alanı paylaşan diğer nesnelerin) yönetme](../mfc/managing-menus-control-bars-and-accelerators.md)

**Özel bir çerçeve penceresi özellikleriyle ilgili konular**

- [Dosyaları sürükleme ve bırakma](../mfc/dragging-and-dropping-files-in-a-frame-window.md) dosya Gezgini ya da bir çerçeve penceresinin içine Dosya Yöneticisi

- [Dinamik veri değişimine (DDE) yanıt verme](../mfc/responding-to-dynamic-data-exchange-dde.md)

- [Yarı kalıcı durumlar: (diğer pencere işlemlerini) Windows Context-sensitive Help](../mfc/orchestrating-other-window-actions.md)

- [Yarı kalıcı durumlar: yazdırmayı ve Baskı Önizleme (diğer pencere işlemlerini)](../mfc/orchestrating-other-window-actions.md)

**Windows diğer türden konuları**

- [Görünümleri Kullanma](../mfc/using-views.md)

- [İletişim kutuları](../mfc/dialog-boxes.md)

- [Denetimler](../mfc/controls-mfc.md)

## <a name="see-also"></a>Ayrıca Bkz.

[Windows](../mfc/windows.md)

