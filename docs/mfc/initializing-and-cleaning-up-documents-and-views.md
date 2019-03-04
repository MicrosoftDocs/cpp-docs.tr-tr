---
title: Belgeleri ve Görünümleri Başlatma ve Temizleme
ms.date: 11/04/2016
helpviewer_keywords:
- initializing documents [MFC]
- views [MFC], cleaning up
- documents [MFC], initializing
- documents [MFC], cleaning up
- views [MFC], initializing
- initializing objects [MFC], document objects
- document objects [MFC], life cycle of
- initializing views [MFC]
ms.assetid: 95d6f09b-a047-4079-856a-ae7d0548e9d2
ms.openlocfilehash: 59e86f4000e2da588749ca48887d34c3effdfc3a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57286853"
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Başlatma ve Temizleme

Başlatma ve, belgeler ve görünümler sonra Temizleme için aşağıdaki yönergeleri kullanın:

- MFC çerçevesi, belgeler ve görünümler başlatır; bunları Ekle herhangi bir veri başlatır.

- Framework belgeleri olarak temizler ve görünümleri kapatın; yığından bu belgeleri ve görünümleri içindeki üye işlevleri ayrılan herhangi bir bellek ayırması gerekir.

> [!NOTE]
>  Tüm uygulama geçersiz kılmada en iyi şekilde yapılır için o başlatma geri çağırma [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) sınıfının üye işlevinde `CWinApp`, ve temizleme tüm uygulama için en iyi geçersiz Bitti`CWinApp`üye işlevi [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance).

Bir belge (ve alt çerçeve penceresi ve görünümü veya görünümlerde) bir MDI yaşam döngüsünü uygulama aşağıdaki gibidir:

1. Belge Oluşturucu dinamik oluşturma sırasında çağrılır.

1. Her yeni belgenin, belge için [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) veya [OnOpenDocument](../mfc/reference/cdocument-class.md#onopendocument) çağrılır.

1. Belgenin ömrü boyunca kullanıcının etkileşime. Seçme ve veri düzenleme belge verilerine görünüm aracılığıyla kullanıcı çalışıyor gibi genellikle bu gerçekleşir. Görünüm, belge depolama ve diğer görünümleri güncelleştirme için değişiklikleri geçirir. Bu süre boyunca, hem belge ve görünüm komutları işleyebilir.

1. Framework çağrıları [DeleteContents](../mfc/reference/cdocument-class.md#deletecontents) belgeye özgü verileri silmek için.

1. Belgenin yok Edicisi çağrılır.

Belge ilk oluşturulduğunda sonra bir SDI uygulamasında, 1. adım gerçekleştirilir. Daha sonra 2 ile 4 arasındaki adımları her bir yeni belge açıldığında sürekli olarak gerçekleştirilir. Yeni belge mevcut belge nesnesi kullanır. Son olarak, uygulama sona erdiğinde 5. adım gerçekleştirilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belgeleri ve Görünümleri Başlatma](../mfc/initializing-documents-and-views.md)

- [Belgeleri ve Görünümleri Temizleme](../mfc/cleaning-up-documents-and-views.md)

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](../mfc/document-view-architecture.md)
