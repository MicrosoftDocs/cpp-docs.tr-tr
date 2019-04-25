---
title: Ağaç Denetimi ile İletişim
ms.date: 11/04/2016
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
ms.openlocfilehash: 920608724ebb362b91efdcb3eab50b80acd20474
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62151265"
---
# <a name="communicating-with-a-tree-control"></a>Ağaç Denetimi ile İletişim

Arayan üye işlevleri için farklı yöntemler kullanma bir [CTreeCtrl](../mfc/reference/ctreectrl-class.md) nesne nasıl oluşturulduğuna bağlı olarak nesnesi:

- Ağaç denetimi iletişim kutusunda, bir üye değişkeni türü kullanın `CTreeCtrl` , iletişim kutusu sınıfı oluşturma.

- Ağaç denetimi alt pencere ise kullanın `CTreeCtrl` nesnesi (veya işaretçi), kullanılan nesneyi oluşturmak için.

- Kullanıyorsanız, bir `CTreeView` nesne, işlevini [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) ağaç denetimi bir başvuru almak için. Bu değere sahip başka bir başvuruyu başlatmak veya adresine yapılan başvurunun bir `CTreeCtrl` işaretçi.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
