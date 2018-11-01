---
title: Kayıt (MFC veri erişimi) kaydırma için komut işleyicileri
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
ms.openlocfilehash: 0e35baf561693b90b661ac1fe73844961570b29e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460781"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>Kayıt (MFC veri erişimi) kaydırma için komut işleyicileri

[CRecordView](../mfc/reference/crecordview-class.md) sınıf varsayılan komut işleme için standart aşağıdakileri sağlar:

- ID_RECORD_MOVE_FIRST

- ID_RECORD_MOVE_LAST

- ID_RECORD_MOVE_NEXT

- ID_RECORD_MOVE_PREV

`OnMove` Üye işlevini varsayılan komut kayda gelen tüm dört komutları için işleme sağlar. Bu komutları verildiğinde RFX (veya DFX) yeni bir kayıt kümesinin alanlarına yükler ve DDX kayıt formun denetimlere değerlerini taşır. RFX hakkında daha fazla bilgi için bkz. [kayıt alanı değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md).

> [!NOTE]
>  Standart kayıt gezinti komutları ile ilişkili herhangi bir kullanıcı arabirimi nesneleri için bu standart komut kimlikleri kullandığınızdan emin olun.

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt Görünümünde Gezintiyi Destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)