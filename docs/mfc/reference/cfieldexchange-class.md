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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62346359"
---
# <a name="cfieldexchange-class"></a>CFieldExchange sınıfı

Kayıt alanı değişimi (RFX) ve veritabanı sınıfları tarafından kullanılan toplu kayıt alanı değişimi (Bulk RFX) yordamlarını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CFieldExchange
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CFieldExchange::IsFieldType](#isfieldtype)|Geçerli işlem olursa sıfır değerini döndürür, güncelleştirilen alan türü için uygun.|
|[CFieldExchange::SetFieldType](#setfieldtype)|Kayıt kümesi veri üyesi türünü belirtir: sütunu veya parametresi — tüm aşağıdaki çağrıları RFX işlevleri tarafından temsil edilen sonraki çağrı kadar `SetFieldType`.|

## <a name="remarks"></a>Açıklamalar

`CFieldExchange` bir temel sınıfa sahip değil.

Bu sınıf, özel veri türleri ya da zaman toplu satır getirme uyguluyor için veri değişimi rutinleri yazıyorsanız kullanın; Aksi takdirde, bu sınıf doğrudan kullanmaz. RFX ve toplu RFX veri alan veri üyeleri, kayıt kümesi nesnesi geçerli kaydın veri kaynağında ilgili alanları arasındaki birbiriyle değiştirir.

> [!NOTE]
>  Açık veritabanı bağlantısı (ODBC) sınıfları yerine veri erişim nesneleri (DAO) sınıfları ile çalışıyorsanız, sınıf kullanmak [CDaoFieldExchange](../../mfc/reference/cdaofieldexchange-class.md) yerine. Daha fazla bilgi için bkz [genel bakış: veritabanı programlama](../../data/data-access-programming-mfc-atl.md).

A `CFieldExchange` nesnesi sağlar bağlam bilgisi kayıt alanı değişimi veya toplu kayıt alanı değişimi yapılacak yerleştirin. `CFieldExchange` nesneleri bağlama parametreleri ve alan veri üyeleri içeren ve çeşitli bayrakları geçerli kaydın alanları ayarlama işlemleri, bir dizi destekler. Kayıt kümesi sınıf veri üyeleri tarafından tanımlanan türleri üzerinde gerçekleştirilen RFX ve toplu RFX işlemler **enum** **FieldType** içinde `CFieldExchange`. Olası **FieldType** değerler şunlardır:

- `CFieldExchange::outputColumn` alan veri üyeleri için.

- `CFieldExchange::inputParam` veya `CFieldExchange::param` giriş parametre veri üyeleri için.

- `CFieldExchange::outputParam` çıkış parametresi veri üyeleri için.

- `CFieldExchange::inoutParam` veri üyeleri için giriş/çıkış parametresi.

Çoğu sınıfın üye işlevleri ve veri üyeleri, kendi özel RFX rutinleri yazmak için sağlanır. Kullanacağınız `SetFieldType` sık. Daha fazla bilgi için makalelere bakın [kayıt alanı değişimi (RFX)](../../data/odbc/record-field-exchange-rfx.md) ve [kayıt kümesi (ODBC)](../../data/odbc/recordset-odbc.md). Toplu satır getirme hakkında daha fazla bilgi için bkz [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). RFX ve toplu RFX genel işlevleri hakkında daha fazla ayrıntı için bkz: [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md) MFC makroları ve genel öğeleri bölümünde bu başvuru.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CFieldExchange`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdb.h

##  <a name="isfieldtype"></a>  CFieldExchange::IsFieldType

Kendi RFX işlevi yazarsanız, çağrı `IsFieldType` belirli bir alan veya parametre veri üyesi tür üzerinde geçerli işlemi gerçekleştirip gerçekleştirmediğini belirlemek için işlevin başında (bir `CFieldExchange::outputColumn`, `CFieldExchange::inputParam`, `CFieldExchange::param`, `CFieldExchange::outputParam`, veya `CFieldExchange::inoutParam`).

```
BOOL IsFieldType(UINT* pnField);
```

### <a name="parameters"></a>Parametreler

*pnField*<br/>
Bu parametrede sıralı alan veya parametre veri üyesi sayısı döndürülür. Bu sayı veri üyesinin sırayla karşılık gelen [CRecordset::DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [CRecordset::DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) işlevi.

### <a name="return-value"></a>Dönüş Değeri

Geçerli işlem, geçerli bir alan veya parametre türü üzerinde gerçekleştirilebilir olursa sıfır dışı.

### <a name="remarks"></a>Açıklamalar

Mevcut RFX işlevleri modelini izler.

##  <a name="setfieldtype"></a>  CFieldExchange::SetFieldType

Bir çağrı ihtiyacınız `SetFieldType` kayıt sınıfın içinde [DoFieldExchange](../../mfc/reference/crecordset-class.md#dofieldexchange) veya [DoBulkFieldExchange](../../mfc/reference/crecordset-class.md#dobulkfieldexchange) geçersiz kılar.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Parametreler

*nFieldType*<br/>
Değerini `enum FieldType`bildirilen `CFieldExchange`, olabilen aşağıdakilerden biri:

- `CFieldExchange::outputColumn`

- `CFieldExchange::inputParam`

- `CFieldExchange::param`

- `CFieldExchange::outputParam`

- `CFieldExchange::inoutParam`

### <a name="remarks"></a>Açıklamalar

Alan veri üyeleri için çağırmalısınız `SetFieldType` parametresi ile `CFieldExchange::outputColumn`çizgidir RFX veya Bulk RFX işlevleri çağırır. Toplu satır getirme uygulanmadı durumunda ClassWizard bu yerleştirir `SetFieldType` sizin için alan haritası kısmında arama `DoFieldExchange`.

Kayıt kümesi sınıfı Parametreleştirme varsa çağırmalıdır `SetFieldType` yeniden herhangi bir alan eşlemesi bölümü dışında ardından RFX çağrılarının tüm parametre veri üyeleri için. Her parametre veri üye türü kendi olmalıdır `SetFieldType` çağırın. Aşağıdaki tabloda farklı değerler için geçirebilirsiniz ayıran `SetFieldType` sınıfınızın parametre veri üyeleri göstermek için:

|SetFieldType parametre değeri|Tür parametresi veri üyesi|
|----------------------------------|-----------------------------------|
|`CFieldExchange::inputParam`|Giriş parametresi. Kayıt kümesinin sorgu veya saklı yordam içinde geçirilen değer.|
|`CFieldExchange::param` | Aynı `CFieldExchange::inputParam`.|
|`CFieldExchange::outputParam`|Çıkış parametresi. Kayıt kümesi saklı yordam dönüş değeri.|
|`CFieldExchange::inoutParam`|Giriş/çıkış parametresi. Yöntemlere geçirilen veya kümesinin bir saklı yordamdan döndürülen değer.|

RFX işlev çağrılarının alan veri üyeleri veya parametre veri üyeleri ile ilişkili her grup için bir çağrı tarafından genel olarak, gelmelidir `SetFieldType`. *NFieldType* her parametresinin `SetFieldType` çağrı izleyen RFX işlev çağrıları tarafından temsil edilen veri üyeleri türünü tanımlar `SetFieldType` çağırın.

Çıkış ve giriş/çıkış parametreleri işleme hakkında daha fazla bilgi için bkz. `CRecordset` üye işlevi [FlushResultSet](../../mfc/reference/crecordset-class.md#flushresultset). RFX ve toplu RFX işlevleri hakkında daha fazla bilgi için Ek Yardım konusuna [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md). Toplu satır getirme hakkında ilgili bilgi için bkz [kayıt kümesi: Kayıtları toplu yakalama (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Örnek

Bu örnekte çağrıları eşlik eden ile RFX işlevleri çeşitli çağrılar gösterilmektedir `SetFieldType`. Unutmayın `SetFieldType` aracılığıyla adlı `pFX` işaretçi bir `CFieldExchange` nesne.

[!code-cpp[NVC_MFCDatabase#33](../../mfc/codesnippet/cpp/cfieldexchange-class_1.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CRecordset Sınıfı](../../mfc/reference/crecordset-class.md)
