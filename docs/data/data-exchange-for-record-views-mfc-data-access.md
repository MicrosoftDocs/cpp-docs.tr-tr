---
title: "Kayıt görünümleri (MFC veri erişimi) için veri değişimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), data exchange mechanism
- RFX (record field exchange), record views
- record views, data exchange
- DDX (dialog data exchange), record views
- RFX (record field exchange)
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1db5adaab66fec2b587f7a15005caa3a9374ff12
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="data-exchange-for-record-views---mfc-data-access"></a>Kayıt görünümleri (MFC veri erişimi) için veri değişimi
Kullandığınızda [sınıfı Ekle](../mfc/reference/adding-an-mfc-odbc-consumer.md) kayıt görünümünün iletişim şablon kaynağı denetimlerinde kayıt alanlarına eşlemek için her iki yönde veri değişimi framework yönetir — denetimlerine kayıt kümesi ve kayıt kümesine denetimleri. DDX mekanizmasını kullanarak kendiniz geri ve İleri veri aktarmak için kod yazmanız gerekmez anlamına gelir.  
  
 Kayıt görünümleri için DDX çalışır birlikte [RFX](../data/odbc/record-field-exchange-rfx.md) sınıfının kayıt kümeleri için `CRecordset` (ODBC).  RFX veri kaynağının geçerli kaydı ve bir kayıt kümesi nesnesi alan veri üyeleri arasında verileri taşır. DDX formundaki denetimler için alan veri üyeleri verileri taşır. Bu birleşim başlangıçta ve kullanıcı kayıttan kayda form denetimlerini doldurur. Bu da güncelleştirilmiş verileri geri kayıt kümesi ve ardından veri kaynağını taşıyabilirsiniz.  
  
 Aşağıdaki şekil kayıt görünümleri için DDX ve RFX arasındaki ilişkiyi gösterir.  
  
 ![İletişim &#45; veri değişimi ve kayıt &#45; alan exchange](../data/media/vc37xt1.gif "vc37xt1")  
İletişim kutusu veri değişimi ve kayıt alanı değişimi  
  
 DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../mfc/dialog-data-exchange-and-validation.md). RFX hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi (RFX)](../data/odbc/record-field-exchange-rfx.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt görünümleri (MFC veri erişimi)](../data/record-views-mfc-data-access.md)   
 [ODBC Sürücü Listesi](../data/odbc/odbc-driver-list.md)