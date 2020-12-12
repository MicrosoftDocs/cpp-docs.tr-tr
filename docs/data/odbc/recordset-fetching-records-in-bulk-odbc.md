---
description: 'Şu konuda daha fazla bilgi edinin: kayıt kümesi: kayıtları toplu yakalama (ODBC)'
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
ms.openlocfilehash: 6f77186a640971e6763160dde397f5aeb0b97f3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322357"
---
# <a name="recordset-fetching-records-in-bulk-odbc"></a>Kayıt Kümesi: Kayıtları Toplu Yakalama (ODBC)

Bu konu MFC ODBC sınıfları için geçerlidir.

Sınıfı, `CRecordset` toplu satır getirme için destek sağlar. Bu, birden çok kaydın tek bir getirme sırasında, veri kaynağından tek bir kayıt almak yerine bir kez alınalabileceği anlamına gelir. Yalnızca türetilmiş bir sınıfta toplu satır getirme uygulayabilirsiniz `CRecordset` . Veri kaynağından kayıt kümesi nesnesine veri aktarma işlemi toplu kayıt alanı değişimi (toplu RFX) olarak adlandırılır. Türetilmiş bir sınıfta toplu satır getirmeyi kullanmıyorsanız `CRecordset` , verilerin kayıt alanı değişimi (RFX) aracılığıyla aktarılacağını unutmayın. Daha fazla bilgi için bkz. [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md).

Bu konuda aşağıdakiler açıklanmaktadır:

