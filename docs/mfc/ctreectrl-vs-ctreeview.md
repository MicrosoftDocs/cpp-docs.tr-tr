---
title: CTreeCtrl ile CTreeView
ms.date: 11/04/2016
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
ms.openlocfilehash: 7c78dfa9920c913fdbedb009c5a6f275a3e3e273
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445223"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl ile CTreeView

MFC, ağaç denetimlerini kapsülleyen iki sınıf sağlar: [Ctreeci](../mfc/reference/ctreectrl-class.md) ve [CTreeView](../mfc/reference/ctreeview-class.md). Her sınıf farklı durumlarda faydalıdır.

Düz bir alt pencere denetimine ihtiyacınız olduğunda `CTreeCtrl` kullanın; Örneğin, bir iletişim kutusunda. Genellikle, normal bir iletişim kutusunda olduğu gibi, pencerede diğer alt denetimler olacak şekilde `CTreeCtrl` kullanmak istersiniz.

Ağaç denetiminin belge/görünüm mimarisi ve ağaç denetimi gibi bir görünüm penceresi gibi davranmasını istediğinizde `CTreeView` kullanın. Bir `CTreeView`, bir çerçeve penceresinin veya ayırıcı pencerenin tüm istemci alanını kaplayacaktır. Üst penceresi yeniden boyutlandırılırken otomatik olarak yeniden boyutlandırılır ve menü, kısayol tuşları ve araç çubuklarından komut iletilerini işleyebilir. Ağaç denetimi ağacı görüntülemesi gereken verileri içerdiğinden, karşılık gelen belge nesnesinin karmaşık olması gerekmez; [CDocument](../mfc/reference/cdocument-class.md) 'i belge şablonunuzda belge türü olarak da kullanabilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
