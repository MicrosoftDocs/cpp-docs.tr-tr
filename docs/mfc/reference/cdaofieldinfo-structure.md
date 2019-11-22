---
title: CDaoFieldInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: e2638ac908e4e286530301bc913173e87008df47
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303696"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo Yapısı

`CDaoFieldInfo` yapısı, veri erişim nesneleri (DAO) için tanımlanan alan nesnesi hakkında bilgi içerir.

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

- Evet/Hayır, doğru/yanlış ile aynı `dbBoolean`

- `dbByte` bayt

- `dbInteger` kısa

- `dbLong` Long

- `dbCurrency` para birimi; bkz. MFC sınıfı [Colet para birimi](../../mfc/reference/colecurrency-class.md)

- Tek `dbSingle`

- `dbDouble` Double

- `dbDate` tarih/saat; bkz. MFC sınıfı [Cotatarihsaat](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText` metin; bkz. MFC sınıfı [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary` Long Binary (OLE nesnesi); `CByteArray` daha zengin ve kullanımı daha kolay olduğundan `CLongBinary` sınıf yerine bir MFC sınıfı [CByteArray](../../mfc/reference/cbytearray-class.md) kullanmak isteyebilirsiniz.

- `dbMemo` faturası; bkz. MFC sınıfı `CString`

- uzak yordam çağrılarında kullanılan genel benzersiz tanımlayıcı/evrensel benzersiz tanımlayıcı `dbGUID`. Daha fazla bilgi için, DAO yardımı 'nda "tür özelliği" konusuna bakın.

> [!NOTE]
>  İkili veriler için dize veri türleri kullanmayın. Bu, verilerinizin Unicode/ANSI çeviri katmanından geçmesine neden olur ve bu da daha fazla ek yük ve muhtemelen beklenmeyen çeviri sağlar.

*m_lSize*<br/>
Metin veya sayısal değerler içeren bir alan nesnesinin sabit boyutunu veya metin içeren bir DAO alanı nesnesinin en büyük boyutunu bayt cinsinden belirten bir değer. Ayrıntılar için, DAO yardımı 'nda "boyut özelliği" konusuna bakın. Boyutlar aşağıdaki değerlerden biri olabilir:

|Type|Boyut (bayt)|Açıklama|
|----------|--------------------|-----------------|
|`dbBoolean`|1 bayt|Evet/Hayır (true/false ile aynı)|
|`dbByte`|1\.|Bayt|
|`dbInteger`|2|Tamsayı|
|`dbLong`|4|Uzun|
|`dbCurrency`|8|Para birimi ([Copapara birimi](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Tek|
|`dbDouble`|8|Çift|
|`dbDate`|8|Tarih/saat ([Copadatetime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Metin ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Long Binary (OLE nesnesi; [CByteArray](../../mfc/reference/cbytearray-class.md); `CLongBinary`yerine kullanın)|
|`dbMemo`|0|Memo ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|Uzak yordam çağrılarında kullanılan, genel olarak benzersiz tanımlayıcı/evrensel benzersiz tanımlayıcı.|

*m_lAttributes*<br/>
Bir TableDef, Recordset, QueryDef veya Index nesnesi tarafından içerilen bir Field nesnesinin karakteristiklerini belirtir. Döndürülen değer, C++ BIT düzeyinde OR ( **&#124;** ) işleciyle oluşturulan bu sabitlerin toplamı olabilir:

- `dbFixedField` alan boyutu sabittir (sayısal alanlar için varsayılan).

- alan boyutu değişken (yalnızca metin alanları) `dbVariableField`.

- Yeni kayıtlar için alan değeri `dbAutoIncrField`, değiştirilemeyen benzersiz bir uzun tamsayıya otomatik olarak artırılır. Yalnızca Microsoft Jet veritabanı tabloları için desteklenir.

- `dbUpdatableField` alan değeri değiştirilebilir.

- `dbDescending` alan azalan (Z-A veya 100-0) düzende sıralanır (yalnızca bir dizin nesnesinin Fields koleksiyonundaki Field nesnesi için geçerlidir; MFC 'de, dizin nesnelerinin kendisi TableDef nesnelerinde bulunur). Bu sabiti atlarsanız, alan artan (A-Z veya 0-100) bir düzende sıralanır (varsayılan).

Bu özelliğin ayarını denetlerken, belirli bir özniteliği sınamak için C++ BIT düzeyinde and işlecini ( **&** ) kullanabilirsiniz. Birden çok öznitelik ayarlarken, bit düzeyinde OR ( **&#124;** ) işleciyle uygun sabitleri birleştirerek bunları birleştirebilirsiniz. Ayrıntılar için, DAO yardımı 'nda "öznitelikler özelliği" konusuna bakın.

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

TableDefs hakkında ilgili bilgi için, [Cdaotabledefinınfo](../../mfc/reference/cdaotabledefinfo-structure.md) yapısının `m_strValidationRule` üyesine bakın.

*m_strValidationText*<br/>
Bir DAO alan nesnesinin değeri ValidationRule özelliği ayarı tarafından belirtilen doğrulama kuralına uygun değilse uygulamanızın görüntüleyeceği iletinin metnini belirten bir değer. Ayrıntılar için, DAO yardımı 'nda "ValidationText özelliği" konusuna bakın. Bu özelliği, [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)ile bir TableDef için ayarlayabilirsiniz.

*m_strDefaultValue*<br/>
Bir DAO alan nesnesinin varsayılan değeri. Yeni bir kayıt oluşturulduğunda, DefaultValue özellik ayarı, alanın değeri olarak otomatik olarak girilir. Ayrıntılar için, DAO yardımı 'nda "DefaultValue özelliği" konusuna bakın. Bu özelliği, [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield)ile bir TableDef için ayarlayabilirsiniz.

## <a name="remarks"></a>Açıklamalar

Birincil, Ikincil ve tüm sürümler başvuruları, bilgilerin [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)sınıflarında `GetFieldInfo` üye işlevi tarafından nasıl döndürüleceğini gösterir.

Alan nesneleri bir MFC sınıfıyla temsil edilmez. Bunun yerine, aşağıdaki sınıfların MFC nesnelerini temeldeki DAO nesneleri alan nesnelerinin koleksiyonlarını içerir: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)ve [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Bu sınıflar, alan bilgilerinin bazı ayrı öğelerine erişmek için üye işlevleri sağlar veya kapsayan nesnenin `GetFieldInfo` üye işlevini çağırarak bir `CDaoFieldInfo` nesnesi ile tümüne tek seferde erişebilirsiniz.

Nesne özelliklerini incelemek için kullanmanın yanı sıra, bir TableDef içinde yeni alanlar oluşturmak için bir giriş parametresi oluşturmak üzere `CDaoFieldInfo` de kullanabilirsiniz. Bu görevde daha basit seçenekler bulunur, ancak daha hassas bir denetim istiyorsanız, bir `CDaoFieldInfo` parametresi alan [CDaoTableDef:: CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) sürümünü kullanabilirsiniz.

`GetFieldInfo` üye işlevi tarafından alınan bilgiler (alanı içeren sınıfın) `CDaoFieldInfo` yapısında depolanır. Fields koleksiyonundaki Field nesnesinin depolandığı kapsayan nesnenin `GetFieldInfo` üye işlevini çağırın. `CDaoFieldInfo` Ayrıca hata ayıklama yapılarında bir `Dump` member işlevi tanımlar. Bir `CDaoFieldInfo` nesnesinin içeriğini dökmek için `Dump` kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef:: GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset:: GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef:: GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)
