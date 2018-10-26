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
ms.openlocfilehash: 6733603ff95d4bf12b9eec142fff12b5ca0458a9
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50057770"
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