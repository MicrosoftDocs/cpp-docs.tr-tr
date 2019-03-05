---
title: 'TN053: DAO veritabanı sınıfları için özel DFX rutinleri'
ms.date: 11/04/2016
f1_keywords:
- vc.mfc.dfx
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
ms.openlocfilehash: b610604c1b7a68128dc9eb6fb5515225ed22b16e
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57282415"
---
# <a name="tn053-custom-dfx-routines-for-dao-database-classes"></a>TN053: DAO veritabanı sınıfları için özel DFX rutinleri

> [!NOTE]
>  Sihirbazlar ve Visual C++ ortamına DAO (DAO sınıflarına eklenmiştir ve bunları kullanmaya devam edebilirsiniz ancak) desteklemez. Microsoft, kullanmanızı önerir [OLE DB Şablonları](../data/oledb/ole-db-templates.md) veya [ODBC ve MFC](../data/odbc/odbc-and-mfc.md) yeni projeler için. Yalnızca var olan uygulamaları sürdürmek DAO kullanmanız gerekir.

Bu teknik Not DAO kayıt alanı değişimi (DFX) mekanizmasını açıklar. DFX rutinleri içinde neler olduğunu anlamanıza yardımcı olması için `DFX_Text` işlevi, ayrıntılı bir örnek olarak verilecektir. Bu teknik Not bilgilerinin ek bir kaynak, kod diğeri için tek tek DFX işlevleri inceleyebilirsiniz. Büyük olasılıkla bir özel DFX yordamı (ODBC veritabanı sınıfları ile kullanılan) özel bir RFX yordamı ihtiyacınız olabilecek sıklıkta gerekli değildir.

Bu teknik Not içerir:

- DFX genel bakış

