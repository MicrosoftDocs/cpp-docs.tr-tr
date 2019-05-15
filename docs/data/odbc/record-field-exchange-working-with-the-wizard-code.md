---
title: 'Kayıt Alanı Değişimi: Sihirbaz kodu ile çalışma'
ms.date: 05/09/2019
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
ms.openlocfilehash: 81b26e61f64623d1e3da5ed207d0e8e43350229d
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65708000"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>Kayıt Alanı Değişimi: Sihirbaz kodu ile çalışma

> [!NOTE] 
> MFC ODBC Tüketici Sihirbazı'nı ve sonrasında Visual Studio 2019 içinde kullanılabilir değil. Bir tüketici yine de el ile oluşturabilirsiniz.

Bu konu, kod açıklar, MFC Uygulama Sihirbazı ve **sınıfı Ekle** (açıklandığı [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)) RFX ve bu kodu değiştirmek nasıl isteyebileceğiniz desteklemek yazma.

> [!NOTE]
>  Bu konu, türetilen sınıflar için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (Bulk RFX) uygulanır. Toplu RFX RFX için benzerdir. Farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

MFC Uygulama Sihirbazı'nı kullanarak bir kayıt kümesi sınıfı oluşturduğunuzda, veya **sınıfı Ekle**, sihirbaz, veri kaynağını temel tablo ve sütun seçenekleri Sihirbazı'nda yapmak için aşağıdaki RFX ilgili öğeleri Yazar:

- Kayıt kümesi sınıf veri üyeleri kayıt kümesinin bildirimleri alan

- Geçersiz kılma `CRecordset::DoFieldExchange`

- Kayıt kümesi sınıfı oluşturucusunda kayıt alan veri üyeleri başlatma

##  <a name="_core_the_field_data_member_declarations"></a> Alan veri üye bildirimleri

Sihirbazlar bir kayıt kümesi sınıf bildiriminin sınıf için aşağıdakine benzer bir .h dosyası yazma `CSections`:

```cpp
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

Parametre veri üyeleri veya kendiniz bağlama yeni alan veri üyeleri eklerseniz, bunları sonra sihirbazın ürettiği olanları ekleyin.

Ayrıca, sihirbaz geçersiz kılan bildirimi `DoFieldExchange` sınıfının üye işlevinde `CRecordset`.

##  <a name="_core_the_dofieldexchange_override"></a> DoFieldExchange geçersiz kılma

[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) RFX kalbidir. Framework çağrıları `DoFieldExchange` veri kaynağına veri kaynağı kayıt kümesine ya da kayıt kümesinden verileri taşımak için ihtiyaç duyduğu her zaman. `DoFieldExchange` Ayrıca desteklediği hakkında bilgi edinme alanı üzerinden veri üyelerine [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty) ve [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull) üye işlevleri.

Aşağıdaki `DoFieldExchange` geçersiz kıldığından `CSections` sınıfı. Sihirbaz işlevi kayıt sınıfınız için .cpp dosyasına yazar.

```cpp
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

İşlevin aşağıdaki önemli özelliklere dikkat edin:

- Bu bölümde işlevin alan eşlemesi çağrılır.

- Bir çağrı `CFieldExchange::SetFieldType`temellidir `pFX` işaretçi. Bu çağrı, tüm RFX işlevi sonuna ProcessOrder belirtir `DoFieldExchange` veya sonraki çağrı `SetFieldType` çıktı sütunlarıdır. Daha fazla bilgi için [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).

- Çeşitli çağrılar `RFX_Text` genel işlev — veri üyesi alanı başına bir (bir işlem olan tüm `CString` örnekte değişkenleri). Bu çağrılar veri kaynağında bir sütun adı ve alan veri üyesi arasındaki ilişkiyi belirtin. RFX işlevlerini gerçek veri aktarımı yapabilirsiniz. Sınıf kitaplığı, ortak veri türleri için RFX işlevleri sağlar. RFX işlevleri hakkında daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX işlevlerini kullanma](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).

    > [!NOTE]
    >  RFX işlev çağrılarında sırası, sonuç kümesindeki sütunların sırasını eşleşmelidir `DoFieldExchange`.

- `pFX` İşaretçi bir [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) çağırdığında framework geçirir nesnesini `DoFieldExchange`. `CFieldExchange` Nesnesini işlemi belirtir, `DoFieldExchange` gerçekleştirmek için aktarımı ve diğer bağlam bilgileriyle yönü.

##  <a name="_core_the_recordset_constructor"></a> Kayıt kümesi Oluşturucusu

Sihirbazlar kayıt oluşturucusu için RFX ilgili iki şey içerir:

- Her alanın veri üyesi için bir başlatma

- İçin bir başlatma [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) alan veri üyeleri sayısını içeren veri üyesi

Oluşturucusu `CSections` kayıt örnek şöyle görünür:

```cpp
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
>  Yeni sütunlar dinamik olarak bağlarsanız, olabileceği gibi herhangi bir alan veri üyeleri el ile eklerseniz, artırmalısınız `m_nFields`. Başka bir satır kod ekleyerek bunu:

```cpp
m_nFields += 3;
```

Üç yeni alanlar eklemek için kod budur. Tüm parametre veri üyeleri eklerseniz, başlatmalıdır [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) veri üyesi, parametre veri üyeleri sayısını içerir. PUT `m_nParams` başlatma köşeli ayraçlar dışında.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)