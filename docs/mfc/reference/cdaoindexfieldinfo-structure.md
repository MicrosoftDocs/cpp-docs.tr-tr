---
title: CDaoIndexFieldInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: 10c786ef4fed9ecb3bbbb93526cd68a11e18d58c
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303627"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo Yapısı

`CDaoIndexFieldInfo` yapısı, veri erişim nesneleri (DAO) için tanımlanan bir dizin alanı nesnesi hakkında bilgi içerir.

DAO, Office 2013 aracılığıyla desteklenir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

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
Dizin alanı nesnesini benzersiz olarak adlandırır. Ayrıntılar için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

*m_bDescending*<br/>
Dizin nesnesi tarafından tanımlanan dizin sıralamasını gösterir. Sıra azalan ise doğru.

## <a name="remarks"></a>Açıklamalar

Bir dizin nesnesi, bir TableDef (veya bir tabloya dayalı bir kayıt kümesi) için hangi alanların dizine alınacağını gösteren bir dizi alana sahip olabilir. Yukarıdaki birincil başvurular, bilgilerin [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) veya [cdaorecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)sınıfının `GetIndexInfo` member işlevini çağırarak elde edilen bir [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) nesnesinin `m_pFieldInfos` üyesinde nasıl döndürüldüğünü gösterir.

Dizin nesneleri ve Dizin alanı nesneleri bir MFC sınıfıyla temsil edilmez. Bunun yerine, [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) veya [CDAORECORDSET](../../mfc/reference/cdaorecordset-class.md) sınıfının MFC nesnelerini temel alan DAO nesneleri, dizinler koleksiyonu olarak adlandırılan dizin nesnelerinin bir koleksiyonunu içerir. Her dizin nesnesi, sırasıyla alan nesnelerinin bir koleksiyonunu içerir. Bu sınıflar, dizin bilgilerinin tek tek öğelerine erişmek için üye işlevleri sağlar veya kapsayan nesnenin `GetIndexInfo` üye işlevini çağırarak bir `CDaoIndexInfo` nesnesine bir kez erişebilirsiniz. `CDaoIndexInfo` nesnesi, `m_pFieldInfos`bir `CDaoIndexFieldInfo` nesne dizisine işaret eden bir veri üyesine sahiptir.

Dizinler koleksiyonu ilgilendiğiniz dizin nesnesini depoındaki içeren tabledef veya Recordset nesnesinin `GetIndexInfo` üye işlevini çağırın. Ardından, [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) nesnesinin `m_pFieldInfos` üyesine erişin. `m_pFieldInfos` dizisinin uzunluğu `m_nFields`depolanır. `CDaoIndexFieldInfo` Ayrıca hata ayıklama yapılarında bir `Dump` member işlevi tanımlar. Bir `CDaoIndexFieldInfo` nesnesinin içeriğini dökmek için `Dump` kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef:: GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset:: GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)
