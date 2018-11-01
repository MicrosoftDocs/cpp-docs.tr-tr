---
title: Ağaç Denetimi ile İletişim
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: a5749b76468a7ba30cd48dc3a9b61f2de7ac67b9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654196"
---
# <a name="communicating-with-a-tree-control"></a>Ağaç Denetimi ile İletişim

Arayan üye işlevleri için farklı yöntemler kullanma bir [CTreeCtrl](../mfc/reference/ctreectrl-class.md) nesne nasıl oluşturulduğuna bağlı olarak nesnesi:

- Ağaç denetimi iletişim kutusunda, bir üye değişkeni türü kullanın `CTreeCtrl` , iletişim kutusu sınıfı oluşturma.

- Ağaç denetimi alt pencere ise kullanın `CTreeCtrl` nesnesi (veya işaretçi), kullanılan nesneyi oluşturmak için.

- Kullanıyorsanız, bir `CTreeView` nesne, işlevini [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) ağaç denetimi bir başvuru almak için. Bu değere sahip başka bir başvuruyu başlatmak veya adresine yapılan başvurunun bir `CTreeCtrl` işaretçi.

## <a name="see-also"></a>Ayrıca Bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

