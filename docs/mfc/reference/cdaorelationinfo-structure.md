---
title: CDaoRelationInfo Yapısı
ms.date: 06/25/2018
f1_keywords:
- CDaoRelationInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
ms.openlocfilehash: 7d1c86732966d8222582dc6d4527af89963a5cdc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62152832"
---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo Yapısı

`CDaoRelationInfo` Yapısı iki tablo alanlar arasında tanımlanmış bir ilişkisi hakkında bilgi içeren bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesne.

## <a name="syntax"></a>Sözdizimi

```cpp
struct CDaoRelationInfo
{
    CDaoRelationInfo();                     // Constructor
    CString m_strName;                      // Primary
    CString m_strTable;                     // Primary
    CString m_strForeignTable;              // Primary
    long m_lAttributes;                     // Secondary
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary
    short m_nFields;                        // Secondary
    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

#### <a name="parameters"></a>Parametreler

*m_strName*<br/>
İlişki nesnesi benzersiz olarak adlandırır. Daha fazla bilgi için "Name özelliği" DAO Yardım konusuna bakın.

*m_strTable*<br/>
İçindeki birincil tablo adları.

*m_strForeignTable*<br/>
İlişki yabancı tabloda adları. Bir dış tablo, yabancı anahtarlar kapsamak için kullanılmış bir tablodur. Genellikle, bir dış tablo oluşturmak veya bilgi tutarlılığını zorlamak için kullanın. Yabancı genellikle birçok bire çok ilişkisi tarafında tablosudur. Dış tablolar örnekleri Amerikan durumlarını veya Kanada il veya müşteri siparişleri için kodları barındıran tablolar içerir.

*m_lAttributes*<br/>
İlişki türü hakkında bilgi içerir. Bu üyenin değeri aşağıdakilerden biri olabilir:

- `dbRelationUnique` Bire bir ilişkidir.

- `dbRelationDontEnforce` İlişki (hiçbir bilgi tutarlılığı) zorunlu tutulur.

- `dbRelationInherited` İlişki, iki bağlı tabloları içeren çerçevesidir bir veritabanında zaten var.

- `dbRelationLeft` Sol birleştirme ilişkidir. Sol dış birleşim ilk kayıtlarını içerir (soldaki) iki tablonun ikinci (sağdaki) tablodaki kayıtların eşleşen değer yoksa olsa bile.

- `dbRelationRight` Sağ birleştirme ilişkidir. Sağ dış birleşim tüm ikinci kayıtlarını içerir (sağdaki) iki tablonun ilk (soldaki) bir tablodaki kayıtları için eşleşen değer yoksa olsa bile.

- `dbRelationUpdateCascade` Güncelleştirmeleri basamaklı.

- `dbRelationDeleteCascade` Silme işlemleri basamaklı.

*m_pFieldInfos*<br/>
Bir dizi işaretçi [Cdaorelationfieldınfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) yapıları. Dizi içindeki her bir alan için bir nesne içerir. `m_nFields` Veri üyesi, dizi öğelerinin sayısını verir.

*M_nFields*<br/>
Sayısını `CDaoRelationFieldInfo` nesneler `m_pFieldInfos` veri üyesi.

## <a name="remarks"></a>Açıklamalar

Birincil ve ikincil yukarıdaki başvuruları nasıl bilgileri tarafından döndürülen belirtmek [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) sınıf üyesi işlevinde `CDaoDatabase`.

İlişki nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, bir MFC nesnesinin temelindeki DAO nesne `CDaoDatabase` sınıfı ilişkisi nesnelerinin koleksiyonunu tutar: `CDaoDatabase` ilişkisi bilgilerini veya bazı tek tek öğelere erişmek için üye işlevleri kaynakları erişebileceği tek seferde bir ile`CDaoRelationInfo` çağırarak `GetRelationInfo` içeren veritabanı nesnesinin üye işlevi.

Tarafından alınan bilgileri [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) üye işlevi depolanan bir `CDaoRelationInfo` yapısı. `CDaoRelationInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoRelationInfo` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[CDaoRelationFieldInfo Yapısı](../../mfc/reference/cdaorelationfieldinfo-structure.md)
