---
title: CDaoRelationFieldInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoRelationFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
ms.openlocfilehash: 9a00d1cbaf58729863a85d4e9053c9241e9566ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599413"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoRelationInfo Yapısı](../../mfc/reference/cdaorelationinfo-structure.md)
