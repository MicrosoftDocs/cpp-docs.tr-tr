---
title: OLE kapsayıcı sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.ole
dev_langs:
- C++
helpviewer_keywords:
- ActiveX classes [MFC]
- container classes [MFC]
- OLE classes [MFC]
- visual editing [MFC], classes
- OLE [MFC], classes
- containers [MFC], OLE container applications
ms.assetid: 1e27e1ab-4c22-41eb-8547-6915c72668ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cfdff6023beeedfa14d37e5b404fa3c223691b85
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349060"
---
# <a name="ole-container-classes"></a>OLE Kapsayıcı Sınıfları
Bu sınıfların kapsayıcı uygulamalar tarafından kullanılır. Her ikisi de `COleLinkingDoc` ve `COleDocument` koleksiyonlarını `COleClientItem` nesneleri. Belge sınıfından türetilen yerine **CDocument**, bu sınıftan türetilen `COleLinkingDoc` veya `COleDocument`bağlantıları belgenizi katıştırılmış nesneler için destek istemenize bağlı olarak.  
  
 Kullanım bir `COleClientItem` her OLE öğesi başka bir belgeden katıştırılmış veya başka bir belge için bir bağlantı belgeyi temsil eden nesne.  
  
 [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md)  
 Etkin belge kapsaması destekler.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Bileşik belge uygulaması, yanı sıra temel kapsayıcı desteği kullanılır. Türetilmiş sınıflar için bir kapsayıcı olarak hizmet veren `CDocItem`. Bu sınıf kapsayıcı belgeler ve taban sınıf için temel sınıf olarak kullanılabilir `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 Öğesinden türetilmiş bir sınıf `COleDocument` , bağlama için altyapı sağlar. Belge sınıfları için kapsayıcı uygulamalarınızdan yerine bu sınıftan türetilmelidir `COleDocument` katıştırılmış nesnelere bağlantılarını desteklemek istiyorsanız.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Zengin düzenleme denetimine OLE istemci öğeleri listesini tutar. İle kullanılan [CRichEditView](../mfc/reference/cricheditview-class.md) ve [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Soyut taban sınıfı `COleClientItem` ve `COleServerItem`. Sınıfların nesnelerini türetilen `CDocItem` belge parçalarını temsil eder.  
  
 [COleClientItem](../mfc/reference/coleclientitem-class.md)  
 Katıştırılmış veya bağlantılı bir OLE öğe bağlantısı istemci tarafında temsil eden bir istemci öğesi sınıf. İstemci öğeleri bu sınıfından türetilir.  
  
 [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md)  
 Öğesi ile kullanıldığında bir zengin düzenleme denetimindeki depolanan bir OLE istemci-tarafı erişim sağlayan `CRichEditView` ve `CRichEditDoc`.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 OLE işlenirken bir hata kaynaklanan bir özel durum. Bu sınıf, kapsayıcılar ve sunucular tarafından kullanılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

