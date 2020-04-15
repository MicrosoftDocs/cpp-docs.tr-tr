---
title: CDaoFieldInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
ms.openlocfilehash: 9466386fefc6e5ab8fcf89bf497c1d5219e3e807
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368405"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo Yapısı

Yapı, `CDaoFieldInfo` veri erişim nesneleri (DAO) için tanımlanan bir alan nesnesi hakkında bilgi içerir.

DAO, Office 2013 aracılığıyla desteklenir. DAO 3.6 son sürümüdür ve eski miş olarak kabul edilir.

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
Alan nesnesini benzersiz olarak adlandırır. Ayrıntılar için DAO Yardım'daki "Ad Özelliği" konusuna bakın.

*m_nType*<br/>
Alanın veri türünü gösteren bir değer. Ayrıntılar için DAO Yardım'daki "Özellik Yazın" konusuna bakın. Bu özelliğin değeri aşağıdakilerden biri olabilir:

- `dbBoolean`Evet/Hayır, DOĞRU/YANLIŞ ile aynı

- `dbByte`Bayt

- `dbInteger`Kısa

- `dbLong`Uzun

- `dbCurrency`Para birimi; bkz. MFC sınıfı [COleCurrency](../../mfc/reference/colecurrency-class.md)

- `dbSingle`Tek

- `dbDouble`Çift