- [CRecordset toplu satır getirmeyi nasıl destekler](#_core_how_crecordset_supports_bulk_row_fetching).

- [Toplu satır getirme kullanırken bazı özel önemli noktalar](#_core_special_considerations).

- [Toplu kayıt alanı değişimini uygulama](#_core_how_to_implement_bulk_record_field_exchange).

## <a name="how-crecordset-supports-bulk-row-fetching"></a><a name="_core_how_crecordset_supports_bulk_row_fetching"></a> CRecordset toplu satır getirmeyi nasıl destekler

Kayıt kümesi nesneniz açılmadan önce, üye işlevi ile bir satır kümesi boyutu tanımlayabilirsiniz `SetRowsetSize` . Satır kümesi boyutu, tek bir getirme sırasında kaç kaydın alınması gerektiğini belirtir. Toplu satır getirme uygulandığında, varsayılan satır kümesi boyutu 25 ' tir. Toplu satır getirme uygulanmadığı takdirde satır kümesi boyutu 1 ' de sabit kalır.

Satır kümesi boyutunu başlattıktan sonra, [Açık](../../mfc/reference/crecordset-class.md#open) üye işlevini çağırın. Burada, `CRecordset::useMultiRowFetch` toplu satır getirmeyi uygulamak Için *dwOptions* parametresinin seçeneğini belirtmeniz gerekir. Ayrıca, seçeneğini de ayarlayabilirsiniz `CRecordset::userAllocMultiRowBuffers` . Toplu kayıt alanı değişim mekanizması, bir getirme sırasında alınan verilerin birden çok satırını depolamak için dizileri kullanır. Bu depolama arabellekleri çerçeve tarafından otomatik olarak ayrılabilir veya bunları el ile ayırabilirsiniz. Seçeneğinin belirtilmesi `CRecordset::userAllocMultiRowBuffers` , ayırmayı yapacaksınız anlamına gelir.

Aşağıdaki tabloda, `CRecordset` toplu satır getirmeyi desteklemek için tarafından sunulan üye işlevleri listelenmektedir.

|Üye işlevi|Açıklama|
|---------------------|-----------------|
|[CheckRowsetError](../../mfc/reference/crecordset-class.md#checkrowseterror)|Getirme sırasında oluşan tüm hataları işleyen sanal işlev.|
|[DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange)|Toplu kayıt alanı değişimini uygular. Veri kaynağından birden fazla veri satırını kayıt kümesi nesnesine aktarmak için otomatik olarak çağırılır.|
|[GetRowsetSize](../../mfc/reference/crecordset-class.md#getrowsetsize)|Satır kümesi boyutu için geçerli ayarı alır.|
|[Getrowsgetirilen](../../mfc/reference/crecordset-class.md#getrowsfetched)|Belirli bir getirme işleminden sonra kaç satır gerçekten alındığını söyler. Çoğu durumda, tamamlanmamış bir satır kümesi getirilmediği takdirde bu satır kümesi boyutudur.|
|[GetRowStatus](../../mfc/reference/crecordset-class.md#getrowstatus)|Satır kümesi içindeki belirli bir satır için getirme durumunu döndürür.|
|[RefreshRowset](../../mfc/reference/crecordset-class.md#refreshrowset)|Satır kümesi içindeki belirli bir satırın verilerini ve durumunu yeniler.|
|[SetRowsetCursorPosition](../../mfc/reference/crecordset-class.md#setrowsetcursorposition)|İmleci bir satır kümesi içindeki belirli bir satıra taşımıştır.|
|[SetRowsetSize](../../mfc/reference/crecordset-class.md#setrowsetsize)|Satır kümesi boyutu için ayarı belirtilen değere değiştiren sanal işlev.|

## <a name="special-considerations"></a><a name="_core_special_considerations"></a> Özel Konular

Toplu satır getirme bir performans kazanımı olsa da, bazı özellikler farklı şekilde çalışır. Toplu satır getirmeyi uygulamaya karar vermeden önce aşağıdakileri göz önünde bulundurun:

- Çerçeve, veri kaynağından veri `DoBulkFieldExchange` kümesi nesnesine veri aktarmak için üye işlevini otomatik olarak çağırır. Ancak, veriler kayıt kümesinden veri kaynağına geri aktarılmaz. ,, `AddNew` `Edit` `Delete` Veya `Update` üye işlevlerinin çağrılması başarısız bir onaylama ile sonuçlanır. `CRecordset`Şu anda toplu veri satırlarını güncelleştirmek için bir mekanizma sağlamasa da, ODBC API işlevini kullanarak kendi işlevlerinizi yazabilirsiniz `SQLSetPos` . Hakkında daha fazla bilgi için `SQLSetPos` bkz. [ODBC Programcı başvurusu](/sql/odbc/reference/odbc-programmer-s-reference).

- ,,, `IsDeleted` , `IsFieldDirty` `IsFieldNull` `IsFieldNullable` `SetFieldDirty` , Ve işlevleri `SetFieldNull` toplu satır getirmeyi uygulayan kayıt kümelerinde kullanılamaz. Ancak, yerine ve yerinde çağırabilirsiniz `GetRowStatus` `IsDeleted` `GetODBCFieldInfo` `IsFieldNullable` .

- `Move`İşlemler, kayıt kümesini satır kümesine göre konumlandırır. Örneğin, ilk satır kümesi boyutu 10 olan 100 kayda sahip bir kayıt kümesi açtığınızı varsayın. `Open` 1 ' den 10 ' a kadar satırları getirir ve geçerli kayıt 1. satırda konumlandırılır. Sonraki `MoveNext` satırı değil, sonraki satır kümesini getiren bir çağrı. Bu satır kümesi 11 ' den 20 ' ye kadar olan satırlar 11 ' de konumlandırılmış olan satırları içerir. `MoveNext` `Move( 1 )` Toplu satır getirme uygulandığında eşdeğer değildir. `Move( 1 )` geçerli kayıttan 1 satır Başlatan satır kümesini getirir. Bu örnekte, çağırma `Move( 1 )` sonrasında çağırmak `Open` , geçerli kayıt satır 2 ' de konumlandığı sırada 2 ' den 11 ' den 11 ' den fazla satır kümesi getirir. Daha fazla bilgi için üye [Taşı](../../mfc/reference/crecordset-class.md#move) işlevine bakın.

- Kayıt alanı değişimi 'nin aksine, sihirbazlar toplu kayıt alanı değişimini desteklemez. Diğer bir deyişle `DoBulkFieldExchange` , toplu RFX işlevlerine çağrılar yazarak alan veri üyelerinizi el ile bildirmeniz ve el ile geçersiz kılmanız gerekir. Daha fazla bilgi için bkz. *sınıf kitaplığı başvurusunda* [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md) .

## <a name="how-to-implement-bulk-record-field-exchange"></a><a name="_core_how_to_implement_bulk_record_field_exchange"></a> Toplu kayıt alanı değişimini uygulama

Toplu kayıt alanı değişimi, veri kaynağındaki veri kümesini kayıt kümesi nesnesine aktarır. Toplu RFX işlevleri bu verilerin depolanması için dizileri, ayrıca satır kümesindeki her bir veri öğesinin uzunluğunu depolamak için dizileri kullanır. Sınıf tanımınızda, veri dizilerine erişmek için alan veri üyelerinizi işaretçiler olarak tanımlamanız gerekir. Ayrıca, uzunluklardan oluşan dizilere erişmek için bir işaretçiler kümesi tanımlamanız gerekir. Tüm parametre veri üyeleri işaretçiler olarak bildirilmelidir; Toplu kayıt alanı değişimi kullanılırken parametre veri üyelerini bildirmek, kayıt alanı değişimi kullanılırken bunları bildirme ile aynıdır. Aşağıdaki kod basit bir örnek göstermektedir:

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

Bu depolama arabelleklerini el ile ayırabilir veya çerçeveyi ayırmayı sağlayabilirsiniz. Arabellekleri kendiniz ayırmak için, `CRecordset::userAllocMultiRowBuffers` üye Işlevindeki *dwOptions* parametresinin seçeneğini belirtmeniz gerekir `Open` . Dizilerin boyutlarını en az satır kümesi boyutuna eşit olarak ayarladığınızdan emin olun. Çerçevenin ayırmayı yapmak istiyorsanız, işaretçilerinizi NULL olarak başlatmalısınız. Bu genellikle kayıt kümesi nesnesinin oluşturucusunda yapılır:

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

Son olarak, üye işlevini geçersiz kılmanız gerekir `DoBulkFieldExchange` . Alan veri üyeleri için toplu RFX işlevlerini çağırın; herhangi bir parametre veri üyesi için RFX işlevlerini çağırın. ' A bir SQL ifadesini veya saklı yordamı geçirerek kayıt kümesini açtıysanız `Open` , toplu RFX çağrılarını yaptığınız sıra, kayıt kümesindeki sütunların sırasına karşılık gelmelidir; benzer şekilde, PARAMETRELERIN RFX çağrılarının sırası, SQL deyimindeki veya saklı yordamdaki parametre sırasına karşılık gelmelidir.

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
> `Close`Türetilmiş sınıfınız kapsam dışına geçmeden önce üye işlevini çağırmanız gerekir `CRecordset` . Bu, çerçeve tarafından ayrılan tüm belleğin serbest olmasını sağlar. `Close`Toplu satır getirme uygulanıp uygulanmadığı bağımsız olarak her zaman açıkça çağrı yapmak için iyi bir programlama uygulamasıdır.

Kayıt alanı değişimi (RFX) hakkında daha fazla bilgi için bkz. [kayıt alanı değişimi: RFX 'In nasıl çalıştığı](../../data/odbc/record-field-exchange-how-rfx-works.md). Parametreleri kullanma hakkında daha fazla bilgi için bkz. [CFieldExchange:: SETTI](../../mfc/reference/cfieldexchange-class.md#setfieldtype) ve [kayıt kümesi: bir kayıt kümesini PARAMETRIZE (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Kümesi (ODBC)](../../data/odbc/recordset-odbc.md)<br/>
[CRecordset:: m_nFields](../../mfc/reference/crecordset-class.md#m_nfields)<br/>
[CRecordset:: m_nParams](../../mfc/reference/crecordset-class.md#m_nparams)
