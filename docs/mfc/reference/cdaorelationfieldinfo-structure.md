---
title: CDaoRelationFieldInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoRelationFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
ms.openlocfilehash: 85dd853a9aae41a87bbe7ef5c69e22846678cf8a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57298431"
---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo Yapısı

`CDaoRelationFieldInfo` Yapısı için veri erişim nesneleri (DAO) tanımlanmış bir ilişkisi alanında hakkında bilgiler içerir.

## <a name="syntax"></a>Sözdizimi

```
struct CDaoRelationFieldInfo
{
    CString m_strName;           // Primary
    CString m_strForeignName;    // Primary
};
```

#### <a name="parameters"></a>Parametreler

*m_strName*<br/>
Birincil Tablo ilişkisinin alanın adı.

*m_strForeignName*<br/>
İlişkinin yabancı tablosundaki alan adı.

## <a name="remarks"></a>Açıklamalar

DAO ilişki nesnesi alanları birincil tabloya ve bu ilişkiyi tanımlayan bir dış tablo alanları belirtir. Bilgileri nasıl döndürülür birincil yapı tanımında yukarıdaki başvuruları göstermek `m_pFieldInfos` üyesi bir [Cdaorelationınfo](../../mfc/reference/cdaorelationinfo-structure.md) çağırılarak nesne [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)sınıfının üye işlevinde `CDaoDatabase`.

İlişki nesneleri ve ilişki alan nesneleri bir MFC sınıfı tarafından temsil edilmez. Bunun yerine, DAO temel alınan MFC sınıfın nesneleri [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) ilişkiler koleksiyonu adlı ilişki nesnelerinin bir koleksiyonu içerir. Her ilişki nesnesi sırayla ilişkisi alan nesnelerinin bir koleksiyonunu içerir. Her ilişki alan nesne birincil tablo bir alan yabancı tablosundaki bir alanla ilişkilendirir. Birlikte ele alındığında, ilişki alan nesneleri bir grup alanlarının her tabloda birlikte bu ilişkiyi tanımlayan tanımlayın. `CDaoDatabase` İlişki nesneleriyle erişim sağlar. bir `CDaoRelationInfo` çağırarak `GetRelationInfo` üye işlevi. `CDaoRelationInfo` Nesnesi daha sonra veri üyesi vardır `m_pFieldInfos`, işaret eden bir dizisi olarak `CDaoRelationFieldInfo` nesneleri.

Çağrı [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) içeren üye işlevi `CDaoDatabase` nesne ilgilendiğiniz ilişki nesnesi koleksiyonu ilişkileri depolanır ayarlanmış. Ardından erişim `m_pFieldInfos` üyesi [Cdaorelationınfo](../../mfc/reference/cdaorelationinfo-structure.md) nesne. `CDaoRelationFieldInfo` Ayrıca tanımlayan bir `Dump` hata ayıklama üye işlevinde oluşturur. Kullanabileceğiniz `Dump` içeriğini dökümünü almak için bir `CDaoRelationFieldInfo` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoRelationInfo Yapısı](../../mfc/reference/cdaorelationinfo-structure.md)
