---
title: Belge sınıfları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.document
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 33068a96d8d0ca0a228012385da6437c455468e5
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928547"
---
# <a name="document-classes"></a>Belge Sınıfları
Belge şablonu nesneler tarafından oluşturulan belge sınıfı nesneleri uygulamanın veri yönetin. Bir sınıf belgeleriniz için bu sınıfların birinden türetin.  
  
 Belge sınıfı nesneleri görünüm nesnelerle etkileşim. Görünüm nesneleri penceresinin istemci alanını temsil eder, bir belgenin verileri görüntülemek ve kullanıcıların ile etkileşime girmesine izin. Belgeler ve görünümler bir belge şablonu nesnesi tarafından oluşturulur.  
  
 [CDocument](../mfc/reference/cdocument-class.md)  
 Uygulamaya özgü belgeleri için temel sınıf. Belge sınıfı veya sınıftan türetilen `CDocument`.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Bileşik belge uygulaması, yanı sıra temel kapsayıcı desteği kullanılır. Türetilmiş sınıflar için bir kapsayıcı olarak hizmet veren [CDocItem](../mfc/reference/cdocitem-class.md). Bu sınıf kapsayıcı belgeler ve taban sınıf için temel sınıf olarak kullanılabilir `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 Öğesinden türetilmiş bir sınıf `COleDocument` , bağlama için altyapı sağlar. Belge sınıfları için kapsayıcı uygulamalarınızdan yerine bu sınıftan türetilmelidir `COleDocument` katıştırılmış nesnelere bağlantılarını desteklemek istiyorsanız.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Zengin düzenleme denetimine OLE istemci öğeleri listesini tutar. İle kullanılan [CRichEditView](../mfc/reference/cricheditview-class.md) ve [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Sunucu uygulaması belge sınıfları için temel sınıf olarak kullanılır. `COleServerDoc` nesneler sağlayın sunucu desteği ile etkileşim aracılığıyla toplu [COleServerItem](../mfc/reference/coleserveritem-class.md) nesneleri. Görsel düzenleme yeteneğini sınıf kitaplığının belge/görünüm mimarisi kullanarak sağlanır.  
  
 [CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)  
 Sağladığı ile [CHtmlEditView](../mfc/reference/chtmleditview-class.md), MFC belge görünüm mimarisi bağlamında WebBrowser HTML düzenleme platform işlevselliğini.  
  
## <a name="related-classes"></a>İlgili sınıflar  
 Belge sınıfı nesneleri kalıcı olabilir — diğer bir deyişle, bunlar durumlarına bir depolama ortamına yazabilir ve geri okuyun. MFC sağlar `CArchive` belgenin verileri bir depolama ortamına aktarmak kolaylaştırmak için sınıf.  
  
 [CArchive](../mfc/reference/carchive-class.md)  
 İle cooperates bir [CFile](../mfc/reference/cfile-class.md) nesneleri seri hale getirme yoluyla için kalıcı depolama uygulamak için nesne (bkz [CObject::Serialize](../mfc/reference/cobject-class.md#serialize)).  
  
 Belgeleri de OLE nesneleri içerebilir. `CDocItem` Sunucu ve istemci öğelerinin temel sınıftır.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Soyut taban sınıfı [COleClientItem](../mfc/reference/coleclientitem-class.md) ve [COleServerItem](../mfc/reference/coleserveritem-class.md). Sınıfların nesnelerini türetilen `CDocItem` belge parçalarını temsil eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

