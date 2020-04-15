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
ms.openlocfilehash: 8e42fc9da672ca4ef97e775776935650ab7f545a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367124"
---
# <a name="record-field-exchange-working-with-the-wizard-code"></a>Kayıt Alanı Değişimi: Sihirbaz Kodu ile Çalışma

> [!NOTE]
> MFC ODBC Tüketici sihirbazı Visual Studio 2019 ve sonraki yıllarda kullanılamaz. Yine de bir tüketiciyi el ile oluşturabilirsiniz.

Bu konu, MFC Uygulama Sihirbazı ve **Add Class** 'ın [(MFC ODBC Tüketici eklemede](../../mfc/reference/adding-an-mfc-odbc-consumer.md)açıklandığı gibi) RFX'i desteklemek için yazdığı kodu ve bu kodu nasıl değiştirmek isteyebileceğini açıklar.

> [!NOTE]
> Bu konu, toplu satır `CRecordset` alma nın uygulanmadığı sınıflar için geçerlidir. Toplu satır alma kullanıyorsanız, toplu kayıt alanı değişimi (Toplu RFX) uygulanır. Toplu RFX RFX benzer. Farklılıkları anlamak için bkz: [Recordset: Kayıtları Toplu Olarak Alma (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

MFC Application Wizard veya **Add Class**ile bir kayıt kümesi sınıfı oluşturduğunuzda, sihirbaz, sihirbazda yaptığınız veri kaynağı, tablo ve sütun seçimlerini temel alınarak sizin için Aşağıdaki RFX ile ilgili öğeleri yazar:

- Kayıt kümesi sınıfındaki kayıt alanı veri üyelerinin bildirimleri

- Bir geçersiz kılma`CRecordset::DoFieldExchange`

- Recordset alan veri üyelerinin kayıt kümesi sınıfı oluşturucuda başlatılması

## <a name="field-data-member-declarations"></a><a name="_core_the_field_data_member_declarations"></a>Alan Verileri Üye Beyanları

Sihirbazlar, sınıf `CSections`için aşağıdakileri andıran bir .h dosyasına bir kayıt kümesi sınıf bildirimi yazar:

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

Kendi bağlandığınız parametre veri üyeleri veya yeni alan veri üyeleri eklerseniz, bunları sihirbaz tarafından oluşturulanlardan sonra ekleyin.

Ayrıca, sihirbaz Sınıfın `DoFieldExchange` `CRecordset`üye işlevini geçersiz kılar dikkat edin.

## <a name="dofieldexchange-override"></a><a name="_core_the_dofieldexchange_override"></a>DoFieldExchange Geçersiz Kılma

[DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) RFX kalbidir. Çerçeve, `DoFieldExchange` verileri veri kaynağından kayıt kümesine veya kayıt kümesinden veri kaynağına taşıması gereken her zaman çağırır. `DoFieldExchange`ayrıca [IsFieldDirty](../../mfc/reference/crecordset-class.md#isfielddirty) ve [IsFieldNull](../../mfc/reference/crecordset-class.md#isfieldnull) üye işlevleri aracılığıyla alan veri üyeleri hakkında bilgi edinmeyi destekler.

Aşağıdaki `DoFieldExchange` geçersiz kılma `CSections` sınıf içindir. Sihirbaz, kayıt kümesi sınıfınız için .cpp dosyasındaki işlevi yazar.

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

Fonksiyonun aşağıdaki temel özelliklerine dikkat edin:

- İşlevin bu bölümüne alan haritası denir.

- İşaretçi `CFieldExchange::SetFieldType`aracılığıyla bir çağrı. `pFX` Bu çağrı, tüm RFX işlevinin sonuna `DoFieldExchange` kadar veya bir `SetFieldType` sonraki çağrının çıkış sütunları olduğunu belirtir. Daha fazla bilgi için [Bkz. CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).

- Genel işleve `RFX_Text` birkaç çağrı - alan veri üyesi `CString` başına bir çağrı (hepsi örnekte değişkendir). Bu çağrılar, veri kaynağındaki sütun adı ile alan veri üyesi arasındaki ilişkiyi belirtir. Gerçek veri aktarımını RFX işlevleri yapar. Sınıf kitaplığı, tüm ortak veri türleri için RFX işlevleri sağlar. RFX işlevleri hakkında daha fazla bilgi için Kayıt [Alanı Değişimi: RFX Fonksiyonlarını Kullanma.](../../data/odbc/record-field-exchange-using-the-rfx-functions.md)

    > [!NOTE]
    >  Sonuç kümesinizdeki sütunların sırası, `DoFieldExchange`RFX işlevi ndeki çağrıların sırasına uygun olmalıdır.

- Bir `pFX` [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) nesnesinin işaretçisi, `DoFieldExchange`çerçeveyi aradığında geçer. Nesne, `CFieldExchange` gerçekleştirecek işlemi, `DoFieldExchange` aktarım yönünü ve diğer bağlam bilgilerini belirtir.

## <a name="recordset-constructor"></a><a name="_core_the_recordset_constructor"></a>Recordset Yapıcı

Sihirbazların yazdığı kaydedici oluşturucu, RFX ile ilgili iki şey içerir:

- Her alan veri üyesi için bir başlatma

- Alan veri üye sayısını içeren [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) veri üyesi için bir başlatma

Kayıt kümesi örneğinin `CSections` oluşturucusu aşağıdaki gibi görünür:

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
> Herhangi bir alan veri üyesini el ile eklerseniz, yeni sütunları dinamik olarak `m_nFields`bağlarsanız, artırıcı nız gerekir. Bunu, şu gibi başka bir kod satırı ekleyerek yapın:

```cpp
m_nFields += 3;
```

Bu, üç yeni alan eklemek için koddur. Herhangi bir parametre veri üyesi eklerseniz, parametre veri üye sayısını içeren [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams) veri üyesini başlatmanız gerekir. Başlaştırmayı parantezin `m_nParams` dışına koyun.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md)
