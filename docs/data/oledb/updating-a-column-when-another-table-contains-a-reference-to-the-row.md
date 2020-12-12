---
description: 'Daha fazla bilgi edinin: başka bir tablo satıra başvuru Içerdiğinde bir sütunu güncelleştirme'
title: Başka bir tablo satıra başvuru içerdiğinde bir sütunu Güncelleştir
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 5c4562aaaa435c9745bedd146c04c98158d50cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272623"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Başka Bir Tablo Satır için Başvuru İçerirken Sütunu Güncelleştirme

Bazı sağlayıcılar, satırdaki hangi sütunların değiştiğini tespit edebilir, ancak birçok sağlayıcı olamaz. Sonuç olarak, güncelleştirmeye çalıştığınız satıra bir başvuru olduğunda bir sütunun güncelleştirilmesi hata oluşmasına neden olabilir. Bu sorunu çözmek için yalnızca değiştirmek istediğiniz sütunları tutan ayrı bir erişimci oluşturun. Erişimcinin sayısını öğesine geçirin `SetData` .

## <a name="see-also"></a>Ayrıca bkz.

[Erişimcileri kullanma](../../data/oledb/using-accessors.md)
