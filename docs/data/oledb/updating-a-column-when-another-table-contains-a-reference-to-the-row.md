---
title: Başka bir tablo satır için başvuru içerirken sütunu güncelleştirme
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 46de5f54a3ec6525f779a6b55a700429a2a84fef
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59039221"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Başka Bir Tablo Satır için Başvuru İçerirken Sütunu Güncelleştirme

Bazı sağlayıcılar hangi sütunların değiştiğini tespit edebilir, ancak birçok sağlayıcı bunu yapamaz. Sonuç olarak, güncelleştirmeye çalıştığınız satıra bir başvuru olduğunda bir sütunu güncelleştirme hataya neden. Bu sorunu çözmek için yalnızca değiştirmek istediğiniz sütunları bulunduran ayrı bir erişimci oluşturun. Geçirmek için bir erişimci sayısını `SetData`.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)