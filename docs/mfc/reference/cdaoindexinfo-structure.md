---
title: Cdaoındexınfo yapısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: 3d8c98181a9ec049308d7b85e57c028740927cc2
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo Yapısı
`CDaoIndexInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanan bir dizin nesne hakkında bilgiler içerir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
struct CDaoIndexInfo {  
    CDaoIndexInfo();
*// Constructor  
    CString m_strName;  // Primary  
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary  
    short m_nFields;    // Primary  
    BOOL m_bPrimary;    // Secondary  
    BOOL m_bUnique;     // Secondary  
    BOOL m_bClustered;  // Secondary  
    BOOL m_bIgnoreNulls;                // Secondary  
    BOOL m_bRequired;   // Secondary  
    BOOL m_bForeign;    // Secondary  
    long m_lDistinctCount;              // All  
 *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};   
```  
  
#### <a name="parameters"></a>Parametreler  
 `m_strName`  
 Alan nesne adlandıran. Ayrıntılar için DAO Yardımı'ndaki "Name özelliği" konusuna bakın.  
  
 `m_pFieldInfos`  
 Bir dizi için bir işaretçi [Cdaoındexfieldınfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) hangi tabledef veya kayıt bir dizinde anahtar alanları alanlardır gösteren nesne. Her nesnenin dizin içindeki bir alanı tanımlar. Varsayılan dizin Sıralama artan. Bir dizin nesnesi, her kayıt için dizin anahtarlarının temsil eden bir veya daha fazla alan sahip olabilir. Bunlar, azalan, veya bir birleşimini artan.  
  
 `m_nFields`  
 Depolanan alan sayısını `m_pFieldInfos`.  
  
 *m_bPrimary*  
 Birincil özelliği olan ise **doğru**, dizin nesnesi birincil dizin temsil eder. Önceden tanımlı bir sırada bir tablodaki tüm kayıtları benzersiz şekilde tanımlayan bir veya daha fazla alan, birincil dizin oluşur. Dizin alanın benzersiz olması gerektiğinden dizin nesnesinin benzersiz özelliği de ayarlanır **TRUE** DAO içinde. Birincil dizin birden fazla alanı oluşuyorsa, her bir alan yinelenen değerler içerebilir, ancak tüm dizinli alanlardan değerlerin her birleşimi benzersiz olmalıdır. Birincil dizin tablo için bir anahtar içerir ve genellikle birincil anahtarı aynı alanları içerir.  
  
 Bir tablo için bir birincil anahtar ayarladığınızda, birincil anahtar tablosunun birincil dizin olarak otomatik olarak tanımlanır. Daha fazla bilgi için "Birincil özelliği" ve "Benzersiz özelliğinde" DAO Yardım konularına bakın.  
  
> [!NOTE]
>  Olabilir, en fazla bir tabloda bir birincil dizin.  
  
 *m_bUnique*  
 Bir dizin nesnesi bir tablo için benzersiz bir dizin temsil edip etmediğini gösterir. Bu özellik ise **doğru**, dizin nesnesi benzersiz bir dizin temsil eder. Benzersiz bir dizin mantıksal olarak benzersiz, önceden tanımlanmış bir sırada bir tablodaki tüm kayıtları düzenleyen bir veya daha fazla alandan oluşur. Dizin bir alanın oluşuyorsa, bu alandaki değerlerin tüm tablosu için benzersiz olmalıdır. Dizin birden fazla alanı oluşuyorsa, her bir alan yinelenen değerler içerebilir, ancak tüm dizinli alanlardan değerlerin her birleşimi benzersiz olmalıdır.  
  
 Bir dizin nesnenin benzersiz ve birincil özelliği ayarlandıysa **TRUE**, benzersiz ve birincil dizin: önceden tanımlanmış, mantıksal bir sırada tablosundaki tüm kayıtları benzersiz şekilde tanımlar. Birincil özelliği ayarlanmışsa **yanlış**, dizin ikincil bir dizindir. İkincil dizinler (anahtar ve anahtarı olmayan) tablosundaki kayıtlar için bir tanımlayıcı olarak hizmet veren olmadan kayıtları önceden tanımlanmış bir düzende mantıksal olarak düzenleyin.  
  
 Daha fazla bilgi için "Birincil özelliği" ve "Benzersiz özelliğinde" DAO Yardım konularına bakın.  
  
 *m_bClustered*  
 Bir dizin nesnesi bir tablo için kümelenmiş bir dizin temsil edip etmediğini gösterir. Bu özellik ise **doğru**, dizin nesnesi bir kümelenmiş dizin temsil eder; Aksi halde, yok. Kümelenmiş bir dizin birini oluşur veya daha fazla tuşdışı alanları, birlikte ele alındığında, önceden tanımlı bir sırada bir tablodaki tüm kayıtları düzenleyin. Kümelenmiş bir dizin ile tablodaki verileri tam anlamıyla kümelenmiş dizini tarafından belirtilen sırada depolanır. Kümelenmiş bir dizin tablo kayıtları etkili erişim sağlar. Daha fazla bilgi için DAO Yardımı'nda "özellik kümelenmiş" konusuna bakın.  
  
