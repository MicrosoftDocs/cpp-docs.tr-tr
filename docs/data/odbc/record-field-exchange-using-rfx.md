---
title: 'Kayıt Alanı Değişimi: RFX kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: 2a029f653753363e08b3c4f8b9fceab6295924af
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59034121"
---
# <a name="record-field-exchange-using-rfx"></a>Kayıt Alanı Değişimi: RFX kullanma

Bu konuda RFX framework yaptığı ilgili olarak kullanmak için neler açıklanmaktadır.

> [!NOTE]
>  Bu konu, türetilen sınıflar için geçerlidir. [CRecordset](../../mfc/reference/crecordset-class.md) toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (Bulk RFX) uygulanır. Toplu RFX RFX için benzerdir. Farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Aşağıdaki konular, ilgili bilgileri içerir:

- [Kayıt Alanı Değişimi: Sihirbaz kodu ile çalışma](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) RFX ana bileşenlerini tanıtır ve kod açıklar, MFC Uygulama Sihirbazı ve **sınıfı Ekle** (açıklandığı [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) yazma RFX ve nasıl sihirbaz kodu değiştirmek isteyebileceğiniz desteklemek için.

- [Kayıt Alanı Değişimi: RFX işlevlerini kullanma](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) çağrı RFX işlevleri yazmayı açıklar, `DoFieldExchange` geçersiz kılar.

Aşağıdaki tabloda rolünüze göre framework sizin için ne yaptığını gösterir.

### <a name="using-rfx-you-and-the-framework"></a>RFX kullanma: Siz ve Framework

|Bunun için,|Framework|
|---------|-------------------|
|Kayıt kümesi sınıflarını sihirbazla bildirin. Alan veri üyelerinin adları ve veri türlerini belirtin.|Sihirbaz türetilen bir `CRecordset` sınıfı ve yazma işlemleri bir [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) RFX dahil olmak üzere, işlev çağrısı için her alanın veri üyesi, sizin için geçersiz kılar.|
|(İsteğe bağlı) El ile tüm gerekli parametre veri üyeleri sınıfına ekleyin. El ile bir RFX işlev çağrısını ekleyin `DoFieldExchange` her parametre veri üyesi için bir çağrı ekleyin [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) parametreleri grubunun ve parametrelerinde toplam sayısını belirtin [m_nParams ](../../mfc/reference/crecordset-class.md#m_nparams). Bkz: [kayıt kümesi: (ODBC) bir kayıt kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).||
|(İsteğe bağlı) El ile ek sütunlar için alan veri üyeleri bağlayın. El ile Artır [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields). Bkz: [kayıt kümesi: (ODBC) veri sütunlarını dinamik olarak bağlama](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||
|Kayıt kümesi sınıfının bir nesnesi oluşturun. Nesne kullanmadan önce parametre değerlerini veri üyeleri, varsa ayarlayın.|Verimlilik için framework ODBC kullanarak parametreleri, Önden bağlar. Parametre değerlerini geçirmek, framework bunları veri kaynağına geçirir. Sıralama ve filtreleme dizeleri değiştirmediğiniz sürece yalnızca parametre değerlerini sorgular için gönderilir.|
|Kayıt kümesi nesnesi kullanılarak açık [CRecordset::Open](../../mfc/reference/crecordset-class.md#open).|Kümesinin sorguyu yürütür, sütunlar için kayıt kümesi ve çağrıları alan veri üyeleri bağlar `DoFieldExchange` ilk seçili kayıt kümesinin alan veri üyeleri arasında veri değişimi için.|
|Kayıt kümesi kullanarak kaydırma [CRecordset::Move](../../mfc/reference/crecordset-class.md#move) veya bir menü veya araç çubuğunu komutu.|Çağrıları `DoFieldExchange` veri alan veri üyeleri için yeni geçerli kayıttan aktarmak için.|
|Ekleme, güncelleştirme ve kayıtlarını silin.|Çağrıları `DoFieldExchange` veri kaynağına veri aktarmak için.|

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Kayıt Alanı Değişimi: RFX'in çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Kayıt kümesi: SUM'ları ve diğer toplama sonuçlarını (ODBC) alma](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange sınıfı](../../mfc/reference/cfieldexchange-class.md)<br/>
[Makrolar, Genel İşlevler ve Genel Değişkenler](../../mfc/reference/mfc-macros-and-globals.md)