- [Örnekler](#_mfcnotes_tn053_examples) DAO kayıt alanı değişimi ve dinamik bağlama kullanma

- [DFX nasıl çalışır?](#_mfcnotes_tn053_how_dfx_works)

- [Özel DFX alışkanlık yapar](#_mfcnotes_tn053_what_your_custom_dfx_routine_does)

- [DFX_Text ayrıntıları](#_mfcnotes_tn053_details_of_dfx_text)

**DFX genel bakış**

DAO kayıt alanı değişimi mekanizması (DFX) alma ve veri kullanırken, güncelleştirme yordamı basitleştirmek için kullanılan `CDaoRecordset` sınıfı. Veri üyeleri kullanarak işlemi basitleştirilmiştir `CDaoRecordset` sınıfı. Türetilen `CDaoRecordset`, bir tablodaki veya sorgudaki her bir alanda temsil eden bir türetilmiş sınıf veri üyelerini ekleyebilirsiniz. Bu "statik bağlama" mekanizması basittir, ancak tüm uygulamalar için veri alma/güncelleştirme yöntemini tercih ettiğiniz olmayabilir. DFX ilişkili her alan geçerli kayıt değiştirilir her zaman alır. Para birimi değiştirildiğinde, her alan getirilirken gerektirmeyen bir performans duyarlı uygulama geliştiriyorsanız "dinamik bağlama" aracılığıyla `CDaoRecordset::GetFieldValue` ve `CDaoRecordset::SetFieldValue` tercih ettiğiniz veri erişimi yöntemi olabilir.

> [!NOTE]
>  Statik ve dinamik bağlama karma kullanımını kullanılabilmesi DFX ve dinamik bağlama birbirini dışlayan değildir.

## <a name="_mfcnotes_tn053_examples"></a> Örnek 1: DAO kayıt alanı değişimi yalnızca kullanımı

(varsayar `CDaoRecordset` — türetilmiş sınıf `CMySet` açık)

```
// Add a new record to the customers table
myset.AddNew();

myset.m_strCustID = _T("MSFT");

myset.m_strCustName = _T("Microsoft");

myset.Update();
```

**Örnek 2: kullanımı, yalnızca dinamik bağlama**

(kullanarak varsayar `CDaoRecordset` sınıfı `rs`, ve zaten açıktır)

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

**Örnek 3: Kullanım DAO kayıt alanı değişimi ve dinamik bağlama**

(gözatma çalışan verilerle varsayar `CDaoRecordset`-türetilmiş sınıf `emp`)

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

## <a name="_mfcnotes_tn053_how_dfx_works"></a> DFX nasıl çalışır?

MFC ODBC sınıfları tarafından kullanılan kayıt alanı değişimi (RFX) mekanizmasına benzer bir biçimde DFX mekanizması çalışır. DFX ve RFX prensipleri aynıdır, ancak çok sayıda dahili farklılıklar vardır. Neredeyse tüm kod bireysel DFX rutinleri tarafından paylaşılan şekilde DFX işlevleri tasarımını oluştu. En yüksek düzey DFX yalnızca birkaç şeyi yapar.

- DFX SQL yapıları **seçin** yan tümcesi ve SQL **parametreleri** gerekirse yan tümcesi.

- DFX DAO tarafından 's kullanılan bağlama yapısı oluşturur `GetRows` işlevi (Bu, daha sonra daha fazla).

- DFX (iki kez arabelleğe alma kullanılıyorsa) kirli alanları algılamak için kullanılan veri arabelleği yönetir

- DFX yönetir **NULL** ve **KİRLİ** durum diziler ve gerekirse, güncelleştirmeleri değerlerini ayarlar.

DFX yaklaşımının temelindeki mekanizmadır `CDaoRecordset` sınıfın türetilmiş `DoFieldExchange` işlevi. Bu işlev çağrıları tek tek DFX işlevleri uygun işlemi türü gönderir. Çağırmadan önce `DoFieldExchange` işlem türü iç MFC işlevleri ayarlayın. Aşağıdaki listede, çeşitli işlem türlerini ve kısa bir açıklaması gösterilir.

|Çalışma|Açıklama|
|---------------|-----------------|
|`AddToParameterList`|Derleme parametreleri yan tümcesi|
|`AddToSelectList`|Yapılar SELECT yan tümcesi|
|`BindField`|Bağlama yapısını ayarlar|
|`BindParam`|Parametre değerlerini ayarlar|
|`Fixup`|NULL durumu ayarlar|
|`AllocCache`|Önbellek kirli denetle ayırır.|
|`StoreField`|Geçerli kayıt önbelleğine kaydeder.|
|`LoadField`|Üye değerleri önbelleğe geri yükler|
|`FreeCache`|Önbellek serbest bırakır|
|`SetFieldNull`|& Durum null değer kümeleri alan|
|`MarkForAddNew`|Alanları kirli değilse SÖZDE NULL işaretler|
|`MarkForEdit`|İşaretleri alanları kirli if önbellek eşleşmiyor|
|`SetDirtyField`|Kirli olarak işaretlenmiş değerleri kümesi alanı|

Daha fazla ayrıntı için her işlem sonraki bölümde açıklanacaktır `DFX_Text`.

DAO kayıt alanı değişim işlemi hakkında anlamak için en önemli özelliği bunu kullanır `GetRows` işlevi `CDaoRecordset` nesne. DAO `GetRows` işlevi birkaç şekilde çalışabilir. Bu teknik not yalnızca kısaca açıklayın `GetRows` bu Teknik Not kapsamı dışında olsa da.

DAO `GetRows` birkaç şekilde çalışabilir.

- Tek seferde birden çok kayıt ve verilerin birden çok alan getirebilir. Bu, büyük veri yapısı ve her alana uygun uzaklıkları uğraşmanızı komplikasyon ile daha hızlı veri erişimi ve verilerin yapısı, her kayıt için sağlar. MFC mekanizması getirilirken bu birden çok kayıt avantajlarından almaz.

- Başka bir şekilde `GetRows` olabilir eserleridir alınan verilere ilişkin her alan için bir kayıt veri bağlama adresleribi belirtmek almak programcılar izin vermek için.

- DAO "Geri arayan değişken uzunluğu sütununa için bellek tahsis etmek çağrıyı yapanın için çağırıp" olur. Bu ikinci özellik verilerin kopyaları sayısını en aza indirme yanı sıra doğrudan depolama veri sağlayan bir sınıfın üyeleri avantajına sahiptir ( `CDaoRecordset` türetilmiş sınıf). MFC kullanan veri üyelerinde bağlamak için yöntemi bu ikinci mekanizmadır `CDaoRecordset` türetilmiş sınıflar.

##  <a name="_mfcnotes_tn053_what_your_custom_dfx_routine_does"></a> Özel DFX alışkanlık yapar

Herhangi bir DFX işlevde uygulanan en önemli işlemin başarıyla çağırmak için gerekli veri yapılarını ayarlamanıza olanak olması gereken bu tartışma açıktır `GetRows`. DFX işlevi de desteklemesi gereken diğer işlemleri, ancak hiçbiri olarak önemli ya da doğru şekilde hazırlama karmaşık bir dizi vardır `GetRows` çağırın.

Çevrimiçi belgelerdeki DFX kullanımı açıklanmaktadır. Esas olarak, iki gereksinimi yoktur. Üyeleri önce eklenmelidir `CDaoRecordset` türetilmiş sınıf için her bir ilişkili alan ve parametre. Bu aşağıdaki `CDaoRecordset::DoFieldExchange` geçersiz kılınmalıdır. Üyenin veri türü önemli olduğunu unutmayın. Alanından veritabanındaki verilerin eşleşmesi veya en az bu türe dönüştürülebilir olmalıdır. Örneğin sayısal bir alan gibi büyük bir tamsayı, veritabanındaki her zaman metne dönüştürülecek ve bağlı bir `CString` üyesi, ancak bir veritabanında bir metin alanı mutlaka uzun tamsayı gibi sayısal bir gösterimi dönüştürülür ve için bir uzun integ bağlı er üyesi. DAO ve Microsoft Jet veritabanı altyapısı, dönüştürme (yerine için MFC) sorumludur.

##  <a name="_mfcnotes_tn053_details_of_dfx_text"></a> DFX_Text ayrıntıları

Daha önce belirtildiği gibi DFX nasıl çalıştığını açıklamak için en iyi bir örnek üzerinde çalışmak için yoludur. İç işlevleri giderek bu amaçla `DFX_Text` DFX temel en az bir anlayış sağlamak için oldukça iyi çalışması.

- `AddToParameterList`

   Bu işlem, SQL yapıları **parametreleri** yan tümcesi ("`Parameters <param name>, <param type> ... ;`") tarafından Jet gerekli. Her parametre adlı ve (RFX çağrısında belirtildiği şekilde) türü belirtilmiş. İşlevi görmek `CDaoFieldExchange::AppendParamType` tek tek türleri adlarını görmek için işlev. Durumunda, `DFX_Text`, kullanılan türü **metin**.

- `AddToSelectList`

   SQL derlemeleri **seçin** yan tümcesi. Bu oldukça kolay anlaşılır DFX çağrı tarafından belirtilen sütun adı yalnızca olarak eklenir ("`SELECT <column name>, ...`").

- `BindField`

   En karmaşık işlemleri. Bu, DAO bağlama yapısı tarafından kullanıldığı daha önce belirtildiği gibi `GetRows` ayarlanır. Koddan gördüğünüz gibi `DFX_Text` kullanılan DAO türü yapısında bilgi türlerini içerir (**DAO_CHAR** veya **DAO_WCHAR** durumunda `DFX_Text`). Ayrıca, kullanılan bağlama türünü de ayarlanır. Bir önceki bölümdeki `GetRows` yalnızca kısaca açıklandığı gibi, ancak MFC tarafından kullanılan bağlama türünü her zaman doğrudan adresi bağlama olduğunu açıklamak yeterli (**DAOBINDING_DIRECT**). Değişken uzunluklu sütun bağlama için buna (gibi `DFX_Text`) geri çağırma bağlama kullanılan MFC denetim bellek ayırma ve doğru uzunlukta bir adres belirtin. Ne Bu, MFC anlamına gelir her zaman DAO böylece doğrudan üye değişkenlerine bağlama izin vererek verilerini yerleştirmek "nerede" söyleyebilirsiniz. Bağlama yapısı geri kalanını adresini bellek ayırma geri çağırma işlevi ve türü sütun bağlama (bağlama sütun adına göre) gibi şeyleri doldurulur.

- `BindParam`

   Bu çağıran, basit bir işlemdir `SetParamValue` , parametre üye belirtilen parametre değeri.

- `Fixup`

   Doldurur **NULL** her alan için durum.

- `SetFieldNull`

   Bu işlem yalnızca her alan durumu olarak işaretler **NULL** ve üye değişkenin değeri olarak ayarlar **PSEUDO_NULL**.

- `SetDirtyField`

   Çağrıları `SetFieldValue` kirli olarak işaretlenmiş her bir alan için.

Kalan tüm işlemleri, yalnızca veri önbelleğini kullanmaya ilgilenir. Veri önbelleği belirli şeyleri daha basit hale getirmek için kullanılan geçerli kayıt verilerin fazladan bir arabellek değil. Örneğin, "kirli" alanları otomatik olarak algılanabilir. Çevrimiçi belgelerdeki açıklandığı gibi tam olarak veya alan düzeyinde kapatılabilir. Arabellek uygulamasını bir eşleme kullanır. Bu harita dinamik olarak ayrılan verilerin kopyalarını "bağlı" alanının adresi oluşturan eşleştirmek için kullanılır (veya `CDaoRecordset` veri üyesi türetilmiş).

- `AllocCache`

   Dinamik olarak önbelleğe alan değeri ayırır ve haritayı ekler.

- `FreeCache`

   Önbelleğe alınan bir alan değerini siler ve eşlemden kaldırır.

- `StoreField`

   Geçerli alan değeri, verileri önbelleğe kopyalar.

- `LoadField`

   Önbelleğe alınan değeri alan üye kopyalar.

- `MarkForAddNew`

   Geçerli alan değeri olmayan olup olmadığını denetler**NULL** ve kirli gerekirse eşitler.

- `MarkForEdit`

   Veri önbelleği ile güncel alan değerini karşılaştırır ve gerekirse kirli olarak işaretler.

> [!TIP]
> Standart veri türleri için mevcut DFX rutinleri üzerinde özel DFX rutinleri model.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
