---
title: "Kayıt alanı değişimi (RFX) | Microsoft Docs"
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
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 50fc0aea1ef50124cd98b0d0498b767d1f00e5c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="record-field-exchange-rfx"></a>Kayıt Alanı Değişimi (RFX)
MFC ODBC veritabanı sınıfları veri kaynağı arasında veri taşımayı otomatikleştirmek ve [kayıt kümesi](../../data/odbc/recordset-odbc.md) nesnesi. Öğesinden bir sınıf türetin zaman [CRecordset](../../mfc/reference/crecordset-class.md) ve toplu satır getirme kullanmayın, kayıt alanı değişimi (RFX) mekanizması tarafından aktarılan veriler.  
  
> [!NOTE]
>  Toplu satır türetilmiş bir getirme uyguladıysanız `CRecordset` sınıfı, framework toplu kayıt alanı değişimi (Toplu RFX) mekanizması veri aktarımı için kullanır. Daha fazla bilgi için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 RFX iletişim kutusu veri değişimi (DDX) benzer. Bir veri kaynağı ile kayıt alan veri üyeleri arasında veri taşıma gerektirir kayıt kümesinin için birden fazla çağrı [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) framework arasındaki işlevi ve önemli etkileşim ve [ODBC](../../data/odbc/odbc-basics.md). RFX mekanizması tür kullanımı uyumlu olduğundan ve ODBC işlevleri gibi çağırma işlemlerini kaydeder **:: SQLBindCol**. DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
 RFX çoğunlukla için saydamdır. MFC Uygulama Sihirbazı'nı kullanarak, kayıt kümesi sınıfları bildirme varsa veya **sınıfı Ekle** (açıklandığı gibi [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)), RFX oluşturulan içine otomatik olarak. Kayıt kümesi sınıfınız temel sınıfından türetilmiş olmalıdır `CRecordset` framework tarafından sağlanan. MFC Uygulama Sihirbazı, ilk kayıt kümesi sınıfı oluşturmanızı sağlar. **Sınıf ekleme** ihtiyaç duyarsanız diğer kayıt kümesi sınıfları eklemenize olanak sağlar. Daha fazla bilgi ve örnekler için bkz: [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Aşağıdakileri yapmak istediğinizde üç durumda RFX kodu az miktarda el ile eklemeniz gerekir:  
  
-   Parametreli sorgular kullanın. Daha fazla bilgi için bkz: [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
-   (İki veya daha fazla tablodan sütun için bir kayıt kümesini kullanma) birleştirmeler gerçekleştirme. Daha fazla bilgi için bkz: [kayıt kümesi: bir birleştirme (ODBC) gerçekleştirme](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
-   Veri sütunlarını dinamik olarak bağlayın. Bu parametrelemeyi daha az yaygın bir durumdur. Daha fazla bilgi için bkz: [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 RFX daha gelişmiş bir anlayış gerekirse bkz [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
 Aşağıdaki konularda, kayıt kümesi nesnelerini kullanarak ayrıntılarını açıklanır:  
  
-   [Kayıt Alanı Değişimi: RFX Kullanma](../../data/odbc/record-field-exchange-using-rfx.md)  
  
-   [Kayıt Alanı Değişimi: RFX İşlevlerini Kullanma](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)  
  
-   [Kayıt Alanı Değişimi: RFX'in Çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Açık veritabanı bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)   
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [MFC ODBC tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Veritabanı desteği, MFC Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md)   
 [CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)