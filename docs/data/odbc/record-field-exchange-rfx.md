---
title: Kayıt alanı değişimi (RFX) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 03b827b9f6ec1b1a378b1ffd04aa2c1e1c6aa111
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087766"
---
# <a name="record-field-exchange-rfx"></a>Kayıt Alanı Değişimi (RFX)

MFC ODBC veritabanı sınıfları veri kaynağındaki veri taşımayı otomatikleştirin ve [kayıt](../../data/odbc/recordset-odbc.md) nesne. Türetilen bir sınıftan zaman [CRecordset](../../mfc/reference/crecordset-class.md) ve toplu satır getirme kullanmayın, verileri kayıt alanı değişimi (RFX) mekanizması tarafından aktarılır.  
  
> [!NOTE]
>  Bir türetilmiş toplu satır getirme uyguladıysanız `CRecordset` sınıfı framework toplu kayıt alanı değişimi (Bulk RFX) mekanizması veri aktarımı için kullanır. Daha fazla bilgi için [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
RFX iletişim kutusu veri değişimi (DDX) için benzer. Bir veri kaynağını ve bir kayıt kümesi alan veri üyeleri arasında veri taşıma, kayıt kümesinin birden çok çağrı gerektirir [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) framework arasındaki işlev ve önemli etkileşim ve [ODBC](../../data/odbc/odbc-basics.md). RFX mekanizması tür bakımından güvenlidir ve ODBC işlevleri gibi çağırma iş kaydeder `::SQLBindCol`. DDX hakkında daha fazla bilgi için bkz: [iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).  
  
RFX çoğunlukla için saydamdır. MFC Uygulama Sihirbazı kayıt kümesi sınıflarını bildirirseniz veya **sınıfı Ekle** (açıklandığı [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)), RFX oluşturulan bunları otomatik olarak. Kayıt kümesi sınıfı, temel sınıftan türetilmelidir `CRecordset` framework tarafından sağlanan. MFC Uygulama Sihirbazı, ilk kayıt kümesi sınıfı oluşturmanızı sağlar. **Sınıf ekleme** gerek duydukça başka kayıt kümesi sınıfları eklemenizi sağlar. Daha fazla bilgi ve örnekler için bkz. [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
Aşağıdakileri yapmak istediğinizde üç durumda RFX kod az miktarda el ile eklemeniz gerekir:  
  
- Parametreli sorgular kullanma. Daha fazla bilgi için [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
- (İki veya daha fazla tablodan sütun için bir kayıt kümesini kullanma) birleştirmeler gerçekleştirme. Daha fazla bilgi için [kayıt kümesi: bir birleştirme (ODBC) gerçekleştirme](../../data/odbc/recordset-performing-a-join-odbc.md).  
  
- Veri sütunlarını dinamik olarak bağlayın. Bu Parametreleştirme daha az yaygındır. Daha fazla bilgi için [kayıt kümesi: dinamik olarak bağlama veri sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
RFX daha gelişmiş bir bilgiye ihtiyacınız varsa bkz [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md).  
  
Aşağıdaki konularda, kayıt kümesi nesnelerini kullanarak ayrıntılarını açıklanır:  
  
- [Kayıt Alanı Değişimi: RFX Kullanma](../../data/odbc/record-field-exchange-using-rfx.md)  
  
- [Kayıt Alanı Değişimi: RFX İşlevlerini Kullanma](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)  
  
- [Kayıt Alanı Değişimi: RFX'in Çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[MFC ODBC tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Veritabanı Desteği, MFC Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)