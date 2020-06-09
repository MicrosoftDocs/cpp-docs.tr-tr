---
title: OLE Sürükle/Bırak ve Veri Aktarımı Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
ms.openlocfilehash: 530b1772dfb623689facd5b14eebe9ed1eacd4fd
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84624139"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE Sürükle/Bırak ve Veri Aktarımı Sınıfları

Bu sınıflar OLE veri aktarımlarında kullanılır. Bunlar, pano kullanılarak veya sürükleme ve bırakma aracılığıyla verilerin uygulamalar arasında aktarılmasına izin verir.

[COleDropSource](reference/coledropsource-class.md)<br/>
Sürükleme ve bırakma işlemini başlangıçtan sona kadar denetler. Bu sınıf sürükleme işleminin ne zaman başlayacağını ve ne zaman sona ereceğini belirler. Sürükle ve bırak işlemi sırasında imleç geri bildirimi de görüntülenir.

[COleDataSource](reference/coledatasource-class.md)<br/>
Bir uygulama veri aktarımı için veri sağlıyorsa kullanılır. `COleDataSource`nesne odaklı bir pano nesnesi olarak görüntülenebilir.

[COleDropTarget](reference/coledroptarget-class.md)<br/>
Bir sürükle ve bırak işleminin hedefini temsil eder. Bir `COleDropTarget` nesne ekrandaki bir pencereye karşılık gelir. Bu, üzerine bırakılan verilerin kabul edilip edilmeyeceğini belirler ve gerçek bırakma işlemini uygular.

[Cotadataobject](reference/coledataobject-class.md)<br/>
Alıcı tarafı olarak ' de kullanılır `COleDataSource` . `COleDataObject`nesneler bir nesne tarafından depolanan verilere erişim sağlar `COleDataSource` .

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](class-library-overview.md)
