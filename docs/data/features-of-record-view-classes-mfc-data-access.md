---
title: Kayıt özelliklerini görüntülemek sınıfları (MFC veri erişimi) | Microsoft Docs
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
ms.openlocfilehash: 9b6717c0ef1167e01df2f5e8de14408b23a9dbb1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>Kayıt görünümü sınıfları (MFC veri erişimi) özellikleri
Form tabanlı veri erişimi programlama sınıfı ile yapabileceğiniz [Cformview'yu](../mfc/reference/cformview-class.md), ancak [CRecordView](../mfc/reference/crecordview-class.md) genellikle türetmek bir daha iyi bir sınıftır. Ek olarak kendi `CFormView` özellikleri `CRecordView`:  
  
-   Form denetimleri ile ilişkili kayıt kümesi nesnesi arasındaki iletişim kutusu veri değişimi (DDX) sağlar.  
  
-   İlişkili kayıt kümesi nesnesindeki kayıtlar gezinme için taşıma ilk, sonrakine Taşı, öncekine taşı ve taşıma son komutları işler.  
  
-   Kullanıcı başka bir kayda geçtiğinde geçerli kayda değişiklikleri güncelleştirir.  
  
 Gezinme hakkında daha fazla bilgi için bkz: [kayıt görünümleri: kayıt görünümü gezintiyi destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)   
 [ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)