---
title: CTreeCtrl ile CTreeView
ms.date: 11/04/2016
f1_keywords:
- CTreeCtrl
- CTreeView
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
ms.openlocfilehash: 29349e169e5ad8475001235d9b355da52156d683
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271638"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl ile CTreeView

MFC ağaç denetimleri kapsayan iki sınıf sağlar: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) ve [CTreeView](../mfc/reference/ctreeview-class.md). Her sınıf, farklı durumlarda kullanışlıdır.

Kullanım `CTreeCtrl` düz bir alt pencere denetimi; gerektiğinde örneği için bir iletişim kutusu içinde. Özellikle kullanmak isteyebilirsiniz `CTreeCtrl` olacaksa diğer alt denetimler gibi tipik iletişim kutusu penceresinde.

Kullanım `CTreeView` belge/görünüm mimarisinin bir Görünüm penceresinde gibi davranmasını ağaç denetimi yanı sıra bir ağaç denetimi istediğinizde. A `CTreeView` bir çerçeve penceresinin veya ayırıcı penceresi tüm istemci alanını kaplar. Otomatik olarak üst pencereye boyutlandırılır ve menülerini ve Hızlandırıcı tuşları araç çubukları komut iletileri işleyebilir boyutlandırılır. Ağaç denetimi ağaç görüntülemek gereken verileri içerdiğinden, karşılık gelen belge nesnesi karmaşık olması gerekmez; bile kullanabilir [CDocument](../mfc/reference/cdocument-class.md) belge şablonunuzdaki belge türü olarak.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
