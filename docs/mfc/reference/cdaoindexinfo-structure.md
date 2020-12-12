---
description: 'Daha fazla bilgi edinin: CDaoIndexInfo yapısı'
title: CDaoIndexInfo Yapısı
ms.date: 06/25/2018
f1_keywords:
- CDaoIndexInfo
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure [MFC]
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
ms.openlocfilehash: 2e09846789dc91e4d0df67665f3e975b557c07c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250770"
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo Yapısı

`CDaoIndexInfo`Yapı, veri erişim nesneleri (DAO) için tanımlanan bir dizin nesnesi hakkındaki bilgileri içerir.

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
Alan nesnesini benzersiz olarak adlandırır. Ayrıntılar için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

*m_pFieldInfos*<br/>
Bir dizin içinde hangi tabledef veya kayıt kümesi alanlarının anahtar alanları olduğunu gösteren bir [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) nesneleri dizisine yönelik bir işaretçi. Her nesne dizindeki bir alanı tanımlar. Varsayılan dizin sıralaması artan bir şekilde yapılır. Bir dizin nesnesi, her kayıt için Dizin anahtarlarını temsil eden bir veya daha fazla alana sahip olabilir. Bunlar artan, azalan veya bir bileşim olabilir.

*m_nFields*<br/>
İçinde depolanan alan sayısı `m_pFieldInfos` .

*m_bPrimary*<br/>
Birincil özelliği TRUE ise, dizin nesnesi bir birincil dizini temsil eder. Birincil dizin, bir tablodaki tüm kayıtları önceden tanımlanmış bir sırada tanımlayan bir veya daha fazla alandan oluşur. Dizin alanının benzersiz olması gerektiğinden, dizin nesnesinin benzersiz özelliği de DAO 'da TRUE olarak ayarlanır. Birincil dizin birden fazla alandan oluşuyorsa, her alan yinelenen değerler içerebilir, ancak her bir dizinli alandan değerlerin her birleşimi benzersiz olmalıdır. Birincil dizin, tablo için bir anahtardan oluşur ve genellikle birincil anahtarla aynı alanları içerir.

Bir tablo için birincil anahtar ayarladığınızda, birincil anahtar otomatik olarak tablonun birincil dizini olarak tanımlanır. Daha fazla bilgi için, DAO yardımı 'nda "birincil özellik" ve "benzersiz özellik" konularına bakın.

> [!NOTE]
> Tabloda en çok bir birincil dizin olabilir.

*m_bUnique*<br/>
Bir dizin nesnesinin bir tablo için benzersiz bir dizin temsil edip etmediğini gösterir. Bu özellik TRUE ise, Index nesnesi benzersiz olan bir dizini temsil eder. Benzersiz bir dizin, bir tablodaki tüm kayıtları benzersiz, önceden tanımlanmış bir düzende mantıksal olarak düzenleyen bir veya daha fazla alandan oluşur. Dizin bir alandan oluşuyorsa, bu alandaki değerlerin tüm tablo için benzersiz olması gerekir. Dizin birden fazla alandan oluşuyorsa, her alan yinelenen değerler içerebilir, ancak her bir dizinli alandan değerlerin her birleşimi benzersiz olmalıdır.

Bir dizin nesnesinin benzersiz ve birincil özelliklerinin her ikisi de TRUE olarak ayarlanırsa, Dizin benzersizdir ve birincil: tablodaki tüm kayıtları, önceden tanımlanmış, mantıksal bir düzende benzersiz şekilde tanımlar. Birincil özellik FALSE olarak ayarlandıysa, Dizin ikincil bir dizindir. İkincil dizinler (anahtar ve olmayan), tablodaki kayıtlar için tanımlayıcı olarak hizmet vermeden kayıtları, önceden tanımlanmış bir sırada mantıksal olarak düzenler.

Daha fazla bilgi için, DAO yardımı 'nda "birincil özellik" ve "benzersiz özellik" konularına bakın.

*m_bClustered*<br/>
Bir dizin nesnesinin bir tablonun kümelenmiş dizinini temsil edip etmediğini gösterir. Bu özellik TRUE ise, Index nesnesi bir kümelenmiş dizini temsil eder; Aksi takdirde, değildir. Kümelenmiş dizin bir veya daha fazla anahtar olmayan alandan oluşur ve bir tablodaki tüm kayıtları önceden tanımlanmış bir sırada düzenleyin. Kümelenmiş bir dizinle, tablodaki veriler, kümelenmiş dizin tarafından belirtilen sırada depolanmaz. Kümelenmiş dizin, bir tablodaki kayıtlara verimli erişim sağlar. Daha fazla bilgi için, DAO yardımı 'nda "kümelenmiş özellik" konusuna bakın.

> [!NOTE]
> Jet veritabanı altyapısı kümelenmiş dizinleri desteklemediğinden, Microsoft Jet veritabanı altyapısını kullanan veritabanları için kümelenmiş özellik yoksayılır.

