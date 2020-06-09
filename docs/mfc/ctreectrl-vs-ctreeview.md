---
title: CTreeCtrl ile CTreeView
ms.date: 11/04/2016
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
ms.openlocfilehash: 83e07c75b9eab6df05dbcd0f52cfbe8b90e1d768
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620478"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl ile CTreeView

MFC, ağaç denetimlerini kapsülleyen iki sınıf sağlar: [Ctreeci](reference/ctreectrl-class.md) ve [CTreeView](reference/ctreeview-class.md). Her sınıf farklı durumlarda faydalıdır.

`CTreeCtrl`Düz bir alt pencere denetimine ihtiyacınız olduğunda kullanın; örneğin, bir iletişim kutusunda. Özellikle `CTreeCtrl` , genel iletişim kutusunda olduğu gibi, pencerede başka alt denetimler de varsa, bunu kullanmak istersiniz.

`CTreeView`Ağaç denetiminin belge/görünüm mimarisi ve ağaç denetimi gibi bir görünüm penceresi gibi davranmasını istediğinizde kullanın. Bir `CTreeView` çerçeve penceresinin veya ayırıcı pencerenin tüm istemci alanını kaplayacaktır. Üst penceresi yeniden boyutlandırılırken otomatik olarak yeniden boyutlandırılır ve menü, kısayol tuşları ve araç çubuklarından komut iletilerini işleyebilir. Ağaç denetimi ağacı görüntülemesi gereken verileri içerdiğinden, karşılık gelen belge nesnesinin karmaşık olması gerekmez; [CDocument](reference/cdocument-class.md) 'i belge şablonunuzda belge türü olarak da kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](using-ctreectrl.md)<br/>
[Denetimler](controls-mfc.md)
