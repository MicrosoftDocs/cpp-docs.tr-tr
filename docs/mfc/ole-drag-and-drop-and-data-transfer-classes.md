---
title: "OLE sürükle ve bırak ve veri aktarımı sınıfları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0e8c5a54184bcf6450bf39b39a6b90d7865c09d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-drag-and-drop-and-data-transfer-classes"></a>OLE Sürükle/Bırak ve Veri Aktarımı Sınıfları
Bu sınıfların OLE veri aktarımları kullanılır. Bunlar, uygulamalar Pano kullanarak ya da sürükle ve bırak arasında aktarılacak veri izin verin.  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 Sürükle ve bırak işlemi başlangıçtan bitişe kadar denetler. Bu sınıf, sürükleme işlemi başlatıldığında ve sona erdiğinde belirler. Ayrıca sürükle ve bırak işlemi sırasında imleç geri bildirim görüntüler.  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 Bir uygulama için bir veri aktarımı veri sağladığında kullanılır. `COleDataSource`Nesne Odaklı Pano nesnesi olarak görüntülenmesine.  
  
 [COleDropTarget](../mfc/reference/coledroptarget-class.md)  
 Sürükle ve bırak işlemi hedefi temsil eder. A `COleDropTarget` ekranında bir pencere nesnesi karşılık gelir. Tüm veriler sürüklediğinizde bırakılan ve gerçek bırakma işlemi uygulayan kabul edilip edilmeyeceğini belirler.  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 Alıcı tarafında olarak kullanılan `COleDataSource`. `COleDataObject`nesneleri tarafından depolanan verilere erişim sağlayan bir `COleDataSource` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../mfc/class-library-overview.md)

