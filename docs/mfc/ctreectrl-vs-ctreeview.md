---
title: CTreeCtrl ile CTreeView | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CTreeCtrl
- CTreeView
dev_langs:
- C++
helpviewer_keywords:
- tree view controls
- CTreeCtrl class [MFC], vs. CTreeView class [MFC]
- CTreeView class [MFC], vs. CTreeCtrl class [MFC]
- tree controls [MFC], and tree view
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e8acaecbdfb99b8ae0b27023145a0ef6aee1f219
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399158"
---
# <a name="ctreectrl-vs-ctreeview"></a>CTreeCtrl ile CTreeView

MFC ağaç denetimleri kapsayan iki sınıflar sağlar: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) ve [CTreeView](../mfc/reference/ctreeview-class.md). Her sınıf, farklı durumlarda kullanışlıdır.

Kullanım `CTreeCtrl` düz bir alt pencere denetimi; gerektiğinde örneği için bir iletişim kutusu içinde. Özellikle kullanmak isteyebilirsiniz `CTreeCtrl` olacaksa diğer alt denetimler gibi tipik iletişim kutusu penceresinde.

Kullanım `CTreeView` belge/görünüm mimarisinin bir Görünüm penceresinde gibi davranmasını ağaç denetimi yanı sıra bir ağaç denetimi istediğinizde. A `CTreeView` bir çerçeve penceresinin veya ayırıcı penceresi tüm istemci alanını kaplar. Otomatik olarak üst pencereye boyutlandırılır ve menülerini ve Hızlandırıcı tuşları araç çubukları komut iletileri işleyebilir boyutlandırılır. Ağaç denetimi ağaç görüntülemek gereken verileri içerdiğinden, karşılık gelen belge nesnesi karmaşık olması gerekmez; bile kullanabilir [CDocument](../mfc/reference/cdocument-class.md) belge şablonunuzdaki belge türü olarak.

## <a name="see-also"></a>Ayrıca Bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

