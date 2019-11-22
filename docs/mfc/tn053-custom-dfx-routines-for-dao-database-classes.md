---
title: 'TN053: DAO Veritabanı Sınıfları için Özel DFX Rutinleri'
ms.date: 09/17/2019
helpviewer_keywords:
- MFC, DAO and
- database classes [MFC], DAO
- DAO [MFC], MFC
- DFX (DAO record field exchange) [MFC], custom routines
- TN053
- DAO [MFC], classes
- DFX (DAO record field exchange) [MFC]
- custom DFX routines [MFC]
ms.assetid: fdcf3c51-4fa8-4517-9222-58aaa4f25cac
ms.openlocfilehash: 6dde96520d9472726da86f8da295770cccc5d42c
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303433"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>TN053: DAO Veritabanı Sınıfları için Özel DFX Rutinleri

> [!NOTE]
>  DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir. Visual C++ ortamı ve sihirbazları DAO 'yu desteklemez (DAO sınıfları dahil edilir ancak yine de kullanabilirsiniz). Microsoft, yeni projeler için [OLE DB şablonlarını](../data/oledb/ole-db-templates.md) veya [ODBC 'yi ve MFC 'yi](../data/odbc/odbc-and-mfc.md) kullanmanızı önerir. Yalnızca var olan uygulamaları korumak için DAO kullanmanız gerekir.

Bu teknik notta, DAO Kayıt alanı değişimi (DFX) mekanizması açıklanmaktadır. DFX yordamlarına ne olduğunu anlamanıza yardımcı olmak için `DFX_Text` işlevi bir örnek olarak ayrıntılı olarak açıklanacaktır. Bu teknik nota ek bilgi kaynağı olarak, diğer bireysel DFX işlevlerinin kodunu inceleyebilirsiniz. Özel bir RFX yordamına (ODBC veritabanı sınıflarıyla birlikte kullanılır) ihtiyacınız olabileceği için muhtemelen özel bir DFX yordamına ihtiyaç duymayacak.

Bu teknik notta şunları içerir:

- DFX genel bakış

