---
title: "Belge sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.classes.document
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5a2436b46b7486bd30398dffc530d2adea3d2e48
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="document-classes"></a>Belge Sınıfları
Belge şablonu nesneler tarafından oluşturulan belge sınıfı nesneleri uygulamanın veri yönetin. Bir sınıf belgeleriniz için bu sınıfların birinden türetin.  
  
 Belge sınıfı nesneleri görünüm nesnelerle etkileşim. Görünüm nesneleri penceresinin istemci alanını temsil eder, bir belgenin verileri görüntülemek ve kullanıcıların ile etkileşime girmesine izin. Belgeler ve görünümler bir belge şablonu nesnesi tarafından oluşturulur.  
  
 [CDocument](../mfc/reference/cdocument-class.md)  
 Uygulamaya özgü belgeleri için temel sınıf. Belge sınıfı veya sınıftan türetilen **CDocument**.  
  
 [COleDocument](../mfc/reference/coledocument-class.md)  
 Bileşik belge uygulaması, yanı sıra temel kapsayıcı desteği kullanılır. Türetilmiş sınıflar için bir kapsayıcı olarak hizmet veren [CDocItem](../mfc/reference/cdocitem-class.md). Bu sınıf kapsayıcı belgeler ve taban sınıf için temel sınıf olarak kullanılabilir `COleServerDoc`.  
  
 [COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)  
 Öğesinden türetilmiş bir sınıf `COleDocument` , bağlama için altyapı sağlar. Belge sınıfları için kapsayıcı uygulamalarınızdan yerine bu sınıftan türetilmelidir `COleDocument` katıştırılmış nesnelere bağlantılarını desteklemek istiyorsanız.  
  
 [CRichEditDoc](../mfc/reference/cricheditdoc-class.md)  
 Zengin düzenleme denetimine OLE istemci öğeleri listesini tutar. İle kullanılan [CRichEditView](../mfc/reference/cricheditview-class.md) ve [CRichEditCntrItem](../mfc/reference/cricheditcntritem-class.md).  
  
 [COleServerDoc](../mfc/reference/coleserverdoc-class.md)  
 Sunucu uygulaması belge sınıfları için temel sınıf olarak kullanılır. `COleServerDoc`nesneler sağlayın sunucu desteği ile etkileşim aracılığıyla toplu [COleServerItem](../mfc/reference/coleserveritem-class.md) nesneleri. Görsel düzenleme yeteneğini sınıf kitaplığının belge/görünüm mimarisi kullanarak sağlanır.  
  
 [CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)  
 Sağladığı ile [CHtmlEditView](../mfc/reference/chtmleditview-class.md), MFC belge görünüm mimarisi bağlamında WebBrowser HTML düzenleme platform işlevselliğini.  
  
## <a name="related-classes"></a>İlgili sınıflar  
 Belge sınıfı nesneleri kalıcı olabilir — diğer bir deyişle, bunlar durumlarına bir depolama ortamına yazabilir ve geri okuyun. MFC sağlar `CArchive` belgenin verileri bir depolama ortamına aktarmak kolaylaştırmak için sınıf.  
  
 [CArchive](../mfc/reference/carchive-class.md)  
 İle cooperates bir [CFile](../mfc/reference/cfile-class.md) nesneleri seri hale getirme yoluyla için kalıcı depolama uygulamak için nesne (bkz [CObject::Serialize](../mfc/reference/cobject-class.md#serialize)).  
  
 Belgeleri de OLE nesneleri içerebilir. `CDocItem`Sunucu ve istemci öğelerinin temel sınıftır.  
  
 [CDocItem](../mfc/reference/cdocitem-class.md)  
 Soyut taban sınıfı [COleClientItem](../mfc/reference/coleclientitem-class.md) ve [COleServerItem](../mfc/reference/coleserveritem-class.md). Sınıfların nesnelerini türetilen `CDocItem` belge parçalarını temsil eder.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

