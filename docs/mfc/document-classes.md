---
description: 'Daha fazla bilgi edinin: belge sınıfları'
title: Belge Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.document
helpviewer_keywords:
- document classes [MFC]
ms.assetid: 4bf19b02-0a4f-4319-b68e-cddcba2705cb
ms.openlocfilehash: 7f5bd3011dec84cad20b10668e0a997838e79dbb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330283"
---
# <a name="document-classes"></a>Belge Sınıfları

Belge şablonu nesneleri tarafından oluşturulan belge sınıfı nesneleri, uygulamanın verilerini yönetir. Bu sınıflardan birindeki belgeleriniz için bir sınıf türetirsiniz.

Belge sınıfı nesneleri görünüm nesneleriyle etkileşime geçin. Nesneleri görüntüleme, bir pencerenin istemci alanını temsil eder, bir belgenin verilerini görüntüler ve kullanıcıların onunla etkileşime geçmesini sağlar. Belgeler ve görünümler bir belge şablonu nesnesi tarafından oluşturulur.

[CDocument](reference/cdocument-class.md)<br/>
Uygulamaya özgü belgeler için temel sınıf. Belge sınıfınızı veya sınıflarınızı öğesinden türetirsiniz `CDocument` .

[Colet belgesi](reference/coledocument-class.md)<br/>
Bileşik belge uygulamasının yanı sıra temel kapsayıcı desteği için de kullanılır. [CDocItem](reference/cdocitem-class.md)'dan türetilmiş sınıflar için bir kapsayıcı görevi görür. Bu sınıf, kapsayıcı belgeleri için temel sınıf olarak kullanılabilir ve için temel sınıftır `COleServerDoc` .

[Cotalinkingdoc](reference/colelinkingdoc-class.md)<br/>
Öğesinden türetilmiş bir sınıf `COleDocument` , bağlama için altyapıyı sağlar. Kapsayıcı uygulamalarınızın belge sınıflarını, ' ın `COleDocument` katıştırılmış nesne bağlantılarını desteklemesini istiyorsanız yerine bu sınıftan türetirsiniz.

[CRichEditDoc](reference/cricheditdoc-class.md)<br/>
Zengin düzenleme denetimindeki OLE istemci öğelerinin listesini tutar. [CRichEditView](reference/cricheditview-class.md) ve [Cricheditcntridıtem](reference/cricheditcntritem-class.md)ile kullanılır.

[Cotaserverdoc](reference/coleserverdoc-class.md)<br/>
Sunucu-uygulama belge sınıfları için temel sınıf olarak kullanılır. `COleServerDoc` nesneler, [Copaserveritem](reference/coleserveritem-class.md) nesneleriyle etkileşimler aracılığıyla sunucu desteği toplu sağlar. Görsel düzen özelliği, sınıf kitaplığının belge/görünüm mimarisi kullanılarak sağlanır.

[CHtmlEditDoc](reference/chtmleditdoc-class.md)<br/>
, [CHtmlEditView](reference/chtmleditview-class.md)Ile, MFC belge görünümü mimarisinin bağlamı IÇINDE WebBrowser HTML düzenlemesi platformunun işlevlerini sağlar.

## <a name="related-classes"></a>İlgili sınıflar

Belge sınıfı nesneleri kalıcı olabilir. başka bir deyişle, durumlarını bir depolama ortamına yazabilir ve geri okuyabilirler. MFC, `CArchive` belge verilerinin bir depolama ortamına aktarılmasını kolaylaştırmak için sınıfını sağlar.

[CArchive](reference/carchive-class.md)<br/>
Serileştirme yoluyla nesneler için kalıcı depolamayı uygulamak üzere bir [CFile](reference/cfile-class.md) nesnesiyle birlikte çalışır (bkz. [CObject:: Serialize](reference/cobject-class.md#serialize)).

Belgeler, OLE nesneleri de içerebilir. `CDocItem` , sunucunun ve istemci öğelerinin temel sınıfıdır.

[CDocItem](reference/cdocitem-class.md)<br/>
[Colet Clienentidıtem](reference/coleclientitem-class.md) ve [Copaserverıtem](reference/coleserveritem-class.md)soyut temel sınıfı. Sınıfından türetilmiş sınıfların nesneleri `CDocItem` , belgelerin parçalarını temsil eder.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
