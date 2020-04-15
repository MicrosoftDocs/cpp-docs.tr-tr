---
title: CfieldExchange Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CFieldExchange
- AFXDB/CFieldExchange
- AFXDB/CFieldExchange::IsFieldType
- AFXDB/CFieldExchange::SetFieldType
helpviewer_keywords:
- CFieldExchange [MFC], IsFieldType
- CFieldExchange [MFC], SetFieldType
ms.assetid: 24c5c0b3-06a6-430e-9b6f-005a2c65e29f
ms.openlocfilehash: d4b99a4992075072253d4f9b3182a926673bdfd0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373924"
---
# <a name="cfieldexchange-class"></a>CfieldExchange Sınıfı

Veritabanı sınıfları tarafından kullanılan kayıt alanı değişimi (RFX) ve toplu kayıt alanı değişimi (Toplu RFX) yordamlarını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CFieldExchange
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CfieldExchange::IsfieldType](#isfieldtype)|Geçerli işlem güncelleştirilen alan türü için uygunsa sıfırsız döndürür.|
|[CfieldExchange::SetfieldType](#setfieldtype)|Bir sonraki çağrıya kadar RFX işlevlerine yapılan tüm aşağıdaki çağrılar tarafından temsil edilen kayıt `SetFieldType`kümesi veri üyesinin türünü (sütun veya parametre) belirtir.|

## <a name="remarks"></a>Açıklamalar

`CFieldExchange`taban sınıfa sahip değildir.

Özel veri türleri için veri alışverişi yordamları yazıyorsanız veya toplu satır alma uygularken bu sınıfı kullanın; aksi takdirde, bu sınıfı doğrudan kullanmazsınız. RFX ve Bulk RFX, kayıt kümesi nesnenizin alan veri üyeleri ile veri kaynağındaki geçerli kaydın ilgili alanları arasında veri alışverişi yapmaktadır.

> [!NOTE]
> Açık Veritabanı Bağlantısı (ODBC) sınıfları yerine Veri Erişim Nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) sınıfını kullanın. Daha fazla bilgi için genel bakış makalesine [bakın: Veritabanı Programlama.](../../data/data-access-programming-mfc-atl.md)

Nesne, `CFieldExchange` kayıt alanı değişimi veya toplu kayıt alanı değişiminin gerçekleşmesi için gereken bağlam bilgilerini sağlar. `CFieldExchange`nesneler, parametreleri ve alan veri üyelerini bağlama ve geçerli kaydın alanlarında çeşitli bayraklar ayarlama dahil olmak üzere bir dizi işlemi destekler. RFX ve Bulk RFX **işlemleri, enum** **FieldType** tarafından tanımlanan türlerin kayıt `CFieldExchange`kümesi sınıfı veri üyeleri üzerinde gerçekleştirilir. Olası **FieldType** değerleri şunlardır:

- `CFieldExchange::outputColumn`alan veri üyeleri için.

- `CFieldExchange::inputParam`veya `CFieldExchange::param` giriş parametresi veri üyeleri için.

- `CFieldExchange::outputParam`çıkış parametre veri üyeleri için.

- `CFieldExchange::inoutParam`giriş/çıkış parametresi veri üyeleri için.

Sınıfın üye işlevlerinin ve veri üyelerinin çoğu kendi özel RFX yordamlarınızı yazmak için sağlanır. Sık sık `SetFieldType` kullanırsınız. Daha fazla bilgi için [Kayıt Alanı Değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md) ve [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)makalelerini incegörün. Toplu satır alma hakkında bilgi için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın. RFX ve Toplu RFX global işlevleri hakkında ayrıntılı bilgi için, bu başvurunun MFC Makroları ve Globaller [bölümündeki Kayıt Alanı Değişim Fonksiyonları](../../mfc/reference/record-field-exchange-functions.md) bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CFieldExchange`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdb.h

## <a name="cfieldexchangeisfieldtype"></a><a name="isfieldtype"></a>CfieldExchange::IsfieldType

Kendi RFX işlevinizi yazarsanız, geçerli işlemin belirli bir alan veya parametre veri üye türünde `IsFieldType` (a `CFieldExchange::outputColumn`, `CFieldExchange::inputParam` `CFieldExchange::param`, `CFieldExchange::outputParam`, `CFieldExchange::inoutParam`, , veya ) gerçekleştirilip gerçekleştirilemeyeceğini belirlemek için işlevinizin başında arama yapabilirsiniz.

```
BOOL IsFieldType(UINT* pnField);
```

### <a name="parameters"></a>Parametreler

*pnField*<br/>
Alan veya parametre veri üyesinin sıralı sayısı bu parametrede döndürülür. Bu sayı [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) işlevindeki veri üyesinin siparişine karşılık gelir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli çalışma geçerli alan veya parametre türünde gerçekleştirilebiliyorsa sıfırsız.

### <a name="remarks"></a>Açıklamalar

Varolan RFX işlevlerinin modelini izleyin.

## <a name="cfieldexchangesetfieldtype"></a><a name="setfieldtype"></a>CfieldExchange::SetfieldType

Kayıt ayarlı `SetFieldType` sınıfınızın [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) geçersiz kılma için bir çağrı gerekir.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Parametreler

*nFieldType*<br/>
Aşağıdakilerden biri `enum FieldType`olabilecek `CFieldExchange`, beyan edilen bir değer:

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>Açıklamalar

Alan veri üyeleri için, `SetFieldType` RFX veya `CFieldExchange::outputColumn`Toplu RFX işlevlerine yapılan çağrıları n için bir parametre ile aramanız gerekir. Toplu satır alma uygulamadıysanız, ClassWizard bu `SetFieldType` çağrıyı sizin için alan `DoFieldExchange`haritası bölümüne yerleştirir.

Kayıt kümesi sınıfınızı parametrenize ayarlarsanız, herhangi bir alan haritası bölümünün dışında yeniden aramanız `SetFieldType` ve ardından tüm parametre veri üyeleri için RFX çağrıları almanız gerekir. Parametre veri üyesinin her türü `SetFieldType` kendi araması olmalıdır. Aşağıdaki tablo, sınıfınızın parametre veri `SetFieldType` üyelerini temsil etmek için geçebileceğiniz farklı değerleri ayırt eder:

|SetFieldType parametre değeri|Parametre veri üyesinin türü|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|Giriş parametresi. Kayıt kümesinin sorgusuna veya depolanan yordamına geçirilen değer.|
|`CFieldExchange::param` | olarak `CFieldExchange::inputParam`aynıdır.|
|`CFieldExchange::outputParam`|Çıkış parametresi. Kayıt kümesinin depolanan yordamının iade değeri.|
|`CFieldExchange::inoutParam`|Giriş/çıkış parametresi. Kayıt kümesinin depolanan yordamına aktarılan ve döndürülen bir değer.|

Genel olarak, alan veri üyeleri veya parametre veri üyeleri ile ilişkili RFX işlev `SetFieldType`çağrıları her grup önce bir çağrı olmalıdır. Her `SetFieldType` çağrının `SetFieldType` *nFieldType* parametresi, çağrıyı izleyen RFX işlevi çağrıları tarafından temsil edilen veri üyelerinin türünü tanımlar.

Çıktı ve girdi/çıkış parametrelerini işleme hakkında `CRecordset` daha fazla bilgi için, üye işlev [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset)bakın. RFX ve Toplu RFX işlevleri hakkında daha fazla bilgi için, kayıt [alanı değişim fonksiyonları](../../mfc/reference/record-field-exchange-functions.md)konusuna bakın. Toplu satır alma yla ilgili ilgili ilgili bilgiler için [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md)makalesine bakın.

### <a name="example"></a>Örnek

Bu örnek, RFX işlevlerine eşlik eden `SetFieldType`çağrılar ile birkaç çağrı gösterir. İşaretçi aracılığıyla bir `CFieldExchange` nesneye çağrılan not. `SetFieldType` `pFX`

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
