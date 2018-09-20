---
title: Ağaç denetimi ile iletişim | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- tree controls [MFC], communicating with
- CTreeCtrl class [MFC], calling member functions
- communications, tree controls
- tree controls
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78bb6a6d6421a5336f8efbffc7d24a6121e208e6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46432160"
---
# <a name="communicating-with-a-tree-control"></a>Ağaç Denetimi ile İletişim

Arayan üye işlevleri için farklı yöntemler kullanma bir [CTreeCtrl](../mfc/reference/ctreectrl-class.md) nesne nasıl oluşturulduğuna bağlı olarak nesnesi:

- Ağaç denetimi iletişim kutusunda, bir üye değişkeni türü kullanın `CTreeCtrl` , iletişim kutusu sınıfı oluşturma.

- Ağaç denetimi alt pencere ise kullanın `CTreeCtrl` nesnesi (veya işaretçi), kullanılan nesneyi oluşturmak için.

- Kullanıyorsanız, bir `CTreeView` nesne, işlevini [CTreeView::GetTreeCtrl](../mfc/reference/ctreeview-class.md#gettreectrl) ağaç denetimi bir başvuru almak için. Bu değere sahip başka bir başvuruyu başlatmak veya adresine yapılan başvurunun bir `CTreeCtrl` işaretçi.

## <a name="see-also"></a>Ayrıca Bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

