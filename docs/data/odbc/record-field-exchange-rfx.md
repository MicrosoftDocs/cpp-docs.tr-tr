---
title: Kayıt Alanı Değişimi (RFX)
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC) [C++]
- data [MFC], moving between sources and recordsets
- database classes [C++], RFX
- data [MFC]
- ODBC [C++], RFX
ms.assetid: f5ddfbf0-2901-48d7-9848-4fb84de3c7ee
ms.openlocfilehash: 6f965b90e1e0bbcfd3ad04bb5b40644d61050b2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367157"
---
# <a name="record-field-exchange-rfx"></a>Kayıt Alanı Değişimi (RFX)

MFC ODBC veritabanı sınıfları, veri kaynağı ve [kayıt kümesi nesnesi](../../data/odbc/recordset-odbc.md) arasında taşınan verileri otomatikleştirin. [CRecordset'ten](../../mfc/reference/crecordset-class.md) bir sınıf türettiğinizde ve toplu satır alma kullanmadığınızda, veriler kayıt alanı değişimi (RFX) mekanizması tarafından aktarılır.

> [!NOTE]
> Türemiş `CRecordset` bir sınıfta toplu satır alma uyguladıysanız, çerçeve veri aktarmak için toplu kayıt alanı değişimi (Toplu RFX) mekanizmasını kullanır. Daha fazla bilgi için [bkz: Kayıt Kümesi: Toplu Olarak Kayıt Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

RFX, iletişim veri alışverişine (DDX) benzer. Bir veri kaynağı ile bir kayıt kümesinin alan veri üyeleri arasında veri taşıma, kayıt setinin [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) işlevine birden çok çağrı ve çerçeve ile [ODBC](../../data/odbc/odbc-basics.md)arasında önemli bir etkileşim gerektirir. RFX mekanizması tür güvenlidir ve o döb gibi işlevleri `::SQLBindCol`çağırma işini kurtarır. DDX hakkında daha fazla bilgi için [İletişim Veri Alışverişi ve Doğrulama'ya](../../mfc/dialog-data-exchange-and-validation.md)bakın.

RFX çoğunlukla sizin için şeffaftır. Kayıt kümesi sınıflarınızı MFC Uygulama Sihirbazı veya **Add Class** ile bildirirseniz [(MFC ODBC Tüketici eklemede](../../mfc/reference/adding-an-mfc-odbc-consumer.md)açıklandığı gibi), RFX bunları otomatik olarak yerleşik hale getirmektedir. Kayıt kümesi sınıfınız çerçeve tarafından `CRecordset` sağlanan taban sınıftan türetilmelidir. MFC Uygulama Sihirbazı, bir başlangıç kayıt kümesi sınıfı oluşturmanıza olanak tanır. **Sınıf Ekle,** ihtiyacınız olan diğer kayıt kümesi sınıflarını eklemenize olanak tanır. Daha fazla bilgi ve örnekler için [bkz.](../../mfc/reference/adding-an-mfc-odbc-consumer.md)

İstediğinize göre, üç durumda küçük miktarda RFX kodu el ile eklemeniz gerekir:

- Parametreli sorguları kullanın. Daha fazla bilgi için [bkz: Kayıt Kümesini Parametreleme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

- Birleştirmeler gerçekleştirin (iki veya daha fazla tablodaki sütunlar için bir kayıt kümesi ni kullanarak). Daha fazla bilgi için [bkz: Recordset: Performing a Join (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).

- Veri sütunlarını dinamik olarak bağla. Bu parametrelendirme daha az yaygındır. Daha fazla bilgi için [Bkz. Kayıt Kümesi: Dinamik Bağlama Veri Sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

RFX hakkında daha gelişmiş bir anlayışa ihtiyacınız varsa, [Bkz. Kayıt Alanı Değişimi: RFX Nasıl Çalışır.](../../data/odbc/record-field-exchange-how-rfx-works.md)

Aşağıdaki konular kayıt kümesi nesnelerini kullanmanın ayrıntılarını açıklar:

- [Kayıt Alanı Değişimi: RFX Kullanma](../../data/odbc/record-field-exchange-using-rfx.md)

- [Kayıt Alanı Değişimi: RFX İşlevlerini Kullanma](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)

- [Kayıt Alanı Değişimi: RFX'in Çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[MFC ODBC Tüketimi](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Veritabanı Desteği, MFC Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
