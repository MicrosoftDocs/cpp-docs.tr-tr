---
title: CDaoFieldInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: e98f5ba69f6702dd768cfe6605f993064e1b896c
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096108"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo Yapısı

Yapı `CDaoFieldInfo` , veri erişim nesneleri (DAO) için tanımlanan bir alan nesnesi hakkında bilgiler içerir.

DAO, Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

## <a name="syntax"></a>Sözdizimi

```
struct CDaoFieldInfo
{
    CString m_strName;           // Primary
    short m_nType;               // Primary
    long m_lSize;                // Primary
    long m_lAttributes;          // Primary
    short m_nOrdinalPosition;    // Secondary
    BOOL m_bRequired;            // Secondary
    BOOL m_bAllowZeroLength;     // Secondary
    long m_lCollatingOrder;      // Secondary
    CString m_strForeignName;    // Secondary
    CString m_strSourceField;    // Secondary
    CString m_strSourceTable;    // Secondary
    CString m_strValidationRule; // All
    CString m_strValidationText; // All
    CString m_strDefaultValue;   // All
};
```

#### <a name="parameters"></a>Parametreler

*m_strName*<br/>
Alan nesnesini benzersiz olarak adlandırır. Ayrıntılar için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

*m_nType*<br/>
Alanın veri türünü gösteren bir değer. Ayrıntılar için, DAO yardımı 'nda "tür özelliği" konusuna bakın. Bu özelliğin değeri aşağıdakilerden biri olabilir:

- `dbBoolean`Evet/Hayır, doğru/yanlış ile aynı

- `dbByte`Bayt

- `dbInteger`Kısadır

- `dbLong`Kalacağını

- `dbCurrency`Birimindeki bkz. MFC sınıfı [Colet para birimi](../../mfc/reference/colecurrency-class.md)

- `dbSingle`Sunuculu

- `dbDouble`Çift

