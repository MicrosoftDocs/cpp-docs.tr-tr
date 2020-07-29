---
title: Cdadofieldexchange sınıfı
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
ms.openlocfilehash: 62e9d1917e2d1eea19b9e8db4b6c56b6ad25d9e9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231838"
---
# <a name="cdaofieldexchange-class"></a>Cdadofieldexchange sınıfı

DAO veritabanı sınıfları tarafından kullanılan DAO Kayıt alanı değişimi (DFX) yordamlarını destekler.

DAO, Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

## <a name="syntax"></a>Sözdizimi

```
class CDaoFieldExchange
```

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[Cdadofieldexchange:: IsValidOperation](#isvalidoperation)|Güncel işlem güncelleştirilmekte olan alanın türü için uygun ise sıfır olmayan bir değer döndürür.|
|[Cdadofieldexchange:: settc](#setfieldtype)|Sonraki çağrıya kadar DFX işlevlerine yapılan tüm sonraki çağrılar tarafından temsil edilen kayıt kümesi veri üyesi (sütun veya parametre) türünü belirtir `SetFieldType` .|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[Cdadofieldexchange:: m_nOperation](#m_noperation)|Kayıt kümesinin üye işlevine geçerli çağrı tarafından gerçekleştirilen DFX işlemi `DoFieldExchange` .|
|[Cdadofieldexchange:: m_prs](#m_prs)|DFX işlemlerinin gerçekleştirildiği kayıt kümesine yönelik bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

`CDaoFieldExchange`taban sınıfına sahip değildir.

Özel veri türleri için veri değişim yordamlarını yazıyorsanız, bu sınıfı kullanın; Aksi takdirde, bu sınıfı doğrudan kullanamazsınız. DFX, [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnenizin alan veri üyeleri ile veri kaynağındaki geçerli kaydın karşılık gelen alanları arasında verileri değiş tokuş eder. DFX, Exchange 'i veri kaynağından ve veri kaynağından her iki yönde yönetir. Özel DFX yordamları yazma hakkında bilgi için bkz. [Teknik Note 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md) .

> [!NOTE]
> DAO veritabanı sınıfları, açık veritabanı bağlantısı (ODBC) tabanlı MFC veritabanı sınıflarından farklıdır. Tüm DAO veritabanı sınıf adlarında "CDao" öneki vardır. ODBC veri kaynaklarına, DAO sınıflarıyla erişmeye devam edebilirsiniz. Genel olarak, DAO tabanlı MFC sınıfları ODBC tabanlı MFC sınıflarından daha yetenekli değildir. DAO tabanlı sınıflar, ODBC sürücüleri dahil olmak üzere verilere kendi veritabanı altyapıları aracılığıyla erişebilir. Ayrıca, DAO 'YU çağırmak zorunda kalmak yerine sınıfları kullanarak tablo ekleme gibi veri tanımlama dili (DDL) işlemlerini de destekler.

> [!NOTE]
> DAO Kayıt alanı değişimi (DFX), ODBC tabanlı MFC veritabanı sınıflarında (,) kayıt alanı değişimi 'ne (RFX) çok benzer `CDatabase` `CRecordset` . RFX 'i anladıysanız, DFX kullanmayı daha kolay bulacaksınız.

Bir `CDaoFieldExchange` nesnesi, DAO Kayıt alanı değişimi 'nin gerçekleşmesi için gereken bağlam bilgilerini sağlar. `CDaoFieldExchange`nesneler, bağlama parametreleri ve alan veri üyeleri dahil olmak üzere bir dizi işlemi destekler ve geçerli kaydın alanlarında çeşitli bayraklar ayarlar. DFX işlemleri, **`enum`** ' ın ' **in tarafından** tanımlanan türlerin kayıt kümesi sınıfı veri üyeleri üzerinde gerçekleştirilir `CDaoFieldExchange` . Olası **bir** bu değer şunlardır:

- `CDaoFieldExchange::outputColumn`alan veri üyeleri için.

- `CDaoFieldExchange::param`parametre veri üyeleri için.

[IsValidOperation](#isvalidoperation) member işlevi kendı özel DFX yordamlarını yazmak için sağlanır. [:D oFieldExchange işlevlerinde, Cdaokayıt kümenizde setıbu](../../mfc/reference/cdaorecordset-class.md#dofieldexchange) sıklıkla kullanacaksınız. [SetFieldType](#setfieldtype) DFX genel işlevleri hakkında daha fazla bilgi için bkz. [kayıt alanı değişim işlevleri](../../mfc/reference/record-field-exchange-functions.md). Kendi veri türlerinizin özel DFX yordamlarını yazma hakkında daha fazla bilgi için bkz. [teknik notta 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`CDaoFieldExchange`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="cdaofieldexchangeisvalidoperation"></a><a name="isvalidoperation"></a>Cdadofieldexchange:: IsValidOperation

Kendi DFX işlevinizi yazarsanız, `IsValidOperation` geçerli işlemin belirli bir alan veri üyesi türü (a `CDaoFieldExchange::outputColumn` veya a) üzerinde gerçekleştirilip gerçekleştirilebileceğini öğrenmek için işlevinizin başlangıcında çağırın `CDaoFieldExchange::param` .

```
BOOL IsValidOperation();
```

### <a name="return-value"></a>Dönüş Değeri

Güncel işlem güncelleştirilmekte olan alanın türü için uygun ise sıfır dışında.

### <a name="remarks"></a>Açıklamalar

DFX mekanizması tarafından gerçekleştirilen işlemlerden bazıları yalnızca olası alan türlerinden biri için geçerlidir. Mevcut DFX işlevlerinin modelini izleyin.

Özel DFX yordamları yazma hakkında daha fazla bilgi için bkz. [teknik notta 53](../../mfc/tn053-custom-dfx-routines-for-dao-database-classes.md).

## <a name="cdaofieldexchangem_noperation"></a><a name="m_noperation"></a>Cdadofieldexchange:: m_nOperation

Alan değişimi nesnesiyle ilişkili [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesinde gerçekleştirilecek işlemi tanımlar.

### <a name="remarks"></a>Açıklamalar

`CDaoFieldExchange`Nesnesi, kayıt kümesinde çeşitli farklı DFX işlemleri için bağlam sağlar.

> [!NOTE]
> Aşağıdaki MarkForAddNew ve SetFieldNull işlemlerinde tanımlanan sözde değer, alanları null olarak işaretlemek için kullanılan bir değerdir. DAO Kayıt alanı değişim mekanizması (DFX), hangi alanların açık olarak null olarak işaretlendiğini belirlemede bu değeri kullanır. [Copaull](../../atl-mfc-shared/reference/coledatetime-class.md) ve [cotacurrency](../../mfc/reference/colecurrency-class.md) alanları için sözde değer gerekmez.

Olası değerleri `m_nOperation` şunlardır:

|İşlem|Açıklama|
|---------------|-----------------|
|`AddToParameterList`|SQL ifadesinin **Parameters** yan tümcesini oluşturur.|
|`AddToSelectList`|SQL ifadesinin **Select** yan tümcesini oluşturur.|
|`BindField`|Veritabanındaki bir alanı uygulamanızdaki bir bellek konumuna bağlar.|
|`BindParam`|Kayıt kümesi sorgusunun parametre değerlerini ayarlar.|
|`Fixup`|Bir alanın null durumunu ayarlar.|
|`AllocCache`|Kayıt kümesindeki "kirli" alanları denetlemek için kullanılan önbelleği ayırır.|
|`StoreField`|Geçerli kaydı önbelleğe kaydeder.|
|`LoadField`|Kayıt kümesindeki önbelleğe alınmış veri üye değişkenlerini geri yükler.|
|`FreeCache`|Kayıt kümesindeki "kirli" alanları denetlemek için kullanılan önbelleği boşaltır.|
|`SetFieldNull`|Bir alanın durumunu null ve değeri sözde olarak ayarlar.|
|`MarkForAddNew`|SÖZDE değilse alanları "kirli" olarak işaretler.|
|`MarkForEdit`|Önbellekte eşleşmeyen alanları "kirli" olarak işaretler.|
|`SetDirtyField`|"Kirli" olarak işaretlenen alan değerlerini ayarlar|
|`DumpField`|Bir alanın içeriğinin dökümünü yapar (yalnızca Hata Ayıkla).|
|`MaxDFXOperation`|Giriş denetimi için kullanılır.|

## <a name="cdaofieldexchangem_prs"></a><a name="m_prs"></a>Cdadofieldexchange:: m_prs

Nesneyle ilişkili [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) nesnesine yönelik bir işaretçi içerir `CDaoFieldExchange` .

### <a name="remarks"></a>Açıklamalar

## <a name="cdaofieldexchangesetfieldtype"></a><a name="setfieldtype"></a>Cdadofieldexchange:: settc

`SetFieldType` `CDaoRecordset` Sınıfınızın `DoFieldExchange` geçersiz kılmada çağırın.

```cpp
void SetFieldType(UINT nFieldType);
```

### <a name="parameters"></a>Parametreler

*N,*<br/>
' De, aşağıdakilerden biri olabilecek olarak belirtilen **sabit**listesinin bir değeri `CDaoFieldExchange` :

- `CDaoFieldExchange::outputColumn`

- `CDaoFieldExchange::param`

### <a name="remarks"></a>Açıklamalar

Normalde, ClassWizard bu çağrıyı sizin için yazar. Kendi işlevinizi yazarsanız ve işlevinizi yazmak için sihirbazı kullanıyorsanız `DoFieldExchange` , alan eşlemesi dışında kendi işlevinizdeki çağrıları ekleyin. Sihirbazı kullanmıyorsanız, bir alan eşlemesi olmayacaktır. Çağrı, sınıfınızın her bir alan veri üyesi için bir tane olmak üzere DFX işlevlerini çağırır ve alan türünü olarak tanımlar `CDaoFieldExchange::outputColumn` .

Kayıt kümesi sınıfınızı parametreleştirebilirsiniz, tüm parametre veri üyeleri (alan haritası dışında) için DFX çağrıları eklemeniz ve bu çağrıların önüne ' a çağrı uygulamanız gerekir `SetFieldType` . Değeri geçirin `CDaoFieldExchange::param` . (Bunun yerine, bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) kullanabilir ve parametre değerlerini ayarlayabilirsiniz.)

Genel olarak, alan veri üyeleri veya parametre veri üyeleri ile ilişkili her bir DFX işlev çağrısı öncesinde öğesine bir çağrı gelmelidir `SetFieldType` . Her çağrının *Neli* parametresi, `SetFieldType` çağrıyı izleyen DFX işlev çağrılarının gösterdiği veri üyelerinin türünü tanımlar `SetFieldType` .

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset sınıfı](../../mfc/reference/cdaorecordset-class.md)
