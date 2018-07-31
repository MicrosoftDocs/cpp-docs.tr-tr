---
title: 'Kayıt kümesi: Kayıtları toplu yakalama (ODBC) getirilirken | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: cdc9b7d4dc3447bdad1bd6906e3011ef33612496
ms.sourcegitcommit: 889a75be1232817150be1e0e8d4d7f48f5993af2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/30/2018
ms.locfileid: "39337410"
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>Kayıt Kümesi: Kayıtları Toplu Yakalama (ODBC)
Bu konu MFC ODBC sınıflarına uygulanır.  
  
 Sınıf `CRecordset` birden fazla kayıt aynı anda tek bir getirme yerine sırasında bir kayıt teker teker veri kaynağından getirilebileceği anlamına gelir toplu satır getirme için destek sağlar. Toplu satır getirme yalnızca türetilmiş içinde uygulayabilirsiniz `CRecordset` sınıfı. Kayıt kümesi nesnesi için veri kaynağından veri aktarma işleminin toplu kayıt alanı değişimi (Bulk RFX) adı verilir. İçinde toplu satır getirme kullanmıyorsanız unutmayın bir `CRecordset`-türetilmiş sınıf, verileri kayıt alanı değişimi (RFX) aktarılır. Daha fazla bilgi için [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
 Bu konu şunları açıklar:  
  
-   [Toplu satır getirme CRecordset nasıl desteklediğini](#_core_how_crecordset_supports_bulk_row_fetching).  
  
-   [Toplu satır getirme kullanırken bazı özel durumlar](#_core_special_considerations).  
  
-   [Toplu kayıt alanı değişimi uygulamak nasıl](#_core_how_to_implement_bulk_record_field_exchange).  
  
##  <a name="_core_how_crecordset_supports_bulk_row_fetching"></a> Toplu satır getirme CRecordset nasıl destekler  
 Kayıt kümesi nesnenizin açmadan önce bir satır kümesi boyutu ile tanımlayabilirsiniz `SetRowsetSize` üye işlevi. Satır kümesi boyutu, tek bir getirme sırasında kaç tane kaydın alınması gerektiğini belirtir. Toplu satır getirme uygulandığında, varsayılan satır boyutu 25'tir. Toplu satır getirme kullanılırsa, satır boyutu 1 sabit kalır.  
  
 Satır kümesi boyutunu ayarladıktan sonra çağrı [açık](../../mfc/reference/crecordset-class.md#open) üye işlevi. Burada belirtmelisiniz `CRecordset::useMultiRowFetch` seçeneği *dwOptions* toplu satır getirme uygulamak için parametre. Buna ek olarak ayarlayabilirsiniz `CRecordset::userAllocMultiRowBuffers` seçeneği. Toplu kayıt alanı değişimi mekanizması diziler birden çok satır getirme sırasında alınan veri depolamak için kullanır. Bu depolama arabellekleri framework tarafından otomatik olarak ayrılabilen veya el ile ayırın. Belirtme `CRecordset::userAllocMultiRowBuffers` seçenek ayırma yapacağınız anlamına gelir.  
  
 Aşağıdaki tabloda üye işlevleri tarafından sağlanan `CRecordset` toplu satır getirme desteklemek için.  
  
|Üye işlevi|Açıklama|  
|---------------------|-----------------|  
|[CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)|Yakalama sırasında oluşan hataları işleyecek sanal işlev.|  
|[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|Toplu kayıt alanı değişimi olarak uygular. Otomatik olarak kayıt kümesi nesnesi için veri kaynağından birden çok sayıda veri aktarımları için çağrılır.|  
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|Satır kümesi boyutu için geçerli ayarını alır.|  
|[GetRowsFetched](../../mfc/reference/crecordset-class.md#getrowsfetched)|Satır sayısı belirli bir getirmeden sonra gerçekten alındığını belirtir. Çoğu durumda, tamamlanmamış bir satır kümesi getirilmezse satır boyutu budur.|  
|[GetRowStatus](../../mfc/reference/crecordset-class.md#getrowstatus)|Bir satır kümesi içinde belirli bir satır getirme durumunun döndürür.|  
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|Bir satır kümesi içinde belirli bir satıra durumunu ve verileri yeniler.|  
|[SetRowsetCursorPosition](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|İşaretçiyi bir satır kümesi içinde belirli bir satıra taşır.|  
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|Satır kümesi boyutu için ayarı belirtilen değerle değiştiren sanal işlev.|  
  
##  <a name="_core_special_considerations"></a> Özel durumlar  
 Toplu satır getirme bir performans kazancı olsa da, bazı özellikler farklı çalışır. Toplu satır getirme uygulamak karar vermeden önce aşağıdakileri göz önünde bulundurun:  
  
-   Framework otomatik olarak çağıran `DoBulkFieldExchange` kayıt kümesi nesnesi için veri kaynağından veri aktarmak için üye işlevi. Ancak, veri, veri kaynağına kayıt kümesinden aktarılmaz. Çağırma `AddNew`, `Edit`, `Delete`, veya `Update` üye işlevleri başarısız onaylama sonuçlanır. Ancak `CRecordset` mekanizması sağlamaz toplu veri satırlarını güncelleştirmek için kendi işlevlerinizi ODBC API işlevini kullanarak yazabileceğiniz `SQLSetPos`. Hakkında daha fazla bilgi için `SQLSetPos`, bkz: *ODBC SDK Programcının Başvurusu* MSDN belgelerinde.  
  
-   Üye işlevleri `IsDeleted`, `IsFieldDirty`, `IsFieldNull`, `IsFieldNullable`, `SetFieldDirty`, ve `SetFieldNull` toplu satır getirme uygulayan kümelerinde kullanılamaz. Ancak, çağırabilirsiniz `GetRowStatus` yerine `IsDeleted`, ve `GetODBCFieldInfo` yerine `IsFieldNullable`.  
  
-   `Move` Operations kayıt kümesi tarafından yeniden konumlandırır. Örneğin, bir ilk satır boyutu 10 ile 100 kayıtları içeren bir kayıt açın varsayalım. `Open` 1. satırda yerleştirilmiş satır 1'den geçerli kayıtla 10 getirir. Bir çağrı `MoveNext` sonraki satırda satır kümesi getirir. Bu satır kümesi 11 satırda yerleştirilmiş satır 11 geçerli kayıt ile 20 arasında oluşur. Unutmayın `MoveNext` ve `Move( 1 )` toplu satır getirme uygulandığında eşdeğer değildir. `Move( 1 )` Geçerli kayıt öğesinden 1 satır başlayan satır kümesi getirir. Bu örnekte, çağırma `Move( 1 )` arama sonra `Open` satır 2 ila 11'de, 2. satırda geçerli kaydın ile oluşan satır kümesi getirir. Daha fazla bilgi için [taşıma](../../mfc/reference/crecordset-class.md#move) üye işlevi.  
  
-   Kayıt alanı değişimi, toplu kayıt alanı değişimi sihirbazları desteklemez. Yani el ile alan veri üyeleri bildirme ve el ile geçersiz kılma `DoBulkFieldExchange` yazarak Bulk RFX işlevleri çağırır. Daha fazla bilgi için [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md) içinde *sınıf kitaplığı başvurusu*.  
  
##  <a name="_core_how_to_implement_bulk_record_field_exchange"></a> Toplu kayıt alanı değişimi gerçekleştirme  
 Toplu kayıt alanı değişimi veri kümesi veri kaynağından recordset nesnesine aktarır. Toplu RFX işlevleri satır kümesinde, her veri öğesinin uzunluğunu depolamak için dizi yanı sıra, bu verileri depolamak için dizi kullanın. Sınıf tanımında, dizi verisi erişmeye gibi işaretçiler alan veri üyelerini tanımlamanız gerekir. Ayrıca, bir dizi uzunluktaki diziler erişmek için işaretçiler tanımlamanız gerekir. Tüm parametre veri üyeleri işaretçileri bildirilmemelidir; Toplu kayıt alanı değişimi kullanırken parametre veri üyeleri bildirme kayıt alanı değişimi kullanırken bildirme aynıdır. Aşağıdaki kod, basit bir örnek göstermektedir:  
  
```cpp  
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
  
 Bu depolama arabellekleri el ile ayırmak veya ayırmayı Framework'ün yüklü. Arabellekleri kendiniz ayırmak için belirtmeniz gerekir `CRecordset::userAllocMultiRowBuffers` seçeneği *dwOptions* parametresinde `Open` üye işlevi. Dizi boyutları en az satır kümesi boyutuna eşit ayarladığınızdan emin olun. Ayırmayı framework olmasını istiyorsanız, NULL işaretçileri başlatması gerekir. Bu, genellikle kayıt kümesi nesnesinin oluşturucuda gerçekleştirilir:  
  
```cpp  
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
  
 Son olarak, kılmalı `DoBulkFieldExchange` üye işlevi. Alan veri üyeleri'için Toplu RFX işlevlerini çağırın. tüm parametre veri üyeleri için RFX işlevlerini çağırın. Kayıt kümesi bir SQL deyimi veya saklı yordam için geçirerek açtıysanız `Open`, siparişin Bulk RFX aramalar yapma kayıt kümesi sütunları sırayla eşleşmelidir; RFX sırasını benzer şekilde, çağrı için parametreleri karşılık gelmelidir SQL deyimi veya saklı yordam parametreleri sıradadır.  
  
```cpp  
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
>  Çağırmalısınız `Close` üye işlevi türetilmiş önce `CRecordset` sınıfı kapsam dışına gider. Bu çerçeve tarafından ayrılan belleği serbest olduğunu sağlar. İyi bir her zaman açıkça çağırmak için programlama `Close`olup toplu satır getirme uyguladıysanız bakılmaksızın.  
  
 Kayıt alanı değişimi (RFX) hakkında daha fazla bilgi için bkz: [kayıt alanı değişimi: RFX Works nasıl](../../data/odbc/record-field-exchange-how-rfx-works.md). Parametreleri kullanma hakkında daha fazla bilgi için bkz. [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) ve [kayıt kümesi: bir kayıt kümesi (ODBC) kümesini parametreleştirme](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)   
 [CRecordset::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)