*m_bIgnoreNulls*<br/>
Dizin alanlarında null değerleri olan kayıtlar için dizin girişleri olup olmadığını gösterir. Bu özellik TRUE ise, null değerlere sahip alanların bir dizin girişi yoktur. Alanı daha hızlı kullanarak kayıt aramayı yapmak için alan için bir dizin tanımlayabilirsiniz. Dizinli bir alanda null girişlere izin verirseniz ve birçok girişin null olması beklendiğinde, dizinin kullandığı depolama alanı miktarını azaltmak için dizin nesnesi için IgnoreNulls özelliğini TRUE olarak ayarlayabilirsiniz. IgnoreNulls özellik ayarı ve gerekli özellik ayarı birlikte, aşağıdaki tabloda gösterildiği gibi, null dizin değeri olan bir kaydın bir dizin girişi olup olmadığını belirtir.

|IgnoreNulls|Gerekli|Dizin alanında null|
|-----------------|--------------|-------------------------|
|Doğru|Yanlış|Null değere izin verilir; Dizin girişi eklenmedi.|
|Yanlış|Yanlış|Null değere izin verilir; Dizin girişi eklendi.|
|True veya false|Doğru|Null değere izin verilmiyor; Dizin girişi eklenmedi.|

Daha fazla bilgi için, DAO yardımı 'nda "IgnoreNulls özelliği" konusuna bakın.

*m_bRequired*<br/>
Bir DAO dizin nesnesinin null olmayan bir değer gerektirip gerektirmediğini belirtir. Bu özellik TRUE ise, dizin nesnesi null değere izin vermez. Daha fazla bilgi için, DAO yardımı 'nda "gerekli özellik" konusuna bakın.

> [!TIP]
> Bu özelliği bir DAO dizin nesnesi veya alan nesnesi (örneğin, bir TableDef, Recordset veya QueryDef nesnesi) için ayarlarsanız, alan nesnesi için ayarlayın. Bir Field nesnesi için özellik ayarının geçerliliği, Dizin nesnesinden önce denetlenir.

*m_bForeign*<br/>
Bir dizin nesnesinin bir tablodaki yabancı anahtarı temsil edip etmediğini gösterir. Bu özellik TRUE ise, dizin bir tablodaki yabancı anahtarı temsil eder. Yabancı anahtar, yabancı bir tablodaki bir veya daha fazla alandan oluşur ve birincil tablodaki bir satırı benzersiz bir şekilde tanımlar. Microsoft Jet veritabanı altyapısı, yabancı tablo için bir dizin nesnesi oluşturur ve başvurusal bütünlüğü zorlayan bir ilişki oluşturduğunuzda yabancı özelliği ayarlar. Daha fazla bilgi için, DAO yardımı 'nda "yabancı özellik" konusuna bakın.

*m_lDistinctCount*<br/>
İlişkili tabloya dahil edilen dizin nesnesi için benzersiz değerlerin sayısını gösterir. Bir dizinde benzersiz değer veya anahtar sayısını öğrenmek için Dıstıntcount özelliğini denetleyin. Her anahtar yalnızca bir kez sayılır, ancak dizin yinelenen değerlere izin veriyorsa bu değerin birden çok tekrarı olabilir. Bu bilgiler, dizin bilgilerini değerlendirerek veri erişimini optimize etmeye çalışacak uygulamalarda yararlıdır. Benzersiz değer sayısı bir dizin nesnesinin kardinalitesi olarak da bilinir. Dıstıntcount özelliği, belirli bir zamanda gerçek anahtar sayısını her zaman yansıtmayacaktır. Örneğin, bir işlem geri almanın neden olduğu bir değişiklik, Dıstıntcount özelliğinde hemen yansıtılmayacaktır. Daha fazla bilgi için, DAO yardımı 'nda "Dıstıntcount özelliği" konusuna bakın.

## <a name="remarks"></a>Açıklamalar

Birincil, Ikincil ve tüm sürümler başvuruları, bilgilerin `GetIndexInfo` [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)' teki üye işlevi tarafından nasıl döndürüleceğini gösterir.

Dizin nesneleri bir MFC sınıfıyla temsil edilmez. Bunun yerine, [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) veya [CDAORECORDSET](../../mfc/reference/cdaorecordset-class.md) sınıfının MFC nesnelerini temel alan DAO nesneleri, dizinler koleksiyonu olarak adlandırılan dizin nesnelerinin bir koleksiyonunu içerir. Bu sınıflar, dizin bilgilerinin tek tek öğelerine erişmek için üye işlevleri sağlar veya `CDaoIndexInfo` `GetIndexInfo` kapsayan nesnenin üye işlevini çağırarak bir nesne ile tümüne tek seferde erişebilirsiniz.

`CDaoIndexInfo` içindeki dizin alanı bilgilerini doğru bir şekilde ayırmak ve serbest bırakmak için bir oluşturucuya ve yok ediciye sahiptir `m_pFieldInfos` .

`GetIndexInfo`Bir TableDef nesnesinin üye işlevi tarafından alınan bilgiler bir `CDaoIndexInfo` yapıda depolanır. `GetIndexInfo`Dizinler koleksiyonu dizin nesnesinin depolandığı içeren TableDef nesnesinin üye işlevini çağırın. `CDaoIndexInfo` Ayrıca `Dump` , hata ayıklama yapılarında bir üye işlevi tanımlar. `Dump`Bir nesnenin içeriğini dökmek için kullanabilirsiniz `CDaoIndexInfo` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef:: GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)
