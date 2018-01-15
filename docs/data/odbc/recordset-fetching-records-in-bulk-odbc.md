---
title: "Kayıt kümesi: Kayıtları toplu (ODBC) yakalama | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- bulk row fetching, implementing
- ODBC recordsets, bulk row fetching
- bulk record field exchange
- bulk row fetching
- bulk RFX functions
- recordsets, bulk row fetching
- DoBulkFieldExchange method
- fetching ODBC records in bulk
- RFX (ODBC), bulk
- rowsets, bulk row fetching
- RFX (ODBC), bulk row fetching
ms.assetid: 20d10fe9-c58a-414a-b675-cdf9aa283e4f
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8d9738af557cb8d4dd26b792851f8be276e91380
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>Kayıt Kümesi: Kayıtları Toplu Yakalama (ODBC)
Bu konu MFC ODBC sınıfları için geçerlidir.  
  
 Sınıf `CRecordset` birden fazla kayıt aynı anda tek bir getirme yerine sırasında bir kayıt aynı anda veri kaynağı'ndan alınabilir, yani toplu satır getirme için destek sağlar. Toplu satır getirme yalnızca türetilmiş içinde uygulayabilirsiniz `CRecordset` sınıfı. Kayıt kümesi nesnesi için veri kaynağından veri aktarma işlemi toplu kayıt alanı değişimi (Toplu RFX) adı verilir. İçindeki toplu satır getirme kullanmıyorsanız unutmayın bir `CRecordset`-türetilmiş bir sınıf, veri kayıt alanı değişimi (RFX) aktarılır. Daha fazla bilgi için bkz: [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
 Bu konuda açıklanmaktadır:  
  
