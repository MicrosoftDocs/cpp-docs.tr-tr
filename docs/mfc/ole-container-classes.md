---
title: OLE Kapsayıcı Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
ms.openlocfilehash: 87db824e5ab4daec15870b245ea8341be7442109
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57292568"
---
# <a name="ole-container-classes"></a>OLE Kapsayıcı Sınıfları

Bu sınıflar, kapsayıcı uygulamalar tarafından kullanılır. Her ikisi de `COleLinkingDoc` ve `COleDocument` koleksiyonları yönetme `COleClientItem` nesneleri. Öğesinden, belge sınıfı türetme yerine `CDocument`, bu sınıftan türetilen `COleLinkingDoc` veya `COleDocument`bağlantıları belgenize katıştırılmış nesneler için destek istemediğinizi bağlı olarak.

Kullanım bir `COleClientItem` başka bir belgeden gömülü veya başka bir belge bağlantısına belgeyi her OLE öğesinde göstermek için nesne.

[Coledocobjectıtem](../mfc/reference/coledocobjectitem-class.md)<br/>
Etkin belge kapsaması destekler.

[COleDocument](../mfc/reference/coledocument-class.md)<br/>
Bileşik belge uygulaması, ek olarak temel kapsayıcı desteği kullanılır. Türetilen sınıflar için bir kapsayıcı olarak hizmet veren `CDocItem`. Bu sınıfın temel sınıf olarak kullanılabilir kapsayıcı belgeleri ve temel sınıfı olan `COleServerDoc`.

[COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)<br/>
Öğesinden türetilen bir sınıf `COleDocument` bağlamak için altyapı sağlar. Belge sınıfları için kapsayıcı uygulamalarınızı yerine bu sınıftan türetilmelidir `COleDocument` katıştırılmış nesnelere bağlantıları desteklemek istiyorsanız.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Zengin düzenleme denetimine OLE istemci öğeleri listesini tutar. İle kullanılan [CRichEditView](../mfc/reference/cricheditview-class.md) ve [Cricheditcntrıtem](../mfc/reference/cricheditcntritem-class.md).

[Cdocıtem](../mfc/reference/cdocitem-class.md)<br/>
Soyut taban sınıfı `COleClientItem` ve `COleServerItem`. Sınıfından türetilen sınıfların nesnelerini `CDocItem` belge parçalarını temsil eder.

[Coleclientıtem](../mfc/reference/coleclientitem-class.md)<br/>
Gömülü veya bağlantılı OLE öğesini bağlantı istemci tarafında temsil eden bir istemci Item sınıfı. İstemci öğelerinizi sınıfından türetilir.

[Cricheditcntrıtem](../mfc/reference/cricheditcntritem-class.md)<br/>
OLE öğesi ile kullanıldığında bir zengin düzenleme denetimindeki depolanan istemci tarafı erişim sağlayan `CRichEditView` ve `CRichEditDoc`.

[COleException](../mfc/reference/coleexception-class.md)<br/>
OLE işlenirken bir hata kaynaklanan bir özel durum. Bu sınıf, kapsayıcılar ve sunucular tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)
