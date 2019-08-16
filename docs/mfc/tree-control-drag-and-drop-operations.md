---
title: Ağaç Denetimi Sürükle ve Bırak İşlemleri
ms.date: 11/04/2016
helpviewer_keywords:
- CTreeCtrl class [MFC], drag and drop operations
- drag and drop [MFC], CTreeCtrl
- tree controls [MFC], drag and drop operations
ms.assetid: 3cf78b4c-4579-4fe1-9bc9-c5ab876e4af1
ms.openlocfilehash: 5d2c5aa511844a3d7cbe64d9a15f8ffb46046b29
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510913"
---
# <a name="tree-control-drag-and-drop-operations"></a>Ağaç Denetimi Sürükle ve Bırak İşlemleri

Ağaç denetimi ([Ctreeci](../mfc/reference/ctreectrl-class.md)) Kullanıcı bir öğeyi sürüklemeye başladığında bir bildirim gönderir. Kullanıcı sağ düğmeyle sürüklemeye başladığında Kullanıcı bir öğeyi sol fare düğmesi ve bir [TVN_BEGINRDRAG](/windows/win32/Controls/tvn-beginrdrag) bildirim iletisi ile sürüklemeye başladığında denetim bir [TVN_BEGINDRAG](/windows/win32/Controls/tvn-begindrag) bildirim iletisi gönderir. Ağaç denetiminin TVS_DISABLEDRAGDROP stilini vererek, bir ağaç denetiminin bu bildirimleri göndermesini önleyebilirsiniz.

Bir sürükleme işlemi sırasında [Createdragimage](../mfc/reference/ctreectrl-class.md#createdragimage) üye işlevini çağırarak görüntülenecek bir görüntü elde edersiniz. Ağaç denetimi, sürüklediğiniz öğenin etiketine göre bir sürükleme bit eşlemi oluşturur. Sonra ağaç denetimi bir görüntü listesi oluşturur, bit eşlemini buna ekler ve [CImageList](../mfc/reference/cimagelist-class.md) nesnesine bir işaretçi döndürür.

Öğeyi gerçekten sürüklediği kodu sağlamanız gerekir. Bu genellikle görüntü listesi işlevlerinin sürükleme özelliklerini kullanmayı ve sürükleme işlemi başladıktan sonra gönderilen [WM_MOUSEMOVE](/windows/win32/inputdev/wm-mousemove) ve [WM_LBUTTONUP](/windows/win32/inputdev/wm-lbuttonup) (veya [WM_RBUTTONUP](/windows/win32/inputdev/wm-rbuttonup)) iletilerini işlemeyi içerir. Görüntü listesi işlevleri hakkında daha fazla bilgi için, Windows SDK *MFC başvurusu* ve [görüntü listelerindeki](/windows/win32/controls/image-lists) [CImageList](../mfc/reference/cimagelist-class.md) bölümüne bakın. Ağaç denetim öğesini sürükleme hakkında daha fazla bilgi için, bkz. [Ağaç Görünüm öğesini](/windows/win32/Controls/tree-view-controls)de Windows SDK sürükleme.

Bir ağaç denetimindeki öğeler sürükle ve bırak işleminin hedefi ise, fare imlecinin bir hedef öğe üzerinde ne zaman olduğunu bilmeniz gerekir. [HitTest](../mfc/reference/ctreectrl-class.md#hittest) üye işlevini çağırarak bulabilirsiniz. Bir nokta ve tamsayı ya da fare imlecinin geçerli koordinatlarını içeren bir [Tvhittestınfo](/windows/win32/api/commctrl/ns-commctrl-tvhittestinfo) yapısının adresini belirtirsiniz. İşlev döndürüldüğünde, tamsayı veya yapı, ağaç denetimine göre fare imlecinin konumunu gösteren bir bayrak içerir. İmleç ağaç denetimindeki bir öğenin üzerindeyken, yapı öğenin tanıtıcısını de içerir.

Bir öğenin bir sürükle ve bırak işleminin hedefi olduğunu, durumu `TVIS_DROPHILITED` değere ayarlamak için [SetItem](../mfc/reference/ctreectrl-class.md#setitem) üye işlevini çağırarak belirtebilirsiniz. Bu duruma sahip bir öğe, sürükle ve bırak hedefini göstermek için kullanılan stilde çizilir.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
