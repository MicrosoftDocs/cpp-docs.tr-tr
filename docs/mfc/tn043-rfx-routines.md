---
description: 'Daha fazla bilgi edinin: TN043: RFX yordamları'
title: 'TN043: RFX Rutinleri'
ms.date: 06/28/2018
f1_keywords:
- RFX
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
ms.openlocfilehash: 6e5ac8271739e5cab80b79cb915b07e7d25622cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97215228"
---
# <a name="tn043-rfx-routines"></a>TN043: RFX Rutinleri

> [!NOTE]
> Aşağıdaki teknik Not, çevrimiçi belgelere ilk eklenmesinden beri güncelleştirilmemiş. Sonuç olarak, bazı yordamlar ve konular güncel olmayabilir veya yanlış olabilir. En son bilgiler için çevrimiçi belge dizininde ilgilendiğiniz konuyu aramanız önerilir.

Bu notta kayıt alanı değişimi (RFX) mimarisi açıklanmaktadır. Ayrıca, bir **RFX_** yordamının nasıl yazılacağını açıklar.

## <a name="overview-of-record-field-exchange"></a>Kayıt alanı değişimine genel bakış

Tüm kayıt kümesi alanı işlevleri C++ kodu ile yapılır. Özel kaynak veya sihirli makrolar yoktur. Mekanizmanın kalp, her türetilmiş kayıt kümesi sınıfında geçersiz kılınabilmesi gereken bir sanal işlevdir. Bu formda her zaman bulunur:

```cpp
void CMySet::DoFieldExchange(CFieldExchange* pFX)
{
    //{{AFX_FIELD_MAP(CMySet)
        <recordset exchange field type call>
        <recordset exchange function call>
    //}}AFX_FIELD_MAP
}
```

Özel biçim AFX açıklamaları ClassWizard 'ın bu işlev içindeki kodu bulmasını ve düzenlemesini sağlar. ClassWizard ile uyumlu olmayan kod, özel biçim açıklamalarının dışına yerleştirilmelidir.

Yukarıdaki örnekte, \<recordset_exchange_field_type_call> şu biçimdedir:

```cpp
pFX->SetFieldType(CFieldExchange::outputColumn);
```

ve \<recordset_exchange_function_call> şu biçimdedir:

```cpp
RFX_Custom(pFX, "Col2", m_Col2);
```

Çoğu **RFX_** işlevi yukarıda gösterildiği gibi üç bağımsız değişkene sahiptir, ancak bazıları (ör. `RFX_Text` ve `RFX_Binary` ) ek isteğe bağlı bağımsız değişkenlere sahiptir.

Her işlevde birden fazla **RFX_** bulunabilir `DoDataExchange` .

MFC ile birlikte sunulan tüm kayıt kümesi alanı değişim yordamlarının listesi için bkz. ' Afxdb. h '.

Kayıt kümesi alan çağrıları, bir sınıf için alan verilerini depolamak üzere bellek konumlarını (genellikle veri üyeleri) kaydetmenin bir yoludur `CMySet` .

## <a name="notes"></a>Notlar

Kayıt kümesi alanı işlevleri yalnızca sınıflarla çalışacak şekilde tasarlanmıştır `CRecordset` . Bunlar, diğer MFC sınıfları tarafından genel olarak kullanılabilir değildir.

İlk veri değerleri standart C++ oluşturucusunda, genellikle ve açıklamaları olan bir blokta ayarlanır `//{{AFX_FIELD_INIT(CMylSet)` `//}}AFX_FIELD_INIT` .

Her bir **RFX_** işlevi, alanı düzenlemenin hazırlanmasından alanı arşivlemek için alanın kirli durumunun döndürülmesinin yanı değişen çeşitli işlemleri desteklemelidir.

Çağıran her işlev `DoFieldExchange` (örneğin `SetFieldNull` , `IsFieldDirty` ), çağrısı etrafında kendi başlatmasını yapar `DoFieldExchange` .

## <a name="how-does-it-work"></a>Nasıl çalışır?

Kayıt alanı değişimini kullanmak için aşağıdakileri anlamanız gerekmez. Ancak, bunun arka planda nasıl çalıştığını anlamak kendi Exchange yordamınıza yazmanızı sağlamanıza yardımcı olur.

`DoFieldExchange`Üye işlevi, üye işlevine çok benzer `Serialize` — bir dış formdan (bir ODBC sorgusunun sonucundan alınan sütunlarda), sınıftaki üye verilerinden/öğesinden veri alma veya sunucudan veri ayarlamaktan sorumludur. *PFX* parametresi, veri değişimi yapma bağlamıdır ve *CArchive* parametresine benzerdir `CObject::Serialize` . *PFX* (bir `CFieldExchange` nesne) için bir işlem göstergesi, ancak *CArchive* yön bayrağının genelleştirilmesidir. Bir RFX işlevinin aşağıdaki işlemleri desteklemesi gerekebilir:

- `BindParam` — ODBC 'nin parametre verilerini alması gereken yeri belirtin

- `BindFieldToColumn` — ODBC 'nin outputColumn verilerini alması/depozito gereken yeri belirtin

- `Fixup` — `CString/CByteArray` Uzunlukları ayarla, null durum bitini ayarla

- `MarkForAddNew` — AddNew çağrısından bu yana değer değiştiyse kirli olarak işaretle

- `MarkForUpdate` — Bu tarihten sonra değer değiştiyse kirli olarak işaretle

- `Name` — Kirli olarak işaretlenmiş alanlar için alan adlarını ekleyin

- `NameValue` — \<column name> Kirli olarak işaretlenmiş alanlar için "=" ekleyin

- `Value` — ', ' Veya ' ' gibi ayracın ardından "" ekleyin

