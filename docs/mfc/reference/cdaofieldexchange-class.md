---
title: CDaoFieldExchange sınıfı
ms.date: 11/04/2016
f1_keywords:
- CDaoFieldExchange
- AFXDAO/CDaoFieldExchange
- AFXDAO/CDaoFieldExchange::IsValidOperation
- AFXDAO/CDaoFieldExchange::SetFieldType
- AFXDAO/CDaoFieldExchange::m_nOperation
- AFXDAO/CDaoFieldExchange::m_prs
helpviewer_keywords:
- CDaoFieldExchange [MFC], IsValidOperation
- CDaoFieldExchange [MFC], SetFieldType
- CDaoFieldExchange [MFC], m_nOperation
- CDaoFieldExchange [MFC], m_prs
ms.assetid: 350a663e-92ff-44ab-ad53-d94efa2e5823
ms.openlocfilehash: d28739ced9aedd29106937cb717c87a241993036
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57291034"
---
# <a name="cdaofieldexchange-class"></a>CDaoFieldExchange sınıfı

DAO veritabanı sınıfları tarafından kullanılan DAO kayıt alanı değişimi (DFX) yordamlarını destekler.

## <a name="syntax"></a>Sözdizimi

```
class CDaoFieldExchange
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|Geçerli işlem olursa sıfır değerini döndürür, güncelleştirilen alan türü için uygun.|
|[CDaoFieldExchange::SetFieldType](#setfieldtype)|Kayıt kümesi veri üyesinin türü belirtir; sütunu veya parametresi — DFX işlevleri yapılan tüm sonraki çağrılar tarafından temsil edilen sonraki çağrı kadar `SetFieldType`.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CDaoFieldExchange::m_nOperation](#m_noperation)|DFX işlem kümesinin geçerli çağrı tarafından gerçekleştirilmekte olan `DoFieldExchange` üye işlevi.|
|[CDaoFieldExchange::m_prs](#m_prs)|Hangi DFX üzerinde gerçekleştirilen işlemleri kayıt kümesine bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

`CDaoFieldExchange` bir temel sınıfa sahip değil.

Bu sınıf, özel veri türleri için veri değişimi rutinleri yazıyorsanız kullanın. Aksi takdirde, bu sınıf doğrudan kullanmaz. DFX birbiriyle değiştirir veri alan veri üyeleri arasında [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesini ve karşılık gelen alanlar veri kaynağında geçerli kaydın. DFX her iki yönde exchange veri kaynağı ve veri kaynağına yönetir. Bkz: [Teknik Not 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) özel DFX rutinleri yazma konusunda bilgi için.

> [!NOTE]
>  DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) üzerinde göre MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adları "CDao" önekini alır. DAO sınıfları ile ODBC veri kaynaklarına erişim yine de kullanabilirsiniz. Genel olarak, üzerinde DAO göre MFC ODBC tabanlı MFC sınıfları daha yetenekli sınıflardır. DAO dayalı sınıflar kendi veritabanı altyapısı aracılığıyla ODBC sürücüleri dahil olmak üzere, verilere erişebilir. Bunlar da DAO kendiniz çağırmak zorunda kalmak yerine sınıfları aracılığıyla tablo ekleme gibi veri tanımlama dili (DDL) işlemleri destekler.

> [!NOTE]
>  DAO kayıt alanı değişimi (DFX) benzer çok kayıt alanı değişimi (RFX), ODBC tabanlı MFC veritabanı sınıfları ( `CDatabase`, `CRecordset`). RFX anlarsanız, kullanımı kolay DFX bulabilirsiniz.

A `CDaoFieldExchange` nesnesi, bağlam bilgisi için DAO kayıt alanı değişimi gerçekleşmesi için sağlar. `CDaoFieldExchange` nesneleri bağlama parametreleri ve alan veri üyeleri içeren ve çeşitli bayrakları geçerli kaydın alanları ayarlama işlemleri, bir dizi destekler. Kayıt kümesi sınıf veri üyeleri tarafından tanımlanan türleri üzerinde gerçekleştirilen DFX işlemler **enum** **FieldType** içinde `CDaoFieldExchange`. Olası **FieldType** değerler şunlardır:

- `CDaoFieldExchange::outputColumn` alan veri üyeleri için.

- `CDaoFieldExchange::param` parametre veri üyeleri için.

[IsValidOperation](#isvalidoperation) üye işlevi, kendi özel DFX rutinleri yazmak için sağlanır. Kullanacağınız [SetFieldType](#setfieldtype) sıklıkla, [CDaoRecordset::DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) işlevleri. DFX genel işlevleri hakkında daha fazla ayrıntı için bkz: [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md). Kendi veri türleri için özel DFX rutinleri yazma hakkında daha fazla bilgi için bkz: [Teknik Not 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDaoFieldExchange`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

##  <a name="isvalidoperation"></a>  CDaoFieldExchange::IsValidOperation

Kendi DFX işlevi yazarsanız, çağrı `IsValidOperation` üzerinde belirli alan veri üye türü geçerli işlemi gerçekleştirip gerçekleştirmediğini belirlemek için işlevin başında (bir `CDaoFieldExchange::outputColumn` veya `CDaoFieldExchange::param`).

