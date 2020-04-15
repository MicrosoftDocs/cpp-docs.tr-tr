---
title: 'Kayıt Kümesi: Önceden Tanımlanmış Sorgu için Bir Sınıf Bildirme (ODBC)'
ms.date: 05/09/2019
helpviewer_keywords:
- ODBC recordsets, queries
- predefined queries and recordsets
- stored procedures, and recordsets
- recordsets, predefined queries
- recordsets, stored procedures
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
ms.openlocfilehash: f9618f25d738c092ab1818ef7c4ea52928e2ea60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367035"
---
# <a name="recordset-declaring-a-class-for-a-predefined-query-odbc"></a>Kayıt Kümesi: Önceden Tanımlanmış Sorgu için Bir Sınıf Bildirme (ODBC)

> [!NOTE]
> MFC ODBC Tüketici sihirbazı Visual Studio 2019 ve sonraki yıllarda kullanılamaz. Yine de bir tüketiciyi el ile oluşturabilirsiniz.

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu, önceden tanımlanmış bir sorgu için kayıt kümesi sınıfının nasıl oluşturuluryapılacağını açıklar (bazen Microsoft SQL Server'da olduğu gibi depolanmış yordam olarak adlandırılır).

> [!NOTE]
> Bu konu, toplu satır `CRecordset` alma nın uygulanmadığı türetilen nesneler için geçerlidir. Toplu satır alma uygulanıyorsa, işlem çok benzer. Toplu satır alma uygulayan kayıt kümeleri ile olmayanlar arasındaki farkları anlamak için [bkz.](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)

Bazı veritabanı yönetim sistemleri (DBMSs) önceden tanımlanmış bir sorgu oluşturmanıza ve programlarınızın işlev gibi çağrılmasını sağlar. Sorgunun bir adı vardır, parametreleri alabilir ve kayıtları döndürebilir. Bu konudaki yordam, kayıtları döndüren (ve belki de parametreleri alan) önceden tanımlanmış bir sorgunun nasıl çağrılmasını açıklar.

Veritabanı sınıfları önceden tanımlanmış sorguları güncelleştirmeyi desteklemez. Anlık görüntü önceden tanımlanmış sorgu ile önceden tanımlanmış bir dinamit sorgusu arasındaki fark güncellenebilirlik değildir, ancak kayıt setinizde diğer kullanıcılar (veya programınızdaki diğer kayıt kümeleri) tarafından yapılan değişikliklerin görünüp görülemeyeceğidir.

> [!TIP]
> Kayıtları döndürmeyen önceden tanımlanmış bir sorgu çağırmak için bir kayıt kümesine ihtiyacınız yoktur. SQL deyimini aşağıda açıklandığı gibi hazırlayın, `CDatabase` ancak üye işlev [executeSQL](../../mfc/reference/cdatabase-class.md#executesql)çağırarak çalıştırın.

Önceden tanımlanmış bir sorguyu aramayı yönetmek için tek bir kayıt kümesi sınıfı oluşturabilirsiniz, ancak bazı işleri kendiniz yapmanız gerekir. Sihirbazlar, bu amaç için özel olarak bir sınıf oluşturmayı desteklemez.

#### <a name="to-create-a-class-for-calling-a-predefined-query-stored-procedure"></a>Önceden tanımlanmış bir sorgu (depolanmış yordam) çağırmak için bir sınıf oluşturmak için

1. Sorgu tarafından döndürülen en çok sütuna katkıda bulunan tablo için bir kayıt kümesi sınıfı oluşturmak için **Ekle Sınıfı'ndaki** [MFC ODBC Tüketici](../../mfc/reference/adding-an-mfc-odbc-consumer.md) Sihirbazı'nı kullanın. Bu size bir başlangıç sağlar.

1. Sorgunun döndürdüğü ancak sihirbazın sizin için oluşturmadığı tablolardaki bütünler için alan veri sağlarını el ile ekleyin.

   Örneğin, sorgu iki ek tablodan her biri üç sütun döndürürse, sınıfa altı alan veri üyesi (uygun veri türlerinin) ekleyin.

1. Sınıfın [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlevine, eklenen her alan veri üyesinin veri türüne karşılık gelen [RFX](../../data/odbc/record-field-exchange-rfx.md) işlev çağrılarını el ile ekleyin.

    ```cpp
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:
    pFX->SetFieldType( CFieldExchange::outputColumn );
    ```

    > [!NOTE]
    >  Sonuç kümesinde döndürülen veri türlerini ve sütunların sırasını bilmeniz gerekir. RFX işlev çağrılarının `DoFieldExchange` sırası, sonuç kümesi sütunlarının sırasına uygun olmalıdır.

1. Recordset sınıf oluşturucudaki yeni alan veri üyeleri için el ile başlatma ları ekleyin.

   [Ayrıca, m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) veri üyesinin başlatma değerini de artımgerekir. Sihirbaz başlatmayı yazar, ancak yalnızca sizin için eklediği alan veri üyelerini kapsar. Örneğin:

    ```cpp
    m_nFields += 6;
    ```

   Bazı veri türleri burada, `CLongBinary` örneğin, veya bayt dizileri başharflerine verilmemelidir.

1. Sorgu parametreleri alıyorsa, her parametre için bir parametre veri üyesi, her biri için bir RFX işlevi çağrısı ve her biri için bir başlatma ekleyin.

1. `m_nParams` Bu yordamın `m_nFields` 4. Daha fazla bilgi için [bkz: Kayıt Kümesini Parametreleme (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

1. Aşağıdaki formu içeren bir SQL deyimi dizesini el ile yazın:

    ```
    {CALL proc-name [(? [, ?]...)]}
    ```

   **CALL'ın** Bir ODBC anahtar kelimesi olduğu durumlarda, **proc adı,** veri kaynağında bilindiği gibi sorgunun adıdır ve "?" öğeleri, çalışma zamanında kayıt kümesine sağladığınız parametre değerlerinin yer tutucularıdır (varsa). Aşağıdaki örnek, bir parametre için bir yer tutucu hazırlar:

    ```
    CString mySQL = "{CALL Delinquent_Accts (?)}";
    ```

1. Kayıt kümesini açan kodda, kaydedici setin parametre veri üyelerinin değerlerini ayarlayın `Open` ve *ardından lpszSQL* parametresi için SQL dizenizi geçerek üye işlevini arayın. Ya da bunun yerine, `GetDefaultSQL` sınıfınızdaki üye işlev tarafından döndürülen dizeyi değiştirin.

Aşağıdaki örnekler, bir satış bölge numarası için `Delinquent_Accts`bir parametre alan , adlı önceden tanımlanmış bir sorguyu çağırma yordamını gösterir. Bu sorgu üç `Acct_No`sütun `L_Name` `Phone`döndürür: , , . Tüm sütunlar Müşteriler tablosundan dır.

Aşağıdaki kayıt kümesi, sorgunun döndürdettiği sütunlar için alan veri üyelerini ve çalışma zamanında istenen satış bölgesi numarası için bir parametre belirtir.

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

Bu sınıf bildirimi, el ile eklenen `m_lDistParam` üye dışında sihirbazın yazdığı gibidir. Diğer üyeler burada gösterilmez.

Sonraki örnek, `CDelinquents` oluşturucudaki veri üyelerinin başlangıçlarını gösterir.

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

[m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) ve [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)için başlatmalara dikkat edin. Sihirbaz başlatıyor; `m_nFields` eğer ilk `m_nParams`olarak .

Sonraki örnekte RFX işlevleri `CDelinquents::DoFieldExchange`gösterir:

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

Döndürülen üç sütun için RFX çağrıları yapmanın yanı sıra, bu kod çalışma zamanında geçtiğiniz parametreyi bağlamayı yönetir. Parametre (bölge numarası) `Dist_No` sütununa anahtarlanır.

Sonraki örnek, SQL dizesinin nasıl ayarılacağını ve kayıt kümesini açmak için nasıl kullanılacağını gösterir.

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

Bu kod anlık görüntü oluşturuyor, kullanıcıdan daha önce alınan bir parametreyi aktarıyor ve önceden tanımlanmış sorguyu çağırır. Sorgu çalıştığında, belirtilen satış bölgesinin kayıtlarını döndürür. Her kayıt, hesap numarası, müşterinin soyadı ve müşterinin telefon numarası için sütunlar içerir.

> [!TIP]
> Depolanan yordamdan bir geri dönüş değeri (çıktı parametresi) işlemek isteyebilirsiniz. Daha fazla bilgi ve bir örnek için [Bkz. CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: Bir Kayıt Kümesinde Yeniden Sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)<br/>
[Kayıt Kümesi: Tablo için Sınıf Bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Kayıt Kümesi: Birleşim Gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)
