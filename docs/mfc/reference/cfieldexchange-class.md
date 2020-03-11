---
title: CFieldExchange sınıfı
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
ms.openlocfilehash: e66b3ed16d4f21d46567c37bfaf7929d32f63b8e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78866278"
---
# <a name="cfieldexchange-class"></a>CFieldExchange sınıfı

Veritabanı sınıfları tarafından kullanılan kayıt alanı değişimi (RFX) ve toplu kayıt alanı değişimi (toplu RFX) yordamlarını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CFieldExchange
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CFieldExchange:: Isıbu](#isfieldtype)|Güncel işlem güncelleştirilmekte olan alanın türü için uygun ise sıfır olmayan bir değer döndürür.|
|[CFieldExchange:: SETbir](#setfieldtype)|`SetFieldType`bir sonraki çağrıya kadar RFX işlevlerine yapılan tüm çağrılar tarafından temsil edilen kayıt kümesi veri üyesi (sütun veya parametre) türünü belirtir.|

## <a name="remarks"></a>Açıklamalar

`CFieldExchange` temel bir sınıfa sahip değil.

Özel veri türleri için veri değişim yordamları yazıyorsanız veya toplu satır getirme uyguladığınızda bu sınıfı kullanın; Aksi takdirde, bu sınıfı doğrudan kullanamazsınız. RFX ve toplu RFX, kayıt kümesi nesnenizin alan veri üyeleri ile veri kaynağındaki geçerli kaydın karşılık gelen alanları arasındaki verileri değiş tokuş eder.

> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine [Cdadofieldexchange](../../mfc/reference/cdaofieldexchange-class.md) sınıfını kullanın. Daha fazla bilgi için bkz. [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

`CFieldExchange` nesnesi, kayıt alanı değişimi veya toplu kayıt alanı değişimi için gereken bağlam bilgilerini sağlar. `CFieldExchange` nesneler, bağlama parametreleri ve alan veri üyeleri dahil olmak üzere bir dizi işlemi destekler ve geçerli kaydın alanlarında çeşitli bayraklar ayarlar. RFX ve toplu RFX işlemleri, `CFieldExchange`**numaralandırması** tarafından tanımlanan türlerin kayıt kümesi sınıfı veri üyelerinde gerçekleştirilir. Olası **bir** bu değer şunlardır:

- alan veri üyeleri için `CFieldExchange::outputColumn`.

- giriş parametresi veri üyeleri için `CFieldExchange::inputParam` veya `CFieldExchange::param`.

- çıkış parametresi veri üyeleri için `CFieldExchange::outputParam`.

- giriş/çıkış parametresi veri üyeleri için `CFieldExchange::inoutParam`.

Sınıfın üye işlevlerinin ve veri üyelerinin çoğu kendi özel RFX yordamlarınızı yazmak için sağlanır. `SetFieldType` sık olarak kullanacaksınız. Daha fazla bilgi için, bkz. [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md) ve [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). RFX ve toplu RFX genel işlevleri hakkında daha fazla bilgi için, bu başvurunun MFC makroları ve genel bölümündeki [kayıt alanı değişimi işlevleri](../../mfc/reference/record-field-exchange-functions.md) bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CFieldExchange`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

##  <a name="isfieldtype"></a>CFieldExchange:: Isıbu

Kendi RFX işlevinizi yazarsanız, geçerli işlemin belirli bir alan veya parametre veri üye türü (`CFieldExchange::outputColumn`, `CFieldExchange::inputParam`, `CFieldExchange::param`, `CFieldExchange::outputParam`veya `CFieldExchange::inoutParam`) üzerinde gerçekleştirilip gerçekleştirilebileceğini öğrenmek için işlevinizin başlangıcında `IsFieldType` çağırın.

```
BOOL IsFieldType(UINT* pnField);
```

### <a name="parameters"></a>Parametreler

*pnField*<br/>
Bu parametrede alanın veya parametre veri üyesinin ardışık numarası döndürülür. Bu sayı, [CRecordset::D oFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [CRecordset::D obulkfieldexchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) işlevindeki veri üyesinin sırasına karşılık gelir.

### <a name="return-value"></a>Dönüş Değeri

Geçerli işlem geçerli alan veya parametre türü üzerinde gerçekleştirilebileceği sıfır dışı.

### <a name="remarks"></a>Açıklamalar

Mevcut RFX işlevlerinin modelini izleyin.

##  <a name="setfieldtype"></a>CFieldExchange:: SETbir

Kayıt kümesi sınıfınızın [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) geçersiz kılma `SetFieldType` çağrısı yapmanız gerekir.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Parametreler

*N,*<br/>
`CFieldExchange`olarak belirtilen `enum FieldType`değeri, aşağıdakilerden biri olabilir:

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>Açıklamalar

Alan veri üyeleri için, `SetFieldType` bir `CFieldExchange::outputColumn`parametresiyle ve sonra RFX veya toplu RFX işlevlerine yapılan çağrılar ile çağrı yapmanız gerekir. Toplu satır getirmeyi gerçekleştirdiyseniz, ClassWizard bu `SetFieldType` çağrısını `DoFieldExchange`alan haritası bölümünde sizin için koyar.

Kayıt kümesi sınıfınızı parametreleştirebilirsiniz, herhangi bir alan eşlemesi bölümünün dışında `SetFieldType` yeniden çağırmanız gerekir ve ardından tüm parametre veri üyeleri için RFX çağrıları gelmelidir. Her parametre veri üyesi türünün kendine ait `SetFieldType` çağrısı olmalıdır. Aşağıdaki tablo, sınıfınızın parametre veri üyelerini temsil etmek için `SetFieldType` geçirebilmeniz için farklı değerleri ayırır:

|SETbir parametre değeri|Parametre veri üyesinin türü|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|Giriş parametresi. Kayıt kümesinin sorgusuna veya saklı yordamına geçirilen bir değer.|
|`CFieldExchange::param` | `CFieldExchange::inputParam`ile aynı.|
|`CFieldExchange::outputParam`|Çıkış parametresi. Kayıt kümesinin saklı yordamının dönüş değeri.|
|`CFieldExchange::inoutParam`|Giriş/çıkış parametresi. Kayıt kümesinin saklı yordamından öğesine geçirilen ve döndürülen bir değer.|

Genel olarak, alan veri üyeleri veya parametre veri üyeleri ile ilişkili her RFX işlev çağrısı, öncesinde `SetFieldType`çağrısı olmalıdır. Her `SetFieldType` çağrısının *Neli* parametresi, `SetFieldType` ÇAĞRıSıNı izleyen RFX işlev çağrıları tarafından temsil edilen veri üyelerinin türünü tanımlar.

Çıkış ve giriş/çıkış parametrelerini işleme hakkında daha fazla bilgi için bkz. [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset)`CRecordset` üye işlevi. RFX ve toplu RFX işlevleri hakkında daha fazla bilgi için bkz. [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md). Toplu satır getirme hakkında ilgili bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

Bu örnekte, `SetFieldType`yönelik çağrılar ile RFX işlevlerine yapılan çağrılar gösterilmektedir. `SetFieldType`, bir `CFieldExchange` nesnesine `pFX` işaretçisi aracılığıyla çağrıldığını unutmayın.

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
