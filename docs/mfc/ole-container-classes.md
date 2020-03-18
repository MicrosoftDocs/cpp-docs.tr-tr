---
title: OLE Kapsayıcı Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
ms.openlocfilehash: 61db5310637d13da2d2cc183f12f8f62aa60e328
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447660"
---
# <a name="ole-container-classes"></a>OLE Kapsayıcı Sınıfları

Bu sınıflar kapsayıcı uygulamalar tarafından kullanılır. Hem `COleLinkingDoc` hem de `COleDocument` `COleClientItem` nesne koleksiyonlarını yönetir. Belge sınıfınızı `CDocument`türetmek yerine `COleLinkingDoc` veya `COleDocument`türetireceksiniz. Bu, belgenize katıştırılmış nesneler için destek isteyip istemediğinize bağlıdır.

Belgenizde başka bir belgeden eklenmiş veya başka bir belgenin bağlantısı olan her bir OLE öğesini göstermek için bir `COleClientItem` nesnesi kullanın.

[COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)<br/>
Etkin belge kapsamayı destekler.

[Colet belgesi](../mfc/reference/coledocument-class.md)<br/>
Bileşik belge uygulamasının yanı sıra temel kapsayıcı desteği için de kullanılır. `CDocItem`türetilmiş sınıflar için kapsayıcı görevi görür. Bu sınıf, kapsayıcı belgeleri için temel sınıf olarak kullanılabilir ve `COleServerDoc`için temel sınıftır.

[Cotalinkingdoc](../mfc/reference/colelinkingdoc-class.md)<br/>
Bağlama için altyapıyı sağlayan `COleDocument` türetilen bir sınıf. Kapsayıcı uygulamalarınızın belge sınıflarını, `COleDocument` yerine bu sınıftan türetmeniz gerekir. bu nesnelerin gömülü nesnelere bağlantıları desteklemesini istiyorsanız.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Zengin düzenleme denetimindeki OLE istemci öğelerinin listesini tutar. [CRichEditView](../mfc/reference/cricheditview-class.md) ve [Cricheditcntridıtem](../mfc/reference/cricheditcntritem-class.md)ile kullanılır.

[CDocItem](../mfc/reference/cdocitem-class.md)<br/>
`COleClientItem` ve `COleServerItem`soyut temel sınıfı. `CDocItem` türetilen sınıfların nesneleri, belgelerin parçalarını temsil eder.

[COleClientItem](../mfc/reference/coleclientitem-class.md)<br/>
Gömülü veya bağlantılı bir OLE öğesine bağlantının yüzünü temsil eden istemci öğe sınıfı. Bu sınıftan istemci öğelerinizi türetebilirsiniz.

[CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)<br/>
`CRichEditView` ve `CRichEditDoc`birlikte kullanıldığında zengin düzenleme denetiminde depolanan bir OLE öğesine istemci tarafı erişimi sağlar.

[Colet özel durumu](../mfc/reference/coleexception-class.md)<br/>
OLE işlemedeki bir hatadan kaynaklanan bir özel durum. Bu sınıf, hem kapsayıcılar hem de sunucular tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
