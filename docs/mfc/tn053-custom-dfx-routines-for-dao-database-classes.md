---
description: 'Daha fazla bilgi edinin: TN053: DAO veritabanı sınıfları için özel DFX yordamları'
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
ms.openlocfilehash: cbe34963ec3f46a88e41521f119191e7d0afe1e6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214981"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>TN053: DAO Veritabanı Sınıfları için Özel DFX Rutinleri

> [!NOTE]
> DAO, Access veritabanları ile birlikte kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir. Visual C++ ortamı ve sihirbazları DAO 'YU desteklemez (DAO sınıfları dahil edilip kullanmaya devam edebilirsiniz). Microsoft, yeni projeler için [OLE DB şablonlarını](../data/oledb/ole-db-templates.md) veya [ODBC 'yi ve MFC 'yi](../data/odbc/odbc-and-mfc.md) kullanmanızı önerir. Yalnızca var olan uygulamaları korumak için DAO kullanmanız gerekir.

Bu teknik notta, DAO Kayıt alanı değişimi (DFX) mekanizması açıklanmaktadır. DFX yordamlarına ne olduğunu anlamanıza yardımcı olmak için, `DFX_Text` işlev bir örnek olarak ayrıntılı olarak açıklanacaktır. Bu teknik nota ek bilgi kaynağı olarak, diğer bireysel DFX işlevlerinin kodunu inceleyebilirsiniz. Özel bir RFX yordamına (ODBC veritabanı sınıflarıyla birlikte kullanılır) ihtiyacınız olabileceği için muhtemelen özel bir DFX yordamına ihtiyaç duymayacak.

Bu teknik notta şunları içerir:

- DFX genel bakış

