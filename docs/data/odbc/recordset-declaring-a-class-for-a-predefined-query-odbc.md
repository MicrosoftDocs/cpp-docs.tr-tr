---
title: 'Kayıt Kümesi: Önceden Tanımlanmış Sorgu için Bir Sınıf Bildirme (ODBC)'
ms.date: 11/04/2016
helpviewer_keywords:
- ODBC recordsets, queries
- predefined queries and recordsets
- stored procedures, and recordsets
- recordsets, predefined queries
- recordsets, stored procedures
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
ms.openlocfilehash: e83bf2ecb24a9abfd8dc9800a3a10d2d65025336
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611269"
---
# <a name="recordset-declaring-a-class-for-a-predefined-query-odbc"></a>Kayıt Kümesi: Önceden Tanımlanmış Sorgu için Bir Sınıf Bildirme (ODBC)

Bu konu MFC ODBC sınıflarına uygulanır.

Bu konu (Microsoft SQL Server gibi bir saklı yordam olarak da adlandırılır) önceden tanımlanmış sorgu için bir kayıt kümesi sınıfı oluşturma işlemini açıklar.

> [!NOTE]
>  Bu konu, türetilmiş nesneler için geçerlidir. `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme uygulanmışsa çok benzer bir işlemdir. Toplu satır getirme uygulayan kayıt kümeleri ve değişmeyen arasındaki farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Bazı veritabanı yönetim sistemi (DBMS), önceden tanımlanmış bir sorgu oluşturun ve bir işlev gibi programlarınızın çağırmanıza olanak tanır. Sorgu bir ada sahip parametre alabilir ve kayıtları döndürebilir. Bu konudaki yordamı kayıtları döndürür (ve belki de kullandığı Parametreler) önceden tanımlanmış sorgu çağırmak nasıl açıklar.

Veritabanı sınıfları, önceden tanımlanmış sorguları güncelleme desteklemez. Anlık görüntü önceden tanımlanmış sorgu dynaset önceden tanımlanmış sorgu arasındaki fark güncellenebilirliğini ancak diğer kullanıcılar (veya diğer kayıt kümeleri programınızdaki) tarafından yapılan değişiklikleri kümenizde görünür olup değil.

> [!TIP]
>  Kayıtları döndürmeyen önceden tanımlanmış sorgu çağırmak için bir kayıt gerekmez. Aşağıda açıklandığı gibi SQL deyimini hazırlamak, ancak çağırarak çalıştırırsınız `CDatabase` üye işlevi [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql).

Önceden tanımlanmış sorgu çağırma yönetmek için tek bir kayıt kümesi sınıfı oluşturabilirsiniz, ancak bunu işinin bir kısmını kendiniz yapmanız gerekir. Sihirbazlar, özellikle bu amaç için bir sınıf oluşturma desteklemez.

#### <a name="to-create-a-class-for-calling-a-predefined-query-stored-procedure"></a>Önceden tanımlanmış sorgu çağırmak için bir sınıf oluşturun (saklı yordamı)

1. Kullanım [MFC ODBC Tüketicisi Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) gelen **sınıfı Ekle** sorgu tarafından döndürülen sütunlar en çok katkıda bulunduğu bir tablo için bir kayıt kümesi sınıfı oluşturmak için. Bu size avantajlı bir başlangıç sağlar.

1. Alan veri üyeleri, sihirbaz sizin yerinize oluşturmadınız ancak bu sorgunun döndürdüğü tüm tablolar, sütunlar için el ile ekleyin.

   Örneğin, sorgu iki ek tablodan üç sütun döndürürse, altı alan veri üyeleri (uygun veri türlerinin) sınıfına ekleyin.

1. El ile eklemeniz [RFX](../../data/odbc/record-field-exchange-rfx.md) işlev çağrıları [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) sınıfının üye işlevinde, her veri türü için karşılık gelen bir veri üyesi alanı eklendi.

    ```cpp
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:
    pFX->SetFieldType( CFieldExchange::outputColumn );
    ```

    > [!NOTE]
    >  Veri türleri ve sonuçta döndürülen sütun sırasını bilmeniz gerekir. RFX işlevi sırasını çağrıları `DoFieldExchange` sonuç kümesi sütun eşleşmesi gerekir.

1. Yeni alan veri üyeleri için başlatma işlemleri el ile kayıt kümesi sınıf oluşturucusunda ekleyin.

   Başlatma değeri de artırmalısınız [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) veri üyesi. Sihirbazı başlatma Yazar ancak sizin için ekler alan veri üyeleri yalnızca kapsar. Örneğin:

    ```cpp
    m_nFields += 6;
    ```

   Bazı veri türleri burada Örneğin, başlatılmamış `CLongBinary` veya bayt dizisi.

1. Sorgu parametreleri alırsa, her bir parametre, her bir RFX işlev çağrısı ve her bir başlatma parametre veri üyesi ekleyin.

1. Artırmanız gerekir `m_nParams` yaptığınız gibi her parametre, eklenen için `m_nFields` için alanları bu yordamın 4. adımında eklendi. Daha fazla bilgi için [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

1. El ile bir SQL deyimi dizesiyle aşağıdaki biçimde yazın:

    ```
    {CALL proc-name [(? [, ?]...)]}
    ```

   Burada **çağrı** bir ODBC anahtar sözcüğü **yordam adı** olarak da bilinen veri kaynağında, sorgunun adıdır ve "?" öğeler sağladığınız kayıt için çalışma zamanında (varsa) parametre değerleri için yer tutucu . Aşağıdaki örnek, bir parametre için bir yer tutucu hazırlar:

    ```
    CString mySQL = "{CALL Delinquent_Accts (?)}";
    ```

1. Kayıt kümesi açılır kodda veri üyeleri kümesinin parametre değerlerini ayarlayın ve sonra çağrı `Open` SQL dizenizi geçirmek için üye işlevi *lpszSQL* parametresi. Veya bunun yerine, tarafından döndürülen dize değiştirin `GetDefaultSQL` sınıfınızdaki üye işlevi.

Aşağıdaki örnekler adlı önceden tanımlanmış sorgu, çağırma yordamı `Delinquent_Accts`, bir satış bölgesi numarası için bir parametre alır. Bu sorgunun döndürdüğü üç sütun: `Acct_No`, `L_Name`, `Phone`. Müşteriler tablosundan tüm sütunlarıdır.

Alan veri üyeleri sorgunun döndürdüğü ve satış için bir parametre numarası çalışma zamanında istenen bölge için aşağıdaki kayıt kümesini belirtir.

```cpp
class CDelinquents : public CRecordset
{
// Field/Param Data
    LONG m_lAcct_No;
    CString m_strL_Name;
    CString m_strPhone;
    LONG m_lDistParam;
    // ...
};
```

Bu sınıf bildirimi dışında Yazar Sihirbazı, aynıdır `m_lDistParam` el ile eklenen üye. Diğer üyeleri burada gösterilmez.

Sonraki örnek, veri üyeleri başlatmalarına gösterir `CDelinquents` Oluşturucusu.

```cpp
CDelinquents::CDelinquents(CDatabase* pdb)
   : CRecordset(pdb)
{
    // Wizard-generated params:
    m_lAcct_No = 0;
    m_strL_Name = "";
    m_strPhone = "";
    m_nFields = 3;
    // User-defined params:
    m_nParams = 1;
    m_lDistParam = 0;
}
```

Başlatmalar için Not [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) ve [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams). Sihirbazı'nı başlatır `m_nFields`; başlatır `m_nParams`.

Sonraki örnek, RFX işlevleri gösterir `CDelinquents::DoFieldExchange`:

```cpp
void CDelinquents::DoFieldExchange(CFieldExchange* pFX)
{
    pFX->SetFieldType(CFieldExchange::outputColumn);
    RFX_Long(pFX, "Acct_No", m_lAcct_No);
    RFX_Text(pFX, "L_Name", m_strL_Name);
    RFX_Text(pFX, "Phone", m_strPhone);
    pFX->SetFieldType(CFieldExchange::param);
    RFX_Long(pFX, "Dist_No", m_lDistParam);
}
```

RFX üç döndürülen sütunlar için aramaların yanı sıra, bu kod, çalışma zamanında geçirdiğiniz parametre bağlama yönetir. Parametre anahtarlanır `Dist_No` (bölge numarası) sütunu.

Sonraki örnekte, nasıl SQL dizesi ayarlama ve nasıl kayıt kümesini açmak için kullanılacağını gösterir.

```cpp
// Construct a CDelinquents recordset object
CDelinquents rsDel( NULL );
CString strSQL = "{CALL Delinquent_Accts (?)}"
// Specify a parameter value (obtained earlier from the user)
rsDel.m_lDistParam = lDistrict;
// Open the recordset and run the query
if( rsDel.Open( CRecordset::snapshot, strSQL ) )
    // Use the recordset ...
```

Bu kod, bir anlık görüntü oluşturur, daha önce kullanıcıdan alınan bir parametre geçirir ve önceden tanımlanmış sorgu çağırır. Sorgu çalıştırıldığında, belirtilen satış bölgesi için kayıtları döndürür. Her kayıt için hesap numarası, Müşteri'nin son adı ve müşterinin telefon numarası sütunları içerir.

> [!TIP]
>  Bir saklı yordamdan gelen dönüş değeri (çıkış parametresi) işlemek isteyebilirsiniz. Daha fazla bilgi ve örnek için bkz. [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).

## <a name="see-also"></a>Ayrıca Bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)<br/>
[Kayıt Kümesi: Tablo için Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Kayıt Kümesi: Birleşim Gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)