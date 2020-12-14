---
description: 'Bu konuda daha fazla bilgi edinin: Ctreec, vs. CTreeView'
title: CTreeCtrl ile CTreeView karşılaştırması
ms.date: 11/04/2016
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
ms.openlocfilehash: edaf2662d483a23c7618a143ee4aabe7910cf121
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309426"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl ile CTreeView karşılaştırması

MFC, ağaç denetimlerini kapsülleyen iki sınıf sağlar: [Ctreeci](reference/ctreectrl-class.md) ve [CTreeView](reference/ctreeview-class.md). Her sınıf farklı durumlarda faydalıdır.

`CTreeCtrl`Düz bir alt pencere denetimine ihtiyacınız olduğunda kullanın; örneğin, bir iletişim kutusunda. Özellikle `CTreeCtrl` , genel iletişim kutusunda olduğu gibi, pencerede başka alt denetimler de varsa, bunu kullanmak istersiniz.

`CTreeView`Ağaç denetiminin belge/görünüm mimarisi ve ağaç denetimi gibi bir görünüm penceresi gibi davranmasını istediğinizde kullanın. Bir `CTreeView` çerçeve penceresinin veya ayırıcı pencerenin tüm istemci alanını kaplayacaktır. Üst penceresi yeniden boyutlandırılırken otomatik olarak yeniden boyutlandırılır ve menü, kısayol tuşları ve araç çubuklarından komut iletilerini işleyebilir. Ağaç denetimi ağacı görüntülemesi gereken verileri içerdiğinden, karşılık gelen belge nesnesinin karmaşık olması gerekmez; [CDocument](reference/cdocument-class.md) 'i belge şablonunuzda belge türü olarak da kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](using-ctreectrl.md)<br/>
[Denetimler](controls-mfc.md)
