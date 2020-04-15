---
title: Kayıt Kaydırma (MFC Veri Erişimi) için Komut İşleyicileri
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
ms.openlocfilehash: 14ef845c3029f1d9a30d257f91c1b33017b6ec8b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81336937"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>Kayıt Kaydırma (MFC Veri Erişimi) için Komut İşleyicileri

[CRecordView](../mfc/reference/crecordview-class.md) sınıfı aşağıdaki standart komutlar için varsayılan komut işleme sağlar:

- ID_RECORD_MOVE_FIRST

- ID_RECORD_MOVE_LAST

- ID_RECORD_MOVE_NEXT

- ID_RECORD_MOVE_PREV

`OnMove` Üye işlev, kayıttan kayda taşınan dört komut için de varsayılan komut işleme sağlar. Bu komutlar verildiğinde, RFX (veya DFX) yeni kaydı kayıt kümesinin alanlarına yükler ve DDX değerleri kayıt formunun denetimlerine taşır. RFX hakkında daha fazla bilgi için [Kayıt Alanı Değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md)'ye bakın.

> [!NOTE]
> Bu standart komut titrelerini, standart kayıt gezinti komutlarıyla ilişkili kullanıcı arabirimi nesneleri için kullandığınızdan emin olun.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Görünümünde Gezinmeyi Destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)