> [!NOTE]
>  Kümelenmiş özelliği Jet veritabanı altyapısı Kümelenmiş dizinler desteklemediği için Microsoft Jet Veritabanı Altyapısı'nı kullanan veritabanları için göz ardı edilir.  
  
 *m_bIgnoreNulls*  
 Dizin alanlarında Null değerlere sahip kayıtları için dizin girişleri olup olmadığını gösterir. Bu özellik ise **doğru**, alanları Null değerlere sahip bir dizin girdisi yok. Daha hızlı bir alanını kullanarak kayıt arama yapmak için alan için bir dizin tanımlayabilirsiniz. Dizinlenmiş bir alanda Null girişlere izin ver ve Null olmasına izin girişleri çoğunu beklediğiniz özelliğini dizin nesnesi için ayarlayabileceğiniz **TRUE** dizini kullandığı depolama alanı miktarını azaltmak için. Birlikte IgnoreNulls özelliği ayarı ve gerekli özellik ayarı Null dizin değeri içeren bir kayıt aşağıdaki tabloda gösterildiği gibi bir dizin girişi sahip olup olmadığını belirler.  
  
|IgnoreNulls|Gerekli|Dizin alanında null|  
|-----------------|--------------|-------------------------|  
|Doğru|False|İzin verilen null değer; Dizin girişi eklenir.|  
|False|False|İzin verilen null değer; Dizin girişi eklenir.|  
|TRUE veya False|Doğru|Null değere izin verilmez; Dizin girişi eklenir.|  
  
 Daha fazla bilgi için DAO Yardımı'ndaki "IgnoreNulls özelliği" konusuna bakın.  
  
 `m_bRequired`  
 DAO Index nesnesi Null olmayan bir değer gerekli olup olmadığını gösterir. Bu özellik ise **doğru**, dizin nesnesi Null bir değere izin vermiyor. Daha fazla bilgi için DAO Yardımı'ndaki "özelliği gerekli" konusuna bakın.  
  
> [!TIP]
>  Bu özellik bir DAO Index nesnesi veya (tabledef, kayıt kümesi veya querydef nesnesi tarafından bulunan) bir alan nesnesi için ayarlayabileceğiniz alan nesne için ayarlanır. Bir alan nesne için özellik ayarı geçerliliğini, bir dizin nesnesi önce denetlenir.  
  
 *m_bForeign*  
 Bir dizin nesne tablosundaki yabancı anahtar temsil edip etmediğini gösterir. Bu özellik ise **doğru**, bir tablodaki bir yabancı anahtar dizinini gösterir. Alanların birincil tablosunda bir satırı benzersiz şekilde tanımlayan bir veya daha fazla yabancı tablosundaki yabancı anahtar oluşur. Microsoft Jet veritabanı altyapısı yabancı tablo için bir dizin nesnesi oluşturur ve başvuru bütünlüğü zorlayan bir ilişki oluşturduğunuzda yabancı özelliğini ayarlar. Daha fazla bilgi için DAO Yardımı'ndaki "yabancı özellik" konusuna bakın.  
  
 *m_lDistinctCount*  
 Dizin nesnesi için ilişkili tabloda içerdiği benzersiz değerler sayısını gösterir. Benzersiz değerlerin veya anahtarlarında bir dizin sayısını belirlemek için DistinctCount özelliğini denetleyin. Herhangi bir tuşa olabilir olsa da bu değer birden fazla oluşumu dizin yinelenen değerler veriyorsa yalnızca bir kez sayılır. Bu bilgiler, dizin bilgilerini değerlendirerek veri erişimini iyileştirmek girişimi uygulamalarda yararlıdır. Benzersiz değerler olarak da bilinen bir dizin nesnesi önemi sayısıdır. DistinctCount özelliği her zaman belirli bir zamanda anahtarları gerçek sayısını yansıtmaz. Örneğin, bir işlemi geri alma tarafından neden bir değişikliği hemen DistinctCount özelliğinde yansıtılmaz. Daha fazla bilgi için DAO Yardımı'ndaki "DistinctCount özelliği" konusuna bakın.  
  
## <a name="remarks"></a>Açıklamalar  
 Birincil, ikincil ve yukarıdaki tüm başvuruları nasıl bilgileri tarafından döndürülen belirtmek `GetIndexInfo` sınıflardaki üye işlevi [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) ve [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Dizin nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, DAO temel MFC sınıfının nesneleri [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) dizinler koleksiyonu adlı dizin nesnelerinin bir koleksiyonu içerir. Bu sınıfların dizin bilgilerinin tek tek öğelere erişmek için üye işlevleri sağlamak ya da bunları tamamını tek seferde erişebilirsiniz bir `CDaoIndexInfo` çağırarak nesne `GetIndexInfo` kapsayan nesnenin üye işlevi.  
  
 `CDaoIndexInfo` bir oluşturucu ve düzgün şekilde ayırmak ve dizin alan bilgilerini ayırması amacıyla bir yıkıcı sahip `m_pFieldInfos`.  
  
 Tarafından alınan bilgileri `GetIndexInfo` üye işlevi tabledef nesnesinin depolanır bir `CDaoIndexInfo` yapısı. Çağrı `GetIndexInfo` üye işlevi içeren tabledef nesnesinin olan dizinler koleksiyonu dizin nesnesi depolanır. `CDaoIndexInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümü bir `CDaoIndexInfo` nesnesi.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdao.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yapılar, stiller, geri aramalar ve ileti eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)

