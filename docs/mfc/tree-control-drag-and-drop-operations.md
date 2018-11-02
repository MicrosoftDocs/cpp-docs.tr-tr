---
title: Ağaç Denetimi Sürükle ve Bırak İşlemleri
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
ms.openlocfilehash: 5dc498008c6b019635cd361a950c6d2926e26541
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519372"
---
# <a name="tree-control-drag-and-drop-operations"></a>Ağaç Denetimi Sürükle ve Bırak İşlemleri

Ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) kullanıcı bir öğeyi sürüklemeye başlatıldığında bir bildirim gönderir. Denetim gönderen bir [tvn_begındrag bilgilendirme](/windows/desktop/Controls/tvn-begindrag) kullanıcının öğe farenin sol düğmesiyle sürükleme başladığında bildirim iletisi ve bir [TVN_BEGINRDRAG](/windows/desktop/Controls/tvn-beginrdrag) kullanıcı sürükleme başladığında bildirim iletisi sağ düğme. Ağaç denetimi TVS_DISABLEDRAGDROP stili ağaç denetimi sağlayarak bu bildirimleri göndermesini engelleyebilir.

Bir sürükleme işlemi sırasında çağırarak görüntülenecek bir görüntü elde [CreateDragImage](../mfc/reference/ctreectrl-class.md#createdragimage) üye işlevi. Ağaç denetimi sürüklenen öğenin etikete göre sürükleyerek bir bit eşlem oluşturur. Ağaç denetim görüntü listesi oluşturur, bit eşlem ekler ve bir işaretçi döndürür [Cımagelist](../mfc/reference/cimagelist-class.md) nesne.

Aslında öğesi sürüklediğinde kod sağlamanız gerekir. Bu genellikle görüntü listesi işlevleri sürükleyerek yeteneklerini kullanarak ve işleme içerir [WM_MOUSEMOVE](/windows/desktop/inputdev/wm-mousemove) ve [WM_LBUTTONUP](/windows/desktop/inputdev/wm-lbuttonup) (veya [WM_RBUTTONUP](/windows/desktop/inputdev/wm-rbuttonup)) sürükleme işlemi başladıktan sonra gönderilen iletileri. Görüntü listesi işlevler hakkında daha fazla bilgi için bkz. [Cımagelist](../mfc/reference/cimagelist-class.md) içinde *MFC başvurusu* ve [görüntü listeleri](https://msdn.microsoft.com/library/windows/desktop/bb761389) Windows SDK. Ağaç denetim öğesi sürükleyerek hakkında daha fazla bilgi için bkz. [ağaç görünümü öğesi sürükleyerek](/windows/desktop/Controls/tree-view-controls), Windows SDK'sında da.

Öğeleri bir ağaç denetimi sürükle ve bırak işlemi hedefleri olması durumunda, bir hedef öğe üzerinde fare imlecini olduğunda bilmeniz gerekir. Bunu çağırarak öğrenebilirsiniz [HitTest](../mfc/reference/ctreectrl-class.md#hittest) üye işlevi. Bir nokta ve tamsayı veya adresini belirttiğiniz bir [TVHITTESTINFO](/windows/desktop/api/commctrl/ns-commctrl-tagtvhittestinfo) fare imleci geçerli koordinatları içeren yapısı. İşlevi döndüğünde, tamsayı veya yapı fare imlecini ağaç denetimi göreli konumunu belirten bir bayrak içerir. Ağaç denetimindeki bir öğeyi üzerine imleci ise yapısı tanıtıcı öğesi de içerir.

Çağırarak öğeyi bir Sürükle ve bırak işleminin hedef olduğunu gösterebilir [SetItem](../mfc/reference/ctreectrl-class.md#setitem) durumu ayarlamak için üye işlevi `TVIS_DROPHILITED` değeri. Bu duruma sahip bir öğe, bir Sürükle ve bırak hedef belirtmek için kullanılan stili çizilir.

## <a name="see-also"></a>Ayrıca Bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

