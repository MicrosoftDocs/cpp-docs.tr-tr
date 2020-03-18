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
ms.openlocfilehash: 7e01b6d5a7d14e0af4ca760e6e601e91359c8ab1
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447620"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE Sürükle/Bırak ve Veri Aktarımı Sınıfları

Bu sınıflar OLE veri aktarımlarında kullanılır. Bunlar, pano kullanılarak veya sürükleme ve bırakma aracılığıyla verilerin uygulamalar arasında aktarılmasına izin verir.

[COleDropSource](../mfc/reference/coledropsource-class.md)<br/>
Sürükleme ve bırakma işlemini başlangıçtan sona kadar denetler. Bu sınıf sürükleme işleminin ne zaman başlayacağını ve ne zaman sona ereceğini belirler. Sürükle ve bırak işlemi sırasında imleç geri bildirimi de görüntülenir.

[COleDataSource](../mfc/reference/coledatasource-class.md)<br/>
Bir uygulama veri aktarımı için veri sağlıyorsa kullanılır. `COleDataSource`, nesne odaklı bir pano nesnesi olarak görüntülenebilir.

[COleDropTarget](../mfc/reference/coledroptarget-class.md)<br/>
Bir sürükle ve bırak işleminin hedefini temsil eder. `COleDropTarget` nesnesi ekrandaki bir pencereye karşılık gelir. Bu, üzerine bırakılan verilerin kabul edilip edilmeyeceğini belirler ve gerçek bırakma işlemini uygular.

[Cotadataobject](../mfc/reference/coledataobject-class.md)<br/>
`COleDataSource`için alıcı tarafında kullanılır. `COleDataObject` nesneler, bir `COleDataSource` nesnesi tarafından depolanan verilere erişim sağlar.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../mfc/class-library-overview.md)