```
BOOL IsValidOperation();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli işlem güncelleştirilmesini alan türü için uygun değilse sıfır.

### <a name="remarks"></a>Açıklamalar

DFX mekanizması tarafından gerçekleştirilen işlemleri bazı olası alan türleri yalnızca biri için geçerlidir. Mevcut DFX işlevleri modelini izler.

Özel DFX rutinleri yazma hakkında ek bilgi için bkz: [Teknik Not 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).

##  <a name="m_noperation"></a>  CDaoFieldExchange::m_nOperation

Üzerinde gerçekleştirilecek bir işlemi tanımlayan [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) alanı exchange nesnesiyle ilişkili nesne.

### <a name="remarks"></a>Açıklamalar

`CDaoFieldExchange` Nesne birkaç farklı DFX işlemlerin kayıt kümesi için bağlam sağlar.

> [!NOTE]
>  Aşağıdaki MarkForAddNew ve SetFieldNull işlemleri altında açıklanan PSEUDONULL değeri Null alanlar işaretlemek için kullanılan bir değerdir. DAO kayıt alanı değişimi mekanizması (DFX) bu değeri Null olarak hangi alanların açıkça işaretlendi belirlemek için kullanır. PSEUDONULL için gerekli değil [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) ve [COleCurrency](../../mfc/reference/colecurrency-class.md) alanları.

Olası değerleri `m_nOperation` şunlardır:

|Çalışma|Açıklama|
|---------------|-----------------|
|`AddToParameterList`|Yapılar **parametreleri** SQL deyiminin yan tümcesi.|
|`AddToSelectList`|Yapılar **seçin** SQL deyiminin yan tümcesi.|
|`BindField`|Veritabanı alanına, uygulamanızdaki bir bellek konumuna bağlar.|
|`BindParam`|Kayıt kümesi sorgu parametre değerlerini ayarlar.|
|`Fixup`|Bir alan için Null durumunu ayarlar.|
|`AllocCache`|Kayıt kümesi "kirli" alanları denetlemek için kullanılan önbellek ayırır.|
|`StoreField`|Geçerli kayıt önbelleğe kaydeder.|
|`LoadField`|Kayıt önbelleğe alınmış verileri üye değişkenlerinde geri yükler.|
|`FreeCache`|Kayıt kümesi "kirli" alanları denetlemek için kullanılan önbellek serbest bırakır.|
|`SetFieldNull`|Bir alanın durumu Null ve PSEUDONULL değerine ayarlar.|
|`MarkForAddNew`|İşaretleri alanları "değil PSEUDONULL varsa kirli".|
|`MarkForEdit`|Önbellek eşleşmiyorsa alanları "kirli" olarak işaretler.|
|`SetDirtyField`|Kümeleri değerleri "olarak kirli." olarak işaretlenmiş alan|
|`DumpField`|Bir alanın içeriği (yalnızca debug) dökümünü alır.|
|`MaxDFXOperation`|Giriş denetlemek için kullanılır.|

##  <a name="m_prs"></a>  CDaoFieldExchange::m_prs

Bir işaretçi içeren [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ilişkili nesne `CDaoFieldExchange` nesne.

### <a name="remarks"></a>Açıklamalar

##  <a name="setfieldtype"></a>  CDaoFieldExchange::SetFieldType

Çağrı `SetFieldType` içinde `CDaoRecordset` sınıfın `DoFieldExchange` geçersiz kılar.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Parametreler

*nFieldType*<br/>
Değerini **enum FieldType**bildirilen `CDaoFieldExchange`, olabilen şunlardan biri:

- `CDaoFieldExchange::outputColumn`

- `CDaoFieldExchange::param`

### <a name="remarks"></a>Açıklamalar

Normalde, ClassWizard bu çağrı sizin yerinize yazar. Kendi işlevinizi yazabilir ve yazmak için Sihirbazı'nı kullanarak, `DoFieldExchange` işlev, alan haritası dışında kendi işlev çağrıları ekleyin. Sihirbazı'nı kullanmıyorsanız, alan eşleştirme olmayacak. Çağrı DFX işlevleri sınıfınız, her alan veri üyesi için bir çağrı önündeki ve alan türü olarak tanımlayan `CDaoFieldExchange::outputColumn`.

Kayıt kümesi sınıfı Parametreleştirme ise (alan eşleme dışında) tüm parametre veri üyeleri için DFX çağrıları eklemeli ve bu çağrıları çağrı ile önünde `SetFieldType`. Değeri geçirin `CDaoFieldExchange::param`. (Bunun yerine, kullanabilirsiniz bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) ve parametre değerlerini ayarlar.)

DFX işlev çağrılarının alan veri üyeleri veya parametre veri üyeleri ile ilişkili her grup için bir çağrı tarafından genel olarak, gelmelidir `SetFieldType`. *NFieldType* her parametresinin `SetFieldType` çağrı izleyen DFX işlev çağrıları tarafından temsil edilen veri üyeleri türünü tanımlar `SetFieldType` çağırın.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)
