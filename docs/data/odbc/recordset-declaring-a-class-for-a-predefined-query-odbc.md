---
description: 'Daha fazla bilgi: kayıt kümesi: önceden tanımlanmış sorgu için bir sınıf bildirme (ODBC)'
title: 'Kayıt Kümesi: Önceden Tanımlanmış Sorgu için Bir Sınıf Bildirme (ODBC)'
ms.date: 05/09/2019
helpviewer_keywords:
- ODBC recordsets, queries
- predefined queries and recordsets
- stored procedures, and recordsets
- recordsets, predefined queries
- recordsets, stored procedures
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
ms.openlocfilehash: e2071270bbff92e56b7fc3a2064e7e2f99f2044b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210952"
---
# <a name="recordset-declaring-a-class-for-a-predefined-query-odbc"></a>Kayıt Kümesi: Önceden Tanımlanmış Sorgu için Bir Sınıf Bildirme (ODBC)

> [!NOTE]
> MFC ODBC Tüketicisi Sihirbazı, Visual Studio 2019 ve sonrasında kullanılamaz. Yine de bir tüketicisi el ile oluşturabilirsiniz.

Bu konu MFC ODBC sınıfları için geçerlidir.

Bu konu başlığı altında, önceden tanımlanmış bir sorgu için bir kayıt kümesi sınıfının nasıl oluşturulacağı açıklanmaktadır (bazı durumlarda, Microsoft SQL Server olarak bir saklı yordam olarak adlandırılır).

