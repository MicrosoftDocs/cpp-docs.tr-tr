---
title: Başka bir tablo satıra başvuru içerdiğinde bir sütunu Güncelleştir
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 95cddfd5f030c7bd8d1220cf040de4bc5a883226
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80209488"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Başka Bir Tablo Satır için Başvuru İçerirken Sütunu Güncelleştirme

Bazı sağlayıcılar, satırdaki hangi sütunların değiştiğini tespit edebilir, ancak birçok sağlayıcı olamaz. Sonuç olarak, güncelleştirmeye çalıştığınız satıra bir başvuru olduğunda bir sütunun güncelleştirilmesi hata oluşmasına neden olabilir. Bu sorunu çözmek için yalnızca değiştirmek istediğiniz sütunları tutan ayrı bir erişimci oluşturun. Bu erişimcinin sayısını `SetData`geçirin.

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)
