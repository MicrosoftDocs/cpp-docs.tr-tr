---
title: 'TN043: RFX rutinleri | Microsoft Docs'
ms.custom: ''
ms.date: 06/28/2018
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- RFX
dev_langs:
- C++
helpviewer_keywords:
- RFX (record field exchange), architecture
- TN043
- RFX (record field exchange)
ms.assetid: f552d0c1-2c83-4389-b472-42c9940aa713
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a35fc217b6600fd701dcc1750c327ffc7f241e8e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46376661"
---
# <a name="tn043-rfx-routines"></a>TN043: RFX Rutinleri

> [!NOTE]
> Aşağıdaki Teknik Not çevrimiçi belgelere ilk eklenmiştir beri güncelleştirilmemiş. Eski veya yanlış sonuç olarak, bazı yordamlar ve konular olabilir. En son bilgiler için bu konuyu çevrimiçi belge dizininde arama önerilir.

Bu Not kayıt alanı değişimi (RFX) mimarisini açıklar. Ayrıca, nasıl yazılır açıklar bir **RFX_** yordamı.

## <a name="overview-of-record-field-exchange"></a>Kayıt alanı değişimi genel bakış

Tüm kayıt alan İşlevler, C++ kodu ile gerçekleştirilir. Özel kaynaklar veya Sihirli makroları yoktur. Her kayıt türetilen sınıfta geçersiz kılınması sanal bir işlev mekanizmasını kalbidir. Her zaman bu formda de bulunur:

```cpp
void CMySet::DoFieldExchange(CFieldExchange* pFX)
{
    //{{AFX_FIELD_MAP(CMySet)
        <recordset exchange field type call>
        <recordset exchange function call>
    //}}AFX_FIELD_MAP
}
```

Özel biçim AFX açıklamaları ClassWizard bulun ve bu işlev içindeki kod düzenlemek izin verin. ClassWizard ile uyumlu olmayan kod dışında özel biçim açıklamaları yerleştirilmelidir.

Yukarıdaki örnekte, \<recordset_exchange_field_type_call > şu şekildedir:

```cpp
pFX->SetFieldType(CFieldExchange::outputColumn);
```

ve \<recordset_exchange_function_call > şu şekildedir:

```cpp
RFX_Custom(pFX, "Col2", m_Col2);
```

Çoğu **RFX_** işlevlerine sahip üç yukarıda da gösterildiği gibi bağımsız değişkenleri, ancak bazı (örneğin `RFX_Text` ve `RFX_Binary`) ek isteğe bağlı bağımsız değişkenlere sahip.

Birden fazla **RFX_** her eklenebilir `DoDataExchange` işlevi.

'Afxdb.h' MFC ile sağlanan tüm kayıt alanı değişimi rutinleri listesi için bkz.

Kayıt kümesi alanı çağrılarıdır alan verilerini depolamak için bellek konumları (genellikle veri üyeleri) kaydetme bir yol bir `CMySet` sınıfı.

## <a name="notes"></a>Notlar

Kayıt kümesi alanı işlevleri yalnızca birlikte çalışmak üzere tasarlanan `CRecordset` sınıfları. Bunlar herhangi bir MFC sınıfları tarafından genel olarak kullanılabilir değildir.

İlk veri değerlerinin standart C++ oluşturucuda, genellikle bir bloğu ile ayarlanır `//{{AFX_FIELD_INIT(CMylSet)` ve `//}}AFX_FIELD_INIT` yorumlar.

Her **RFX_** işlevi alan düzenleme, hazırlama alanına arşivlenmesine alanın kirli durumu döndüren arasında çeşitli işlemler desteklemesi gerekir.

Çağıran her işlev `DoFieldExchange` (örneğin `SetFieldNull`, `IsFieldDirty`), kendi başlatmayı etrafında çağrısı yapan `DoFieldExchange`.

## <a name="how-does-it-work"></a>Nasıl çalışır

Kayıt alanı değişimi kullanmak için aşağıdakileri anlamanız gerekmez. Ancak, bunun arka planda nasıl çalıştığını yardımcı olacak anlama, kendi exchange yordamı yazın.

`DoFieldExchange` Üye işlevi olan çok benzer `Serialize` üye işlevi — ayarlamanın ya veri gönderip buralardan bir dış biçiminde (ODBC sorgusunun sonucunu bu büyük/küçük harf sütunları) / sınıf üyesi verilerine sorumludur. *PFX* parametre veri alışverişi yapmak için bağlam ve benzer *CArchive* parametresi `CObject::Serialize`. *PFX* (bir `CFieldExchange` nesnesi) benzer bir işlem göstergesi, ancak genelleştirilmiş *CArchive* yön bayrağı. RFX işlevi aşağıdaki işlemleri desteklemek sahip olabilir:

- `BindParam` — Belirtin ODBC parametre verileri nerede almanız gerekir

- `BindFieldToColumn` Gösterir burada ODBC alma/outputColumn veri havale gerekir

- `Fixup` — Ayarlama `CString/CByteArray` uzunlukları, bit NULL durumu ayarla

- `MarkForAddNew` — İşareti kirli AddNew çağrısından değer değiştiyse

- `MarkForUpdate` — İşareti kirli düzenleme çağrısından değer değiştiyse

- `Name` — Kirli olarak işaretlenmiş alanlar için alan adlarını ekleme

- `NameValue` — Ekleme "\<sütun adı > =" kirli olarak işaretlenmiş alanlar için

- `Value` — Ekle "" ayırıcı tarafından izlenen, ister ',' veya ' '

- `SetFieldDirty` — Durum bit kirli (yani değiştirilen) alanını ayarlayın

- `SetFieldNull` — Durumu bit alanı için null değer belirten ayarlayın

