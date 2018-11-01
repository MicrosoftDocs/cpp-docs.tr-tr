---
title: OLE Sürükle/Bırak ve Veri Aktarımı Sınıfları
ms.date: 11/04/2016
f1_keywords:
- vc.classes.ole
helpviewer_keywords:
- ActiveX classes [MFC]
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
ms.openlocfilehash: 7520881314da9568f6130f5fe2ccf0a3e0e88e2a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475198"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE Sürükle/Bırak ve Veri Aktarımı Sınıfları

Bu sınıfların OLE veri aktarımlarında kullanılır. Bunlar, verilerin uygulamalar Pano kullanarak ya da sürükle ve bırak arasında aktarılmasına izin verin.

[COleDropSource](../mfc/reference/coledropsource-class.md)<br/>
Sürükle ve bırak işlemi baştan sona denetler. Bu sınıf, sürükleme işlemi başladığında ve sona erdiğinde belirler. Sürükle ve bırak işlemi sırasında imleç geri bildirim de görüntüler.

[COleDataSource](../mfc/reference/coledatasource-class.md)<br/>
Uygulama verileri için bir veri aktarımı sağlar. olduğunda kullanılır. `COleDataSource` nesne yönelimli bir Pano nesne olarak görüntülenen.

[COleDropTarget](../mfc/reference/coledroptarget-class.md)<br/>
Bir Sürükle ve bırak işlemi hedefi temsil eder. A `COleDropTarget` nesne bir pencereyi ekranda karşılık gelir. Tüm veriler sürüklediğinizde bırakılmış ve gerçek bırakma işlemi uygulayan kabul edilip edilmeyeceğini belirler.

[COleDataObject](../mfc/reference/coledataobject-class.md)<br/>
Alıcı tarafı olarak kullanılan `COleDataSource`. `COleDataObject` nesneleri tarafından depolanan verilere erişim sağlayan bir `COleDataSource` nesne.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../mfc/class-library-overview.md)

