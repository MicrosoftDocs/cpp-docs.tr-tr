---
title: Cdaofieldınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure [MFC]
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aaf3f41bf6a6fe5d67ec5835d57889f6ec7dbae6
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46437698"
---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo Yapısı

`CDaoFieldInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanmış bir alan nesne hakkında bilgiler içerir.

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
Benzersiz alan nesne adları. Ayrıntılar için "Name özelliği" DAO Yardım konusuna bakın.

*m_nType*<br/>
Alanın veri türünü gösteren bir değer. Ayrıntılar için DAO Yardımı'nda "Type özelliği" konusuna bakın. Bu özelliğin değeri aşağıdakilerden biri olabilir:

- `dbBoolean` Evet/Hayır, aynı TRUE/FALSE

- `dbByte` Bayt

- `dbInteger` kısa

- `dbLong` uzun

- `dbCurrency` Para birimi; bkz: MFC sınıfı [COleCurrency](../../mfc/reference/colecurrency-class.md)

- `dbSingle` Tek

- `dbDouble` çift

- `dbDate` Tarih/saat; bkz: MFC sınıfı [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)

- `dbText` Metin; bkz: MFC sınıfı [CString](../../atl-mfc-shared/reference/cstringt-class.md)

- `dbLongBinary` Uzun İkili (OLE nesnesi); MFC sınıf kullanmak isteyebilirsiniz [CByteArray](../../mfc/reference/cbytearray-class.md) sınıfı yerine `CLongBinary` olarak `CByteArray` daha zengin ve kullanmayı daha kolay.

- `dbMemo` Not; bkz: MFC sınıfı `CString`

- `dbGUID` Genel olarak benzersiz bir tanımlayıcı/evrensel benzersiz uzaktan yordam çağrılarında kullanılan tanımlayıcı. Daha fazla bilgi için DAO Yardımı'nda "Type özelliği" konusuna bakın.

> [!NOTE]
>  Dize veri türleri için ikili verileri kullanmayın. Bu, verilerinizi artan yükü ve büyük olasılıkla beklenmeyen çeviri kaynaklanan Unicode/ANSI çeviri katmanı geçmesine neden olur.

*m_lSize*<br/>
Metin veya metin veya sayı değerlerini içeren bir alan nesne sabit boyutu içeren DAO alan nesnesinin bayt cinsinden en büyük boyutunu belirten bir değer. Ayrıntılar için DAO Yardımı'nda "boyut özelliği" konusuna bakın. Boyutları şu değerlerden biri olabilir:

|Tür|Boyut (bayt)|Açıklama|
|----------|--------------------|-----------------|
|`dbBoolean`|1 bayt|Evet/Hayır (True/False ile aynı)|
|`dbByte`|1.|Bayt|
|`dbInteger`|2|Tamsayı|
|`dbLong`|4|uzun|
|`dbCurrency`|8|Para birimi ([COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|Tek|
|`dbDouble`|8|Çift|
|`dbDate`|8|Tarih/saat ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Metin ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Uzun İkili (OLE Object; [CByteArray](../../mfc/reference/cbytearray-class.md); yerine kullanmak `CLongBinary`)|
|`dbMemo`|0|Not ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbGUID`|16|Genel olarak benzersiz bir tanımlayıcı/evrensel benzersiz uzaktan yordam çağrılarında kullanılan tanımlayıcı.|

