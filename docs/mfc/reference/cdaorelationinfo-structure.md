---
description: 'Daha fazla bilgi edinin: CDaoRelationInfo yapısı'
title: CDaoRelationInfo Yapısı
ms.date: 06/25/2018
f1_keywords:
- CDaoRelationInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
ms.openlocfilehash: efcc880d30dd18108005d9c4f265238b81551532
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222248"
---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo Yapısı

`CDaoRelationInfo`Yapı, bir [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) nesnesindeki iki tablonun alanları arasında tanımlı bir ilişki hakkında bilgiler içerir.

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
İlişki nesnesini benzersiz olarak adlandırır. Daha fazla bilgi için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

*m_strTable*<br/>
İlişkide birincil tabloyu adlandırır.

*m_strForeignTable*<br/>
İlişkide yabancı tabloyu adlandırır. Yabancı tablo, yabancı anahtarlar içeren bir tablodur. Genellikle, bilgi tutarlılığı oluşturmak veya zorlamak için bir yabancı tablo kullanırsınız. Yabancı tablo genellikle bire çok ilişkisinin çok tarafında bulunur. Yabancı tablo örnekleri, Amerika ABD veya Kanada eyaletlerinin veya müşteri siparişlerinin kodlarını içeren tabloları içerir.

*m_lAttributes*<br/>
İlişki türü hakkında bilgi içerir. Bu üyenin değeri aşağıdakilerden herhangi biri olabilir:

- `dbRelationUnique` İlişki bire bir.

- `dbRelationDontEnforce` İlişki zorlanmaz (başvurusal bütünlük yok).

- `dbRelationInherited` İlişki, iki bağlantılı tabloyu içeren geçerli olmayan bir veritabanında bulunuyor.

- `dbRelationLeft` İlişki bir sol birleşimdir. Sol dış birleşim, ikinci tablonun birincisine (sol taraftaki) ait tüm kayıtları (sağ taraftaki) tablosunda kayıtlar için eşleşen değer olmasa bile içerir.

- `dbRelationRight` İlişki, doğru bir birleşimdir. Sağ dış birleşim, birinci (sol taraftaki) tablodaki kayıtlar için eşleşen değer olmasa bile, iki tablonun ikinciden (sağ tarafından) tüm kayıtları içerir.

- `dbRelationUpdateCascade` Güncelleştirmeler basamaklandıracaktır.

- `dbRelationDeleteCascade` Silme işlemleri basamaklandıracaktır.

*m_pFieldInfos*<br/>
Bir [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) yapıları dizisine yönelik bir işaretçi. Dizi, ilişkide her alan için bir nesne içerir. `m_nFields`Veri üyesi dizi öğelerinin bir sayısını verir.

*m_nFields*<br/>
`CDaoRelationFieldInfo` `m_pFieldInfos` Veri üyesinde nesne sayısı.

## <a name="remarks"></a>Açıklamalar

Yukarıdaki birincil ve Ikincil başvurular, bilgilerin sınıfında [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) üye işlevi tarafından nasıl döndürüleceğini gösterir `CDaoDatabase` .

İlişki nesneleri bir MFC sınıfıyla temsil edilmez. Bunun yerine, sınıfının bir MFC nesnesini temel alan DAO nesnesi `CDaoDatabase` bir ilişki nesneleri koleksiyonunu tutar: bir dizi `CDaoDatabase` bağımsız öğeye erişmek için üye işlevleri sağlar veya `CDaoRelationInfo` `GetRelationInfo` kapsayan veritabanı nesnesinin üye işlevini çağırarak bir nesne ile tümüne tek seferde erişebilirsiniz.

[CDaoDatabase:: GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) üye işlevi tarafından alınan bilgiler bir `CDaoRelationInfo` yapıda depolanıyor. `CDaoRelationInfo` Ayrıca `Dump` , hata ayıklama yapılarında bir üye işlevi tanımlar. `Dump`Bir nesnenin içeriğini dökmek için kullanabilirsiniz `CDaoRelationInfo` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[CDaoRelationFieldInfo yapısı](../../mfc/reference/cdaorelationfieldinfo-structure.md)
