---
description: 'Daha fazla bilgi edinin: kayıt alanı değişimi: RFX kullanma'
title: 'Kayıt Alanı Değişimi: RFX Kullanma'
ms.date: 11/04/2016
helpviewer_keywords:
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
ms.openlocfilehash: 9ded7bc2a10bc37f7f1f835f8706d385b543af9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298805"
---
# <a name="record-field-exchange-using-rfx"></a>Kayıt Alanı Değişimi: RFX Kullanma

Bu konu başlığı altında, Framework 'ün yaptığı işe göre RFX 'i kullanma işlemleri açıklanmaktadır.

> [!NOTE]
> Bu konu, toplu satır yakalamanın uygulanmadığı [CRecordset](../../mfc/reference/crecordset-class.md) ' ten türetilmiş sınıflar için geçerlidir. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (toplu RFX) uygulanır. Toplu RFX, RFX 'e benzerdir. Farkları anlamak için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Aşağıdaki konular ilgili bilgileri içerir:

- [Kayıt alanı değişimi: sihirbaz kodu Ile çalışma](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) , RFX 'in ana bileşenlerini tanıtır ve MFC Uygulama Sihirbazı 'NıN ( [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)bölümünde AÇıKLANDıĞı gibi), RFX 'i desteklemek için **yazma ve sihirbaz** kodunu nasıl değiştirmek isteyebileceğiniz ile ilgili kodu açıklar.

- [Kayıt alanı değişimi: RFX Işlevlerinin kullanılması,](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) geçersiz KıLMANıZDA RFX işlevlerine çağrı yazmayı açıklar `DoFieldExchange` .

Aşağıdaki tabloda, Framework 'ün sizin için yaptığı işe göre rolü gösterilmektedir.

### <a name="using-rfx-you-and-the-framework"></a>RFX kullanma: siz ve Framework

|Siz|Framework|
|---------|-------------------|
|Kayıt kümesi sınıflarınızı sihirbazla bildirin. Alan veri üyelerinin adlarını ve veri türlerini belirtin.|Sihirbaz bir sınıf türetiliyor `CRecordset` ve sizin için her alan veri üyesine YÖNELIK RFX işlev çağrısı dahil olmak üzere bir [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) geçersiz kılma yazar.|
|Seçim Gerekli parametre veri üyelerini sınıfa el ile ekleyin. Her bir parametre veri üyesine yönelik bir RFX işlevi çağrısını el ile ekleyin `DoFieldExchange` , parametre grubu Için [CFieldExchange:: SETbir](../../mfc/reference/cfieldexchange-class.md#setfieldtype) çağrısı ekleyin ve [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)toplam parametre sayısını belirtin. Bkz. [kayıt kümesi: bir kayıt kümesini parametrize (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).||
|Seçim Alan veri üyelerine el ile ek sütunları bağlayın. [M_nFields](../../mfc/reference/crecordset-class.md#m_nfields)el ile artırın. Bkz. [kayıt kümesi: dinamik olarak veri sütunlarını bağlama (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).||
|Kayıt kümesi sınıfınızın bir nesnesini oluşturun. Nesnesini kullanmadan önce, varsa parametre veri üyelerinin değerlerini ayarlayın.|Verimlilik açısından, çerçeve ODBC kullanarak parametreleri önceden bağlar. Parametre değerlerini geçirdiğinizde, Framework bunları veri kaynağına geçirir. Sıralama ve/veya filtre dizeleri değişmediği takdirde, yalnızca parametre değerleri sorgular için gönderilir.|
|[CRecordset:: Open](../../mfc/reference/crecordset-class.md#open)kullanarak bir kayıt kümesi nesnesi açın.|Kayıt kümesinin sorgusunu yürütür, sütunları kayıt kümesinin alan veri üyelerine bağlar ve `DoFieldExchange` ilk seçilen kayıt ve kayıt kümesinin alan veri üyeleri arasında Exchange verilerine çağrı yapar.|
|Kayıt kümesinde [CRecordset:: Move](../../mfc/reference/crecordset-class.md#move) veya bir menü ya da araç çubuğu komutu kullanarak kaydırma yapın.|`DoFieldExchange`Yeni geçerli kayıttaki alan veri üyelerine veri aktarmaya yönelik çağrılar.|
|Kayıt ekleyin, güncelleştirin ve silin.|Veri `DoFieldExchange` kaynağına veri aktarmak için çağrılar.|

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)<br/>
[Kayıt alanı değişimi: RFX 'in çalışması](../../data/odbc/record-field-exchange-how-rfx-works.md)<br/>
[Kayıt kümesi: toplamları ve diğer toplama sonuçlarını alma (ODBC)](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)<br/>
[CFieldExchange sınıfı](../../mfc/reference/cfieldexchange-class.md)<br/>
[Makrolar, genel Işlevler ve genel değişkenler](../../mfc/reference/mfc-macros-and-globals.md)
