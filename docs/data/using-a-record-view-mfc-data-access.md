---
title: Kayıt görünümü (MFC veri erişimi) kullanarak | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- record views, customizing default code
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 23dd3335f6c77a3efec26f13e78824806f05821a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33104649"
---
# <a name="using-a-record-view--mfc-data-access"></a>Kayıt görünümü (MFC veri erişimi) kullanma
Bu konu, sihirbaz sizin için yazar kayıt görünümleri için varsayılan kod yaygın olarak nasıl özelleştirebileceğinizi açıklar. Kayıt seçimi kısıtlamak istediğiniz genellikle, bir [filtre](../data/odbc/recordset-filtering-records-odbc.md) veya [parametreleri](../data/odbc/recordset-parameterizing-a-recordset-odbc.md), belki de [sıralama](../data/odbc/recordset-sorting-records-odbc.md) kayıtları SQL deyimini özelleştirme.  
  
 Kullanarak `CRecordView` çok aynı kullanarak [Cformview'yu](../mfc/reference/cformview-class.md). Temel görüntülemek ve belki de tek bir kayıt kümesinin kayıtlarını güncelleştirmek için kayıt görünümü kullanmak için bir yaklaşımdır. Bunun ötesinde, diğer kayıt kümeleri de anlatıldığı gibi kullanmak isteyebilirsiniz [kayıt görünümleri: ikinci kayıt kümesinden liste kutusunu doldurma](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)   
 [ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)