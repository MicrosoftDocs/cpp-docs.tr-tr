---
title: Ağaç denetimi sürükle ve bırak işlemleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9e1c642642f94c021001ae67d2dcc3fd87f4f287
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589091"
---
# <a name="tree-control-drag-and-drop-operations"></a>Ağaç Denetimi Sürükle ve Bırak İşlemleri
Ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) kullanıcı bir öğeyi sürüklemeye başlatıldığında bir bildirim gönderir. Denetim gönderen bir [tvn_begındrag bilgilendirme](http://msdn.microsoft.com/library/windows/desktop/bb773504) kullanıcının öğe farenin sol düğmesiyle sürükleme başladığında bildirim iletisi ve bir [TVN_BEGINRDRAG](http://msdn.microsoft.com/library/windows/desktop/bb773509) kullanıcı sürükleme başladığında bildirim iletisi sağ düğme. Ağaç denetimi TVS_DISABLEDRAGDROP stili ağaç denetimi sağlayarak bu bildirimleri göndermesini engelleyebilir.  
  
 Bir sürükleme işlemi sırasında çağırarak görüntülenecek bir görüntü elde [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage) üye işlevi. Ağaç denetimi sürüklenen öğenin etikete göre sürükleyerek bir bit eşlem oluşturur. Ağaç denetim görüntü listesi oluşturur, bit eşlem ekler ve bir işaretçi döndürür [Cımagelist](../mfc/reference/cimagelist-class.md) nesne.  
  
 Aslında öğesi sürüklediğinde kod sağlamanız gerekir. Bu genellikle görüntü listesi işlevleri sürükleyerek yeteneklerini kullanarak ve işleme içerir [WM_MOUSEMOVE](http://msdn.microsoft.com/library/windows/desktop/ms645616) ve [WM_LBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms645608) (veya [WM_RBUTTONUP](http://msdn.microsoft.com/library/windows/desktop/ms646243)) sürükleme işlemi başladıktan sonra gönderilen iletileri. Görüntü listesi işlevler hakkında daha fazla bilgi için bkz. [Cımagelist](../mfc/reference/cimagelist-class.md) içinde *MFC başvurusu* ve [görüntü listeleri](http://msdn.microsoft.com/library/windows/desktop/bb761389) Windows SDK. Ağaç denetim öğesi sürükleyerek hakkında daha fazla bilgi için bkz. [ağaç görünümü öğesi sürükleyerek](http://msdn.microsoft.com/library/windows/desktop/bb760017), Windows SDK'sında da.  
  
 Öğeleri bir ağaç denetimi sürükle ve bırak işlemi hedefleri olması durumunda, bir hedef öğe üzerinde fare imlecini olduğunda bilmeniz gerekir. Bunu çağırarak öğrenebilirsiniz [HitTest](../mfc/reference/ctreectrl-class.md#hittest) üye işlevi. Bir nokta ve tamsayı veya adresini belirttiğiniz bir [TVHITTESTINFO](http://msdn.microsoft.com/library/windows/desktop/bb773448) fare imleci geçerli koordinatları içeren yapısı. İşlevi döndüğünde, tamsayı veya yapı fare imlecini ağaç denetimi göreli konumunu belirten bir bayrak içerir. Ağaç denetimindeki bir öğeyi üzerine imleci ise yapısı tanıtıcı öğesi de içerir.  
  
 Çağırarak öğeyi bir Sürükle ve bırak işleminin hedef olduğunu gösterebilir [SetItem](../mfc/reference/ctreectrl-class.md#setitem) durumu ayarlamak için üye işlevi `TVIS_DROPHILITED` değeri. Bu duruma sahip bir öğe, bir Sürükle ve bırak hedef belirtmek için kullanılan stili çizilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

