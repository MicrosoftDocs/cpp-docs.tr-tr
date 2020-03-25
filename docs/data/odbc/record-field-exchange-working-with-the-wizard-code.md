---
title: 'Kayıt Alanı Değişimi: Sihirbaz Kodu ile Çalışma'
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
ms.openlocfilehash: 08d58561e0fb9305ff3a8d6aa6a62eb24d9b9d25
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80213050"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>Kayıt Alanı Değişimi: Sihirbaz Kodu ile Çalışma

> [!NOTE]
> MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. Yine de bir tüketicisi el ile oluşturabilirsiniz.

Bu konuda, RFX 'i desteklemek için MFC Uygulama Sihirbazı 'Nın ( [MFC ODBC Tüketicisi Ekleme](../../mfc/reference/adding-an-mfc-odbc-consumer.md)bölümünde açıklandığı gibi) yazma **kodu ve bu** kodu nasıl değiştirmek isteyebileceğiniz açıklanmaktadır.

> [!NOTE]
>  Bu konu, toplu satır yakalamanın uygulanmadığı `CRecordset` türetilen sınıflar için geçerlidir. Toplu satır getirme kullanıyorsanız, toplu kayıt alanı değişimi (toplu RFX) uygulanır. Toplu RFX, RFX 'e benzerdir. Farkları anlamak için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

MFC Uygulama Sihirbazı veya **Sınıf Ekle**ile bir kayıt kümesi sınıfı oluşturduğunuzda sihirbaz, sihirbazda yaptığınız veri kaynağı, tablo ve sütun seçeneklerine bağlı olarak sizin IÇIN aşağıdaki RFX ile ilgili öğeleri Yazar:

- Kayıt kümesi sınıfındaki kayıt kümesi alanı veri üyelerinin bildirimleri

- `CRecordset::DoFieldExchange` geçersiz kılma

- Kayıt kümesi sınıf oluşturucusunda kayıt kümesi alan veri üyeleri başlatma

##  <a name="field-data-member-declarations"></a><a name="_core_the_field_data_member_declarations"></a>Alan veri üyesi bildirimleri

Sihirbazlar, sınıf `CSections`için aşağıdakine benzer bir. h dosyasına bir kayıt kümesi sınıfı bildirimi Yazar:

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

Kendi oluşturduğunuz parametre veri üyelerini veya yeni alan veri üyelerini eklerseniz, bunları sihirbaz tarafından oluşturulan bir sonraki şekilde ekleyin.

Ayrıca, sihirbazın `CRecordset`sınıfının `DoFieldExchange` üye işlevini geçersiz kıldığını unutmayın.

##  <a name="dofieldexchange-override"></a><a name="_core_the_dofieldexchange_override"></a>DoFieldExchange geçersiz kılma

[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) , RFX 'in kalbidir. Çerçeve, verileri veri kaynağından kayıt kümesine ya da kayıt kümesinden veri kaynağına taşımak için gereken her seferinde `DoFieldExchange` çağırır. `DoFieldExchange` Ayrıca, [ıfielddirty](../../mfc/reference/crecordset-class.md#isfielddirty) ve [ıfieldnull](../../mfc/reference/crecordset-class.md#isfieldnull) üye işlevleri aracılığıyla alan veri üyeleri hakkında bilgi edinmeyi da destekler.

Aşağıdaki `DoFieldExchange` geçersiz kılma `CSections` sınıfı içindir. Sihirbaz, işlevi kayıt kümesi sınıfınız için. cpp dosyasına yazar.

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

İşlevinin aşağıdaki temel özelliklerine dikkat edin:

- İşlevin bu bölümüne alan eşlemesi denir.

- `pFX` işaretçisi aracılığıyla `CFieldExchange::SetFieldType`çağrısı. Bu çağrı, tüm RFX işlevinin `DoFieldExchange` sonuna kadar çağırılacağını veya `SetFieldType` bir sonraki çağrının çıkış sütunları olduğunu belirtir. Daha fazla bilgi için bkz. [CFieldExchange:: SETbir](../../mfc/reference/cfieldexchange-class.md#setfieldtype).

- `RFX_Text` genel işlevine birkaç çağrı — alan veri üyesi başına bir tane (örnekteki `CString` değişken). Bu çağrılar, veri kaynağındaki bir sütun adı ve alan veri üyesi arasındaki ilişkiyi belirtir. RFX işlevleri gerçek veri aktarımını işler. Sınıf kitaplığı tüm ortak veri türleri için RFX işlevlerini sağlar. RFX işlevleri hakkında daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX Işlevlerini kullanma](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).

    > [!NOTE]
    >  Sonuç kümesindeki sütunların sırası, `DoFieldExchange`RFX işlev çağrılarının sırasıyla aynı olmalıdır.

- `pFX`, `DoFieldExchange`çağırdığında çerçevenin aktardığı bir [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesine işaretçi. `CFieldExchange` nesnesi, `DoFieldExchange` gerçekleştirilecek işlemi, aktarmanın yönünü ve diğer bağlam bilgilerini belirtir.

##  <a name="recordset-constructor"></a><a name="_core_the_recordset_constructor"></a>Kayıt kümesi Oluşturucusu

Sihirbazların yazacağı kayıt kümesi Oluşturucusu RFX ile ilgili iki şey içerir:

- Her alan veri üyesi için bir başlatma

- Alan veri üyelerinin sayısını içeren [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) veri üyesine yönelik bir başlatma

`CSections` kayıt kümesi örneği için Oluşturucu şuna benzer:

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
>  Herhangi bir alan veri üyesini el ile eklerseniz, yeni sütunları dinamik olarak bağladığınızda `m_nFields`artırmanız gerekir. Bunu başka bir kod satırı ekleyerek yapın, örneğin:

```cpp
m_nFields += 3;
```

Bu, üç yeni alan eklemek için koddur. Herhangi bir parametre veri üyesi eklerseniz, parametre veri üyelerinin sayısını içeren [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) veri üyesini başlatmalısınız. `m_nParams` başlatmayı köşeli ayracın dışına koyun.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)
