---
title: Kayıt (MFC veri erişimi) kaydırma için komut işleyicileri
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
ms.openlocfilehash: 66944221910dbd23d78a78fc951030efbee86bd0
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038527"
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

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Görünümünde Gezintiyi Destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)