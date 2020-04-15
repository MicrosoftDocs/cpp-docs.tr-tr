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
ms.openlocfilehash: f7ad854f4dbb4e90c09e886c69260e4e2eea3be2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365255"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>TN053: DAO Veritabanı Sınıfları için Özel DFX Rutinleri

> [!NOTE]
> DAO Access veritabanları ile kullanılır ve Office 2013 aracılığıyla desteklenir. DAO 3.6 son sürümüdür ve eski miş olarak kabul edilir. Visual C++ ortamı ve sihirbazlar DAO'yu desteklemez (her ne kadar DAO sınıfları dahil olsa da ve bunları kullanmaya devam edebilirsiniz). Microsoft, yeni projeler için [OLE DB Şablonları](../data/oledb/ole-db-templates.md) veya [ODBC ve MFC](../data/odbc/odbc-and-mfc.md) kullanmanızı önerir. DAO'yu yalnızca varolan uygulamaları korurken kullanmalısınız.

Bu teknik not, DAO kayıt alanı değişimi (DFX) mekanizmasını açıklar. DFX yordamlarında neler olduğunu anlamalarına yardımcı `DFX_Text` olmak için, işlev ayrıntılı olarak bir örnek olarak açıklanacaktır. Bu teknik nota ek bir bilgi kaynağı olarak, diğer tek tek DFX işlevleriiçin kodu inceleyebilirsiniz. Özel bir RFX yordamı (ODBC veritabanı sınıfları ile birlikte kullanılan) gerekebilir gibi sık sık özel bir DFX yordamı gerekmez büyük olasılıkla.

Bu teknik not şunları içerir:

- DFX Genel Bakış