- DAO Kayıt alanı değişimi ve dinamik bağlama kullanan [örnekler](#_mfcnotes_tn053_examples)

- [DFX nasıl çalışacaktır?](#_mfcnotes_tn053_how_dfx_works)

- [Özel DFX yordamınız ne yapar](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)

- [DFX_Text ayrıntıları](#_mfcnotes_tn053_details_of_dfx_text)

**DFX genel bakış**

DAO Kayıt alanı değişim mekanizması (DFX), sınıfı kullanırken verileri alma ve güncelleştirme yordamını basitleştirmek için kullanılır `CDaoRecordset` . İşlem, sınıfının veri üyeleri kullanılarak basitleştirilmiştir `CDaoRecordset` . Öğesinden türeterek `CDaoRecordset` , bir tablo veya sorgudaki her alanı temsil eden türetilmiş sınıfa veri üyeleri ekleyebilirsiniz. Bu "statik bağlama" mekanizması basittir, ancak tüm uygulamalar için tercih edilen veri getirme/güncelleştirme yöntemi olmayabilir. DFX, geçerli kayıt her değiştirildiğinde her bağlantılı alanı alır. Para birimi değiştirildiğinde her alanı getirmeyi gerektirmeyen, performans duyarlı bir uygulama geliştiriyorsanız, ile "dinamik bağlama" `CDaoRecordset::GetFieldValue` seçeneği, ve `CDaoRecordset::SetFieldValue` tercih edilen veri erişim yöntemi olabilir.

> [!NOTE]
> DFX ve dinamik bağlama birbirini dışlamalı değildir, bu nedenle statik ve dinamik bağlamanın karma kullanımı kullanılabilir.

## <a name="example-1--use-of-dao-record-field-exchange-only"></a><a name="_mfcnotes_tn053_examples"></a> Örnek 1 — yalnızca DAO Kayıt alanı değişimi kullanımı

( `CDaoRecordset` türetilen sınıfın `CMySet` zaten açık olduğu varsayılır)

```
// Add a new record to the customers table
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```

**Örnek 2 — yalnızca dinamik bağlamanın kullanımı**

(sınıfını kullanarak, `CDaoRecordset` `rs` ve zaten açık olduğunu varsayar)

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

(çalışan verilerine ile `CDaoRecordset` türetilmiş sınıfı göz atmayı varsayar `emp` )

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

## <a name="how-dfx-works"></a><a name="_mfcnotes_tn053_how_dfx_works"></a> DFX nasıl çalışacaktır?

DFX mekanizması, MFC ODBC sınıfları tarafından kullanılan kayıt alanı değişimi (RFX) mekanizmasına benzer bir biçimde çalışmaktadır. DFX ve RFX 'in ilkeleri aynı ancak çok sayıda iç fark vardır. DFX işlevlerinin tasarımı, neredeyse tüm kodun bireysel DFX yordamları tarafından paylaşıldığından bu şekilde oluşturulmuştur. En üst düzey DFX yalnızca birkaç şey vardır.

- DFX gerekirse SQL **Select** yan TÜMCESINI ve SQL **Parameters** yan tümcesini oluşturur.

- DFX, DAO işlevi tarafından kullanılan bağlama yapısını oluşturur `GetRows` (daha sonra bu konuda daha fazla).

- DFX, kirli alanları algılamak için kullanılan veri arabelleğini yönetir (çift arabelleğe alma kullanılıyorsa)

- DFX **null** ve **kirli** durum dizilerini yönetir ve güncelleştirmelerde gerekirse değerleri ayarlar.

DFX mekanizması, `CDaoRecordset` türetilen sınıfın `DoFieldExchange` işlevidir. Bu işlev, uygun bir işlem türünün bireysel DFX işlevlerine çağrı gönderir. `DoFieldExchange`Iç MFC işlevlerini çağırmadan önce işlem türünü ayarlayın. Aşağıdaki listede çeşitli işlem türleri ve kısa bir açıklama gösterilmektedir.

|İşlem|Açıklama|
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

Sonraki bölümde, her işlem için daha ayrıntılı olarak açıklanacaktır `DFX_Text` .

DAO Kayıt alanı değişim süreci hakkında anlaşılması gereken en önemli özellik `GetRows` nesnenin işlevini kullanmadır `CDaoRecordset` . DAO `GetRows` işlevi birkaç şekilde çalışabilir. Bu teknik notta yalnızca `GetRows` Bu teknik notun kapsamı dışında olduğu için kısaca kısaca açıklama uygulanır.
DAO `GetRows` , birkaç şekilde çalışabilir.

- Tek seferde birden çok kayıt ve birden çok veri alanı getirebilir. Bu, büyük bir veri yapısıyla ve her bir alana uygun uzaklıklara ve yapıdaki her veri kaydına yönelik daha hızlı veri erişimi sağlar. MFC bu birden fazla kayıt getirme mekanizmasından yararlanamaz.

- Diğer bir yöntem de `GetRows` programcıların bir veri kaydı için her alanın alınan verileri için bağlama adreslerini belirtmesini sağlar.

- Ayrıca, arayanın bellek ayırmasına izin vermek için, değişken uzunluklu sütunlar için de "geri çağrı" yapılır. Bu ikinci özellik, verilerin kopyalarının sayısını en aza indirmesinin yanı sıra verilerin bir sınıfın (türetilmiş sınıf) üyelerine doğrudan depolanmasını sağlayan avantajına sahiptir `CDaoRecordset` . Bu ikinci mekanizma, MFC 'nin türetilmiş sınıflarda veri üyelerine bağlamak için kullandığı yöntemdir `CDaoRecordset` .

## <a name="what-your-custom-dfx-routine-does"></a><a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a> Özel DFX yordamınız ne yapar

Bu tartışmadan, herhangi bir DFX işlevinde uygulanan en önemli işlemin, başarıyla çağırmak için gerekli veri yapılarını ayarlama yeteneğinin olması gerektiğini unutmayın `GetRows` . Bir DFX işlevinin desteklemesi gereken birçok farklı işlem vardır, ancak çağrı için doğru şekilde hazırlanmadığı sürece önemli veya karmaşık olarak yoktur `GetRows` .

DFX kullanımı çevrimiçi belgelerde açıklanmıştır. Temelde, iki gereksinim vardır. İlk olarak, Üyeler `CDaoRecordset` her bir bağlantılı alan ve parametre için türetilmiş sınıfa eklenmelidir. Bunun için aşağıdaki `CDaoRecordset::DoFieldExchange` geçersiz kılınmalıdır. Üyenin veri türünün önemli olduğunu unutmayın. Bu, veritabanındaki alandan alınan verilerle eşleşmelidir veya en azından bu türe dönüştürülebilir. Örneğin, bir long integer gibi veritabanındaki bir sayısal alan, her zaman metne dönüştürülebilir ve bir `CString` üyeye bağlanabilir, ancak veritabanındaki bir metin alanı uzun tamsayı ve uzun tamsayı üyesine sınırlı olmak üzere sayısal bir gösterimine dönüştürülemez. DAO ve Microsoft Jet veritabanı altyapısı, dönüşümden sorumludur (MFC yerine).

## <a name="details-of-dfx_text"></a><a name="_mfcnotes_tn053_details_of_dfx_text"></a> DFX_Text ayrıntıları

Daha önce bahsedildiği gibi, DFX nasıl çalıştığını açıklayabileceğiniz en iyi yolu bir örnek aracılığıyla çalışmaktır. Bu amaçla, iç yapıları için `DFX_Text` en az BIR DFX en az bir temel anlama sağlamaya yardımcı olmak çok iyi çalışmalıdır.

- `AddToParameterList`

   Bu işlem, Jet için gereken SQL **Parameters** yan tümcesini (" `Parameters <param name>, <param type> ... ;` ") oluşturur. Her parametre adlandırılmış ve yazılır (RFX çağrısında belirtildiği gibi). `CDaoFieldExchange::AppendParamType`Tek türlerin adlarını görmek için işlev işlevine bakın. Bu durumda `DFX_Text` , kullanılan tür **metindir**.

- `AddToSelectList`

   SQL **Select** yan tümcesini oluşturur. DFX çağrısı tarafından belirtilen sütun adı yalnızca eklenmiş ("") olduğundan, bu oldukça basit bir işlemdir `SELECT <column name>, ...` .

- `BindField`

   İşlemlerin en karmaşıktır. Daha önce belirtildiği gibi, tarafından kullanılan DAO bağlama yapısının ayarlandığı yerdir `GetRows` . Yapıdaki bilgi türlerindeki koddan görebileceğiniz gibi, `DFX_Text` kullanılan dao türünü (**DAO_CHAR** veya **dao_wchar** `DFX_Text` ) içerir. Ayrıca, kullanılan bağlamanın türü de ayarlanır. Daha önceki bir bölümde `GetRows` yalnızca kısaca açıklanmıştı, ancak MFC tarafından kullanılan bağlama türünün her zaman doğrudan adres bağlama (**DAOBINDING_DIRECT**) olduğunu açıklamak yeterlidir. Değişken uzunlukta sütun bağlama (gibi `DFX_Text` ) geri çağırma bağlamasının yanı sıra, MFC 'nin bellek ayırmayı denetleyebilmesi ve doğru uzunlukta bir adres belirtmesi için kullanılır. Bu anlamı MFC 'nin her zaman "Where" DAO 'ya verileri koyabileceği, böylece doğrudan üye değişkenlerine bağlamaya izin vereceğini belirtir. Bağlama yapısının geri kalanı, bellek ayırma geri arama işlevinin adresi ve sütun bağlama türü (sütun adına göre bağlama) gibi şeyler ile doldurulur.

- `BindParam`

   Bu, `SetParamValue` parametre üyesinde belirtilen parametre değeriyle çağıran basit bir işlemdir.

- `Fixup`

   Her bir alan için **null** durumunu doldurur.

- `SetFieldNull`

   Bu işlem yalnızca her bir alan durumunu **null** olarak işaretler ve üye değişkeninin değerini **pseudo_null** olarak ayarlar.

- `SetDirtyField`

   `SetFieldValue`Kirli olarak işaretlenmiş her alan için çağrılar.

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

   Geçerli alan değerinin **null** olup olmadığını denetler ve gerekirse kirli olarak işaretler.

- `MarkForEdit`

   Geçerli alan değerini veri önbelleğiyle karşılaştırır ve gerekirse kirli olarak işaretler.

> [!TIP]
> Standart veri türleri için mevcut DFX yordamlarında özel DFX yordamlarını modelleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
