---
title: 'Kayıt kümesi: bir sınıf bir önceden tanımlanmış sorgu için bildirme (ODBC) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ODBC recordsets, queries
- predefined queries and recordsets
- stored procedures, and recordsets
- recordsets, predefined queries
- recordsets, stored procedures
ms.assetid: d27c4df9-dad2-4484-ba72-92ab0c8ff928
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cbbb9202aaf56681a792e1acf2a0c02eff5636d9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33092381"
---
# <a name="recordset-declaring-a-class-for-a-predefined-query-odbc"></a>Kayıt Kümesi: Önceden Tanımlanmış Sorgu için Bir Sınıf Bildirme (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Bu konuda (Microsoft SQL Server gibi bir saklı yordam de denir) önceden tanımlanmış sorgu için bir kayıt kümesi sınıfın nasıl oluşturulacağı açıklanmaktadır.  
  
> [!NOTE]
>  Bu konuda türetilen nesnelere uygulanır `CRecordset` toplu satır getirme uygulanmadı. Toplu satır getirme uygulanmışsa çok benzer bir işlemdir. Toplu satır getirme uygulamak kayıt kümeleri ve değişmeyen arasındaki farkları anlamak için bkz: [kayıt kümesi: Kayıtları toplu (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Bazı veritabanı yönetim sistemi (DBMS), önceden tanımlanmış bir sorgu oluşturup programlarınızı bir işlev gibi çağırmanıza olanak tanır. Sorgu bir adı vardır, parametreler alabilir ve kayıtları döndürebilir. Bu konudaki yordamı kayıtları döndüren (ve belki de kullandığı Parametreler) tanımlanmış bir sorguyu çağırmak açıklar.  
  
 Veritabanı sınıfları önceden tanımlanmış sorgular güncelleştirme desteklemez. Anlık görüntü önceden tanımlanmış sorgu dynaset önceden tanımlanmış sorgu arasındaki fark güncellenebilirliğini ancak diğer kullanıcılar (veya diğer kayıt kümeleri programınızdaki) tarafından yapılan değişiklikleri kümenizde görünür olup değil.  
  
> [!TIP]
>  Kayıtları döndürmeyen tanımlanmış bir sorguyu çağırmak için bir kayıt gerekmez. SQL deyimi aşağıda açıklandığı şekilde hazırlayın, ancak çağırarak yürütün `CDatabase` üye işlevi [ExecuteSQL](../../mfc/reference/cdatabase-class.md#executesql).  
  
 Önceden tanımlanmış sorgu çağırma yönetmek için tek bir kayıt kümesi sınıfı oluşturabilirsiniz, ancak bazı iş kendiniz yapmanız gerekir. Sihirbazlar, özellikle bu amaç için bir sınıf oluşturma desteklemez.  
  
#### <a name="to-create-a-class-for-calling-a-predefined-query-stored-procedure"></a>Önceden tanımlanmış sorgu çağırmak için bir sınıf oluşturun (saklı yordamı)  
  
1.  Kullanım [MFC ODBC Tüketici Sihirbazı](../../mfc/reference/adding-an-mfc-odbc-consumer.md) gelen **sınıfı Ekle** en sorgu tarafından döndürülen sütunları katkıda bulunan tablo için bir kayıt kümesi sınıfı oluşturmak için. Bu bir başlangıç sağlar.  
  
2.  Alan veri üyeleri bir sütuna sihirbaz sizin için oluşturmadı ancak bu sorgunun döndürdüğü herhangi bir tabloya ait el ile ekleyin.  
  
     Örneğin, sorgu iki ek tablodan üç sütun döndürürse, altı alan veri üyeleri (uygun veri türleri için) sınıfına ekleyin.  
  
3.  El ile eklemeniz [RFX](../../data/odbc/record-field-exchange-rfx.md) işlev çağrıları [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) üye işlevi sınıfın her bir veri türüne karşılık gelen bir alan veri üyesi eklendi.  
  
    ```  
    Immediately before these RFX calls, call <MSHelp:link keywords="_mfc_CFieldExchange.3a3a.SetFieldType" TABINDEX="0">SetFieldType</MSHelp:link>, as shown here:   
    pFX->SetFieldType( CFieldExchange::outputColumn );  
    ```  
  
    > [!NOTE]
    >  Veri türleri ve sonuçta döndürülen sütunların sırasını ayarlama bilmeniz gerekir. RFX işlevi sırasını çağrıları `DoFieldExchange` sonuç kümesi sütunlarının eşleşmesi gerekir.  
  
4.  El ile yeni alan veri üyeleri için başlatmaları kayıt kümesi sınıf oluşturucusunda ekleyin.  
  
     Başlatma değerini artırmanız gerekir [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) veri üyesi. Sihirbazı başlatma yazar, ancak yalnızca sizin için eklediği alan veri üyeleri kapsar. Örneğin:  
  
    ```  
    m_nFields += 6;  
    ```  
  
     Bazı veri türleri Burada, örneğin, başlatılmamış `CLongBinary` veya bayt dizileri.  
  
5.  Sorgu parametreleri alıyorsa, her bir parametreyi, her bir RFX işlev çağrısı ve her biri için bir başlatma için parametre veri üyesi ekleyin.  
  
6.  Artırmanız gerekir `m_nParams` yaptığınız her eklenen parametresi için `m_nFields` için alanları bu yordamın 4 adımda eklendi. Daha fazla bilgi için bkz: [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
7.  El ile bir SQL deyimi dizeyle aşağıdaki biçimde yazın:  
  
    ```  
    {CALL proc-name [(? [, ?]...)]}  
    ```  
  
     Burada **ÇAĞRISI** bir ODBC anahtar sözcüğü **proc adı** veri kaynağında tanındığı sorgu adıdır ve "?" öğeleridir sağladığınız kayıt kümesine çalışma zamanında (varsa) parametre değerleri için yer tutucuları . Aşağıdaki örnek, bir parametre için bir yer tutucu hazırlar:  
  
    ```  
    CString mySQL = "{CALL Delinquent_Accts (?)}";  
    ```  
  
8.  Kayıt kümesi açar kodda, kayıt kümesinin parametre veri üyeleri ayarlayın ve ardından arama **açık** SQL dizesi geçirmesi üye işlevi **lpszSQL** parametresi. Veya bunun yerine, tarafından döndürülen dize Değiştir `GetDefaultSQL` sınıfınızda üye işlevi.  
  
 Aşağıdaki örnekler adlı önceden tanımlanmış bir sorguyu çağırmak için yordamı `Delinquent_Accts`, satış bölgesi numarası için bir parametre alır. Bu sorgu üç sütun döndürür: `Acct_No`, `L_Name`, `Phone`. Tüm sütunları Müşteriler tablosundan olur.  
  
 Aşağıdaki kayıt kümesi sorgunun döndürdüğü ve satış için bir parametre bölge numarası çalışma zamanında istenen sütunlar için alan veri üyeleri belirtir.  
  
```  
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
  
 Sihirbaz, dışında yazar gibi bu sınıf bildirimi olan `m_lDistParam` el ile eklenen üye. Diğer üyeleri burada gösterilmiyor.  
  
 Veri üyeleri için başlatmaları sonraki örnekte gösterildiği `CDelinquents` Oluşturucusu.  
  
```  
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
  
 Başlatmalarına Not [m_nFields](../../mfc/reference/crecordset-class.md#m_nfields) ve [m_nParams](../../mfc/reference/crecordset-class.md#m_nparams). Sihirbazı'nı başlatır `m_nFields`; başlatır `m_nParams`.  
  
 RFX işlevleri sonraki örnekte gösterildiği `CDelinquents::DoFieldExchange`:  
  
```  
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
  
 Döndürülen üç sütun için RFX çağrıları yapma yanı sıra, bu kod çalışma zamanında geçirdiğiniz parametre bağlama yönetir. Parametre anahtarlanır `Dist_No` (bölge numarası) sütun.  
  
 Sonraki örnek SQL dizesi ayarlama ve kayıt açmak için kullanmak gösterir.  
  
```  
// Construct a CDelinquents recordset object  
CDelinquents rsDel( NULL );  
CString strSQL = "{CALL Delinquent_Accts (?)}"  
// Specify a parameter value (obtained earlier from the user)  
rsDel.m_lDistParam = lDistrict;  
// Open the recordset and run the query  
if( rsDel.Open( CRecordset::snapshot, strSQL ) )  
    // Use the recordset ...  
```  
  
 Bu kod bir anlık görüntü oluşturur, daha önce kullanıcıdan alınan parametre geçirir ve önceden tanımlanmış sorgu çağırır. Sorgu çalıştırıldığında, belirtilen satış bölgesi kayıtlarını döndürür. Her kayıt sütunları hesap numarası, Müşteri'nin soyadı ve müşterinin telefon numarasını içerir.  
  
> [!TIP]
>  Saklı yordam gelen bir dönüş değeri (çıktı parametresi) işlemek isteyebilirsiniz. Daha fazla bilgi ve bir örnek için bkz: [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [Kayıt kümesi: kayıt kümesi (ODBC) yeniden sorgulama](../../data/odbc/recordset-requerying-a-recordset-odbc.md)   
 [Kayıt kümesi: bir sınıf bir tablo için bildirme (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)   
 [Kayıt Kümesi: Birleşim Gerçekleştirme (ODBC)](../../data/odbc/recordset-performing-a-join-odbc.md)