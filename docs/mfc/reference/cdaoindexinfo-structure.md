---
title: Cdaoındexınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 06/25/2018
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CDaoIndexInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2cfeaada169addc01bc09893db0dedba2b7528d0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46403116"
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo Yapısı

`CDaoIndexInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanmış bir dizin nesne hakkında bilgiler içerir.

## <a name="syntax"></a>Sözdizimi

```cpp
struct CDaoIndexInfo {
    CDaoIndexInfo();                    // Constructor
    CString m_strName;                  // Primary
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary
    short m_nFields;                    // Primary
    BOOL m_bPrimary;                    // Secondary
    BOOL m_bUnique;                     // Secondary
    BOOL m_bClustered;                  // Secondary
    BOOL m_bIgnoreNulls;                // Secondary
    BOOL m_bRequired;                   // Secondary
    BOOL m_bForeign;                    // Secondary
    long m_lDistinctCount;              // All

    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

### <a name="parameters"></a>Parametreler

*m_strName*<br/>
Benzersiz alan nesne adları. Ayrıntılar için "Name özelliği" DAO Yardım konusuna bakın.

*m_pFieldInfos*<br/>
Bir dizi işaretçi [Cdaoındexfieldınfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) hangi tabledef ya da kayıt bir dizinde anahtar alanları alanları gösteren nesne. Her nesne bir alan olarak tanımlar. Varsayılan dizin Sıralama artan düzendedir. Bir dizin nesnesi, her kayıt için dizin anahtarlarının temsil eden bir veya daha fazla alan sahip olabilir. Bunlar, azalan, veya bir birleşimini artan.

*M_nFields*<br/>
Depolanan alanların sayısını `m_pFieldInfos`.

*m_bPrimary*<br/>
Dizin nesnesi, birincil özelliği TRUE ise, birincil dizin temsil eder. Önceden tanımlanmış bir sırada bir tablodaki tüm kayıtları benzersiz olarak tanımlayan bir veya daha fazla alan birincil dizin oluşur. Dizin alanı benzersiz olması gerektiğinden, benzersiz dizin nesnesinin özelliğini de true olarak DAO ayarlanır. Birincil dizin birden fazla alanı oluşuyorsa, her alan, yinelenen değerler içerebilir, ancak her dizini oluşturulmuş tüm alanların değerlerinden bileşimi benzersiz olması gerekir. Birincil dizin tablosu için bir anahtar içerir ve genellikle birincil anahtarı olarak aynı alanları içerir.

Bir tablonun birincil anahtar ayarladığınızda, birincil anahtar tablosu için birincil dizin olarak otomatik olarak tanımlanır. Daha fazla bilgi için "birincil" ve "Benzersiz özelliğini" DAO Yardımı'ndaki konulara bakın.

> [!NOTE]
> Olabilir, en fazla bir tabloda bir birincil dizin.

*m_bUnique*<br/>
Bir dizin nesnesi bir tablo için benzersiz bir dizin temsil edip etmediğini belirtir. Bu özellik TRUE ise dizin nesnesi, benzersiz bir dizin temsil eder. Benzersiz, önceden tanımlanmış bir sırada bir tablodaki tüm kayıtları mantıksal olarak düzenlemek bir veya daha fazla alan benzersiz bir dizin oluşur. Dizin bir alanda oluşuyorsa, bu alandaki değerlerin tüm tablo için benzersiz olmalıdır. Dizin birden fazla alanı oluşuyorsa, her alan, yinelenen değerler içerebilir, ancak her dizini oluşturulmuş tüm alanların değerlerinden bileşimi benzersiz olması gerekir.

Bir dizin nesnenin benzersiz ve birincil özelliklerini TRUE olarak ayarlarsanız, benzersiz ve birincil dizinidir: önceden tanımlanmış, mantıksal bir sırada tablosundaki tüm kayıtlar benzersiz olarak tanımlar. Birincil özelliği FALSE olarak ayarlarsanız, dizin ikincil bir dizindir. İkincil dizinler (anahtar ve anahtarı olmayan) bir tablodaki kayıtları tanımlayıcısı olarak hizmet veren olmadan kayıtları önceden tanımlanmış bir düzende mantıksal olarak düzenleyin.

Daha fazla bilgi için "birincil" ve "Benzersiz özelliğini" DAO Yardımı'ndaki konulara bakın.

*m_bClustered*<br/>
Bir dizin nesnesi bir tablo için kümelenmiş bir dizin temsil edip etmediğini belirtir. Bu özellik TRUE ise, dizin nesnesi, bir kümelenmiş dizin temsil eder; Aksi takdirde yok. Kümelenmiş bir dizin birini oluşur veya daha fazla tuşdışı alanları, birlikte ele alındığında, önceden tanımlanmış bir sırada bir tablodaki tüm kayıtları düzenleyin. Kümelenmiş bir dizin ile bir tablodaki verileri tam anlamıyla kümelenmiş dizini tarafından belirtilen sırada depolanır. Kümelenmiş bir dizin, bir tablodaki kayıtların verimli erişim sağlar. Daha fazla bilgi için DAO Yardımı'nda "özelliği kümelenmiş" konusuna bakın.

> [!NOTE]
> Kümelenmiş özelliği, Jet veritabanı altyapısı Kümelenmiş dizinler desteklemediğinden, Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için göz ardı edilir.

*m_bIgnoreNulls*<br/>
Dizin alanlarında Null değerlere sahip kayıtlar için dizin girdileri olup olmadığını gösterir. Bu özellik TRUE ise, Null değerlerini dizin girdisi yok. Kayıt bir alan daha hızlı bir şekilde kullanarak arama yapmak için alan için dizin tanımlayabilirsiniz. Dizinlenmiş bir alanda Null girişlere izin vermek ve Null olmasına izin girişleri birçoğu beklediğiniz özelliğini dizin nesnesi için dizinin kullandığı depolama alanı miktarını azaltmak için TRUE olarak ayarlayabilirsiniz. Birlikte IgnoreNulls özelliği ayarı ve gerekli özellik ayarı bir dizin değeri içeren bir kayıt aşağıdaki tabloda gösterildiği gibi bir dizin girişi olup olmadığını belirleyin.

|IgnoreNulls|Gerekli|Dizin alanı null|
|-----------------|--------------|-------------------------|
|Doğru|False|İzin verilen null değer; Dizin girişi eklenir.|
|False|False|İzin verilen null değer; Dizin girişi eklenir.|
|TRUE veya False|Doğru|Null değere izin verilmez; Dizin girişi eklenir.|

Daha fazla bilgi için DAO Yardımı'nda "IgnoreNulls özelliğini" konusuna bakın.

*m_bRequired*<br/>
DAO dizin nesnesi Null olmayan bir değer gerekli olup olmadığını gösterir. Bu özellik TRUE ise, dizin nesnesi Null bir değere izin vermiyor. Daha fazla bilgi için DAO Yardımı'nda "özellik gerekiyor" konusuna bakın.

> [!TIP]
> Bu özellik DAO dizin nesnesi veya bir alan nesnesi (tabledef, kayıt kümesi veya QueryDefs yer alan) için ayarlayabileceğiniz alan nesne için ayarlanır. Bir alanı nesnesi için özellik ayarı geçerliliğini, bir dizin nesne önce denetlenir.

*m_bForeign*<br/>
Bir dizin nesne tablosundaki yabancı anahtar temsil edip etmediğini belirtir. Bu özellik TRUE ise dizin tablosundaki yabancı anahtar temsil eder. Yabancı anahtar, yabancı bir tabloda bir birincil tablosunda bir satırı benzersiz olarak tanımlanabilmesi bir veya daha fazla alan oluşur. Microsoft Jet veritabanı altyapısı, yabancı bir tablo için bir dizin nesnesi oluşturur ve bilgi tutarlılığını zorlar bir ilişki oluşturduğunuzda yabancı özelliği ayarlar. Daha fazla bilgi için DAO Yardımı'nda "yabancı özelliği" konusuna bakın.

*m_lDistinctCount*<br/>
Dizin nesne için ilişkili tabloda bulunan benzersiz değerlerin sayısını gösterir. Benzersiz değerler ya da dizin anahtarlarında sayısını belirlemek için DistinctCount özelliğini denetleyin. Olabilir olsa da bu değer birden çok defa geçmelerine dizin yinelenen değerler veriyorsa herhangi bir tuşa yalnızca bir kez sayılır. Bu bilgiler dizin bilgilerini değerlendirerek veri erişimini iyileştirmek için uygulamalarda kullanışlıdır. Benzersiz değerlerin sayısını bir dizin nesnenin kardinalite de denir. DistinctCount özelliği her zaman belirli bir zamanda anahtar gerçek sayısı yansıtmaz. Örneğin, bir işlemi geri alma tarafından neden değişikliği hemen DistinctCount özelliğinde yansıtılmaz. Daha fazla bilgi için DAO Yardımı'nda "DistinctCount özelliği" konusuna bakın.

## <a name="remarks"></a>Açıklamalar

Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek `GetIndexInfo` sınıflarındaki üye işlev [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).

Dizin nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, DAO temel alınan MFC sınıfın nesneleri [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) dizinler koleksiyonu adlı dizin nesnelerinin bir koleksiyonu içerir. Bu sınıfların tek tek öğelerine dizin bilgilerinin erişmek için üye işlevleri, veya bunları tamamını tek seferde erişim bir `CDaoIndexInfo` çağırarak `GetIndexInfo` kapsayan nesnenin üye işlevi.

`CDaoIndexInfo` bir oluşturucu ve yıkıcı düzgün bir şekilde ayırmak ve dizin alan bilgilerini ayırması için `m_pFieldInfos`.

Tarafından alınan bilgileri `GetIndexInfo` tabledef nesnesinin üye işlevi depolanan bir `CDaoIndexInfo` yapısı. Çağrı `GetIndexInfo` dizin nesnesi, dizinleri koleksiyonda depolanan kapsayan tabledef nesnenin üye işlevi. `CDaoIndexInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoIndexInfo` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)