> [!NOTE]
> Bu konu, `CRecordset` toplu satır yakalamanın uygulanmadığı, öğesinden türetilmiş nesneler için geçerlidir. Toplu satır getirme uygulanmışsa, işlem çok benzerdir. Toplu satır getirmeyi uygulayan kayıt kümeleri ve olmayanlar arasındaki farkları anlamak için bkz. [kayıt kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Bazı veritabanı yönetim sistemleri (DBMS 'ler), önceden tanımlanmış bir sorgu oluşturmanıza ve bunu bir işlev gibi programlarınızdan çağırlamanızı sağlar. Sorgu bir ada sahip, parametreler alabilir ve kayıt döndürebilir. Bu konudaki yordam, kayıtları döndüren önceden tanımlanmış bir sorgunun nasıl çağrılacağını açıklar (ve belki Parametreler alır).

Veritabanı sınıfları, önceden tanımlanmış sorguların güncelleştirilmesini desteklemez. Anlık görüntü önceden tanımlanmış bir sorgu ve Dynaset önceden tanımlanmış bir sorgu arasındaki fark updatebeceri değildir ancak diğer kullanıcılar (veya programınızdaki diğer kayıt kümeleri) tarafından yapılan değişikliklerin kayıt kümenizde görünür olup olmadığı.

> [!TIP]
> Kayıtlar döndürmeyen önceden tanımlanmış bir sorguyu çağırmak için bir kayıt kümesi gerekmez. SQL ifadesini aşağıda açıklandığı şekilde hazırlayın, ancak `CDatabase` [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql)üye işlevini çağırarak yürütün.

Önceden tanımlanmış bir sorgunun çağrılmasını yönetmek için tek bir kayıt kümesi sınıfı oluşturabilirsiniz, ancak bazı çalışmalarınız sizin yapmanız gerekir. Sihirbazlar, bu amaçla özel olarak bir sınıf oluşturulmasını desteklemez.

#### <a name="to-create-a-class-for-calling-a-predefined-query-stored-procedure"></a>Önceden tanımlanmış bir sorgu (saklı yordam) çağırmak için bir sınıf oluşturmak için

1. Sorgu tarafından döndürülen en fazla sütuna katkıda bulunan tablo için bir kayıt kümesi sınıfı oluşturmak üzere **Sınıf Ekle** ' den [MFC ODBC Tüketicisi Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) ' nı kullanın. Bu size bir baş başlangıç sağlar.

1. Sorgunun döndürdüğü, ancak sihirbazın sizin için oluşturmadığından tablo sütunlarının sütunları için alan veri üyelerini el ile ekleyin.

   Örneğin, sorgu iki ek tablodan üç sütun döndürürse, sınıfa altı alan veri üyesi (uygun veri türleri) ekleyin.

1. Eklenen her bir alan veri üyesinin veri türüne karşılık gelen, sınıfının [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye Işlevine, [RFX](../../data/odbc/record-field-exchange-rfx.md) işlev çağrılarını el ile ekleyin.

    ```cpp
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:
    pFX->SetFieldType( CFieldExchange::outputColumn );
    ```

    > [!NOTE]
    >  Sonuç kümesinde döndürülen veri türlerini ve sütunların sırasını bilmeniz gerekir. ' Deki RFX işlev çağrılarının sırası `DoFieldExchange` , sonuç kümesi sütunlarının sırası ile aynı olmalıdır.

1. Kayıt kümesi sınıf oluşturucusunda yeni alan veri üyeleri için başlatmaları el ile ekleyin.

   Ayrıca, [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) veri üyesinin başlatma değerini de artırmanız gerekir. Sihirbaz başlatmayı yazar, ancak yalnızca sizin için eklediği alan veri üyelerini ele alır. Örneğin:

    ```cpp
    m_nFields += 6;
    ```

   Bazı veri türleri, örneğin veya bayt dizileri için burada başlatılmamalıdır `CLongBinary` .

1. Sorgu Parametreler alırsa her bir parametre için bir parametre veri üyesi, her biri için bir RFX işlev çağrısı ve her biri için bir başlatma ekleyin.

1. `m_nParams` `m_nFields` Bu yordamın 4. adımında eklenen alanlar için yaptığınız gibi, eklenen her parametre için artırmanız gerekir. Daha fazla bilgi için bkz. [kayıt kümesi: bir kayıt kümesini parametrize (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

1. Aşağıdaki biçimde bir SQL deyimdizesi el ile yazın:

    ```
    {CALL proc-name [(? [, ?]...)]}
    ```

   Burada **Call** bir ODBC anahtar kelimedir, **proc-Name** veri kaynağında bilinen sorgunun adıdır ve "?" öğeleri, çalışma zamanında (varsa) kayıt kümesine sağladığınız parametre değerleri için yer tutuculardır. Aşağıdaki örnek bir parametre için bir yer tutucu hazırlar:

    ```
    CString mySQL = "{CALL Delinquent_Accts (?)}";
    ```

1. Kayıt kümesini açan kodda, kayıt kümesinin parametre veri üyelerinin değerlerini ayarlayın ve sonra `Open` , SQL dizenizi *lpszSQL* parametresi için geçirerek üye işlevini çağırın. Bunun yerine, `GetDefaultSQL` sınıfınıza üye işlevi tarafından döndürülen dizeyi değiştirin.

Aşağıdaki örneklerde, bir `Delinquent_Accts` Satış bölgesi numarası için bir parametre alan adlı önceden tanımlanmış bir sorgu çağırma yordamı gösterilmektedir. Bu sorgu üç sütun döndürür: `Acct_No` , `L_Name` , `Phone` . Tüm sütunlar müşteriler tablosudur.

Aşağıdaki kayıt kümesi, sorgunun döndürdüğü sütunlar için alan veri üyelerini ve çalışma zamanında istenen satış bölgesi numarası için bir parametre belirtir.

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

Bu sınıf bildirimi, sihirbaz tarafından yazdığı ve `m_lDistParam` üye için el ile eklenen bir durum değildir. Diğer Üyeler burada gösterilmez.

Sonraki örnekte, oluşturucuda veri üyeleri için başlatmalar gösterilmektedir `CDelinquents` .

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

[M_nFields](../../mfc/reference/crecordset-class.md#m_nfields) ve [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)için başlatmaları aklınızda edin. Sihirbaz başlatılır `m_nFields` ; başlatırsınız `m_nParams` .

Sonraki örnekte, içindeki RFX işlevleri gösterilmektedir `CDelinquents::DoFieldExchange` :

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

Döndürülen üç sütun için RFX çağrıları yapmanın yanı sıra, bu kod, çalışma zamanında geçirdiğiniz parametrenin bağlamasını yönetir. Parametresi `Dist_No` (District numarası) sütununa anahtarlanır.

Sonraki örnekte, SQL dizesinin nasıl ayarlanacağı ve kayıt kümesini açmak için nasıl kullanılacağı gösterilmektedir.

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

Bu kod bir anlık görüntü oluşturur, bunu kullanıcıdan daha önce elde edilen bir parametreye geçirir ve önceden tanımlanmış sorguyu çağırır. Sorgu çalıştırıldığında, belirtilen satış bölgesi için kayıtları döndürür. Her kayıt, hesap numarası, müşterinin son adı ve müşterinin telefon numarası için sütunlar içerir.

> [!TIP]
> Bir saklı yordamdan dönüş değeri (çıkış parametresi) işlemek isteyebilirsiniz. Daha fazla bilgi ve örnek için bkz. [CFieldExchange:: SETbir](../../mfc/reference/cfieldexchange-class.md#setfieldtype).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[Kayıt kümesi: bir kayıt kümesini yeniden sorgulama (ODBC)](../../data/odbc/recordset-requerying-a-recordset-odbc.md)<br/>
[Kayıt kümesi: tablo için sınıf bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)<br/>
[Kayıt kümesi: JOIN gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)
