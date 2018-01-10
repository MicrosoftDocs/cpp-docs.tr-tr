---
title: "Ağaç denetimi sürükle ve bırak işlemleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 978c577a01b2f574009c601ca594a235e0712d71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-drag-and-drop-operations"></a>Ağaç Denetimi Sürükle ve Bırak İşlemleri
Ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) kullanıcı bir öğeyi sürüklemek başlatıldığında bir bildirim gönderir. Denetim gönderir bir [TVN_BEGINDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773504) kullanıcı sol fare düğmesini bir öğesiyle sürükleyerek başladığında bildirim iletisi ve [TVN_BEGINRDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773509) kullanıcı sürükleme başladığında bildirim iletisi Sağdaki düğme. Ağaç denetimi vererek bu bildirimleri gönderme ağaç denetimi engelleyebilirsiniz **TVS_DISABLEDRAGDROP** stili.  
  
 Çağırarak bir sürükleme işlemi sırasında görüntülenecek bir görüntü elde [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage) üye işlevi. Ağaç denetimi sürüklenen öğenin etikete göre sürükleyerek bir bit eşlem oluşturur. Ağaç denetim resim listesi oluşturur, bit eşlem ekler ve bir işaretçi döndürür [Cımagelist](../mfc/reference/cimagelist-class.md) nesnesi.  
  
 Gerçekte öğesi sürüklediği kod sağlamanız gerekir. Bu görüntü listesi işlevleri sürükleme özelliklerini kullanarak ve işleme genellikle içerir [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) ve [WM_LBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms645608) (veya [WM_RBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646243)) sürükleme işlemi başladıktan sonra gönderilen iletileri. Görüntü listesi işlevleri hakkında daha fazla bilgi için bkz: [Cımagelist](../mfc/reference/cimagelist-class.md) içinde *MFC başvurusu* ve [görüntü listeleri](http://msdn.microsoft.com/library/windows/desktop/bb761389) Windows SDK'sındaki. Ağaç denetim öğesi sürükleme hakkında daha fazla bilgi için bkz: [ağaç görünümü öğesi sürükleyerek](http://msdn.microsoft.com/library/windows/desktop/bb760017), ayrıca [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 Ağaç denetimindeki öğeleri sürükle ve bırak işlemi hedeflerini olması durumunda, fare imleci bir hedef öğede olduğunda bilmeniz gerekir. Arayarak bulabilirsiniz [HitTest](../mfc/reference/ctreectrl-class.md#hittest) üye işlevi. Bir nokta ve tamsayı veya adresini belirttiğiniz bir [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448) fare imleci geçerli koordinatlarını içerir yapısı. İşlevi döndüğünde, tamsayı veya yapısı fare imleci ağaç denetimi göreli konumunu belirten bir bayrak içeriyor. İmleç ağaç denetimindeki bir öğe üzerinde ise, yapısı tanıtıcı öğenin de içerir.  
  
 Çağırarak öğeyi sürükle ve bırak işlemi hedefinin olduğunu gösteriyor [SetItem](../mfc/reference/ctreectrl-class.md#setitem) durumu ayarlamak için üye işlevi `TVIS_DROPHILITED` değeri. Bu durumuna sahip bir öğe bir Sürükle ve bırak hedef göstermek için kullanılan stilde çizilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

