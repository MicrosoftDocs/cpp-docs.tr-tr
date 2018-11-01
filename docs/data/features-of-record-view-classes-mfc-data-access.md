---
title: Kayıt görünümü sınıfları (MFC veri erişimi) özellikleri
ms.date: 11/04/2016
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
ms.openlocfilehash: 2feda8f8f446e02a5056287c656707ea038f5387
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50461158"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>Kayıt görünümü sınıfları (MFC veri erişimi) özellikleri

Form tabanlı veri erişim programlama sınıfı ile yapabileceğiniz [Cformview'yu](../mfc/reference/cformview-class.md), ancak [CRecordView](../mfc/reference/crecordview-class.md) genellikle türetilmesi için bir daha iyi bir sınıftır. Ek olarak kendi `CFormView` özellikleri `CRecordView`:

- Formu denetimleri ile ilişkili kayıt kümesi nesnesi arasındaki iletişim kutusu veri değişimi (DDX) sağlar.

- İlişkili kayıt kümesi nesnesi kayıtları arasında gezinmek için Taşı, ileri taşıma, öncekine taşı ve sona Taşı komutları işler.

- Güncelleştirmeleri, kullanıcının başka bir kayıda taşır, geçerli kayıtta değiştirir.

Gezintisi hakkında daha fazla bilgi için bkz. [kayıt görünümleri: kayıt görünümü içinde gezinme destekleyen](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)