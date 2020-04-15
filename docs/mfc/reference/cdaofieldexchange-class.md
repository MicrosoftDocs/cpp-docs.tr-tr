---
title: CDaoFieldExchange Sınıfı
ms.date: 09/17/2019
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
ms.openlocfilehash: e1ce6e13b9c6045881cc0bb4114a6e11d58365c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368985"
---
# <a name="cdaofieldexchange-class"></a>CDaoFieldExchange Sınıfı

DAO veritabanı sınıfları tarafından kullanılan DAO kayıt alanı değişimi (DFX) yordamlarını destekler.

DAO, Office 2013 aracılığıyla desteklenir. DAO 3.6 son sürümüdür ve eski miş olarak kabul edilir.

## <a name="syntax"></a>Sözdizimi

```
class CDaoFieldExchange
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CDaoFieldExchange::IsValidOperation](#isvalidoperation)|Geçerli işlem güncelleştirilen alan türü için uygunsa sıfırsız döndürür.|
|[CDaoFieldExchange::SetFieldType](#setfieldtype)|Bir sonraki çağrıya kadar DFX işlevlerine sonraki tüm çağrılar tarafından temsil edilen kayıt kümesi `SetFieldType`veri üyesinin türünü (sütun veya parametre) belirtir.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CDaoFieldExchange::m_nOperation](#m_noperation)|DFX işlemi, kayıt kümesinin `DoFieldExchange` üye işlevine yapılan geçerli çağrı tarafından gerçekleştirilir.|
|[CDaoFieldExchange::m_prs](#m_prs)|DFX işlemlerinin gerçekleştirildiği kayıt kümesine işaretçi.|

## <a name="remarks"></a>Açıklamalar

`CDaoFieldExchange`taban sınıfa sahip değildir.

Özel veri türleri için veri alışverişi yordamları yazıyorsanız bu sınıfı kullanın; aksi takdirde, bu sınıfı doğrudan kullanmazsınız. DFX, [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnenizin alan veri üyeleri ile veri kaynağındaki geçerli kaydın ilgili alanları arasında veri alışverişi. DFX, veri kaynağından veri kaynağına kadar her iki yönde de değişimi yönetir. Özel DFX yordamları yazma hakkında bilgi için [Teknik Not 53'e](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) bakın.

> [!NOTE]
> DAO veritabanı sınıfları Açık Veritabanı Bağlantısı (ODBC) dayalı MFC veritabanı sınıfları farklıdır. Tüm DAO veritabanı sınıf adları "CDao" öneki vardır. DAO sınıfları ile ODBC veri kaynaklarına erişebilirsiniz. Genel olarak, DAO'ya dayalı MFC sınıfları ODBC'ye dayalı MFC sınıflardan daha yeteneklidir. DAO tabanlı sınıflar, ODBC sürücüleri de dahil olmak üzere verilere kendi veritabanı altyapıları aracılığıyla erişebilir. Ayrıca, DAO'yu kendiniz aramak yerine sınıflar üzerinden tablo eklemek gibi Veri Tanım Dili (DDL) işlemlerini de desteklerler.

> [!NOTE]
> DAO kayıt alanı değişimi (DFX), ODBC tabanlı MFC veritabanı sınıflarındaki kayıt alanı `CDatabase`değişimine (RFX) çok benzerdir . `CRecordset` RFX'i anlıyorsanız, DFX'i kolayca kullanabilirsiniz.

Bir `CDaoFieldExchange` nesne, DAO kayıt alanı değişiminin gerçekleşmesi için gereken bağlam bilgilerini sağlar. `CDaoFieldExchange`nesneler, parametreleri ve alan veri üyelerini bağlama ve geçerli kaydın alanlarında çeşitli bayraklar ayarlama dahil olmak üzere bir dizi işlemi destekler. DFX **işlemleri, enum** **FieldType** tarafından tanımlanan türlerin kayıt kümesi `CDaoFieldExchange`sınıfı veri üyeleri üzerinde gerçekleştirilir. Olası **FieldType** değerleri şunlardır:

- `CDaoFieldExchange::outputColumn`alan veri üyeleri için.

- `CDaoFieldExchange::param`parametre veri üyeleri için.

[IsValidOperation](#isvalidoperation) üye işlevi, kendi özel DFX yordamlarınızı yazmak için sağlanır. [SetFieldType'ı](#setfieldtype) [CDaoRecordset::DoFieldExchange](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) fonksiyonlarınızda sık sık kullanacaksınız. DFX global işlevleri hakkında ayrıntılı bilgi [için, Kayıt Alanı Değişim Fonksiyonları'na](../../mfc/reference/record-field-exchange-functions.md)bakın. Kendi veri türleri için özel DFX yordamları yazma hakkında bilgi için [Teknik Not 53'e](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDaoFieldExchange`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="cdaofieldexchangeisvalidoperation"></a><a name="isvalidoperation"></a>CDaoFieldExchange::IsValidOperation

Kendi DFX işlevinizi yazarsanız, geçerli işlemin belirli bir alan veri üye türünde (a veya `CDaoFieldExchange::outputColumn` a) `CDaoFieldExchange::param`gerçekleştirilip gerçekleştirilemeyeceğini belirlemek için işlevinizin başında arama yapabilirsiniz. `IsValidOperation`

```
BOOL IsValidOperation();
```