- `SetFieldDirty` — Durum bit kirli (ör. değiştirilen) alanını ayarla

- `SetFieldNull` — Alanın null değerini gösteren durum bitini ayarla

- `IsFieldDirty` — Kirli durum bitinin dönüş değeri

- `IsFieldNull` — Null durum bitinin dönüş değeri

- `IsFieldNullable` — Alan NULL değerleri tutabiliyorsa, TRUE döndürün

- `StoreField` — Arşiv alanı değeri

- `LoadField` — Arşivlenmiş alan değerini yeniden yükle

- `GetFieldInfoValue` — Bir alanla ilgili genel bilgileri döndür

- `GetFieldInfoOrdinal` — Bir alanla ilgili genel bilgileri döndür

## <a name="user-extensions"></a>Kullanıcı Uzantıları

Varsayılan RFX mekanizmasını genişletmek için birkaç yol vardır. Şunları yapabilirsiniz

- Yeni veri türleri ekleyin. Örneğin:

    ```cpp
    CBookmark
    ```

- Yeni Exchange yordamları (RFX_) ekleyin.

    ```cpp
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
        const char *szName,
        BIGINT& value);
    ```

- `DoFieldExchange`Üye işlevine, ek RFX çağrılarını veya diğer geçerli C++ deyimlerini koşullu olarak ekleyin.

    ```cpp
    while (posExtraFields != NULL)
    {
        RFX_Text(pFX,
        m_listName.GetNext(posExtraFields),
        m_listValue.GetNext(posExtraValues));
    }
    ```

> [!NOTE]
> Bu kod, ClassWizard tarafından düzenlenemez ve yalnızca özel biçim açıklamalarının dışında kullanılmalıdır.

## <a name="writing-a-custom-rfx"></a>Özel bir RFX yazma

Kendi özel RFX işlevinizi yazmak için, var olan bir RFX işlevini kopyalamanız ve kendi amacınıza göre değiştirmeniz önerilir. Kopyalanacak doğru RFX seçilmesi, işinizi çok daha kolay hale getirir. Bazı RFX işlevleri, kopyalamanın ne olduğuna karar verirken dikkate almanız gereken bazı benzersiz özelliklere sahiptir.

`RFX_Long` ve `RFX_Int` : Bunlar en basıt RFX işlevleridir. Veri değeri herhangi bir özel yorumu gerektirmez ve veri boyutu sabittir.

`RFX_Single` ve `RFX_Double` : yukarıdaki RFX_Long ve RFX_Int gibi, bu işlevler basittir ve varsayılan uygulamayı kapsamlı olarak kullanabilir. Ancak, yalnızca açıkça başvurduklarında çalışma zamanı kayan nokta kitaplığını yüklemeyi etkinleştirmek için dbrfx. cpp yerine dbflt. cpp içinde depolanır.

`RFX_Text` ve `RFX_Binary` : Bu iki işlev, dize/ikili bilgileri tutmak için statik bir arabellek önceden ayırır ve bu arabellekleri &değerini kaydetmek yerıne ODBC SQLBindCol ile kaydetmelidir. Bu nedenle, bu iki işlev çok sayıda özel durum koduna sahiptir.

`RFX_Date`: ODBC, kendi TIMESTAMP_STRUCT veri yapısındaki tarih ve saat bilgilerini döndürür. Bu işlev, tarih saat verilerinin gönderilmesi ve alınması için bir TIMESTAMP_STRUCT dinamik olarak bir "proxy" olarak ayırır. Çeşitli işlemler, C++ `CTime` nesnesi ve TIMESTAMP_STRUCT proxy arasında tarih ve saat bilgilerini aktarmalıdır. Bu, bu işlevi önemli ölçüde karmaşıklaştırır, ancak veri aktarımı için proxy kullanma konusunda iyi bir örnektir.

`RFX_LongBinary`: Bu, veri almak ve göndermek için sütun bağlamayı kullanmayan tek sınıf kitaplığı RFX işlevidir. Bu işlev, BindFieldToColumn işlemini yoksayar ve bunun yerine, düzeltme işlemi sırasında depolama alanını gelen SQL_LONGVARCHAR veya SQL_LONGVARBINARY verileri tutacak şekilde ayırır, ardından değeri ayrılan depolamaya almak için bir SQLGetData çağrısı gerçekleştirir. Veri değerlerini veri kaynağına (NameValue ve value işlemleri gibi) geri göndermek için hazırlanırken, bu işlev ODBC 'nin DATA_AT_EXEC işlevselliğini kullanır. SQL_LONGVARBINARY ve SQL_LONGVARCHARs çalışma hakkında daha fazla bilgi için bkz. [Teknik bilgi 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) .

Kendi **RFX_** işlevinizi yazarken, genellikle `CFieldExchange::Default` belirli bir işlemi uygulamak için kullanabilirsiniz. Söz konusu işlem için varsayılan uygulamaya bakın. Bu işlem, **RFX_** işlevinizde yazma işlemi gerçekleştirirse, ' a temsilci seçebilirsiniz `CFieldExchange::Default` . `CFieldExchange::Default`Dbrfx. cpp içinde çağırma örnekleri görebilirsiniz

`IsFieldType`RFX işlevinizin başlangıcında çağırmak önemlidir ve false döndürürse hemen döndürülür. Bu mekanizma, *outputColumns* üzerinde parametre işlemlerinin gerçekleştirilmesini önler ve tam tersi de ( `BindParam` bir *outputColumn* üzerinde çağırma gibi). Ayrıca, `IsFieldType` *outputcolumns* (*m_nFields*) ve params (*m_nParams*) sayısını otomatik olarak izler.

## <a name="see-also"></a>Ayrıca bkz.

[Sayıya göre teknik notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye göre teknik notlar](../mfc/technical-notes-by-category.md)
