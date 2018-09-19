---
title: Başka bir tablo satır için başvuru içerirken sütunu güncelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 6d2d3509b51d083290339514083a541ef9a86b64
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46030670"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Başka Bir Tablo Satır için Başvuru İçerirken Sütunu Güncelleştirme

Bazı sağlayıcılar hangi sütunların değiştiğini tespit edebilir, ancak birçok sağlayıcı bunu yapamaz. Sonuç olarak, güncelleştirmeye çalıştığınız satıra bir başvuru olduğunda bir sütunu güncelleştirme hataya neden. Bu sorunu çözmek için yalnızca değiştirmek istediğiniz sütunları içeren ayrı bir erişimci oluşturun. Geçirmek için bir erişimci sayısını `SetData`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)