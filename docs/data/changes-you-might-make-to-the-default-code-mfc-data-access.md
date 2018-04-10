---
title: Varsayılan kodda (MFC veri erişimi) yaptığınız değişiklikler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 197277a68131c9d63e3eab2f1404cf97169be1f3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>(MFC veri erişimi) varsayılan kodda yapabileceğiniz değişiklikler
[MFC Uygulama Sihirbazı'nı](../mfc/reference/database-support-mfc-application-wizard.md) tüm kayıtları tek bir tabloda seçen sizin için bir kayıt kümesi sınıfı yazar. Genellikle, bir veya daha aşağıdaki yollardan biriyle bu davranışı değiştirmek isteyeceksiniz:  
  
-   Bir filtre ya da kayıt için bir sıralama düzeni ayarlayın. Bunu yapmak `OnInitialUpdate` kayıt kümesi nesnesi önce oluşturulduktan sonra **açık** üye işlevi çağrılır. Daha fazla bilgi için bkz: [kayıt kümesi: kayıtları filtreleme (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) ve [kayıt kümesi: Kayıtları sıralama (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).  
  
-   Kayıt kümesini parametreleştirme. Gerçek çalışma zamanı parametre değeri sonra Filtresi belirtin. Daha fazla bilgi için bkz: [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
-   Özelleştirilmiş bir SQL dizesi geçirmek [açık](../mfc/reference/crecordset-class.md#open) üye işlevi. Bu teknik ile gerçekleştirebileceğiniz bir tartışma için bkz: [SQL: özelleştirme Kümenizin SQL deyimini (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt görünümünü kullanma](../data/using-a-record-view-mfc-data-access.md)