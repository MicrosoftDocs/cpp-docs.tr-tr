---
title: "Kayıt Alanı Değişimi: RFX kullanma | Microsoft Docs"
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
- RFX (ODBC), implementing
ms.assetid: ada8f043-37e6-4d41-9db3-92c997a61957
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 28f1cd743a7ede904c99590e56f08b7020f77d82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="record-field-exchange-using-rfx"></a>Kayıt Alanı Değişimi: RFX Kullanma
Bu konu RFX framework yaptığı ile ilgili olarak kullanmak için bunu açıklar.  
  
> [!NOTE]
>  Bu konu, türetilen sınıflar için geçerlidir [CRecordset](../../mfc/reference/crecordset-class.md) toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (Toplu RFX) uygulanır. Toplu RFX RFX için benzer. Farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Aşağıdaki konular, ilgili bilgiler içerir:  
  
-   [Kayıt Alanı Değişimi: sihirbaz kodu ile çalışma](../../data/odbc/record-field-exchange-working-with-the-wizard-code.md) RFX'in ana bileşenlerini tanıtır ve kod açıklar, MFC Uygulama Sihirbazı'nı ve **sınıfı Ekle** (açıklandığı gibi [MFC ODBC Tüketicisi Ekleme ](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) RFX ve nasıl sihirbaz kodu değiştirmek isteyebilirsiniz desteklemek yazma.  
  
-   [Kayıt Alanı Değişimi: RFX işlevlerini kullanma](../../data/odbc/record-field-exchange-using-the-rfx-functions.md) çağrı RFX işlevlerini yazmayı açıklar, `DoFieldExchange` geçersiz kılar.  
  
 Aşağıdaki tabloda rolünüze framework sizin için ne yaptığını göre gösterir.  
  
### <a name="using-rfx-you-and-the-framework"></a>RFX kullanma: Siz ve Framework  
  
|Bunun için,|Çerçeve|  
|---------|-------------------|  

| Kayıt kümesi sınıflarınızı sihirbaz bildirin. Alan veri üyeleri adları ve veri türlerini belirtin. | Sihirbaz türetilen bir `CRecordset` sınıfı ve yazma işlemleri bir [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) sizin için geçersiz kılma, bir RFX dahil olmak üzere işlev çağrısı için her alan veri üyesi. |  
| (İsteğe bağlı) El ile tüm gerekli parametre veri üyeleri sınıfına ekleyin. El ile bir RFX işlev çağrısı ekleme `DoFieldExchange` her parametre veri üyesi için bir çağrı ekleyin [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) parametreleri, Grup ve parametrelerinde toplam sayısını belirtin [m_nParams ](../../mfc/reference/crecordset-class.md#m_nparams). Bkz: [kayıt kümesi: kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md). ||  
| (İsteğe bağlı) El ile alan veri üyeleri için ek sütunlar bağlayın. El ile Artır [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields). Bkz: [kayıt kümesi: veri sütunlarını (ODBC) dinamik olarak bağlama](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md). ||  

| Kayıt kümesi sınıfın bir nesnesi oluşturun. Nesne kullanmadan önce kendi parametre veri üyeleri varsa ayarlayın. | Verimlilik için framework parametreleri ODBC kullanarak Önden bağlar. Parametre değerlerini geçirdiğinizde, framework bunları veri kaynağına geçirir. Sıralama ve filtreleme dizeleri değiştirmediğiniz sürece yalnızca parametre değerlerini sorgular için gönderilir. |  
| Kayıt kümesi nesnesi kullanarak açmak [CRecordset::Open](../../mfc/reference/crecordset-class.md#open). | Kayıt kümesinin sorgusunu çalıştırır, sütunları alan veri üyeleri kayıt kümesi ve çağrıları için bağlar `DoFieldExchange` ilk seçili kayıt kümesinin alan veri üyeleri arasında veri değişimi için. |  
| Kayıt kümesi kullanarak kaydırma [CRecordset::Move](../../mfc/reference/crecordset-class.md#move) veya menü veya araç komutu. | Çağrıları `DoFieldExchange` yeni geçerli kayıttaki alan veri üyeleri için veri aktarmasına. |  
| Ekleme, güncelleştirme ve kayıt silme. | Çağrıları `DoFieldExchange` veri kaynağına veri aktarmasına. |  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)   
 [Kayıt Alanı Değişimi: RFX nasıl çalışır?](../../data/odbc/record-field-exchange-how-rfx-works.md)   
 [Kayıt kümesi: SUM'ları ve diğer toplama sonuçlarını (ODBC) alma](../../data/odbc/recordset-obtaining-sums-and-other-aggregate-results-odbc.md)   
 [CRecordset sınıfı](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange sınıfı](../../mfc/reference/cfieldexchange-class.md)   
 [Makrolar, genel işlevler ve genel değişkenler](../../mfc/reference/mfc-macros-and-globals.md)