- DAO Kayıt alanı değişimi ve dinamik bağlama kullanan [örnekler](#_mfcnotes_tn053_examples)

- [DFX nasıl çalışacaktır?](#_mfcnotes_tn053_how_dfx_works)

- [Özel DFX yordamınız ne yapar](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)

- [DFX_Text ayrıntıları](#_mfcnotes_tn053_details_of_dfx_text)

**DFX genel bakış**

DAO Kayıt alanı değişim mekanizması (DFX), `CDaoRecordset` sınıfını kullanırken verileri alma ve güncelleştirme yordamını basitleştirmek için kullanılır. İşlem, `CDaoRecordset` sınıfının veri üyeleri kullanılarak basitleştirilmiştir. `CDaoRecordset`türettikten sonra, bir tablo veya sorgudaki her alanı temsil eden türetilmiş sınıfa veri üyeleri ekleyebilirsiniz. Bu "statik bağlama" mekanizması basittir, ancak tüm uygulamalar için tercih edilen veri getirme/güncelleştirme yöntemi olmayabilir. DFX, geçerli kayıt her değiştirildiğinde her bağlantılı alanı alır. Para birimi değiştirildiğinde her alanı getirmeyi gerektirmeyen performans duyarlı bir uygulama geliştiriyorsanız, `CDaoRecordset::GetFieldValue` ve `CDaoRecordset::SetFieldValue` aracılığıyla "dinamik bağlama" seçeneği, tercih ettiğiniz veri erişim yöntemi olabilir.

> [!NOTE]
>  DFX ve dinamik bağlama birbirini dışlamalı değildir, bu nedenle statik ve dinamik bağlamanın karma kullanımı kullanılabilir.

## <a name="_mfcnotes_tn053_examples"></a>Örnek 1 — yalnızca DAO Kayıt alanı değişimi kullanımı

(`CDaoRecordset`) türetilmiş sınıf `CMySet` zaten açık olduğunu varsayar.

```
// Add a new record to the customers table
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```

**Örnek 2 — yalnızca dinamik bağlamanın kullanımı**

(`CDaoRecordset` sınıfını kullanarak, `rs`ve zaten açık olduğunu varsayar)

```
// Add a new record to the customers table
COleVariant  varFieldValue1 (_T("MSFT"),
    VT_BSTRT);

//Note: VT_BSTRT flags string type as ANSI,
    instead of UNICODE default
COleVariant  varFieldValue2  (_T("Microsoft"),
    VT_BSTRT);

rs.AddNew();

rs.SetFieldValue(_T("Customer_ID"),
    varFieldValue1);

rs.SetFieldValue(_T("Customer_Name"),
    varFieldValue2);

rs.Update();
```

**Örnek 3 — DAO Kayıt alanı değişimi ve dinamik bağlama kullanımı**

(`CDaoRecordset`türetilen sınıfla çalışan verilerine göz atmayı varsayar `emp`)

```
// Get the employee's data so that it can be displayed
emp.MoveNext();

// If user wants to see employee's photograph,
// fetch it
COleVariant varPhoto;
if (bSeePicture)
    emp.GetFieldValue(_T("photo"),
    varPhoto);

// Display the data
PopUpEmployeeData(emp.m_strFirstName,
    emp.m_strLastName,
    varPhoto);
```

## <a name="_mfcnotes_tn053_how_dfx_works"></a>DFX nasıl çalışacaktır?

DFX mekanizması, MFC ODBC sınıfları tarafından kullanılan kayıt alanı değişimi (RFX) mekanizmasına benzer bir biçimde çalışmaktadır. DFX ve RFX 'in ilkeleri aynı ancak çok sayıda iç fark vardır. DFX işlevlerinin tasarımı, neredeyse tüm kodun bireysel DFX yordamları tarafından paylaşıldığından bu şekilde oluşturulmuştur. En üst düzey DFX yalnızca birkaç şey vardır.

- DFX gerekirse SQL **Select** yan TÜMCESINI ve SQL **Parameters** yan tümcesini oluşturur.

- DFX, DAO 'nun `GetRows` işlevi tarafından kullanılan bağlama yapısını oluşturur (daha sonra bu konuda daha fazla).

- DFX, kirli alanları algılamak için kullanılan veri arabelleğini yönetir (çift arabelleğe alma kullanılıyorsa)

- DFX **null** ve **kirli** durum dizilerini yönetir ve güncelleştirmelerde gerekirse değerleri ayarlar.

DFX mekanizması, `CDaoRecordset` türetilen sınıfın `DoFieldExchange` işlevidir. Bu işlev, uygun bir işlem türünün bireysel DFX işlevlerine çağrı gönderir. `DoFieldExchange` çağrılmadan önce, iç MFC işlevleri işlem türünü ayarlar. Aşağıdaki listede çeşitli işlem türleri ve kısa bir açıklama gösterilmektedir.

|Çalışma|Açıklama|
|---------------|-----------------|
|`AddToParameterList`|Derlemeler PARAMETRESI yan tümcesi|
|`AddToSelectList`|Derlemeler SELECT yan tümcesi|
|`BindField`|Bağlama yapısını ayarlar|
|`BindParam`|Parametre değerlerini ayarlar|
|`Fixup`|NULL durumunu ayarlar|
|`AllocCache`|Kirli denetim için önbelleği ayırır|
|`StoreField`|Geçerli kaydı önbelleğe kaydeder|
|`LoadField`|Ön belleği üye değerlerine geri yükler|
|`FreeCache`|Önbelleği serbest bırakır|
|`SetFieldNull`|Alan durumu & değerini NULL olarak ayarlar|
|`MarkForAddNew`|SÖZDE NULL değilse alanları kirli olarak işaretler|
|`MarkForEdit`|Önbellekte eşleşmezse alanları kirli olarak işaretler|
|`SetDirtyField`|Kirli olarak işaretlenen alan değerlerini ayarlar|

Sonraki bölümde, her işlem `DFX_Text`daha ayrıntılı olarak açıklanacaktır.

DAO Kayıt alanı değişim süreci hakkında anlaşılması gereken en önemli özellik, `CDaoRecordset` nesnesinin `GetRows` işlevini kullanmadır. DAO `GetRows` işlevi birkaç şekilde çalışabilir. Bu teknik notun yalnızca bu teknik notun kapsamı dışında olduğu için `GetRows` kısaca açıklaması alınacaktır.
DAO `GetRows`, birkaç şekilde çalışabilir.

- Tek seferde birden çok kayıt ve birden çok veri alanı getirebilir. Bu, büyük bir veri yapısıyla ve her bir alana uygun uzaklıklara ve yapıdaki her veri kaydına yönelik daha hızlı veri erişimi sağlar. MFC bu birden fazla kayıt getirme mekanizmasından yararlanamaz.

- `GetRows` başka bir yol da, programcıların bir veri kaydı için her alanın alınan verileri için bağlama adreslerini belirtmesini sağlar.

- Ayrıca, arayanın bellek ayırmasına izin vermek için, değişken uzunluklu sütunlar için de "geri çağrı" yapılır. Bu ikinci özellik, verilerin kopyalarının sayısını en aza indirmesinin yanı sıra verilerin bir sınıfın üyelerine doğrudan depolanmasını sağlayan avantajına sahiptir (`CDaoRecordset` türetilmiş sınıf). Bu ikinci mekanizma, MFC 'nin `CDaoRecordset` türetilmiş sınıflarda veri üyelerine bağlamak için kullandığı yöntemdir.

##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a>Özel DFX yordamınız ne yapar

Bu tartışmadan, herhangi bir DFX işlevinde uygulanan en önemli işlemin, `GetRows`başarıyla çağırmak için gerekli veri yapılarını ayarlama yeteneğinin olması gerektiğini unutmayın. Bir DFX işlevinin desteklediği birçok başka işlem de `GetRows` çağrısı için doğru şekilde hazırlanmalıdır, önemli veya karmaşık olarak yoktur.

DFX kullanımı çevrimiçi belgelerde açıklanmıştır. Temelde, iki gereksinim vardır. İlk olarak, üyelerin her bir bağlantılı alan ve parametre için `CDaoRecordset` türetilmiş sınıfa eklenmesi gerekir. Bu `CDaoRecordset::DoFieldExchange` aşağıdaki geçersiz kılınmalıdır. Üyenin veri türünün önemli olduğunu unutmayın. Bu, veritabanındaki alandan alınan verilerle eşleşmelidir veya en azından bu türe dönüştürülebilir. Örneğin, bir long integer gibi veritabanındaki bir sayısal alan, her zaman metne dönüştürülebilir ve bir `CString` üyeye bağlanabilir, ancak veritabanındaki bir metin alanı uzun tamsayı ve uzun tamsayı üyesine sınırlı olmak üzere sayısal bir gösterimine dönüştürülemez. DAO ve Microsoft Jet veritabanı altyapısı, dönüşümden sorumludur (MFC yerine).

##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a>DFX_Text ayrıntıları

Daha önce bahsedildiği gibi, DFX nasıl çalıştığını açıklayabileceğiniz en iyi yolu bir örnek aracılığıyla çalışmaktır. Bu amaçla `DFX_Text` iç işlevleri sayesinde, DFX en az bir temel anlama sağlamaya yardımcı olmak çok iyi çalışır.

- `AddToParameterList`

   Bu işlem, Jet 'in gerektirdiği SQL **Parameters** yan tümcesini ("`Parameters <param name>, <param type> ... ;`") oluşturur. Her parametre adlandırılmış ve yazılır (RFX çağrısında belirtildiği gibi). Bağımsız türlerin adlarını görmek için bkz. işlev `CDaoFieldExchange::AppendParamType` işlevi. `DFX_Text`durumunda kullanılan tür **metindir**.

- `AddToSelectList`

   SQL **Select** yan tümcesini oluşturur. Bu, DFX çağrısı tarafından belirtilen sütun adı yalnızca eklenmiş olduğundan ("`SELECT <column name>, ...`") oldukça basit bir işlemdir.

- `BindField`

   İşlemlerin en karmaşıktır. Daha önce belirtildiği gibi, `GetRows` tarafından kullanılan DAO bağlama yapısının ayarlandığı yerdir. `DFX_Text` koddan görebileceğiniz gibi, yapıdaki bilgi türleri kullanılan DAO türünü (**dao_char** veya `DFX_Text`durumunda **dao_wchar** ) içerir. Ayrıca, kullanılan bağlamanın türü de ayarlanır. Daha önceki bir bölümde `GetRows` yalnızca kısaca açıklanmıştı, ancak MFC tarafından kullanılan bağlama türünün her zaman doğrudan adres bağlama (**DAOBINDING_DIRECT**) olduğunu açıklamak yeterlidir. Değişken uzunluklu sütun bağlama (benzer `DFX_Text`) için ek olarak, MFC 'nin bellek ayırmayı denetleyebilmesi ve doğru uzunlukta bir adres belirleyebilmesi için kullanılır. Bu anlamı MFC 'nin her zaman "Where" DAO 'ya verileri koyabileceği, böylece doğrudan üye değişkenlerine bağlamaya izin vereceğini belirtir. Bağlama yapısının geri kalanı, bellek ayırma geri arama işlevinin adresi ve sütun bağlama türü (sütun adına göre bağlama) gibi şeyler ile doldurulur.

- `BindParam`

   Bu, parametre üyesinde belirtilen parametre değeriyle `SetParamValue` çağıran basit bir işlemdir.

- `Fixup`

   Her bir alan için **null** durumunu doldurur.

- `SetFieldNull`

   Bu işlem yalnızca her bir alan durumunu **null** olarak işaretler ve üye değişkeninin değerini **pseudo_null**olarak ayarlar.

- `SetDirtyField`

   Kirli olarak işaretlenmiş her alan için `SetFieldValue` çağırır.

Kalan tüm işlemler yalnızca veri önbelleğinin kullanılmasıyla ilgilidir. Veri önbelleği, belirli şeyleri daha kolay hale getirmek için kullanılan geçerli kayıttaki verilerin ek bir arabelleğidir. Örneğin, "kirli" alanları otomatik olarak algılanabilir. Çevrimiçi belgelerde açıklandığı gibi, tamamen veya alan düzeyinde kapatılabilir. Arabellek uygulanması bir eşlemeyi kullanır. Bu harita, verilerin dinamik olarak ayrılmış kopyalarını "bağlı" alanın (veya `CDaoRecordset` türetilen veri üyesinin) adresiyle eşleştirmek için kullanılır.

- `AllocCache`

   Önbelleğe alınan alan değerini dinamik olarak ayırır ve haritaya ekler.

- `FreeCache`

   Önbelleğe alınmış alan değerini siler ve eşlemden kaldırır.

- `StoreField`

   Geçerli alan değerini veri önbelleğine kopyalar.

- `LoadField`

   Önbelleğe alınan değeri alan üyesine kopyalar.

- `MarkForAddNew`

   Geçerli alan değerinin**null** olup olmadığını denetler ve gerekirse kirli olarak işaretler.

- `MarkForEdit`

   Geçerli alan değerini veri önbelleğiyle karşılaştırır ve gerekirse kirli olarak işaretler.

> [!TIP]
> Standart veri türleri için mevcut DFX yordamlarında özel DFX yordamlarını modelleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
