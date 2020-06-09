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
ms.openlocfilehash: c5beed5618d4fa991160ad1688a5a686aeaa842f
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626363"
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Başlatma ve Temizleme

Belgeleriniz ve görünümleriniz sonrasında başlatma ve temizleme için aşağıdaki yönergeleri kullanın:

- MFC çerçevesi belgeler ve görünümleri başlatır; Bunlara eklediğiniz tüm verileri başlatırsınız.

- Çerçeve, belgeler ve görünümler kapalı olarak temizlenir; yığında ayrılan tüm belleği, bu belge ve görünümlerin üye işlevleri içinden serbest bırakmak zorundasınız.

> [!NOTE]
> Tüm uygulama için başlatmanın en iyi şekilde, sınıfının [InitInstance](reference/cwinapp-class.md#initinstance) üye işlevini geçersiz kılmanızda `CWinApp` ve tüm uygulamanın temizlenmesi En Iyi şekilde, `CWinApp` [ExitInstance](reference/cwinapp-class.md#exitinstance)üye işlevi geçersiz kılmanızda yapılır.

Bir MDI uygulamasındaki bir belgenin (ve çerçeve penceresinin ve görüntüleme ya da görünümlerinin) yaşam döngüsü aşağıdaki gibidir:

1. Dinamik oluşturma sırasında belge Oluşturucu çağırılır.

1. Her yeni belge için, belgenin [OnNewDocument](reference/cdocument-class.md#onnewdocument) veya [OnOpenDocument](reference/cdocument-class.md#onopendocument) çağırılır.

1. Kullanıcı, süresi boyunca belge ile etkileşime girer. Genellikle bu durum, Kullanıcı belge verilerinde görünüm, verileri seçme ve düzenlemeyle çalışma gibi olur. Görünüm, diğer görünümleri depolamak ve güncelleştirmek için belgeye değişiklikleri geçirir. Bu süre boyunca hem belge hem de görünüm komutları işleyebilir.

1. Çerçeve, bir belgeye özgü verileri silmek için [DeleteContents](reference/cdocument-class.md#deletecontents) 'i çağırır.

1. Belgenin yıkıcısı çağrılır.

Bir SDI uygulamasında, 1. adım, belge ilk oluşturulduğunda bir kez gerçekleştirilir. Sonra her yeni belge açıldığında 2 ile 4 arasındaki adımlar sürekli olarak gerçekleştirilir. Yeni belge, varolan belge nesnesini yeniden kullanır. Son olarak, uygulama sona erdiğinde 5. adım gerçekleştirilir.

## <a name="what-do-you-want-to-know-more-about"></a>Hakkında daha fazla bilgi edinmek istiyorsunuz

- [Belgeleri ve görünümleri başlatma](initializing-documents-and-views.md)

- [Belge ve görünümleri Temizleme](cleaning-up-documents-and-views.md)

## <a name="see-also"></a>Ayrıca bkz.

[Belge/görünüm mimarisi](document-view-architecture.md)
