---
title: "Varsayılan kodda (MFC veri erişimi) yaptığınız değişiklikler | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: record views [C++], customizing default code
ms.assetid: 9992ed37-a6bf-45a5-a572-5c14e42b6628
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a18b4bb1e544f2cc3d033d58a1c6c1a26eec98dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="changes-you-might-make-to-the-default-code--mfc-data-access"></a>(MFC veri erişimi) varsayılan kodda yapabileceğiniz değişiklikler
[MFC Uygulama Sihirbazı'nı](../mfc/reference/database-support-mfc-application-wizard.md) tüm kayıtları tek bir tabloda seçen sizin için bir kayıt kümesi sınıfı yazar. Genellikle, bir veya daha aşağıdaki yollardan biriyle bu davranışı değiştirmek isteyeceksiniz:  
  
-   Bir filtre ya da kayıt için bir sıralama düzeni ayarlayın. Bunu yapmak `OnInitialUpdate` kayıt kümesi nesnesi önce oluşturulduktan sonra **açık** üye işlevi çağrılır. Daha fazla bilgi için bkz: [kayıt kümesi: kayıtları filtreleme (ODBC)](../data/odbc/recordset-filtering-records-odbc.md) ve [kayıt kümesi: Kayıtları sıralama (ODBC)](../data/odbc/recordset-sorting-records-odbc.md).  
  
-   Kayıt kümesini parametreleştirme. Gerçek çalışma zamanı parametre değeri sonra Filtresi belirtin. Daha fazla bilgi için bkz: [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../data/odbc/recordset-parameterizing-a-recordset-odbc.md)  
  
-   Özelleştirilmiş bir SQL dizesi geçirmek [açık](../mfc/reference/crecordset-class.md#open) üye işlevi. Bu teknik ile gerçekleştirebileceğiniz bir tartışma için bkz: [SQL: özelleştirme Kümenizin SQL deyimini (ODBC)](../data/odbc/sql-customizing-your-recordsets-sql-statement-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt görünümünü kullanma](../data/using-a-record-view-mfc-data-access.md)