-   [Toplu satır getirme CRecordset nasıl desteklediği](#_core_how_crecordset_supports_bulk_row_fetching).  
  
-   [Toplu satır getirme kullanırken bazı özel durumlar](#_core_special_considerations).  
  
-   [Toplu kayıt alanı değişimi uygulamak nasıl](#_core_how_to_implement_bulk_record_field_exchange).  
  
##  <a name="_core_how_crecordset_supports_bulk_row_fetching"></a>Toplu satır getirme CRecordset nasıl destekler  
 Kayıt kümesi nesnenizi açmadan önce bir satır kümesi boyutu ile tanımlayabilirsiniz `SetRowsetSize` üye işlevi. Satır kümesi boyutu, tek bir getirme sırasında kaç kayıt alınması gerektiğini belirtir. Toplu satır getirme uygulandığında varsayılan satır kümesi boyutu 25'tir. Toplu satır getirme uygulanmadıysa, satır kümesi boyutu 1 sabit kalır.  
  
 Satır kümesi boyutunu ayarladıktan sonra arama [açık](../../mfc/reference/crecordset-class.md#open) üye işlevi. Burada, belirtmeniz gerekir `CRecordset::useMultiRowFetch` seçeneği **dwOptions** toplu satır getirme uygulamak için parametre. Ayrıca ayarlayabilirsiniz **CRecordset::userAllocMultiRowBuffers** seçeneği. Toplu kayıt alanı değişimi mekanizması diziler getirme sırasında alınan verilerin birden çok satır depolamak için kullanır. Bu depolama arabellekleri çerçevesi tarafından otomatik olarak ayrılabilen veya el ile ayırın. Belirtme **CRecordset::userAllocMultiRowBuffers** seçeneği ayırma ne yapacağını anlamına gelir.  
  
 Aşağıdaki tabloda tarafından sağlanan üye işlevlerini listeler `CRecordset` toplu satır getirme desteklemek için.  
  
|Üye işlevi|Açıklama|  
|---------------------|-----------------|  
|[CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)|Getirme sırasında oluşan hataları işleme sanal işlev.|  
|[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|Toplu kayıt alanı değişimi olarak uygular. Otomatik olarak kayıt kümesi nesnesi için veri kaynağından birden çok sayıda veri aktarımları için çağrılır.|  
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|Satır kümesi boyutu için geçerli ayarları alır.|  
|[GetRowsFetched](../../mfc/reference/crecordset-class.md#getrowsfetched)|Satır sayısını gerçekte belirli bir getirmeden sonra alındığını belirtir. Çoğu durumda, tamamlanmamış bir satır kümesi getirilmezse satır kümesi boyutu budur.|  
|[GetRowStatus](../../mfc/reference/crecordset-class.md#getrowstatus)|Bir satır kümesi içinde belirli bir satır için getirme durumu döndürür.|  
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|Bir satır kümesi içinde belirli bir satır durumunu ve verileri yeniler.|  
|[SetRowsetCursorPosition](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|İmleç bir satır kümesi içinde belirli bir satır taşır.|  
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|Satır kümesi boyutu ayarı için belirtilen değer değişiklikleri sanal işlev.|  
  
##  <a name="_core_special_considerations"></a>Özel durumlar  
 Toplu satır getirme bir performans kazancı olsa da, bazı özellikler farklı çalışır. Toplu satır getirme uygulamaya karar vermeden önce aşağıdakileri göz önünde bulundurun:  
  
-   Framework otomatik olarak çağırır `DoBulkFieldExchange` kayıt kümesi nesnesi için veri kaynağından veri aktarmak için üye işlevi. Ancak, veri kayıt kümesinden veri kaynağına geri aktarılmaz. Çağırma `AddNew`, **Düzenle**, **silmek**, veya **güncelleştirme** üye işlevleri başarısız onaylama sonuçlanır. Ancak `CRecordset` şu anda bir mekanizma sağlamaz toplu veri satırlarını güncelleştirmek için kendi işlevleri ODBC API işlevini kullanarak yazabilirsiniz **SQLSetPos**. Hakkında daha fazla bilgi için **SQLSetPos**, bkz: *ODBC SDK Programcının Başvurusu* MSDN belgelerinde.  
  
-   Üye işlevleri `IsDeleted`, `IsFieldDirty`, `IsFieldNull`, `IsFieldNullable`, `SetFieldDirty`, ve `SetFieldNull` toplu satır getirme uygulayan kayıt kümelerinde kullanılamaz. Ancak, çağırabilirsiniz `GetRowStatus` yerine `IsDeleted`, ve `GetODBCFieldInfo` yerine `IsFieldNullable`.  
  
-   **Taşıma** işlemleri satır kümesi tarafından kayıt kümenizi yeniden konumlandırır. Örneğin, bir ilk satır kümesi boyutu 10 ile 100 kayıtları içeren bir kayıt kümesi açtığınızı varsayın. **Açık** geçerli kaydın satır 1 ile 1 ile 10 arasında satırları getirir. Çağrı `MoveNext` sonraki satıra satır kümesi getirir. Bu satır kümesi 11 satırındaki konumlandırılmış satır 11-20, geçerli kayıt ile oluşur. Unutmayın `MoveNext` ve **Taşı (1)** toplu satır getirme uygulandığında eşdeğer değildir. **Taşı (1)** geçerli kayıt 1 satırdan başlayan satır kümesi getirir. Bu örnekte, çağırma **Taşı (1)** çağırdıktan sonra **açık** satır 2'den 11, satır 2 konumlandırılmış geçerli kayıtla oluşan satır kümesi getirir. Daha fazla bilgi için bkz: [taşıma](../../mfc/reference/crecordset-class.md#move) üye işlevi.  
  
-   Kayıt alanı değişimi sihirbazlar toplu kayıt alanı değişimi desteklemez. Bunun anlamı, el ile alan veri üyeleri bildirme ve el ile geçersiz kılma `DoBulkFieldExchange` toplu RFX işlevleri çağrıları yazarak. Daha fazla bilgi için bkz: [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md) içinde *sınıf kitaplığı başvurusu*.  
  
##  <a name="_core_how_to_implement_bulk_record_field_exchange"></a>Toplu kayıt alanı değişimi nasıl uygulanır  
 Toplu kayıt alanı değişimi veri kümesi veri kaynağından kayıt kümesi nesnesine aktarır. Toplu RFX işlevleri uzunluğu her bir veri öğesi, satır kümesinde depolamak için diziler yanı sıra, bu verileri depolamak için diziler kullanın. Sınıf tanımınız içinde veri dizilerine erişmek için işaretçiler alan veri üyeleri tanımlamanız gerekir. Ayrıca, dizilerin uzunluklarına erişmek için işaretçiler kümesi tanımlamanız gerekir. Hiçbir parametre veri üyeleri işaretçilerini bildirilmemelidir; Toplu kayıt alanı değişimi kullanırken parametre veri üyeleri bildirme kayıt alanı değişimi kullanırken bildirme aynıdır. Aşağıdaki kod basit bir örnek gösterilmektedir:  
  
```  
class MultiRowSet : public CRecordset  
{  
public:  
   // Field/Param Data  
      // field data members  
      long* m_rgID;  
      LPSTR m_rgName;  
  
      // pointers for the lengths  
      // of the field data  
      long* m_rgIDLengths;  
      long* m_rgNameLengths;  
  
      // input parameter data member  
      CString m_strNameParam;  
  
   .  
   .  
   .  
}  
```  
  
 Bu depolama arabellekleri elle ayırın veya ayırma işlemini Framework'ün yüklü. Arabellekleri kendiniz ayırmak için belirtmelisiniz **CRecordset::userAllocMultiRowBuffers** seçeneği **dwOptions** parametresinde **açık** üye işlevi. Dizi boyutları en az satır kümesi boyutuna eşit ayarladığınızdan emin olun. Ayırma işlemini framework sahip olmak istiyorsanız, işaretçiler başlatmalıdır **NULL.** Bu, genellikle kayıt kümesi nesnesinin oluşturucuda gerçekleştirilir:  
  
```  
MultiRowSet::MultiRowSet( CDatabase* pDB )  
   : CRecordset( pDB )  
{  
   m_rgID = NULL;  
   m_rgName = NULL;  
   m_rgIDLengths = NULL;  
   m_rgNameLengths = NULL;  
   m_strNameParam = "";  
  
   m_nFields = 2;  
   m_nParams = 1;  
  
   .  
   .  
   .  
}  
```  
  
 Son olarak, kılmalıdır `DoBulkFieldExchange` üye işlevi. Alan veri üyeleri için Toplu RFX işlevlerini; Hiçbir parametre veri üyeleri için RFX işlevlerini çağırın. Kayıt kümesi bir SQL deyimi veya saklı yordam geçirerek açtığınız varsa **açık**, sipariş toplu RFX çağrılarının Oluştur kümesindeki sütunların {eşleşmelidir; benzer şekilde, RFX sırasını çağrısı Parametreler SQL deyimindeki parametreleri {karşılık gelmelidir veya saklı yordam.  
  
```  
void MultiRowSet::DoBulkFieldExchange( CFieldExchange* pFX )  
{  
   // call the Bulk RFX functions  
   // for field data members  
   pFX->SetFieldType( CFieldExchange::outputColumn );  
   RFX_Long_Bulk( pFX, _T( "[colRecID]" ),  
                  &m_rgID, &m_rgIDLengths );  
   RFX_Text_Bulk( pFX, _T( "[colName]" ),  
                  &m_rgName, &m_rgNameLengths, 30 );  
  
   // call the RFX functions for  
   // for parameter data members  
   pFX->SetFieldType( CFieldExchange::inputParam );  
   RFX_Text( pFX, "NameParam", m_strNameParam );  
}  
```  
  
> [!NOTE]
>  Çağırmalısınız **Kapat** üye işlevi türetilmiş önce `CRecordset` sınıfınız kapsam dışındadır. Bu çerçeve tarafından ayrılan bellek serbest sağlar. Her zaman açıkça çağırmak için uygulama programlama iyi **Kapat**ne olursa olsun, olup toplu satır getirme uyguladık.  
  
 Kayıt alanı değişimi (RFX) hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX nasıl çalışır](../../data/odbc/record-field-exchange-how-rfx-works.md). Parametreleri kullanma hakkında daha fazla bilgi için bkz: [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) ve [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)   
 [CRecordset::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)

