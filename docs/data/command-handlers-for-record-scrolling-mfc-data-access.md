---
title: Kayıt (MFC veri erişimi) kaydırma için komut işleyicileri | Microsoft Docs
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
ms.openlocfilehash: ef2b57bd37441b9a35c26ab36fcf3cb15cd0d878
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39340334"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>Kayıt (MFC veri erişimi) kaydırma için komut işleyicileri
[CRecordView](../mfc/reference/crecordview-class.md) sınıf varsayılan komut işleme için standart aşağıdakileri sağlar:  
  
-   ID_RECORD_MOVE_FIRST  
  
-   ID_RECORD_MOVE_LAST  
  
-   ID_RECORD_MOVE_NEXT  
  
-   ID_RECORD_MOVE_PREV  
  
 `OnMove` Üye işlevini varsayılan komut kayda gelen tüm dört komutları için işleme sağlar. Bu komutları verildiğinde RFX (veya DFX) yeni bir kayıt kümesinin alanlarına yükler ve DDX kayıt formun denetimlere değerlerini taşır. RFX hakkında daha fazla bilgi için bkz. [kayıt alanı değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md).  
  
> [!NOTE]
>  Standart kayıt gezinti komutları ile ilişkili herhangi bir kullanıcı arabirimi nesneleri için bu standart komut kimlikleri kullandığınızdan emin olun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt Görünümünde Gezintiyi Destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)