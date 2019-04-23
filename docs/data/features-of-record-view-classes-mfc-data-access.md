---
title: Kayıt görünümü sınıfları (MFC veri erişimi) özellikleri
ms.date: 11/04/2016
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
ms.openlocfilehash: 5f8de956065571109c988bd2940d21822bba7cfd
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59029881"
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>Kayıt görünümü sınıfları (MFC veri erişimi) özellikleri

Form tabanlı veri erişim programlama sınıfı ile yapabileceğiniz [Cformview'yu](../mfc/reference/cformview-class.md), ancak [CRecordView](../mfc/reference/crecordview-class.md) genellikle türetilmesi için bir daha iyi bir sınıftır. Ek olarak kendi `CFormView` özellikleri `CRecordView`:

- Formu denetimleri ile ilişkili kayıt kümesi nesnesi arasındaki iletişim kutusu veri değişimi (DDX) sağlar.

- İlişkili kayıt kümesi nesnesi kayıtları arasında gezinmek için Taşı, ileri taşıma, öncekine taşı ve sona Taşı komutları işler.

- Güncelleştirmeleri, kullanıcının başka bir kayıda taşır, geçerli kayıtta değiştirir.

Gezintisi hakkında daha fazla bilgi için bkz. [kayıt görünümleri: Kayıt görünümünde gezintiyi destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)<br/>
[ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)