---
title: Başka bir tablo satır için başvuru içerirken sütunu güncelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 10/24/2018
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
ms.openlocfilehash: 7998897c80e392326213324804c1809656e051f3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50071829"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>Başka Bir Tablo Satır için Başvuru İçerirken Sütunu Güncelleştirme

Bazı sağlayıcılar hangi sütunların değiştiğini tespit edebilir, ancak birçok sağlayıcı bunu yapamaz. Sonuç olarak, güncelleştirmeye çalıştığınız satıra bir başvuru olduğunda bir sütunu güncelleştirme hataya neden. Bu sorunu çözmek için yalnızca değiştirmek istediğiniz sütunları bulunduran ayrı bir erişimci oluşturun. Geçirmek için bir erişimci sayısını `SetData`.

## <a name="see-also"></a>Ayrıca Bkz.

[Erişimcileri Kullanma](../../data/oledb/using-accessors.md)