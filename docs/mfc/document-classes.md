---
title: Belge Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.document
helpviewer_keywords:
- document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
ms.openlocfilehash: eee8cf874230874b519bbd2cb3ebb34c7d4c5c80
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484636"
---
# <a name="document-classes"></a>Belge Sınıfları

Belge şablonu nesneleri tarafından oluşturulan belge sınıfı nesneleri uygulamanın verileri yönetin. Bir sınıf bu sınıflardan birine bir belgelerinizi derleyeceği.

Belge sınıfı nesneleri görünüm nesneleri ile etkileşim kurun. Nesneleri görüntüle penceresinin istemci alanını temsil eden, bir belgenin verilerini görüntülemek ve kullanıcıların onunla etkileşime girmesine izin. Belgeler ve görünümler tarafından bir belge şablonu nesnesi oluşturulur.

[CDocument](../mfc/reference/cdocument-class.md)<br/>
Uygulamaya özgü belgeleri için taban sınıf. Belge sınıfı veya sınıflarından türetilen `CDocument`.

[COleDocument](../mfc/reference/coledocument-class.md)<br/>
Bileşik belge uygulaması, ek olarak temel kapsayıcı desteği kullanılır. Türetilen sınıflar için bir kapsayıcı olarak hizmet veren [Cdocıtem](../mfc/reference/cdocitem-class.md). Bu sınıfın temel sınıf olarak kullanılabilir kapsayıcı belgeleri ve temel sınıfı olan `COleServerDoc`.

[COleLinkingDoc](../mfc/reference/colelinkingdoc-class.md)<br/>
Öğesinden türetilen bir sınıf `COleDocument` bağlamak için altyapı sağlar. Belge sınıfları için kapsayıcı uygulamalarınızı yerine bu sınıftan türetilmelidir `COleDocument` katıştırılmış nesnelere bağlantıları desteklemek istiyorsanız.

[CRichEditDoc](../mfc/reference/cricheditdoc-class.md)<br/>
Zengin düzenleme denetimine OLE istemci öğeleri listesini tutar. İle kullanılan [CRichEditView](../mfc/reference/cricheditview-class.md) ve [Cricheditcntrıtem](../mfc/reference/cricheditcntritem-class.md).

[COleServerDoc](../mfc/reference/coleserverdoc-class.md)<br/>
Sunucu uygulaması belge sınıfları için temel sınıf olarak kullanılır. `COleServerDoc` nesneleri sağlar sunucu desteği ile etkileşim aracılığıyla toplu [Coleserverıtem](../mfc/reference/coleserveritem-class.md) nesneleri. Görsel düzenleme özelliği, Sınıf Kitaplığı'nızın belge/görünüm mimarisi kullanılarak sağlanır.

[CHtmlEditDoc](../mfc/reference/chtmleditdoc-class.md)<br/>
Sağladığı ile [CHtmlEditView](../mfc/reference/chtmleditview-class.md), MFC belge görüntüleme mimarisi bağlamında WebBrowser HTML düzenleme platformu işlevlerini.

## <a name="related-classes"></a>İlgili sınıflar

Belge sınıfı nesneleri kalıcı olabilir — diğer bir deyişle, bunlar durumlarını bir depolama ortamına yazabilir ve geri okuyun. MFC sağlar `CArchive` kolaylaştırmak belgenin verilerini bir depolama ortamına aktarmak için sınıf.

[CArchive](../mfc/reference/carchive-class.md)<br/>
İle cooperates bir [CFile](../mfc/reference/cfile-class.md) kalıcı depolama için seri hale getirme nesnelerde uygulamak için nesne (bkz [CObject::Serialize](../mfc/reference/cobject-class.md#serialize)).

Belgeleri de OLE nesneleri içerebilir. `CDocItem` Sunucu ve istemci öğelerin temel sınıftır.

[Cdocıtem](../mfc/reference/cdocitem-class.md)<br/>
Soyut taban sınıfı [Coleclientıtem](../mfc/reference/coleclientitem-class.md) ve [Coleserverıtem](../mfc/reference/coleserveritem-class.md). Sınıfından türetilen sınıfların nesnelerini `CDocItem` belge parçalarını temsil eder.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

