---
title: "Kayıt özelliklerini görüntülemek sınıfları (MFC veri erişimi) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- record views, classes
- record view classes
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d1a30742a538d941220cf099c33445089c9a907c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="features-of-record-view-classes--mfc-data-access"></a>Kayıt görünümü sınıfları (MFC veri erişimi) özellikleri
Form tabanlı veri erişimi programlama sınıfı ile yapabileceğiniz [Cformview'yu](../mfc/reference/cformview-class.md), ancak [CRecordView](../mfc/reference/crecordview-class.md) genellikle türetmek bir daha iyi bir sınıftır. Ek olarak kendi `CFormView` özellikleri `CRecordView`:  
  
-   Form denetimleri ile ilişkili kayıt kümesi nesnesi arasındaki iletişim kutusu veri değişimi (DDX) sağlar.  
  
-   İlişkili kayıt kümesi nesnesindeki kayıtlar gezinme için taşıma ilk, sonrakine Taşı, öncekine taşı ve taşıma son komutları işler.  
  
-   Kullanıcı başka bir kayda geçtiğinde geçerli kayda değişiklikleri güncelleştirir.  
  
 Gezinme hakkında daha fazla bilgi için bkz: [kayıt görünümleri: kayıt görünümü gezintiyi destekleme](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)   
 [ODBC sürücü listesi](../data/odbc/odbc-driver-list.md)