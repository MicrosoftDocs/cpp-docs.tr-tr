---
description: 'Daha fazla bilgi edinin: kayıt kaydırma için komut Işleyicileri (MFC veri erişimi)'
title: Kayıt kaydırma için komut Işleyicileri (MFC veri erişimi)
ms.date: 11/04/2016
helpviewer_keywords:
- record views [C++], scrolling
- record scrolling [C++]
- scrolling records
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
ms.openlocfilehash: 03fce51e7b045df0ae5ad1ceb0fa99eb98d0b7c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181390"
---
# <a name="command-handlers-for-record-scrolling--mfc-data-access"></a>Kayıt kaydırma için komut Işleyicileri (MFC veri erişimi)

[CRecordView](../mfc/reference/crecordview-class.md) sınıfı aşağıdaki standart komutlar için varsayılan komut işleme sağlar:

- ID_RECORD_MOVE_FIRST

- ID_RECORD_MOVE_LAST

- ID_RECORD_MOVE_NEXT

- ID_RECORD_MOVE_PREV

`OnMove`Member işlevi, kayıttan kayda geçiş yapılan dört komut için varsayılan komut işleme sağlar. Bu komutlar verildiğinde, RFX (veya DFX) kayıt kümesinin alanlarına yeni kaydı yükler ve DDX değerleri kayıt formu denetimlerine taşıır. RFX hakkında daha fazla bilgi için bkz. [kayıt alanı değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md).

> [!NOTE]
> Standart kayıt gezintisi komutlarıyla ilişkili kullanıcı arabirimi nesneleri için bu standart komut kimliklerini kullandığınızdan emin olun.

## <a name="see-also"></a>Ayrıca bkz.

[Bir kayıt görünümünde Gezintiyi Destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)