- `IsFieldDirty` — Kirli durumu bit değeri döndürür

- `IsFieldNull` — Null durumu bit değeri döndürür

- `IsFieldNullable` — Alan NULL değerlerini tutabilecek, TRUE döndürür

- `StoreField` — Arşiv alan değeri

- `LoadField` — Arşivlenmiş alan değeri yeniden yükleyin.

- `GetFieldInfoValue` — Bir alan genel bilgiler döndürür.

- `GetFieldInfoOrdinal` — Bir alan genel bilgiler döndürür.

## <a name="user-extensions"></a>Kullanıcı Uzantıları

Varsayılan RFX mekanizmasını genişletmek için birkaç yolu vardır. Şunları yapabilirsiniz

- Yeni veri türleri ekleyin. Örneğin:

    ```cpp
    CBookmark
    ```

- Yeni exchange yordamlar (RFX_) ekleyin.

    ```cpp
    void AFXAPI RFX_Bigint(CFieldExchange* pFX,
        const char *szName,
        BIGINT& value);
    ```

- Sahip `DoFieldExchange` üye işlevi koşullu olarak dahil ek RFX çağrıları veya diğer herhangi bir geçerli C++ deyimleri.

    ```cpp
    while (posExtraFields != NULL)
    {
        RFX_Text(pFX,
        m_listName.GetNext(posExtraFields),
        m_listValue.GetNext(posExtraValues));
    }
    ```

> [!NOTE]
> Bu tür kod ClassWizard tarafından düzenlenemez ve yalnızca özel biçim yorumları dışında kullanılması gerekir.

## <a name="writing-a-custom-rfx"></a>Özel RFX yazma

Kendi özel RFX işlevi yazmak için mevcut bir RFX işlevi kopyalayıp kendi amaçlarınız için değiştirebilirsiniz önerilir. Kopyalamak için sağ RFX seçmek, işinizi çok daha kolay yapabilirsiniz. Bazı RFX işlevleri kopyalanacağı karar verirken dikkate almanız benzersiz bazı özellikler vardır.

`RFX_Long` ve `RFX_Int`: Basit RFX işlevleri şunlardır. Veri değeri herhangi bir özel yorumu gerekli değildir ve veri boyutu sabit.

`RFX_Single` ve `RFX_Double`: gibi RFX_Long ve yukarıdaki rfx_ınt, bu işlevler basittir ve yapabilirsiniz varsayılan uygulamasını kapsamlı bir şekilde kullanın. Bunlar dbflt.cpp yerine dbrfx.cpp, ancak yalnızca açıkça başvuru olduklarında noktası kitaplığı kayan çalışma zamanı yükleme etkinleştirmek için depolanır.

`RFX_Text` ve `RFX_Binary`: Bu iki işlev dizesi/ikili bilgiyi tutmak için statik bir arabellek erişinceye ve kaydetme & değeri yerine bu arabellekleri ODBC SQLBindCol ile kaydetmeniz gerekir. Bu nedenle, bu iki işlev özel durum kodu bulunmaktadır.

`RFX_Date`: ODBC kendi TIMESTAMP_STRUCT veri yapısında tarih ve saat bilgilerini döndürür. Bu işlev dinamik olarak bir TIMESTAMP_STRUCT bir "proxy" olarak göndermek ve tarih saat verilerini almak için ayırır. Çeşitli işlemler arasında C++ tarih ve saat bilgilerini aktarmalısınız `CTime` nesne ve TIMESTAMP_STRUCT proxy. Bu işlev bu oldukça karmaşık hale getirir, ancak bu veri aktarımı için bir ara sunucu kullanmak nasıl daha iyi bir örnektir.

`RFX_LongBinary`: Yalnızca sınıf kitaplığı veri gönderip için sütun bağlama kullanmaz RFX işlev budur. Bu işlev BindFieldToColumn işlemi yok sayar ve bunun yerine, düzeltme işlemi sırasında gelen SQL_LONGVARCHAR veya SQL_LONGVARBINARY verileri tutmak için depolama alanı ayırır ve ardından ayrılan depolama alanına değerini almak için bir SQLGetData araması gerçekleştirir. Bu işlev, veri değerlerinin (örneğin, işlemi NameValue ve değer) veri kaynağına geri göndermek hazırlık yaparken, ODBC DATA_AT_EXEC işlevselliğini kullanır. Bkz: [Teknik Not 45](../mfc/tn045-mfc-database-support-for-long-varchar-varbinary.md) SQL_LONGVARBINARY ve SQL_LONGVARCHARs ile çalışma hakkında daha fazla bilgi.

Kendi yazarken **RFX_** işlevi, genellikle oluşturabileceksiniz kullanılacak `CFieldExchange::Default` belirli bir işlemini uygulamak için. Varsayılan uygulama söz konusu işlemi için bakın. İşlemi gerçekleştirdiğinde, yazma, **RFX_** işlevi için temsilci `CFieldExchange::Default`. Arama örneklerini gördüğünüz `CFieldExchange::Default` dbrfx.cpp içinde

Çağrılacak önemlidir `IsFieldType` RFX işlevi ve hemen FALSE döndürürse dönüş başlangıcı. Bu mekanizma üzerinde gerçekleştirilen gelen parametre operations tutar *outputColumns*ve bunun tersi de geçerlidir (arama gibi `BindParam` üzerinde bir *outputColumn*). Ayrıca, `IsFieldType` otomatik olarak sayısını izler *outputColumns* (*m_nFields*) ve params (*m_nParams*).

## <a name="see-also"></a>Ayrıca Bkz.

[Sayıya Göre Teknik Notlar](../mfc/technical-notes-by-number.md)<br/>
[Kategoriye Göre Teknik Notlar](../mfc/technical-notes-by-category.md)