### <a name="return-value"></a>Dönüş Değeri

Geçerli işlem güncelleştirilen alan türü için uygunsa sıfırsız.

### <a name="remarks"></a>Açıklamalar

DFX mekanizması tarafından gerçekleştirilen işlemlerden bazıları yalnızca olası alan türlerinden biri için geçerlidir. Varolan DFX işlevlerinin modelini izleyin.

Özel DFX yordamları yazma hakkında daha fazla bilgi için [Teknik Not 53'e](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md)bakın.

## <a name="cdaofieldexchangem_noperation"></a><a name="m_noperation"></a>CDaoFieldExchange::m_nOperation

Alan değişim nesnesi ile ilişkili [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesi üzerinde gerçekleştirilecek işlemi tanımlar.

### <a name="remarks"></a>Açıklamalar

Nesne, `CDaoFieldExchange` kayıt kümesindeki bir dizi farklı DFX işlemi için bağlamı sağlar.

> [!NOTE]
> Aşağıdaki MarkForAddNew ve SetFieldNull işlemleri altında açıklanan PSEUDONULL değeri, Null alanlarını işaretlemek için kullanılan bir değerdir. DAO kayıt alanı değişim mekanizması (DFX), hangi alanların açıkça Null olarak işaretlendiğini belirlemek için bu değeri kullanır. PSEUDONULL [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) ve [COleCurrency](../../mfc/reference/colecurrency-class.md) alanları için gerekli değildir.

Olası değerler `m_nOperation` şunlardır:

|İşlem|Açıklama|
|---------------|-----------------|
|`AddToParameterList`|SQL deyiminin **PARAMETRELER** yan tümcesini oluşturur.|
|`AddToSelectList`|SQL deyiminin **SELECT** yan tümcesini oluşturur.|
|`BindField`|Veritabanındaki bir alanı uygulamanızdaki bir bellek konumuna bağlar.|
|`BindParam`|Kayıt kümesinin sorgusu için parametre değerlerini ayarlar.|
|`Fixup`|Bir alan için Null durumunu ayarlar.|
|`AllocCache`|Kayıt kümesindeki "kirli" alanları denetlemek için kullanılan önbelleği ayırır.|
|`StoreField`|Geçerli kaydı önbelleğe kaydeder.|
|`LoadField`|Önbelleğe alınan veri üyesi değişkenlerini kayıt kümesinde geri yükler.|
|`FreeCache`|Kayıt kümesindeki "kirli" alanları denetlemek için kullanılan önbelleği boşaltır.|
|`SetFieldNull`|Bir alanın durumunu Null'a ve PSEUDONULL'a değer olarak ayarlar.|
|`MarkForAddNew`|PseudoNULL değilse "kirli" alanları işaretler.|
|`MarkForEdit`|Önbellekle eşleşmiyorsa alanları "kirli" olarak işaretler.|
|`SetDirtyField`|"Kirli" olarak işaretlenmiş alan değerlerini ayarlar.|
|`DumpField`|Alanın içeriğini atar (yalnızca hata ayıklama).|
|`MaxDFXOperation`|Giriş denetimi için kullanılır.|

## <a name="cdaofieldexchangem_prs"></a><a name="m_prs"></a>CDaoFieldExchange::m_prs

Nesneyle ilişkili [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine `CDaoFieldExchange` işaretçi siler.

### <a name="remarks"></a>Açıklamalar

## <a name="cdaofieldexchangesetfieldtype"></a><a name="setfieldtype"></a>CDaoFieldExchange::SetFieldType

Sınıfının `SetFieldType` `CDaoRecordset` `DoFieldExchange` geçersiz kılını çağırın.

```
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Parametreler

*nFieldType*<br/>
Enum **FieldType**değeri , içinde `CDaoFieldExchange`beyan , aşağıdakilerden biri olabilir:

- `CDaoFieldExchange::outputColumn`

- `CDaoFieldExchange::param`

### <a name="remarks"></a>Açıklamalar

Normalde, ClassWizard sizin için bu çağrıyı yazar. Kendi işlevinizi yazıyorsanız ve işlevinizi `DoFieldExchange` yazmak için sihirbazı kullanıyorsanız, alan haritasının dışında kendi işlevinize çağrılar ekleyin. Sihirbazı kullanmazsanız, bir alan eşlemesi olmaz. Arama, sınıfınızın her alan veri üyesi için bir tane olan DFX işlevlerine yapılan çağrılardan önce gelir ve alan türünü . olarak `CDaoFieldExchange::outputColumn`tanımlar.

Kayıt kümesi sınıfınızı parametrenize aktarAcaksanız, tüm parametre veri üyeleri (alan haritasının dışında) için DFX çağrıları eklemeli ve bu çağrılardan önce `SetFieldType`. Değeri `CDaoFieldExchange::param`geçir. (Bunun yerine, bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) kullanabilirsiniz ve parametre değerlerini ayarlayın.)

Genel olarak, alan veri üyeleri veya parametre veri üyeleri ile ilişkili DFX işlev `SetFieldType`çağrıları her grup önce bir çağrı olmalıdır . Her `SetFieldType` çağrının `SetFieldType` *nFieldType* parametresi, çağrıyı izleyen DFX işlevi çağrıları tarafından temsil edilen veri üyelerinin türünü tanımlar.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset Sınıfı](../../mfc/reference/cdaorecordset-class.md)
