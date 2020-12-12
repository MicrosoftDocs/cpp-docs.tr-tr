---
description: 'Şu konuda daha fazla bilgi edinin: CDaoRelationFieldInfo yapısı'
title: CDaoRelationFieldInfo Yapısı
ms.date: 11/04/2016
f1_keywords:
- CDaoRelationFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
ms.openlocfilehash: eb470752a9e9da5f610dd59976f2716fa1c4e18a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248170"
---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo Yapısı

`CDaoRelationFieldInfo`Yapı, veri erişim nesneleri (DAO) için tanımlanan ilişkide bir alanla ilgili bilgiler içerir.

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
İlişkinin birincil tablosundaki alanının adı.

*m_strForeignName*<br/>
İlişkinin yabancı tablosundaki alanının adı.

## <a name="remarks"></a>Açıklamalar

Bir DAO Relation nesnesi, birincil tablodaki alanları ve ilişkiyi tanımlayan yabancı tablodaki alanları belirtir. Yukarıdaki yapı tanımında `m_pFieldInfos` birincinin başvuruları, sınıfının [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) üye işlevini çağırarak elde edilen bir [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) nesnesinin üyesinde nasıl döndürüldüğünü gösterir `CDaoDatabase` .

İlişki nesneleri ve ilişki alanı nesneleri, bir MFC sınıfıyla temsil edilmez. Bunun yerine, [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) sınıfının MFC nesnelerini temel alan DAO nesneleri ilişkiler koleksiyonu olarak adlandırılan bir ilişki nesneleri koleksiyonu içerir. Her ilişki nesnesi, sırasıyla bir ilişki alanı nesneleri koleksiyonunu içerir. Her ilişki alanı nesnesi, birincil tablodaki bir alanı yabancı tablodaki bir alanla ilişkilendirir. Birlikte yapılan ilişki alanı nesneleri, her tablodaki bir alan grubunu tanımlar ve bu da ilişkiyi birlikte tanımlar. `CDaoDatabase` üye işlevini çağırarak bir nesne ile ilişki nesnelerine erişmenize izin verir `CDaoRelationInfo` `GetRelationInfo` . `CDaoRelationInfo`Daha sonra nesnesi, bir nesne dizisine işaret eden bir veri üyesine sahiptir `m_pFieldInfos` `CDaoRelationFieldInfo` .

İlişki koleksiyonu ilgilendiğiniz ilişki nesnesini depoladığınız kapsayan nesnenin [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) üye işlevini çağırın `CDaoDatabase` . Ardından, `m_pFieldInfos` [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) nesnesinin üyesine erişin. `CDaoRelationFieldInfo` Ayrıca `Dump` , hata ayıklama yapılarında bir üye işlevi tanımlar. `Dump`Bir nesnenin içeriğini dökmek için kullanabilirsiniz `CDaoRelationFieldInfo` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoRelationInfo yapısı](../../mfc/reference/cdaorelationinfo-structure.md)
