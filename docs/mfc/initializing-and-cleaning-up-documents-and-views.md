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
ms.openlocfilehash: 3c92d60941cd6542bd0d6c27e8a879dc85e3a3d6
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81377210"
---
# <a name="initializing-and-cleaning-up-documents-and-views"></a>Belgeleri ve Görünümleri Başlatma ve Temizleme

Belgelerinizi ve görünümlerinizi aldıktan sonra başlatma ve temizleme için aşağıdaki yönergeleri kullanın:

- MFC çerçevesi belgeleri ve görünümleri önkarşılar; bunlara eklediğiniz verileri başlangıç olarak alabilirsiniz.

- Çerçeve, belgeler ve görünümler yaklaştıkça temizlenir; yığına ayırdığınız herhangi bir belleği bu belge ve görünümlerin üye işlevleri içinden ayırmanız gerekir.

> [!NOTE]
> Tüm uygulama için başlatma en iyi sınıfın `CWinApp` [InitInstance](../mfc/reference/cwinapp-class.md#initinstance) üye işlevini geçersiz kılma yapılır ve tüm uygulama için temizleme en iyi `CWinApp` üye işlevi [ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance)geçersiz kılma yapılır hatırlayın.

Bir MDI uygulamasındabir belgenin yaşam döngüsü (ve çerçeve penceresi ve görünümü veya görünümleri) aşağıdaki gibidir:

1. Dinamik oluşturma sırasında, belge oluşturucu denir.

1. Her yeni belge için belgenin [OnNewDocument](../mfc/reference/cdocument-class.md#onnewdocument) veya [OnOpenDocument'ı](../mfc/reference/cdocument-class.md#onopendocument) çağrılır.

1. Kullanıcı, ömrü boyunca belgeyle etkileşime geçer. Genellikle bu, kullanıcı görünüm üzerinden belge verileri üzerinde çalışırken, verileri seçip düzenlerken gerçekleşir. Görünüm, diğer görünümleri depolamak ve güncelleştirmek için belgeye değişiklikleri geçirir. Bu süre zarfında hem belge hem de görünüm komutları işleyebilir.

1. Çerçeve, [DeleteContents'i](../mfc/reference/cdocument-class.md#deletecontents) belgeye özgü verileri silmek için çağırır.

1. Belgenin yıkıcıdenir.

Bir SDI uygulamasında, belge ilk oluşturulduğunda adım 1 bir kez gerçekleştirilir. Daha sonra, yeni bir belge her açıldığında 2'den 4'e kadar olan adımlar tekrar tekrar gerçekleştirilir. Yeni belge, varolan belge nesnesini yeniden kullanır. Son olarak, uygulama sona erdiğinde adım 5 gerçekleştirilir.

## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilmek istiyorum

- [Belgeleri ve Görünümleri Başlatma](../mfc/initializing-documents-and-views.md)

- [Belge ve Görünümleri Temizleme](../mfc/cleaning-up-documents-and-views.md)

## <a name="see-also"></a>Ayrıca bkz.

[Belge/Görünüm Mimarisi](../mfc/document-view-architecture.md)
