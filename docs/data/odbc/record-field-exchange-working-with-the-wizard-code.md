---
title: 'Kayıt Alanı Değişimi: sihirbaz kodu ile çalışma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DoFieldExchange method, overriding
- Unicode, with database classes
- field data members, declaring
- RFX (ODBC), wizard code
- RFX (ODBC), implementing
- field data members
- ODBC, RFX
- m_nParams data member, initializing
- m_nFields data member
- m_nParams data member
- overriding, DoFieldExchange
- m_nFields data member, initializing
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7d4f817ebfc3e6bb72865b4fc71fd5c5ebe5f671
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092515"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>Kayıt Alanı Değişimi: Sihirbaz Kodu ile Çalışma
Bu konuda kod açıklanmaktadır, MFC Uygulama Sihirbazı'nı ve **sınıfı Ekle** (açıklandığı gibi [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) RFX ve nasıl bu kodu değiştirmek isteyebilirsiniz desteklemek yazma.  
  
> [!NOTE]
>  Bu konu, türetilen sınıflar için geçerlidir `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (Toplu RFX) uygulanır. Toplu RFX RFX için benzer. Farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 MFC Uygulama Sihirbazı'ndaki bir kayıt kümesi sınıfı oluşturduğunuzda veya **sınıfı Ekle**, sihirbaz aşağıdaki RFX ilgili öğeler için veri kaynağına göre tablo ve sütun seçimlerine Sihirbazda yaptığınız Yazar:  
  
-   Bildirimleri kayıt kümesi sınıfı kayıt kümesi alan veri üyeleri  
  
-   Geçersiz kılma `CRecordset::DoFieldExchange`  
  
-   Kayıt kümesi alan veri üyeleri kayıt kümesi sınıfı oluşturucusu başlatma  
  
##  <a name="_core_the_field_data_member_declarations"></a> Alan veri üye bildirimleri  
 Sınıfı için aşağıdakilere benzer bir .h dosyasında bir kayıt kümesi sınıf bildirimi sihirbazlar yazma `CSections`:  
  
```  
class CSections : public CRecordset  
{  
public:  
   CSections(CDatabase* pDatabase = NULL);  
   DECLARE_DYNAMIC(CSections)  
  
// Field/Param Data  
   CString   m_strCourseID;  
   CString   m_strInstructorID;  
   CString   m_strRoomNo;  
   CString   m_strSchedule;  
   CString   m_strSectionNo;  
  
// Overrides  
   // Wizard generated virtual function overrides  
   protected:  
   virtual CString GetDefaultConnect();  // Default connection string  
   virtual CString GetDefaultSQL();      // Default SQL for Recordset  
   virtual void DoFieldExchange(CFieldExchange* pFX);  // RFX support  
  
// Implementation  
#ifdef _DEBUG  
   virtual void AssertValid() const;  
   virtual void Dump(CDumpContext& dc) const;  
#endif  
  
};  
```  
  
 Parametre veri üyeleri veya kendiniz bağlamak yeni alan veri üyeleri eklerseniz, bunları sonra sihirbaz tarafından oluşturulan olanları ekleyin.  
  
 Ayrıca, sihirbaz geçersiz kılmaları bildirimi `DoFieldExchange` sınıfının üye işlevini `CRecordset`.  
  
##  <a name="_core_the_dofieldexchange_override"></a> DoFieldExchange geçersiz kılma  

 [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) RFX Kalp değil. Framework çağrıları `DoFieldExchange` dilediğiniz zaman veri kayıt kümesi veri kaynağına veya kayıt kümesi veri kaynağına geri taşımanız gerekir. `DoFieldExchange` Ayrıca hakkında bilgi edinme destekler alan veri üyeleri aracılığıyla [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty) ve [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull) üye işlevleri.  
  
 Aşağıdaki `DoFieldExchange` geçersiz kıldığından `CSections` sınıfı. Sihirbaz işlevi kayıt kümesi sınıfı için .cpp dosyasına yazar.  
  
```  
void CSections::DoFieldExchange(CFieldExchange* pFX)  
{  
   pFX->SetFieldType(CFieldExchange::outputColumn);  
   RFX_Text(pFX, "CourseID", m_strCourseID);  
   RFX_Text(pFX, "InstructorID", m_strInstructorID);  
   RFX_Text(pFX, "RoomNo", m_strRoomNo);  
   RFX_Text(pFX, "Schedule", m_strSchedule);  
   RFX_Text(pFX, "SectionNo", m_strSectionNo);  
}  
```  
  
 İşlevin aşağıdaki anahtar özelliklere dikkat edin:  
  
-   Bu bölüm işlevinin alan eşlemesi adı verilir.  
  
-   Çağrı `CFieldExchange::SetFieldType`, ile `pFX` işaretçi. Bu çağrı tüm RFX işlevi sonuna çağırdığı belirtir `DoFieldExchange` veya sonraki çağrısı `SetFieldType` çıkış sütunları. Daha fazla bilgi için bkz: [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).  
  
-   Birkaç çağrı `RFX_Text` genel işlevi — her bir alan veri üyesi (tüm hangi olan `CString` örnekte değişkenleri). Bu çağrı veri kaynağında bir sütun adı ile bir alan veri üyesi arasındaki ilişkiyi belirtin. RFX işlevleri gerçek veri aktarımını yapar. Sınıf kitaplığı tüm ortak veri türleri için RFX işlevleri sağlar. RFX işlevleri hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX işlevlerini kullanma](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).  
  
    > [!NOTE]
    >  Sonuç kümesindeki sütunların sırasını RFX işlev çağrılarını sırasını eşleşmelidir `DoFieldExchange`.  
  
-   `pFX` İşaretçi bir [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) çağırdığında framework geçirir nesne `DoFieldExchange`. `CFieldExchange` Nesnesini belirtir. işlemi, `DoFieldExchange` gerçekleştirmek için yönünü aktarımı ve diğer bağlam bilgileri.  
  
##  <a name="_core_the_recordset_constructor"></a> Kayıt kümesi Oluşturucusu  
 Sihirbazlar yazma kayıt kümesi oluşturucusu için RFX ilgili iki şey içerir:  
  
-   Her alan veri üyesi için bir başlatma  
  
-   İçin bir başlatma [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) alan veri üyeleri sayısını içeren veri üyesi  
  
 Oluşturucusu `CSections` kayıt kümesi örnek şöyle görünür:  
  
```  
CSections::CSections(CDatabase* pdb)  
   : CRecordset(pdb)  
{  
   m_strCourseID = "";  
   m_strInstructorID = "";  
   m_strRoomNo = "";  
   m_strSchedule = "";  
   m_strSectionNo = "";  
   m_nFields = 5;  
}  
```  
  
> [!NOTE]
>  Yeni sütunları dinamik olarak bağlarsanız, olabileceği gibi herhangi bir alan veri üyesi el ile eklerseniz, artırmalısınız `m_nFields`. Bunu, kod, başka bir satırı ekleyerek yapın:  
  
```  
m_nFields += 3;  
```  

 Bu üç yeni alanlar ekleyerek koddur. Herhangi bir parametre veri üyesi eklerseniz, başlatmalıdır [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) parametre veri üyeleri sayısını içeren veri üyesi. PUT `m_nParams` başlatma köşeli ayraçlar dışında.  

  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)