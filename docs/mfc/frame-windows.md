---
description: 'Daha fazla bilgi edinin: çerçeve pencereleri'
title: Çerçeve Pencereleri
ms.date: 11/19/2018
helpviewer_keywords:
- document frame windows [MFC]
- windows [MFC], MDI
- window classes [MFC], frame
- single document interface (SDI) [MFC]
- single document interface (SDI) [MFC], frame windows
- views [MFC], and frame windows
- CFrameWnd class [MFC], frame windows
- frame windows [MFC]
- frame windows [MFC], about frame windows
- MFC, frame windows
- MDI [MFC], frame windows
- splitter windows [MFC], and frame windows
ms.assetid: 40677339-8135-4f5e-aba6-3fced3078077
ms.openlocfilehash: ee993b7f8314c28dba38c9ca607366f6fb93da1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193506"
---
# <a name="frame-windows"></a>Çerçeve Pencereleri

Bir uygulama Windows altında çalıştığında, Kullanıcı çerçeve pencereleri içinde gösterilecek belgelerle etkileşime girer. Bir belge çerçevesi penceresinde iki ana bileşen vardır: çerçeve ve çerçevenin içeriği. Belge çerçevesi penceresi [tek bir belge arabirimi](sdi-and-mdi.md) (SDI) çerçeve penceresi veya [birden çok belge arabirimi](sdi-and-mdi.md) (MDI) alt penceresi olabilir. Windows, kullanıcının çerçeve penceresiyle olan etkileşimini çoğunu yönetir: pencereyi taşıma ve yeniden boyutlandırma, kapatma ve en aza indirme ve kaplama. Çerçevenin içindeki içerikleri yönetirsiniz.

## <a name="frame-windows-and-views"></a>Çerçeve pencereleri ve görünümleri

MFC çerçevesi, görünümler içermesi için çerçeve pencerelerini kullanır. İki bileşen (çerçeve ve içerik) MFC 'de iki farklı sınıf tarafından temsil edilir ve yönetilir. Çerçeve pencere sınıfı çerçeveyi yönetir ve bir görünüm sınıfı içeriği yönetir. Görünüm penceresi, çerçeve penceresinin bir alt öğesidir. Belge ile çizim ve diğer Kullanıcı etkileşimi, çerçeve penceresinin istemci alanına değil, görünümün istemci alanında yer alır. Çerçeve penceresi bir görünüm etrafında görünür bir çerçeve sağlar, bir resim yazısı çubuğu ve bir denetim menüsü gibi standart pencere denetimleri, pencereyi en aza indirmek ve en üst düzeye çıkarmak için düğmeler ve pencereyi yeniden boyutlandırma denetimleri sağlar. "İçerik", bir alt pencere tarafından tam olarak bulunan pencerenin istemci alanından oluşur — görünüm. Aşağıdaki şekilde bir çerçeve penceresi ve bir görünüm arasındaki ilişki gösterilmektedir.

![Çerçeve penceresi görünümü](../mfc/media/vc37fx1.gif "Çerçeve penceresi görünümü") <br/>
Çerçeve penceresi ve görünümü

## <a name="frame-windows-and-splitter-windows"></a>Çerçeve pencereleri ve Splitter pencereleri

Yaygın olarak kullanılan başka bir düzenleme ise çerçeve penceresinin, genellikle bir [Splitter penceresi](multiple-document-types-views-and-frame-windows.md)kullanarak birden çok görünümü çerçeveledir. Bölümlendirici penceresinde, çerçeve penceresinin istemci alanı bir ayırıcı pencere ile kullanılıyor. Bu, sırasıyla, görünümler olarak adlandırılan birden çok alt pencere içerir.

### <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

**Genel çerçeve penceresi konuları**

- [Pencere nesneleri](window-objects.md)

- [Çerçeve penceresi sınıfları](frame-window-classes.md)

- [Uygulama Sihirbazı tarafından oluşturulan Frame-Window sınıfları](frame-window-classes-created-by-the-application-wizard.md)

- [Çerçeve pencere stilleri](frame-window-styles-cpp.md)

- [Çerçeve pencerelerinin görevi](what-frame-windows-do.md)

**Çerçeve pencerelerini kullanma konuları**

- [Çerçeve pencerelerini kullanma](using-frame-windows.md)

- [Belge çerçeve pencereleri oluşturma](creating-document-frame-windows.md)

- [Çerçeve pencerelerini yok etme](destroying-frame-windows.md)

- [MDI alt öğe pencerelerini yönetme](managing-mdi-child-windows.md)

- Birden fazla görünüm içeren bir çerçeve penceresinde [geçerli görünümü yönetme](managing-the-current-view.md)

- [Menüleri, denetim çubuklarını ve hızlandırıcıları yönetme (çerçeve penceresinin alanını paylaşan diğer nesneler)](managing-menus-control-bars-and-accelerators.md)

**Özel çerçeve penceresi özellikleri hakkında konular**

- Dosyaları dosya Gezgini 'nden veya dosya yöneticisinden bir çerçeve penceresine [sürükleme ve bırakma](dragging-and-dropping-files-in-a-frame-window.md)

- [Dinamik veri değişimine yanıt verme (DDE)](responding-to-dynamic-data-exchange-dde.md)

- [Semimodal durumlar: bağlama duyarlı Windows Yardımı (diğer pencere eylemlerini yönetme)](orchestrating-other-window-actions.md)

- [Semimodal durumlar: yazdırma ve Baskı Önizleme (diğer pencere eylemlerini düzenleme)](orchestrating-other-window-actions.md)

**Diğer Windows türleriyle ilgili konular**

- [Görünümleri kullanma](using-views.md)

- [İletişim kutuları](dialog-boxes.md)

- [Denetimler](controls-mfc.md)

## <a name="see-also"></a>Ayrıca bkz.

[Windows](windows.md)
