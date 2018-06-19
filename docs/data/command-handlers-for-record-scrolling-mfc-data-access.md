---
title: Komut işleyicileri (MFC veri erişimi) kaydırma kaydı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 03dec2e3eff0f61db5f4c8b7573400a589615b02
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089385"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>Kayıt (MFC veri erişimi) kaydırma için komut işleyicileri
[CRecordView](../mfc/reference/crecordview-class.md) sınıfı, varsayılan komut aşağıdaki standart komutlar için işleme sağlar:  
  
-   **ID_RECORD_MOVE_FIRST**  
  
-   **ID_RECORD_MOVE_LAST**  
  
-   **ID_RECORD_MOVE_NEXT**  
  
-   **ID_RECORD_MOVE_PREV**  
  
 `OnMove` Üye işlevi varsayılan komut gelen kayda tüm dört komutları için işleme sağlar. Bu komutları verildiğinde RFX (ya da DFX) yeni kayıt kümesinin alanlarına yükler ve DDX değerleri kayıt formun denetimlere taşır. RFX hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md).  
  
> [!NOTE]
>  Bu standart komut kimlikleri standart kayıt gezinme komutları ile ilişkili herhangi bir kullanıcı arabirimi nesneleri için kullandığınızdan emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt Görünümünde Gezintiyi Destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)