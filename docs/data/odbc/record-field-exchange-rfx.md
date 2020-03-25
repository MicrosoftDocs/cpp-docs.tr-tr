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
ms.openlocfilehash: e1ba9f29ebf2cb3b1f94620e815882c850bbc7cc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213063"
---
# <a name="record-field-exchange-rfx"></a>Kayıt Alanı Değişimi (RFX)

MFC ODBC veritabanı sınıfları veri kaynağı ve bir [kayıt kümesi](../../data/odbc/recordset-odbc.md) nesnesi arasında veri taşımayı otomatik hale getirir. [CRecordset](../../mfc/reference/crecordset-class.md) 'den bir sınıf türetirsiniz ve toplu satır getirmeyi kullanmazsanız, veriler kayıt alanı DEĞIŞIMI (RFX) mekanizması tarafından aktarılır.

> [!NOTE]
>  Türetilmiş bir `CRecordset` sınıfında toplu satır getirme uyguladıysanız, çerçeve verileri aktarmak için toplu kayıt alanı değişimi (toplu RFX) mekanizmasını kullanır. Daha fazla bilgi için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

RFX, iletişim kutusu veri değişimi (DDX) ile benzerdir. Veri kaynağı ve bir kayıt kümesinin alan veri üyeleri arasında veri taşımak, kayıt kümesinin [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) işlevine birden çok çağrı ve çerçeve ve [ODBC](../../data/odbc/odbc-basics.md)arasında önemli bir etkileşim gerektirir. RFX mekanizması tür açısından güvenlidir ve `::SQLBindCol`gibi ODBC işlevlerini çağırma işini kaydeder. DDX hakkında daha fazla bilgi için bkz. [Iletişim kutusu veri değişimi ve doğrulaması](../../mfc/dialog-data-exchange-and-validation.md).

RFX çoğunlukla sizin için saydamdır. MFC Uygulama Sihirbazı veya **Sınıf Ekle** ( [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)bölümünde açıklandığı gibi) kayıt kümesi sınıflarınızı bildirirseniz, RFX otomatik olarak bunlara yerleşiktir. Kayıt kümesi sınıfınızın, Framework tarafından sağlanan `CRecordset` taban sınıftan türetilmiş olması gerekir. MFC Uygulama Sihirbazı, ilk kayıt kümesi sınıfı oluşturmanızı sağlar. **Sınıf Ekle** , sizin için gerekli olan diğer kayıt kümesi sınıflarını eklemenize olanak sağlar. Daha fazla bilgi ve örnek için bkz. [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md).

Şunları yapmak istediğinizde, üç durumda, az miktarda RFX kodu eklemeniz gerekir:

- Parametreli sorgular kullanın. Daha fazla bilgi için bkz. [kayıt kümesi: bir kayıt kümesini parametrize (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

- Birleşimler gerçekleştirin (iki veya daha fazla tablodan sütunlar için bir kayıt kümesi kullanarak). Daha fazla bilgi için bkz. [kayıt kümesi: JOIN gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md).

- Veri sütunlarını dinamik olarak bağlayın. Bu, Parametreleştirme özelliğinden daha az yaygındır. Daha fazla bilgi için bkz. [kayıt kümesi: dinamik olarak veri sütunlarını bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

RFX 'in daha gelişmiş bir şekilde anlaşılmasına ihtiyacınız varsa [kayıt alanı değişimi: RFX 'In nasıl çalıştığını](../../data/odbc/record-field-exchange-how-rfx-works.md)görün.

Aşağıdaki konularda, kayıt kümesi nesnelerinin kullanımıyla ilgili ayrıntılar açıklanmaktadır:

- [Kayıt Alanı Değişimi: RFX Kullanma](../../data/odbc/record-field-exchange-using-rfx.md)

- [Kayıt Alanı Değişimi: RFX İşlevlerini Kullanma](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)

- [Kayıt Alanı Değişimi: RFX'in Çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md)

## <a name="see-also"></a>Ayrıca bkz.

[Açık Veritabanı Bağlantısı (ODBC)](../../data/odbc/open-database-connectivity-odbc.md)<br/>
[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[MFC ODBC tüketme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)<br/>
[Veritabanı Desteği, MFC Uygulama Sihirbazı](../../mfc/reference/database-support-mfc-application-wizard.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
