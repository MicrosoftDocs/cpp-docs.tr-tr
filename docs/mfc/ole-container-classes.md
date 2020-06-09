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
ms.openlocfilehash: 596b94e7fdbb5d9dc1862867001f6c01c1aea7b2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617803"
---
# <a name="ole-container-classes"></a>OLE Kapsayıcı Sınıfları

Bu sınıflar kapsayıcı uygulamalar tarafından kullanılır. Hem hem de `COleLinkingDoc` `COleDocument` nesne koleksiyonlarını yönetin `COleClientItem` . Belge sınıfınızı ' den türettikten sonra, `CDocument` `COleLinkingDoc` `COleDocument` belgenizde katıştırılmış nesneler için destek isteyip istemediğinize bağlı olarak veya ' dan türetirsiniz.

`COleClientItem`Belgenizde başka bir belgeden eklenen veya başka bir belgenin bağlantısı olan her BIR OLE öğesini temsil eden bir nesne kullanın.

[COleDocObjectItem](reference/coledocobjectitem-class.md)<br/>
Etkin belge kapsamayı destekler.

[Colet belgesi](reference/coledocument-class.md)<br/>
Bileşik belge uygulamasının yanı sıra temel kapsayıcı desteği için de kullanılır. , Öğesinden türetilmiş sınıflar için bir kapsayıcı görevi görür `CDocItem` . Bu sınıf, kapsayıcı belgeleri için temel sınıf olarak kullanılabilir ve için temel sınıftır `COleServerDoc` .

[Cotalinkingdoc](reference/colelinkingdoc-class.md)<br/>
Öğesinden türetilmiş bir sınıf `COleDocument` , bağlama için altyapıyı sağlar. Kapsayıcı uygulamalarınızın belge sınıflarını, ' ın `COleDocument` katıştırılmış nesne bağlantılarını desteklemesini istiyorsanız yerine bu sınıftan türetirsiniz.

[CRichEditDoc](reference/cricheditdoc-class.md)<br/>
Zengin düzenleme denetimindeki OLE istemci öğelerinin listesini tutar. [CRichEditView](reference/cricheditview-class.md) ve [Cricheditcntridıtem](reference/cricheditcntritem-class.md)ile kullanılır.

[CDocItem](reference/cdocitem-class.md)<br/>
Ve soyut taban sınıfı `COleClientItem` `COleServerItem` . Sınıfından türetilmiş sınıfların nesneleri `CDocItem` , belgelerin parçalarını temsil eder.

[COleClientItem](reference/coleclientitem-class.md)<br/>
Gömülü veya bağlantılı bir OLE öğesine bağlantının yüzünü temsil eden istemci öğe sınıfı. Bu sınıftan istemci öğelerinizi türetebilirsiniz.

[CRichEditCntrItem](reference/cricheditcntritem-class.md)<br/>
Ve ile kullanıldığında zengin düzenleme denetiminde depolanan bir OLE öğesine istemci tarafı erişimi sağlar `CRichEditView` `CRichEditDoc` .

[Colet özel durumu](reference/coleexception-class.md)<br/>
OLE işlemedeki bir hatadan kaynaklanan bir özel durum. Bu sınıf, hem kapsayıcılar hem de sunucular tarafından kullanılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