- `dbDate`Tarih/Saat; bkz. MFC sınıfı [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText`Metin; bkz. MFC sınıfı [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary`Uzun İkili (OLE Nesnesi); daha zengin ve kullanımı daha kolay olduğu için `CLongBinary` `CByteArray` sınıf yerine MFC sınıfı [CByteArray'i](../../mfc/reference/cbytearray-class.md) kullanmak isteyebilirsiniz.

- `dbMemo`Not; bkz. MFC sınıfı`CString`

- `dbGUID`Uzak yordam çağrıları yla kullanılan Genel Olarak Benzersiz Tanımlayıcı/Evrensel Benzersiz Tanımlayıcı. Daha fazla bilgi için DAO Yardım'daki "Özellik Yazın" konusuna bakın.

> [!NOTE]
> İkili veri için dize veri türlerini kullanmayın. Bu, verilerinizin Unicode/ANSI çeviri katmanından geçmesine neden olur ve bu da ek yükün artmasına ve muhtemelen beklenmeyen çeviriye neden olur.

*m_lSize*<br/>
Metin veya sayısal değerler içeren bir alan nesnesinin sabit boyutunu içeren bir DAO alan nesnesinin baytlarda maksimum boyutunu gösteren değer. Ayrıntılar için DAO Yardım'daki "Boyut Özelliği" konusuna bakın. Boyutlar aşağıdaki değerlerden biri olabilir:

|Tür|Boyut (Bayt)|Açıklama|
|----------|--------------------|-----------------|
|`dbBoolean`|1 bayt|Evet/Hayır (True/False ile aynı)|
|`dbByte`|1|Bayt|
|`dbInteger`|2|Tamsayı|
|`dbLong`|4|Uzun|
|`dbCurrency`|8|Para Birimi ([COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Tek|
|`dbDouble`|8|Çift|
|`dbDate`|8|Tarih/Saat ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Metin ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Uzun İkili (OLE Nesnesi; [CByteArray](../../mfc/reference/cbytearray-class.md); yerine `CLongBinary`kullanın )|
|`dbMemo`|0|Not ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|Uzak yordam çağrıları yla kullanılan Genel Olarak Benzersiz Tanımlayıcı/Evrensel Benzersiz Tanımlayıcı.|

*m_lAttributes*<br/>
Tablodef, recordset, querydef veya dizin nesnesi tarafından bulunan bir alan nesnesinin özelliklerini belirtir. Döndürülen değer, C++ bitwise-OR (**&#124;**) işleci ile oluşturulan bu sabitlerin toplamı olabilir:

- `dbFixedField`Alan boyutu sabittir (Sayısal alanlar için varsayılan).

- `dbVariableField`Alan boyutu değişkendir (yalnızca Metin alanları).

- `dbAutoIncrField`Yeni kayıtların alan değeri otomatik olarak değiştirilemeyen benzersiz uzun bir tamsayıya dönüştürülr. Yalnızca Microsoft Jet veritabanı tabloları için desteklenir.

- `dbUpdatableField`Alan değeri değiştirilebilir.

- `dbDescending`Alan azalan (Z - A veya 100 - 0) sırasına göre sıralanır (yalnızca dizin nesnesinin Alanlar koleksiyonundaki bir alan nesnesi için geçerlidir; MFC'de dizin nesneleri tablodef nesnelerinde bulunur). Bu sabiti atlarsanız, alan artan (A - Z veya 0 - 100) sırada (varsayılan) sıralanır.

Bu özelliğin ayarını denetlerken, belirli bir öznitelik**&** için test etmek için C++ bitwise-AND işleci () kullanabilirsiniz. Birden çok öznitelik ayarlarken, uygun sabitleri bitwise-OR** (&#124;**) işleciyle birleştirerek bunları birleştirebilirsiniz. Ayrıntılar için DAO Yardım'daki "Öznitelikler Özelliği" konusuna bakın.

*m_nOrdinalPosition*<br/>
Dao alan nesnesi tarafından temsil edilen bir alanın diğer alanlara göre görüntülenmesini istediğiniz sayısal sırayı belirten bir değer. Bu özelliği [CDaoTableDef ile ayarlayabilirsiniz::CreateField.](../../mfc/reference/cdaotabledef-class.md#createfield) Ayrıntılar için DAO Yardım'daki "OrdinalPosition Özelliği" konusuna bakın.

*m_bRequired*<br/>
DAO alan nesnesi Null olmayan bir değer gerektirip gerektirmediğini gösterir. Bu özellik TRUE ise, alan Null değerine izin vermez. Gerekli FALSE olarak ayarlanırsa, alan Null değerlerinin yanı sıra AllowZeroLength ve ValidationRule özellik ayarları tarafından belirtilen koşulları karşılayan değerler içerebilir. Ayrıntılar için DAO Yardım'daki "Gerekli Özellik" konusuna bakın. CDaoTableDef ile bir tablo için bu özelliği [ayarlayabilirsiniz::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_bAllowZeroLength*<br/>
Boş bir dize ("") Metin veya Not veri türüne sahip bir DAO alan nesnesinin geçerli bir değeri olup olmadığını gösterir. Bu özellik TRUE ise, boş bir dize geçerli bir değerdir. Bir alanın değerini ayarlamak için boş bir dize kullanamadığınızdan emin olmak için bu özelliği FALSE olarak ayarlayabilirsiniz. Ayrıntılar için DAO Yardım'daki "AllowZeroLength Özelliği" konusuna bakın. CDaoTableDef ile bir tablo için bu özelliği [ayarlayabilirsiniz::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_lCollatingOrder*<br/>
Dize karşılaştırması veya sıralama için metindeki sıralama sırasının sırasını belirtir. Ayrıntılar için DAO Yardım'da "Veri Erişimi için Windows Kayıt Defteri Ayarlarını Özelleştirme" konusuna bakın. Döndürülen olası değerlerin listesi için `m_lCollatingOrder` [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) yapısının üyesine bakın. CDaoTableDef ile bir tablo için bu özelliği [ayarlayabilirsiniz::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strForeignName*<br/>
Bir ilişkide, birincil tablodaki bir alana karşılık gelen yabancı bir tablodaki DAO alan nesnesinin adını belirten bir değer. Ayrıntılar için DAO Help'deki "ForeignName Property" konusuna bakın.

*m_strSourceField*<br/>
Tabledef, recordset veya querydef nesnesi tarafından bulunan DAO alan nesnesinin orijinal kaynağı olan alanın adını gösterir. Bu özellik, bir alan nesnesi ile ilişkili özgün alan adını gösterir. Örneğin, adı alttaki tablodaki alanın adıyla ilgisi olmayan bir sorgu alanındaki verilerin özgün kaynağını belirlemek için bu özelliği kullanabilirsiniz. Ayrıntılar için DAO Yardım'daki "SourceField, SourceTable Properties" konusuna bakın. CDaoTableDef ile bir tablo için bu özelliği [ayarlayabilirsiniz::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strSourceTable*<br/>
Tabledef, recordset veya querydef nesnesi tarafından bulunan DAO alan nesnesinin orijinal kaynağı olan tablonun adını gösterir. Bu özellik, bir alan nesnesi ile ilişkili özgün tablo adını gösterir. Örneğin, adı alttaki tablodaki alanın adıyla ilgisi olmayan bir sorgu alanındaki verilerin özgün kaynağını belirlemek için bu özelliği kullanabilirsiniz. Ayrıntılar için DAO Yardım'daki "SourceField, SourceTable Properties" konusuna bakın. CDaoTableDef ile bir tablo için bu özelliği [ayarlayabilirsiniz::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strValidationRule*<br/>
Tablodeğiştirildikçe veya eklendikçe alandaki verileri doğrulayan değer. Ayrıntılar için DAO Yardım'daki "Doğrulama Kuralı Özelliği" konusuna bakın. CDaoTableDef ile bir tablo için bu özelliği [ayarlayabilirsiniz::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

Tabledefs hakkında ilgili bilgiler `m_strValidationRule` [için, CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) yapısının üyesine bakın.

*m_strValidationText*<br/>
Bir DAO alan nesnesinin değeri Doğrulama Kuralı özellik ayarı tarafından belirtilen doğrulama kuralını karşılamazsa, uygulamanızın görüntülediği iletimetnini belirten bir değer. Ayrıntılar için DAO Yardım'daki "Doğrulama Metni Özelliği" konusuna bakın. CDaoTableDef ile bir tablo için bu özelliği [ayarlayabilirsiniz::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strDefaultValue*<br/>
DAO alan nesnesinin varsayılan değeri. Yeni bir kayıt oluşturulduğunda, Varsayılan Değer özellik ayarı alanın değeri olarak otomatik olarak girilir. Ayrıntılar için DAO Yardım'daki "DefaultValue Özelliği" konusuna bakın. CDaoTableDef ile bir tablo için bu özelliği [ayarlayabilirsiniz::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

## <a name="remarks"></a>Açıklamalar

Birincil, İkincil ve Tüm yukarıda başvurular nasıl bilgi `GetFieldInfo` [sınıflarcDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)üye işlevi tarafından döndürülür gösterir , [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).

Alan nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, aşağıdaki sınıfların MFC nesnelerinin altında yatan DAO nesneleri alan nesnelerinin koleksiyonlarını içerir: [CDaoTableDef,](../../mfc/reference/cdaotabledef-class.md) [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)ve [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Bu sınıflar, alan bilgilerinin bazı bireysel öğelerine erişmek için üye işlevleri `CDaoFieldInfo` sağlar veya `GetFieldInfo` içeren nesnenin üye işlevini çağırarak bir nesneyle hepsine aynı anda erişebilirsiniz.

Nesne özelliklerini incelemek için kullanımının yanı `CDaoFieldInfo` sıra, bir tablodef yeni alanlar oluşturmak için bir giriş parametresi oluşturmak için de kullanabilirsiniz. Bu görev için daha basit seçenekler mevcuttur, ancak daha hassas bir denetim istiyorsanız, [cdaoTableDef sürümünü kullanabilirsiniz::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) bir `CDaoFieldInfo` parametre alır.

`GetFieldInfo` Üye işlev (alanı içeren sınıfın) tarafından alınan bilgiler bir `CDaoFieldInfo` yapıda depolanır. Alanları `GetFieldInfo` alan nesnesi depolanan içeren nesnenin üye işlevini çağırın. `CDaoFieldInfo`ayrıca hata `Dump` ayıklama yapılarında bir üye işlev tanımlar. Bir `Dump` `CDaoFieldInfo` nesnenin içeriğini dökümü için kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Aramalar ve İleti Haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)
