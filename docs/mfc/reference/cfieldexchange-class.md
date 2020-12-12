---
description: 'Daha fazla bilgi edinin: CFieldExchange Class'
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
ms.openlocfilehash: 128b2a7baf6fff923393f3105e27f1e85657bdde
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97184562"
---
# <a name="cfieldexchange-class"></a>CFieldExchange sınıfı

Veritabanı sınıfları tarafından kullanılan kayıt alanı değişimi (RFX) ve toplu kayıt alanı değişimi (toplu RFX) yordamlarını destekler.

## <a name="syntax"></a>Syntax

```
class CFieldExchange
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFieldExchange:: Isıbu](#isfieldtype)|Güncel işlem güncelleştirilmekte olan alanın türü için uygun ise sıfır olmayan bir değer döndürür.|
|[CFieldExchange:: SETbir](#setfieldtype)|Bir sonraki çağrıya kadar RFX işlevlerine yapılan tüm çağrılar tarafından temsil edilen kayıt kümesi veri üyesi (sütun veya parametre) türünü belirtir `SetFieldType` .|

## <a name="remarks"></a>Açıklamalar

`CFieldExchange` taban sınıfına sahip değildir.

Özel veri türleri için veri değişim yordamları yazıyorsanız veya toplu satır getirme uyguladığınızda bu sınıfı kullanın; Aksi takdirde, bu sınıfı doğrudan kullanamazsınız. RFX ve toplu RFX, kayıt kümesi nesnenizin alan veri üyeleri ile veri kaynağındaki geçerli kaydın karşılık gelen alanları arasındaki verileri değiş tokuş eder.

> [!NOTE]
> Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıflarıyla çalışıyorsanız, bunun yerine [Cdadofieldexchange](../../mfc/reference/cdaofieldexchange-class.md) sınıfını kullanın. Daha fazla bilgi için bkz. [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

Bir `CFieldExchange` nesnesi, kayıt alanı değişimi veya toplu kayıt alanı değişimi için gereken bağlam bilgilerini sağlar. `CFieldExchange` nesneler, bağlama parametreleri ve alan veri üyeleri dahil olmak üzere bir dizi işlemi destekler ve geçerli kaydın alanlarında çeşitli bayraklar ayarlar. RFX ve toplu RFX işlemleri, **`enum`**  ' ın ' in tarafından tanımlanan türlerin kayıt kümesi sınıfı veri üyeleri üzerinde gerçekleştirilir `CFieldExchange` . Olası **bir** bu değer şunlardır:

- `CFieldExchange::outputColumn` alan veri üyeleri için.

- `CFieldExchange::inputParam` ya da `CFieldExchange::param` giriş parametresi veri üyeleri için.

- `CFieldExchange::outputParam` çıkış parametresi veri üyeleri için.

- `CFieldExchange::inoutParam` giriş/çıkış parametresi veri üyeleri için.

Sınıfın üye işlevlerinin ve veri üyelerinin çoğu kendi özel RFX yordamlarınızı yazmak için sağlanır. `SetFieldType`Sıklıkla kullanacaksınız. Daha fazla bilgi için, bkz. [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md) ve [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). RFX ve toplu RFX genel işlevleri hakkında daha fazla bilgi için, bu başvurunun MFC makroları ve genel bölümündeki [kayıt alanı değişimi işlevleri](../../mfc/reference/record-field-exchange-functions.md) bölümüne bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CFieldExchange`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** Afxdb. h

## <a name="cfieldexchangeisfieldtype"></a><a name="isfieldtype"></a> CFieldExchange:: Isıbu

Kendi RFX işlevinizi yazarsanız, `IsFieldType` geçerli işlemin belirli bir alan veya parametre veri üye türü (a `CFieldExchange::outputColumn` ,,,, `CFieldExchange::inputParam` `CFieldExchange::param` `CFieldExchange::outputParam` veya `CFieldExchange::inoutParam` ) üzerinde gerçekleştirilip gerçekleştirilebileceğini öğrenmek için işlevinizin başlangıcında çağırın.

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

## <a name="cfieldexchangesetfieldtype"></a><a name="setfieldtype"></a> CFieldExchange:: SETbir

`SetFieldType`Kayıt kümesi sınıfınızın [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) geçersiz kılma için bir çağrınızın olması gerekir.

```cpp
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Parametreler

*N,*<br/>
Öğesinin ' `enum FieldType` de belirtilen değeri, `CFieldExchange` aşağıdakilerden biri olabilir:

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>Açıklamalar

Alan veri üyeleri için, `SetFieldType` bir parametresiyle ve `CFieldExchange::outputColumn` sonra RFX veya toplu RFX işlevlerine yapılan çağrılar ile çağrı yapmanız gerekir. Toplu satır getirmeyi gerçekleştirdiyseniz, ClassWizard bu `SetFieldType` çağrıyı sizin için alan haritası bölümünde koyar `DoFieldExchange` .

Kayıt kümesi sınıfınızı parametreleştirebilirsiniz, `SetFieldType` herhangi bir alan eşlemesi bölümünün dışında, ardından tüm parametre veri üyeleri IÇIN RFX çağrıları ' nı tekrar çağırmanız gerekir. Her parametre veri üyesi türünün kendi `SetFieldType` çağrısı olmalıdır. Aşağıdaki tablo, `SetFieldType` sınıfınızın parametre veri üyelerini temsil etmek için geçirebilmeniz için kullanabileceğiniz farklı değerleri ayırır:

|SETbir parametre değeri|Parametre veri üyesinin türü|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|Giriş parametresi. Kayıt kümesinin sorgusuna veya saklı yordamına geçirilen bir değer.|
|`CFieldExchange::param` | aynı `CFieldExchange::inputParam` .|
|`CFieldExchange::outputParam`|Çıkış parametresi. Kayıt kümesinin saklı yordamının dönüş değeri.|
|`CFieldExchange::inoutParam`|Giriş/çıkış parametresi. Kayıt kümesinin saklı yordamından öğesine geçirilen ve döndürülen bir değer.|

Genel olarak, alan veri üyeleri veya parametre veri üyeleri ile ilişkili her bir RFX işlevi grubunun önünde bir çağrısı gelmelidir `SetFieldType` . Her çağrının *Neli* parametresi, `SetFieldType` çağrıyı izleyen RFX işlev çağrıları tarafından temsil edilen veri üyelerinin türünü tanımlar `SetFieldType` .

Çıkış ve giriş/çıkış parametrelerini işleme hakkında daha fazla bilgi için bkz `CRecordset` . [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset)üye işlevi. RFX ve toplu RFX işlevleri hakkında daha fazla bilgi için bkz. [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md). Toplu satır getirme hakkında ilgili bilgi için bkz. kayıt [kümesi: kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

Bu örnek, çağrısı yapılan çağrıları içeren RFX işlevlerine yapılan birkaç çağrı gösterir `SetFieldType` . `SetFieldType`Bir nesnenin işaretçisi aracılığıyla çağrıldığını unutmayın `pFX` `CFieldExchange` .

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset sınıfı](../../mfc/reference/crecordset-class.md)