- DAO Kayıt Alanı Değişimi ve Dinamik Bağlama kullanarak [örnekler](#_mfcnotes_tn053_examples)

- [DFX Nasıl Çalışır?](#_mfcnotes_tn053_how_dfx_works)

- [Özel DFX Yordamınız Ne Yapar?](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)

- [DFX_Text ayrıntıları](#_mfcnotes_tn053_details_of_dfx_text)

**DFX Genel Bakış**

DAO kayıt alanı değişim mekanizması (DFX), `CDaoRecordset` sınıfı kullanırken veri alma ve güncelleştirme işlemini basitleştirmek için kullanılır. `CDaoRecordset` İşlem, sınıfın veri üyeleri kullanılarak basitleştirilir. `CDaoRecordset`Bir tablo veya sorguda her alanı temsil eden türemiş sınıfa veri üyeleri ekleyebilirsiniz. Bu "statik bağlama" mekanizması basittir, ancak tüm uygulamalar için tercih edilen veri getirme/güncelleştirme yöntemi olmayabilir. DFX, geçerli kayıt her değiştirilse her bağlı alanı alır. Para birimi değiştiğinde her alanı getirmeyi gerektirmeyen performansa duyarlı bir uygulama geliştiriyorsanız, "dinamik bağlama" yoluyla `CDaoRecordset::GetFieldValue` ve tercih edilen veri erişim yöntemi `CDaoRecordset::SetFieldValue` olabilir.

> [!NOTE]
> DFX ve dinamik bağlama birbirini dışlayan değildir, bu nedenle statik ve dinamik bağlamanın hibrit kullanımı kullanılabilir.

## <a name="example-1--use-of-dao-record-field-exchange-only"></a><a name="_mfcnotes_tn053_examples"></a>Örnek 1 — Yalnızca DAO Kayıt Alanı Değişimi kullanımı

(varsayar `CDaoRecordset` — `CMySet` türemiş sınıf zaten açık)

```
// Add a new record to the customers table
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```

**Örnek 2 — Yalnızca dinamik bağlama kullanımı**

(sınıf `rs`kullanarak `CDaoRecordset` varsayar ve zaten açık)

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

**Örnek 3 — DAO Kayıt Alanı Değişimi ve dinamik bağlama**

(-türetilmiş sınıfile `CDaoRecordset` `emp`çalışan verilerine göz atalım varsayar)

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

## <a name="how-dfx-works"></a><a name="_mfcnotes_tn053_how_dfx_works"></a>DFX Nasıl Çalışır?

DFX mekanizması, MFC ODBC sınıfları tarafından kullanılan kayıt alanı değişimi (RFX) mekanizmasına benzer bir şekilde çalışır. DFX ve RFX ilkeleri aynıdır ama çok sayıda iç farklılıklar vardır. DFX işlevlerinin tasarımı, neredeyse tüm kodun tek tek DFX yordamları tarafından paylaşılacak şekilde ydi. En üst düzeyde DFX sadece birkaç şey yapar.

- DFX gerekirse SQL **SELECT** yan tümcesi ve SQL **PARAMETRELERi** yan tümcesini belirler.

- DFX, DAO'nun `GetRows` işlevi tarafından kullanılan bağlama yapısını (daha sonra bu konuda daha fazla) inşa eder.

- DFX kirli alanları algılamak için kullanılan veri arabelleği yönetir (çift arabelleğe alma kullanılıyorsa)

- **DFX, NULL** ve **DIRTY** durum dizilerini yönetir ve gerektiğinde güncelleştirmelerde değerleri ayarlar.

DFX mekanizmasının kalbinde `CDaoRecordset` türetilmiş sınıfın `DoFieldExchange` işlevi yer almaktadır. Bu işlev, uygun bir işlem türünün tek tek DFX işlevlerine çağrılar gönderir. Dahili `DoFieldExchange` MFC işlevlerini aramadan önce işlem türünü ayarlayın. Aşağıdaki liste çeşitli işlem türlerini ve kısa bir açıklamayı gösterir.

|İşlem|Açıklama|
|---------------|-----------------|
|`AddToParameterList`|PARAMETRELER yan tümcesi oluşturur|
|`AddToSelectList`|SELECT yan tümcesi oluşturur|
|`BindField`|Bağlayıcı yapıyı ayarlar|
|`BindParam`|Parametre değerlerini ayarlar|
|`Fixup`|NULL durumunu ayarlar|
|`AllocCache`|Kirli çek için önbelleği ayırır|
|`StoreField`|Geçerli kaydı önbelleğe kaydeder|
|`LoadField`|Önbelleği üye değerlere geri yükleme|
|`FreeCache`|Önbelleği serbest eder|
|`SetFieldNull`|Alan durumunu null & değerini ayarlar|
|`MarkForAddNew`|Pseudo NULL değilse kirli alanları işaretler|
|`MarkForEdit`|Önbellekle eşleşmiyorsa alanları kirli işaretler|
|`SetDirtyField`|Kirli olarak işaretlenmiş alan değerlerini ayarlar|

Bir sonraki bölümde, her işlem için `DFX_Text`daha ayrıntılı olarak açıklanacaktır.

DAO kayıt alanı değişim süreci hakkında anlaşılması gereken en `GetRows` önemli özellik `CDaoRecordset` nesnenin işlevini kullanmasıdır. DAO `GetRows` işlevi çeşitli şekillerde çalışabilir. Bu teknik not, bu `GetRows` teknik notun kapsamı dışında olduğu için yalnızca kısa bir süre açıklanacaktır.
DAO `GetRows` çeşitli şekillerde çalışabilir.

- Aynı anda birden çok kayıt ve birden çok veri alanını getirebilir. Bu, büyük bir veri yapısı ve her alana ve yapıdaki her veri kaydı için uygun uzaklıklarla başa çıkma komplikasyonuyla daha hızlı veri erişimi sağlar. MFC bu çoklu kayıt alma mekanizmasından yararlanmaz.

- Çalışabilen başka bir yol `GetRows` da, programcıların her alanın alınan verileri için bir veri kaydı için bağlayıcı adresler belirtmesine izin vermektir.

- DAO ayrıca, arayanın bellek ayırmasına izin vermek için değişken uzunluktaki sütunlar için arayanın içine "geri çağrı" yapacaktır. Bu ikinci özellik, veri kopyalarının sayısını en aza indirmenin yanı sıra verilerin bir sınıfın üyelerine `CDaoRecordset` (türetilmiş sınıf) doğrudan depolanmasına izin verme avantajına sahiptir. Bu ikinci mekanizma, MFC'nin türemiş `CDaoRecordset` sınıflardaki veri üyelerine bağlamak için kullandığı yöntemdir.

## <a name="what-your-custom-dfx-routine-does"></a><a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a>Özel DFX Yordamınız Ne Yapar?

Bu tartışmadan, herhangi bir DFX işlevinde uygulanan en önemli işlemin, başarılı bir şekilde aramak `GetRows`için gerekli veri yapılarını ayarlama becerisi olması gerektiği açıktır. Bir DFX işlevinin de desteklemesi gereken bir dizi işlem vardır, ancak hiçbiri `GetRows` çağrıya doğru şekilde hazırlanmak kadar önemli veya karmaşık değildir.

DFX kullanımı çevrimiçi belgelerde açıklanmıştır. Esasen, iki gereksinimleri vardır. İlk olarak, üyeler her `CDaoRecordset` bağlı alan ve parametre için türemiş sınıfa eklenmelidir. Bunu `CDaoRecordset::DoFieldExchange` takiben geçersiz kılınmalıdır. Üyenin veri türünün önemli olduğunu unutmayın. Veritabanındaki alandaki verileri eşleştirmeli veya en azından bu türe dönüştürülebilir olmalıdır. Örneğin, veritabanındaki uzun bir tamsayı gibi sayısal bir alan her zaman metne dönüştürülebilir ve bir `CString` üyeye bağlanabilir, ancak veritabanındaki metin alanı, uzun tamsayı ve uzun bir tamsayı üyesine bağlı gibi sayısal bir gösterime dönüştürülemez. DAO ve Microsoft Jet veritabanı altyapısı dönüştürmeden (MFC yerine) sorumludur.

## <a name="details-of-dfx_text"></a><a name="_mfcnotes_tn053_details_of_dfx_text"></a>DFX_Text ayrıntıları

Daha önce de belirtildiği gibi, DFX'in nasıl çalıştığını açıklamanın en iyi yolu bir örnek üzerinden çalışmaktır. Bu amaçla iç geçiyor oldukça `DFX_Text` iyi DFX en azından temel bir anlayış sağlamak için çalışmalıdır.

- `AddToParameterList`

   Bu işlem, Jet tarafından gerekli`Parameters <param name>, <param type> ... ;`SQL **PARAMETRELERi** yan tümcesini (" ") oluşturur. Her parametre adlandırılmış ve (RFX çağrısında belirtildiği gibi) yazılmıştır. Tek tek `CDaoFieldExchange::AppendParamType` türlerin adlarını görmek için işlev işlevine bakın. Durumda `DFX_Text`, kullanılan tür **metindir.**

- `AddToSelectList`

   SQL **SELECT** yan tümcesini oluşturur. DFX çağrısı tarafından belirtilen sütun adı basitçe eklenmiş olduğundan bu`SELECT <column name>, ...`oldukça yalındır (" ").

- `BindField`

   Operasyonların en karmaşıkı. Daha önce de belirtildiği gibi, bu `GetRows` da kullanılan DAO bağlama yapısı nın kurulduğu yerdir. Koddan da görebileceğiniz `DFX_Text` gibi yapıdaki bilgi türlerinde kullanılan DAO türü **(DAO_CHAR** veya `DFX_Text` **DAO_WCHAR** durumunda) bulunmaktadır. Ayrıca, kullanılan bağlama türü de ayarlanır. Daha önceki `GetRows` bir bölümde sadece kısa bir süre açıklanmıştır, ancak MFC tarafından kullanılan bağlama türü her zaman doğrudan adres bağlama **(DAOBINDING_DIRECT)** olduğunu açıklamak için yeterli ydi. MFC bellek ayırma denetimi ve `DFX_Text`doğru uzunlukta bir adres belirtebilmek için değişken uzunlukta sütun bağlama (gibi) geri arama bağlama için ek olarak kullanılır. Bunun anlamı, MFC'nin DAO'ya her zaman verileri "nereye" koyacağını söyleyebilmesi ve böylece doğrudan üye değişkenlere bağlanmaya izin verdiğidir. Bağlama yapısının geri kalanı bellek ayırma geri arama işlevinin adresi ve sütun bağlama türü (sütun adına göre bağlama) gibi şeylerle doldurulur.

- `BindParam`

   Bu, parametre üyenizde belirtilen parametre değeriyle çağıran `SetParamValue` basit bir işlemdir.

- `Fixup`

   Her alan için **NULL** durumunu doldurur.

- `SetFieldNull`

   Bu işlem yalnızca her alan durumunu **NULL** olarak işaretler ve üye değişkenin değerini **PSEUDO_NULL**ayarlar.

- `SetDirtyField`

   Her `SetFieldValue` alan için aramalar kirli işaretlenmiş.

Kalan tüm işlemler yalnızca veri önbelleğinin kullanılmasıyla ilgilenir. Veri önbelleği, geçerli kayıttaki verilerin belirli şeyleri basithale getirmek için kullanılan ek bir arabelleğidir. Örneğin, "kirli" alanlar otomatik olarak algılanabilir. Çevrimiçi belgelerde açıklandığı gibi tamamen veya alan düzeyinde kapatılabilir. Arabellek uygulaması bir harita kullanır. Bu harita, dinamik olarak ayrılmış veri kopyalarını "bağlı" alanın (veya türetilen `CDaoRecordset` veri üyesinin) adresiyle eşleştirmek için kullanılır.

- `AllocCache`

   Önbelleğe alınmış alan değerini dinamik olarak ayırır ve eşe ekler.

- `FreeCache`

   Önbelleğe alınan alan değerini siler ve haritadan kaldırır.

- `StoreField`

   Geçerli alan değerini veri önbelleğine kopyalar.

- `LoadField`

   Önbelleğe alınmış değeri alan üyesine kopyalar.

- `MarkForAddNew`

   Geçerli alan değerinin**NULL** olup olmadığını denetler ve gerekirse kirli işaretler.

- `MarkForEdit`

   Geçerli alan değerini veri önbelleğiyle karşılaştırır ve gerekirse kirli işaretleri işaretler.

> [!TIP]
> Standart veri türleri için varolan DFX yordamları üzerinde özel DFX yordamları modelleştirin.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
