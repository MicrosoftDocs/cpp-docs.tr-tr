---
title: "Sürükle ve bırak: bir bırakma kaynağı uygulama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- OLE drag and drop [MFC], initiating drag operations
- drag and drop [MFC], calling DoDragDrop
- OLE drag and drop [MFC], drop source
- OLE drag and drop [MFC], calling DoDragDrop
- drag and drop [MFC], initiating drag operations
- drag and drop [MFC], drop source
ms.assetid: 0ed2fda0-63fa-4b1e-b398-f1f142f40035
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 301980f7f5a901aa4e2cba40357b18311eef581e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="drag-and-drop-implementing-a-drop-source"></a>Sürükle ve Bırak: Bir Bırakma Kaynağı Uygulama
Bu makalede bir Sürükle ve bırak işlemi veri sağlamak için uygulamanızın nasıl elde edileceğini açıklar.  
  
 Temel bir bırakma kaynağı görece basit uygulamasıdır. İlk adım, hangi olayların sürükleme işleminin başlayacağı belirlemektir. Kullanıcı arabirimi yönergelerine tanımlamak sürükleme işlemi başına veri seçimi olarak önerilen ve `WM_LBUTTONDOWN` noktasında seçilen verileri içinde gerçekleşen olay. MFC OLE örnekleri [OCLIENT](../visual-cpp-samples.md) ve [HIERSVR](../visual-cpp-samples.md) aşağıdaki yönergeleri izleyin.  
  
 Uygulamanızı bir kapsayıcı ve seçili veri bağlantılı veya katıştırılmış nesne türü ise `COleClientItem`, çağrı kendi `DoDragDrop` üye işlevi. Aksi takdirde oluşturmak bir `COleDataSource` nesnesi, seçimle başlatmak ve veri kaynağı nesnesinin çağrısı `DoDragDrop` üye işlevi. Uygulamanızı bir sunucu ise kullanın `COleServerItem::DoDragDrop`. Standart sürükle ve bırak davranışını özelleştirme hakkında daha fazla bilgi için bkz: [sürükle ve bırak: özelleştirme](../mfc/drag-and-drop-customizing.md).  
  
 Varsa `DoDragDrop` döndürür `DROPEFFECT_MOVE`, veri kaynağını kaynak belgedeki hemen silin. Gelen dönüş diğer değeri `DoDragDrop` bir bırakma kaynağı üzerinde hiçbir etkisi olmaz.  
  
 Daha fazla bilgi için bkz.:  
  
-   [Bırakma hedefi uygulama](../mfc/drag-and-drop-implementing-a-drop-target.md)  
  
-   [Özelleştirme sürükleme ve bırakma](../mfc/drag-and-drop-customizing.md)  
  
-   [Oluşturma ve OLE veri nesneleri ve veri kaynaklarını yok etme](../mfc/data-objects-and-data-sources-creation-and-destruction.md)  
  
-   [OLE veri nesneleri ve veri kaynakları düzenleme](../mfc/data-objects-and-data-sources-manipulation.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sürükleme ve bırakma (OLE)](../mfc/drag-and-drop-ole.md)   
 [COleDataSource::DoDragDrop](../mfc/reference/coledatasource-class.md#dodragdrop)   
 [COleClientItem::DoDragDrop](../mfc/reference/coleclientitem-class.md#dodragdrop)   
 [CView::OnDragLeave](../mfc/reference/cview-class.md#ondragleave)

