---
title: CDaoIndexFieldInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: d03a6f6eadd4cf6ccb5279edf18675605d0b1485
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57304281"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo Yapısı

`CDaoIndexFieldInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanmış bir dizin alan nesne hakkında bilgiler içerir.

## <a name="syntax"></a>Sözdizimi

```
struct CDaoIndexFieldInfo
{
    CString m_strName;          // Primary
    BOOL m_bDescending;         // Primary
};
```

#### <a name="parameters"></a>Parametreler

*m_strName*<br/>
Benzersiz dizin alanı nesnesini adlandırır. Ayrıntılar için "Name özelliği" DAO Yardım konusuna bakın.

*m_bDescending*<br/>
Dizin nesnesi tarafından tanımlanan sıralamaya dizini belirtir. Azalan TRUE.

## <a name="remarks"></a>Açıklamalar

Dizin nesnesi, alanlarının üzerinde değer özelliği (veya bir tabloyu temel alan bir kayıt kümesi) dizine hangi alanları gösteren bir sayı olabilir. Bilgileri nasıl döndürülür birincil yukarıdaki başvuruları göstermek `m_pFieldInfos` üyesi bir [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) çağırılarak nesne `GetIndexInfo` sınıfının üye işlevinde [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).

Dizin nesneleri ve dizin alanı nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, DAO temel alınan MFC sınıfın nesneleri [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) dizinler koleksiyonu adlı dizin nesnelerinin bir koleksiyonu içerir. Her dizin nesnesi, alan nesnelerinin bir koleksiyonunu içerir. Bu sınıfların tek tek öğelerine dizin bilgilerinin erişmek için üye işlevleri, veya bunları tamamını tek seferde erişim bir `CDaoIndexInfo` çağırarak `GetIndexInfo` kapsayan nesnenin üye işlevi. `CDaoIndexInfo` Nesnesi daha sonra veri üyesi vardır `m_pFieldInfos`, işaret eden bir dizisi olarak `CDaoIndexFieldInfo` nesneleri.

Çağrı `GetIndexInfo` üye işlevi dizinleri koleksiyondur kapsayan nesnenin tabledef ya da kayıt depolanan ilgilendiğiniz dizin nesnesi. Ardından erişim `m_pFieldInfos` üyesi [Cdaoındexınfo](../../mfc/reference/cdaoindexinfo-structure.md) nesne. Uzunluğunu `m_pFieldInfos` dizi depolanan `m_nFields`. `CDaoIndexFieldInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoIndexFieldInfo` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)
