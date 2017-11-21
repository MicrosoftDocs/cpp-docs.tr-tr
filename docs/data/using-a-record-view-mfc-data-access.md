---
title: "Kayıt görünümü (MFC veri erişimi) kullanarak | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4d37f40169330fe878eee326628bd26bef9ca8d8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-a-record-view--mfc-data-access"></a>Kayıt görünümü (MFC veri erişimi) kullanma
Bu konu, sihirbaz sizin için yazar kayıt görünümleri için varsayılan kod yaygın olarak nasıl özelleştirebileceğinizi açıklar. Kayıt seçimi kısıtlamak istediğiniz genellikle, bir [filtre](../data/odbc/recordset-filtering-records-odbc.md) veya [parametreleri](../data/odbc/recordset-parameterizing-a-recordset-odbc.md), belki de [sıralama](../data/odbc/recordset-sorting-records-odbc.md) kayıtları SQL deyimini özelleştirme.  
  
 Kullanarak `CRecordView` çok aynı kullanarak [Cformview'yu](../mfc/reference/cformview-class.md). Temel görüntülemek ve belki de tek bir kayıt kümesinin kayıtlarını güncelleştirmek için kayıt görünümü kullanmak için bir yaklaşımdır. Bunun ötesinde, diğer kayıt kümeleri de anlatıldığı gibi kullanmak isteyebilirsiniz [kayıt görünümleri: ikinci kayıt kümesinden liste kutusunu doldurma](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)   
 [ODBC sürücü listesi](../data/odbc/odbc-driver-list.md)