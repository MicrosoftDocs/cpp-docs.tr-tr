---
title: OLE sürükle ve bırak ve veri aktarımı sınıfları | Microsoft Docs
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
- OLE drag and drop [MFC], and data transfer classes
- drag and drop [MFC], classes
- data transfer [MFC], OLE
- data transfer classes [MFC]
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d55d6d171f490631afe17a605f50607fb55f070b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347048"
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE Sürükle/Bırak ve Veri Aktarımı Sınıfları
Bu sınıfların OLE veri aktarımları kullanılır. Bunlar, uygulamalar Pano kullanarak ya da sürükle ve bırak arasında aktarılacak veri izin verin.  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 Sürükle ve bırak işlemi başlangıçtan bitişe kadar denetler. Bu sınıf, sürükleme işlemi başlatıldığında ve sona erdiğinde belirler. Ayrıca sürükle ve bırak işlemi sırasında imleç geri bildirim görüntüler.  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 Bir uygulama için bir veri aktarımı veri sağladığında kullanılır. `COleDataSource` Nesne Odaklı Pano nesnesi olarak görüntülenmesine.  
  
 [COleDropTarget](../mfc/reference/coledroptarget-class.md)  
 Sürükle ve bırak işlemi hedefi temsil eder. A `COleDropTarget` ekranında bir pencere nesnesi karşılık gelir. Tüm veriler sürüklediğinizde bırakılan ve gerçek bırakma işlemi uygulayan kabul edilip edilmeyeceğini belirler.  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 Alıcı tarafında olarak kullanılan `COleDataSource`. `COleDataObject` nesneleri tarafından depolanan verilere erişim sağlayan bir `COleDataSource` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