*m_lAttributes*<br/>
Tabledef, kayıt kümesi, querydef veya dizin nesnesi tarafından içerilen bir alan nesnesinin özelliklerini belirtir. Döndürülen değer bu sabitlerin bit düzeyinde OR C++ ile oluşturulan bir toplam olarak kalabilir (**&#124;**) işleç:

- `dbFixedField` Alan boyutu (sayısal alanlar için varsayılan değer) sabit.

- `dbVariableField` Alan boyutu (yalnızca metin alanları) değişkendir.

- `dbAutoIncrField` Yeni kayıtlar için alan değeri otomatik olarak değiştirilemez bir benzersiz uzun tamsayı olarak artırılır. Yalnızca Microsoft Jet veritabanı tabloları için desteklenir.

- `dbUpdatableField` Alan değeri değiştirilebilir.

- `dbDescending` Alan azalan düzende sıralanır (Z - A veya 100 0) (yalnızca bir alanı nesnesi bir alanlar koleksiyonu dizin nesnenin; MFC, dizin nesneleri kendilerini bulunur tabledef nesneler için geçerlidir). Bu sabitin atlarsanız, alanın artan düzende sıralanır (A - Z veya 0 - 100) order (varsayılan).

Bu özellik ayarı denetlenirken C++ bit düzeyinde kullanabilirsiniz- ve işleci (**&**) için belirli bir öznitelik test etmek için. Birden çok öznitelik ayarlarken, bunları uygun sabitleri bit düzeyinde OR ile birleştirerek birleştirebilirsiniz (**&#124;**) işleci. Ayrıntılar için DAO Yardımı'nda "öznitelikleri özelliği" konusuna bakın.

*m_nOrdinalPosition*<br/>
DAO alanı nesnesi tarafından temsil edilen diğer alanlara göre görüntülenecek bir alanı istediğiniz sayısal düzenini belirten bir değeri. Bu özellik ile ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield). Ayrıntılar için DAO Yardımı'nda "OrdinalPosition özelliğini" konusuna bakın.

*m_bRequired*<br/>
DAO alanı nesnesi Null olmayan bir değer gerekli olup olmadığını gösterir. Bu özellik TRUE ise, alan Null bir değere izin vermiyor. Gerekirse yanlış olarak ayarlandığında alan AllowZeroLength ve ValidationRule özellik ayarları tarafından belirtilen koşulları karşılayan değerlerinin yanı sıra, Null değerler içerebilir. Ayrıntılar için DAO Yardımı'nda "özellik gerekiyor" konusuna bakın. Bu özellik için değer özelliği ile ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_bAllowZeroLength*<br/>
Belirtir olup boş bir dize (""), metin veya Not veri türüne sahip bir DAO alan nesnesinin geçerli bir değer. Bu özellik TRUE ise, boş bir dize geçerli bir değerdir. Bu özellik, bir alanın değerini ayarlamak için boş bir dize kullanamazsınız emin olmak için FALSE olarak ayarlayabilirsiniz. Ayrıntılar için DAO Yardımı'nda "AllowZeroLength özelliğini" konusuna bakın. Bu özellik için değer özelliği ile ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_lCollatingOrder*<br/>
Dize karşılaştırma ve sıralama için metin sıralama düzeni dizisini belirtir. Ayrıntılar için "Özelleştirme Windows kayıt defteri ayarları için veri erişim" DAO Yardım konusuna bakın. Döndürülen değerlerden bir listesi için bkz. `m_lCollatingOrder` üyesi [Cdaodatabaseınfo](../../mfc/reference/cdaodatabaseinfo-structure.md) yapısı. Bu özellik için değer özelliği ile ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strForeignName*<br/>
Bir değer, bir ilişkisi içinde birincil bir tablodaki bir alana karşılık gelen bir tablodur DAO alan nesnesinin adını belirtir. Ayrıntılar için DAO Yardımı'nda "ForeignName özelliği" konusuna bakın.

*m_strSourceField*<br/>
Özgün tabledef, kayıt kümesi veya querydef nesnesi tarafından içerilen DAO alanı nesnesi için veri kaynağı alanının adı gösterir. Bu özellik, alan nesneyle ilişkili özgün alan adını gösterir. Örneğin, özgün veri kaynağı, temel alınan tabloda alan adına ilgisiz adı olan bir sorgu alanında belirlemek için bu özelliği kullanabilirsiniz. Ayrıntılar için DAO Yardımı'ndaki "SourceField SourceTable özellikleri" bölümüne bakın. Bu özellik için değer özelliği ile ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strSourceTable*<br/>
Özgün veri kaynağı, tabledef, kayıt kümesi veya querydef nesnesi tarafından içerilen DAO alanı nesnesi için tablonun adını gösterir. Bu özellik, alan nesneyle ilişkili özgün tablo adını gösterir. Örneğin, özgün veri kaynağı, temel alınan tabloda alan adına ilgisiz adı olan bir sorgu alanında belirlemek için bu özelliği kullanabilirsiniz. Ayrıntılar için DAO Yardımı'ndaki "SourceField SourceTable özellikleri" bölümüne bakın. Bu özellik için değer özelliği ile ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strValidationRule*<br/>
Bir alandaki verileri değiştirildi veya tabloya eklenen doğrulayan bir değer. Ayrıntılar için DAO Yardımı'nda "ValidationRule özelliğini" konusuna bakın. Bu özellik için değer özelliği ile ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

Tabledefs ilgili bilgiler için bkz: `m_strValidationRule` üyesi [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) yapısı.

*m_strValidationText*<br/>
DAO alan nesne değeri ValidationRule özellik ayarı tarafından belirlenen doğrulama kuralı karşılamaz, uygulamanızın görüntülediği iletisinin metni belirten bir değeri. Ayrıntılar için DAO Yardımı'nda "ValidationText özelliği" konusuna bakın. Bu özellik için değer özelliği ile ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

*m_strDefaultValue*<br/>
DAO alan nesnenin varsayılan değeri. Yeni bir kayıt oluşturulduğunda DefaultValue özellik ayarı alan için değer olarak otomatik olarak girilir. Ayrıntılar için DAO Yardımı'nda "DefaultValue özelliği" konusuna bakın. Bu özellik için değer özelliği ile ayarlayabileceğiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).

## <a name="remarks"></a>Açıklamalar

Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek `GetFieldInfo` sınıflarındaki üye işlev [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), ve [ CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).

Alan nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, alan nesne koleksiyonları aşağıdaki sınıflar, MFC nesneleri temel alınan DAO nesneleri içeren: [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), ve [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Bu sınıfların alan bilgilerin bazı tek tek öğelere erişmek için üye işlevleri, veya bunları tamamını tek seferde erişim bir `CDaoFieldInfo` çağırarak `GetFieldInfo` kapsayan nesnenin üye işlevi.

Nesne özellikleri incelemek için kullanımı yanı sıra, ayrıca kullanabilirsiniz `CDaoFieldInfo` değer özelliği yeni alanlar oluşturmak için bir giriş parametresi oluşturmak için. Bu görev için daha basit seçenekleri kullanılabilir, ancak daha hassas bir denetim istiyorsanız sürümünü kullanabilirsiniz [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) almayan bir `CDaoFieldInfo` parametresi.

Tarafından alınan bilgileri `GetFieldInfo` sınıfının üye işlevinde (alanı içeren) depolanan bir `CDaoFieldInfo` yapısı. Çağrı `GetFieldInfo` alanı nesnesi, alanlar koleksiyonunda depolanan kapsayan nesnenin üye işlevi. `CDaoFieldInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoFieldInfo` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)<br/>
[CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)<br/>
[CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)

