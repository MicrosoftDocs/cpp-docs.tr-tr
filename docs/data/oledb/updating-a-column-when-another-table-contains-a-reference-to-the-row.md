---
title: Başka bir tablo satır için bir başvuru içerirken sütunu güncelleştirme | Microsoft Docs
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
ms.openlocfilehash: 17d260f522432a78729c9998c518398dfa41275a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33102891"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Başka Bir Tablo Satır için Başvuru İçerirken Sütunu Güncelleştirme
Bazı sağlayıcılar hangi sütunların satır değişikliği tespit edebilirsiniz, ancak birçok sağlayıcısı olamaz. Sonuç olarak, güncelleştirmeye çalıştığınız satıra bir başvuru olduğunda bir sütunu güncelleştirme hataya neden olabilir. Bu sorunu çözmek için değiştirmek istediğiniz sütunları içeren ayrı bir erişimci oluşturun. Bu erişimcisi sayısı geçirmek `SetData`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Erişimcileri Kullanma](../../data/oledb/using-accessors.md)