- `dbDate`Tarih/saat; bkz. MFC sınıfı [Cotatarihsaat](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText`Metinleri bkz. MFC sınıfı [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary`Long Binary (OLE nesnesi); sınıf`CLongBinary` yerine, daha zengin ve kullanımı daha kolay olan mfc sınıfının CByteArray sınıfını kullanmak isteyebilirsiniz. [](../../mfc/reference/cbytearray-class.md) `CByteArray`

- `dbMemo`Faturasındaki bkz. MFC sınıfı`CString`

- `dbGUID`Uzak yordam çağrılarında kullanılan, genel olarak benzersiz tanımlayıcı/evrensel benzersiz tanımlayıcı. Daha fazla bilgi için, DAO yardımı 'nda "tür özelliği" konusuna bakın.

> [!NOTE]
>  İkili veriler için dize veri türleri kullanmayın. Bu, verilerinizin Unicode/ANSI çeviri katmanından geçmesine neden olur ve bu da daha fazla ek yük ve muhtemelen beklenmeyen çeviri sağlar.

*m_lSize*<br/>
Metin veya sayısal değerler içeren bir alan nesnesinin sabit boyutunu veya metin içeren bir DAO alanı nesnesinin en büyük boyutunu bayt cinsinden belirten bir değer. Ayrıntılar için, DAO yardımı 'nda "boyut özelliği" konusuna bakın. Boyutlar aşağıdaki değerlerden biri olabilir:

|Tür|Boyut (bayt)|Açıklama|
|----------|--------------------|-----------------|
|`dbBoolean`|1 bayt|Evet/Hayır (true/false ile aynı)|
|`dbByte`|1\.|Bayt|
|`dbInteger`|2|Integer|
|`dbLong`|4|Uzun|
|`dbCurrency`|8|Para birimi ([Copapara birimi](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Tek|
|`dbDouble`|8|Çift|
|`dbDate`|8|Tarih/saat ([Copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Metin ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Long Binary (OLE nesnesi; [CByteArray](../../mfc/reference/cbytearray-class.md); yerine `CLongBinary`kullanın)|
|`dbMemo`|0|Memo ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|Uzak yordam çağrılarında kullanılan, genel olarak benzersiz tanımlayıcı/evrensel benzersiz tanımlayıcı.|

*m_lAttributes*<br/>
Bir TableDef, Recordset, QueryDef veya Index nesnesi tarafından içerilen bir Field nesnesinin karakteristiklerini belirtir. Döndürülen değer, C++ BIT düzeyinde OR ( **&#124;** ) işleciyle oluşturulan bu sabitlerin toplamı olabilir:

- `dbFixedField`Alan boyutu sabittir (sayısal alanlar için varsayılan).

- `dbVariableField`Alan boyutu değişken (yalnızca metin alanları).

- `dbAutoIncrField`Yeni kayıtlar için alan değeri, değiştirilemeyen benzersiz bir uzun tamsayıya otomatik olarak artırılır. Yalnızca Microsoft Jet veritabanı tabloları için desteklenir.

- `dbUpdatableField`Alan değeri değiştirilebilir.

- `dbDescending`Alan, azalan (Z-A veya 100-0) düzende sıralanır (yalnızca bir Index nesnesinin Fields koleksiyonundaki Field nesnesi için geçerlidir; MFC 'de, dizin nesnelerinin kendisi TableDef nesnelerinde bulunur). Bu sabiti atlarsanız, alan artan (A-Z veya 0-100) bir düzende sıralanır (varsayılan).

Bu özelliğin ayarını denetlerken, belirli bir özniteliği sınamak için C++ bit düzeyinde and işlecini ( **&** ) kullanabilirsiniz. Birden çok öznitelik ayarlarken, bit düzeyinde OR ( **&#124;** ) işleciyle uygun sabitleri birleştirerek bunları birleştirebilirsiniz. Ayrıntılar için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

*m_nOrdinalPosition*<br/>
Bir DAO alan nesnesi tarafından temsil edilen bir alanın diğer alanlara göre görüntülenmesini istediğiniz sayısal sırayı belirten bir değer. Bu özelliği, [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)ile ayarlayabilirsiniz. Ayrıntılar için, DAO yardımı 'nda "OrdinalPosition özelliği" konusuna bakın.

*m_bRequired*<br/>
Bir DAO alanı nesnesinin null olmayan bir değer gerektirip gerektirmediğini belirtir. Bu özellik TRUE ise, alan null değere izin vermez. Gerekli değeri FALSE olarak ayarlandıysa, alan null değerleri ve AllowZeroLength ve ValidationRule özellik ayarları tarafından belirtilen koşullara uyan değerleri içerebilir. Ayrıntılar için, DAO yardımı 'nda "gerekli özellik" konusuna bakın. Bu özelliği, [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)ile bir TableDef için ayarlayabilirsiniz.

*m_bAllowZeroLength*<br/>
Boş bir dizenin (""), metin veya Not veri türüne sahip bir DAO alan nesnesinin geçerli bir değeri olup olmadığını gösterir. Bu özellik TRUE ise, boş bir dize geçerli bir değerdir. Bir alanın değerini ayarlamak için boş bir dize kullantığınızdan emin olmak için bu özelliği FALSE olarak ayarlayabilirsiniz. Ayrıntılar için, DAO yardımı 'nda "AllowZeroLength özelliği" konusuna bakın. Bu özelliği, [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)ile bir TableDef için ayarlayabilirsiniz.

*m_lCollatingOrder*<br/>
Dize karşılaştırma veya sıralama için metin olarak sıralama düzeni sırasını belirtir. Ayrıntılar için, DAO yardımı 'nda "veri erişimi için Windows kayıt defteri ayarlarını özelleştirme" konusuna bakın. Döndürülen olası değerlerin bir listesi için, [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) yapısının `m_lCollatingOrder` üyesine bakın. Bu özelliği, [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)ile bir TableDef için ayarlayabilirsiniz.

*m_strForeignName*<br/>
Bir ilişkide, birincil tablodaki bir alana karşılık gelen yabancı tablodaki DAO alan nesnesinin adını belirtir. Ayrıntılar için, DAO yardımı 'nda "ForeignName özelliği" konusuna bakın.

*m_strSourceField*<br/>
Bir TableDef, Recordset veya QueryDef nesnesi tarafından içerilen bir DAO alan nesnesi için verilerin özgün kaynağı olan alanın adını gösterir. Bu özellik bir Field nesnesiyle ilişkili özgün alan adını gösterir. Örneğin, bu özelliği, adı temel tablodaki alanın adı ile ilgisi olmayan bir sorgu alanındaki verilerin özgün kaynağını tespit etmek için kullanabilirsiniz. Ayrıntılar için, DAO yardımı 'nda "SourceField, SourceTable özellikleri" konusuna bakın. Bu özelliği, [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)ile bir TableDef için ayarlayabilirsiniz.

*m_strSourceTable*<br/>
Bir TableDef, Recordset veya QueryDef nesnesi tarafından içerilen bir DAO alan nesnesi için verilerin özgün kaynağı olan tablonun adını gösterir. Bu özellik, bir Field nesnesiyle ilişkili özgün tablo adını gösterir. Örneğin, bu özelliği, adı temel tablodaki alanın adı ile ilgisi olmayan bir sorgu alanındaki verilerin özgün kaynağını tespit etmek için kullanabilirsiniz. Ayrıntılar için, DAO yardımı 'nda "SourceField, SourceTable özellikleri" konusuna bakın. Bu özelliği, [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)ile bir TableDef için ayarlayabilirsiniz.

*m_strValidationRule*<br/>
Değiştirilen veya tabloya eklenen bir alandaki verileri doğrulayan bir değer. Ayrıntılar için, DAO yardımı 'nda "ValidationRule özelliği" konusuna bakın. Bu özelliği, [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)ile bir TableDef için ayarlayabilirsiniz.

TableDefs hakkında ilgili bilgi için, `m_strValidationRule` [cdaotabledefinınfo](../../mfc/reference/cdaotabledefinfo-structure.md) yapısının üyesine bakın.

*m_strValidationText*<br/>
Bir DAO alan nesnesinin değeri ValidationRule özelliği ayarı tarafından belirtilen doğrulama kuralına uygun değilse uygulamanızın görüntüleyeceği iletinin metnini belirten bir değer. Ayrıntılar için, DAO yardımı 'nda "ValidationText özelliği" konusuna bakın. Bu özelliği, [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)ile bir TableDef için ayarlayabilirsiniz.

*m_strDefaultValue*<br/>
Bir DAO alan nesnesinin varsayılan değeri. Yeni bir kayıt oluşturulduğunda, DefaultValue özellik ayarı, alanın değeri olarak otomatik olarak girilir. Ayrıntılar için, DAO yardımı 'nda "DefaultValue özelliği" konusuna bakın. Bu özelliği, [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)ile bir TableDef için ayarlayabilirsiniz.

## <a name="remarks"></a>Açıklamalar

Birincil, ikincil ve tüm sürümler başvuruları, bilgilerin [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)sınıflarında `GetFieldInfo` üye işlevi tarafından nasıl döndürüleceğini gösterir.

Alan nesneleri bir MFC sınıfıyla temsil edilmez. Bunun yerine, aşağıdaki sınıfların MFC nesnelerini temeldeki DAO nesneleri alan nesnelerinin koleksiyonlarını içerir: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)ve [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Bu sınıflar, alan bilgilerinin bazı ayrı öğelerine erişmek için üye işlevleri sağlar veya kapsayan nesnenin `CDaoFieldInfo` `GetFieldInfo` üye işlevini çağırarak bir nesne ile tümüne tek seferde erişebilirsiniz.

Nesne özelliklerini incelemek için kullanmanın yanı sıra, bir TableDef içinde yeni `CDaoFieldInfo` alanlar oluşturmak için bir giriş parametresi oluşturmak için de kullanabilirsiniz. Bu görevde daha basit seçenekler bulunur, ancak daha hassas bir denetim istiyorsanız, bir `CDaoFieldInfo` parametre alan [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) sürümünü kullanabilirsiniz.

`GetFieldInfo` Üye işlevi tarafından alınan bilgiler (alanı içeren sınıf) bir `CDaoFieldInfo` yapıda depolanır. Fields koleksiyonundaki Field nesnesinin depolandığı kapsayan nesnenin üyeişleviniçağırın.`GetFieldInfo` `CDaoFieldInfo`Ayrıca, hata `Dump` ayıklama yapılarında bir üye işlevi tanımlar. `Dump` Bir`CDaoFieldInfo` nesnenin içeriğini dökmek için kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef:: GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset:: GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef:: GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)
