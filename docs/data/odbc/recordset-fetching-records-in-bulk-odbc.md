---
title: 'Kayıt Kümesi: Kayıtları Toplu Yakalama (ODBC)'
ms.date: 11/04/2016
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
ms.openlocfilehash: ec4d83481f6335d4c40ffb8f004b617f2ee09c62
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367021"
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>Kayıt Kümesi: Kayıtları Toplu Yakalama (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Sınıf, `CRecordset` veri kaynağından bir defada bir kayıt almak yerine, tek bir alma sırasında birden çok kaydın aynı anda alınabileceği anlamına gelen toplu satır alma desteği sağlar. Yalnızca türemiş `CRecordset` bir sınıfta toplu satır alma uygulayabilirsiniz. Veri kaynağından kayıt kümesi nesnesine veri aktarma işlemine toplu kayıt alanı değişimi (Toplu RFX) denir. Türetilmiş bir `CRecordset`sınıfta toplu satır alma kullanmıyorsanız, verilerin kayıt alanı değişimi (RFX) yoluyla aktarıldığını unutmayın. Daha fazla bilgi için [Bkz. Alan Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

Bu konu açıklar:

- [CRecordset toplu satır getirmeyi nasıl destekler.](#_core_how_crecordset_supports_bulk_row_fetching)

- [Toplu satır alma kullanırken bazı özel hususlar](#_core_special_considerations).

- [Toplu kayıt alanı değişimi nasıl uygulanır.](#_core_how_to_implement_bulk_record_field_exchange)

## <a name="how-crecordset-supports-bulk-row-fetching"></a><a name="_core_how_crecordset_supports_bulk_row_fetching"></a>CRecordset Toplu Satır Alma'yı Nasıl Destekler?

Recordset nesnenizi açmadan `SetRowsetSize` önce, üye işlevle bir rowset boyutu tanımlayabilirsiniz. Satır kümesi boyutu, tek bir getirme sırasında kaç kaydın alınması gerektiğini belirtir. Toplu satır alma uygulandığında, varsayılan satır kümesi boyutu 25'tir. Toplu satır alma uygulanmazsa, satır kümesi boyutu 1 sabit kalır.

Satır kümesi boyutunu niçin açtıktan sonra [Aç](../../mfc/reference/crecordset-class.md#open) üye işlevini arayın. Burada toplu satır `CRecordset::useMultiRowFetch` alma uygulamak için *dwOptions* parametre seçeneğini belirtmeniz gerekir. Ayrıca `CRecordset::userAllocMultiRowBuffers` seçeneği ayarlayabilirsiniz. Toplu kayıt alanı değiştirme mekanizması, bir alma sırasında alınan birden çok veri satırını depolamak için dizileri kullanır. Bu depolama arabellekleri çerçeve tarafından otomatik olarak tahsis edilebilir veya bunları el ile ayırabilirsiniz. `CRecordset::userAllocMultiRowBuffers` Seçeneği belirtmek, tahsisatı yapacağınız anlamına gelir.

Aşağıdaki tabloda toplu satır `CRecordset` getirmeyi desteklemek için sağlanan üye işlevler listelemektedir.

|Üye fonksiyonu|Açıklama|
|---------------------|-----------------|
|[CheckRowsetHatası](../../mfc/reference/crecordset-class.md#checkrowseterror)|Alma sırasında oluşan hataları işleyen sanal işlev.|
|[Dobulkfieldexchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|Toplu kayıt alanı değişimini uygular. Veri kaynağından kayıt kümesi nesnesine birden çok veri satırı aktası vermek için otomatik olarak çağrılır.|
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|Satır kümesi boyutu için geçerli ayarı alır.|
|[GetRowsFetched](../../mfc/reference/crecordset-class.md#getrowsfetched)|Belirli bir getirdikten sonra gerçekte kaç satır alındığını söyler. Tamamlanmamış bir satır kümesi getirilmediği sürece, çoğu durumda bu satır kümesi boyutudur.|
|[GetRowStatus](../../mfc/reference/crecordset-class.md#getrowstatus)|Bir satır kümesi içinde belirli bir satır için bir getirme durumu döndürür.|
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|Bir satır kümesi içindeki belirli bir satırın verilerini ve durumunu yeniler.|
|[SetRowsetCursorPosition](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|İmleci bir satır kümesi içinde belirli bir satıra taşır.|
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|Rowset boyutunun ayarını belirtilen değere değiştiren sanal işlev.|

## <a name="special-considerations"></a><a name="_core_special_considerations"></a>Özel Hususlar

Toplu satır alma bir performans kazancı olsa da, bazı özellikler farklı çalışır. Toplu satır alma uygulamasına karar vermeden önce aşağıdakileri göz önünde bulundurun:

- Çerçeve, veri kaynağından kayıt kümesi nesnesine veri aktarmak için `DoBulkFieldExchange` üye işlevi otomatik olarak çağırır. Ancak, veriler kayıt kümesinden veri kaynağına aktarılmaz. `AddNew`", `Edit`" `Delete`veya `Update` üye işlevler çağrılması, başarısız bir iddiayla sonuçlanır. `CRecordset` Şu anda toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamasa da, ODBC `SQLSetPos`API işlevini kullanarak kendi işlevlerinizi yazabilirsiniz. Hakkında daha `SQLSetPos`fazla bilgi için MSDN belgelerinde *ODBC SDK Programcısı* Referansı'na bakın.

- `IsDeleted`Üye işlevler `IsFieldDirty` `IsFieldNull`, `IsFieldNullable` `SetFieldDirty`, `SetFieldNull` , , , , ve toplu satır alma uygulayan kayıt kümelerinde kullanılamaz. Ancak, yerine `GetRowStatus` arayabilirsiniz `IsDeleted`, `GetODBCFieldInfo` ve yerine `IsFieldNullable`.

- İşlemler `Move` kayıt setinizi rowset'e göre yeniden konumlandırın. Örneğin, ilk satır kümesi boyutu 10 olan 100 kaydı olan bir kayıt kümesini açtığınızı varsayalım. `Open`satır 1'den 10'a kadar getirir ve geçerli kayıt satır 1'de konumlandırılır. Bir sonraki `MoveNext` satır kümesini getirme çağrısı, bir sonraki satırı değil. Bu satır kümesi 11 ile 20 arasında satırlardan oluşur ve geçerli kayıt 11 satırda konumlandırılır. Toplu `MoveNext` satır `Move( 1 )` alma uygulandığında eşdeğer olmadığını unutmayın. `Move( 1 )`geçerli kayıttan 1 satır başlar satır kümesini getirir. Bu örnekte, `Move( 1 )` aramadan sonra arama, `Open` 2 ile 11 arasında satırlardan oluşan satır kümesini getirir ve geçerli kayıt 2 satırına konumlandırılır. Daha fazla bilgi için [Taşı](../../mfc/reference/crecordset-class.md#move) üye işlevine bakın.

- Kayıt alanı değişiminin aksine, sihirbazlar toplu kayıt alanı değişimini desteklemez. Bu, Toplu RFX işlevlerine çağrı yazarak alan `DoBulkFieldExchange` veri üyelerinizi el ile bildirmeniz ve el ile geçersiz kılmanız gerektiği anlamına gelir. Daha fazla bilgi için *Sınıf Kitaplığı Başvurusu'ndaki* [Alan Değiştirme Fonksiyonlarını Kaydet'e](../../mfc/reference/record-field-exchange-functions.md) bakın.

## <a name="how-to-implement-bulk-record-field-exchange"></a><a name="_core_how_to_implement_bulk_record_field_exchange"></a>Toplu Kayıt Alanı Değişimi Nasıl Uygulanır?

Toplu kayıt alanı değişimi, veri kaynağından kayıt kümesi nesnesine bir veri satırı kümesi aktarRZ. Toplu RFX işlevleri, bu verileri depolamak için dizilerin yanı sıra her veri öğesinin uzunluğunu satır kümesinde depolamak için diziler kullanır. Sınıf tanımınızda, veri dizilerine erişmek için alan veri üyelerinizi işaretçi olarak tanımlamanız gerekir. Buna ek olarak, uzunluk dizilerine erişmek için bir işaretçi kümesi tanımlamanız gerekir. Herhangi bir parametre veri üyeleri işaretçi olarak ilan edilmemelidir; toplu kayıt alanı değişimini kullanırken parametre veri üyelerini bildirmek, kayıt alanı değişimini kullanırken bildirmekle aynıdır. Aşağıdaki kod basit bir örnek gösterir:

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

Bu depolama arabelleklerini el ile tahsis edebilir veya ayırmayı çerçeveye ayırabilirsiniz. Arabellekleri kendiniz ayırmak `CRecordset::userAllocMultiRowBuffers` `Open` için, üye işlevdeki *dwOptions* parametre seçeneğini belirtmeniz gerekir. Dizilerin boyutlarını en azından satır kümesi boyutuna eşit olarak ayarladıklarından emin olun. Ayırmayı çerçevenin yapmasını istiyorsanız, işaretçilerinizi NULL'a başlatmanız gerekir. Bu genellikle kaydedici nesnenin oluşturucusunda yapılır:

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

Son olarak, `DoBulkFieldExchange` üye işlevi geçersiz kılmanız gerekir. Alan veri üyeleri için Toplu RFX işlevlerini arayın; herhangi bir parametre veri üyesi için RFX işlevlerini arayın. Bir SQL deyimi ni veya depolanmış yordamı `Open`geçirerek kayıt kümesini açtıysanız, Toplu RFX aramalarını yaptığınız sıra, kayıt kümesindeki sütunların sırasına karşılık gelmelidir; benzer şekilde, RFX parametreleri için çağrı sırası SQL deyimi veya depolanan yordamdaki parametrelerin sırasına karşılık olmalıdır.

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
> Türemiş `CRecordset` `Close` sınıfınız kapsam dışına çıkmadan önce üye işlevi aramalısınız. Bu, çerçeve tarafından ayrılan herhangi bir belleğin serbest kalmasını sağlar. Toplu satır alma uygulamanız olup `Close`olmadığına bakılmaksızın, her zaman açıkça aramak iyi bir programlama uygulamasıdır.

Kayıt alanı değişimi (RFX) hakkında daha fazla bilgi için [bkz.](../../data/odbc/record-field-exchange-how-rfx-works.md) Parametreleri kullanma hakkında daha fazla bilgi için [CFieldExchange::SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) ve [Recordset: Parameterizing bir Recordset (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset::m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)<br/>
[CRecordset::m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)
