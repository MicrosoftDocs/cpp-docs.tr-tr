---
title: Kaydın özelliklerini görüntüleme sınıfları (MFC veri erişimi) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b1c99b8b271b4948584d9bdb25c74518fe835573
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46093226"
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