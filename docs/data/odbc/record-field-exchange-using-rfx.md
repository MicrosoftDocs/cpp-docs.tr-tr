---
title: 'Kayıt Alanı Değişimi: RFX Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: dc0cdcee758f4842b0738068a8a11c4e2e404155
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367140"
---
# <a name="record-field-exchange-using-rfx"></a>Kayıt Alanı Değişimi: RFX Kullanma

Bu konu, çerçevenin ne yaptığıyla ilgili olarak RFX'i kullanmak için ne yaptığınızı açıklar.

> [!NOTE]
> Bu konu, toplu satır alma nın uygulanmadığı [CRecordset'ten](../../mfc/reference/crecordset-class.md) türetilen sınıflar için geçerlidir. Toplu satır alma kullanıyorsanız, toplu kayıt alanı değişimi (Toplu RFX) uygulanır. Toplu RFX RFX benzer. Farklılıkları anlamak için bkz: [Recordset: Kayıtları Toplu Olarak Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Aşağıdaki konular ilgili bilgileri içerir:

- [Kayıt Alanı Değişimi: Sihirbaz Kodu ile çalışmak](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) RFX'in ana bileşenlerini tanıtır ve MFC Uygulama Sihirbazı ve Add **Class'ın** [(MFC ODBC Tüketicisi Ekleme'de](../../mfc/reference/adding-an-mfc-odbc-consumer.md)açıklandığı gibi) Yazdığı kodu rfx'i desteklemek için ve sihirbaz kodunu nasıl değiştirmek isteyebileceğini açıklar.

- [Kayıt Alanı Değişimi: RFX Fonksiyonlarını kullanmak,](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) geçersiz kılmanızdaki `DoFieldExchange` RFX işlevlerine yapılan çağrıları yazmayı açıklar.

Aşağıdaki tablo, çerçevenin sizin için yaptıklarıyla ilgili rolünüzü gösterir.

### <a name="using-rfx-you-and-the-framework"></a>RFX kullanma: Siz ve Çerçeve

|Bunun için,|Çerçeve|
|---------|-------------------|
|Kayıt kümesi sınıflarınızı bir sihirbazla bildirin. Alan veri üyelerinin adlarını ve veri türlerini belirtin.|Sihirbaz bir `CRecordset` sınıf türetir ve her alan veri üyesi için bir RFX işlev çağrısı da dahil olmak üzere sizin için bir [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) geçersiz kılma yazar.|
|(İsteğe bağlı) Gerekli parametre veri üyelerini sınıfa el ile ekleyin. Her parametre veri üyesi `DoFieldExchange` için el ile bir RFX fonksiyon çağrısı ekleyin, [CFieldExchange bir çağrı ekleyin::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) parametrelergrubu için, ve [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)parametrelerin toplam sayısını belirtin. Bkz. [Kayıt Kümesi: Bir Kayıt Kümesini Parametreleme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).||
|(İsteğe bağlı) Alan veri üyelerine ek sütunları el ile bağla. El ile artış [m_nFields.](../../mfc/reference/crecordset-class.md#m_nfields) Bkz. [Kayıt Kümesi: Dinamik Olarak Bağlanan Veri Sütunları (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||
|Kayıt kümesi sınıfınızdan bir nesne oluştur. Nesneyi kullanmadan önce, varsa parametre veri üyelerinin değerlerini ayarlayın.|Verimlilik için, çerçeve ODBC kullanarak parametreleri önceden bindirer. Parametre değerlerini geçtiğiniz zaman, çerçeve bunları veri kaynağına geçirir. Sıralama ve/veya filtre dizeleri değişmediği sürece, yalnızca parametre değerleri yeniden sorgular için gönderilir.|
|CRecordset kullanarak bir kayıt kümesi [nesnesi açın::Aç.](../../mfc/reference/crecordset-class.md#open)|Kayıt kümesinin sorgusunu yürütür, sütunları kayıt kümesinin alan veri `DoFieldExchange` üyelerine bağlar ve ilk seçilen kayıt ile kayıt kümesinin alan veri üyeleri arasında veri alışverişi için çağrılar.|
|[CRecordset::Move](../../mfc/reference/crecordset-class.md#move) veya bir menü veya araç çubuğu komutunu kullanarak kayıt setinde ilerleyin.|Yeni `DoFieldExchange` geçerli kayıttan alan veri üyelerine veri aktarımı için çağrılar.|
|Kayıtları ekleyin, güncelleyin ve silin.|Veri `DoFieldExchange` kaynağına veri aktarmak için çağrılar.|

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Kayıt Alanı Değişimi: RFX'in Çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Kayıt Kümesi: SUM'ları ve Diğer Toplama Sonuçlarını Alma (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CfieldExchange Sınıfı](../../mfc/reference/cfieldexchange-class.md)<br/>
[Makrolar, Genel Fonksiyonlar ve Genel Değişkenler](../../mfc/reference/mfc-macros-and-globals.md)
