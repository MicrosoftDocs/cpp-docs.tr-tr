---
title: CDaoIndexFieldInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: a8b0ff991b8cc4988192b89d7f70309af9b9112a
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096085"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo Yapısı

Yapı `CDaoIndexFieldInfo` , veri erişim nesneleri (DAO) için tanımlanan bir dizin alanı nesnesi hakkında bilgiler içerir.

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

Bir dizin nesnesi, bir TableDef (veya bir tabloya dayalı bir kayıt kümesi) için hangi alanların dizine alınacağını gösteren bir dizi alana sahip olabilir. Yukarıdaki birincil başvurular, bu bilgilerin, [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)sınıfının `m_pFieldInfos` `GetIndexInfo` üye işlevini çağırarak elde edilen bir [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) nesnesinin üyesinde nasıl döndürüldüğünü gösterir.

Dizin nesneleri ve Dizin alanı nesneleri bir MFC sınıfıyla temsil edilmez. Bunun yerine, [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) veya [CDAORECORDSET](../../mfc/reference/cdaorecordset-class.md) sınıfının MFC nesnelerini temel alan DAO nesneleri, dizinler koleksiyonu olarak adlandırılan dizin nesnelerinin bir koleksiyonunu içerir. Her dizin nesnesi, sırasıyla alan nesnelerinin bir koleksiyonunu içerir. Bu sınıflar, dizin bilgilerinin tek tek öğelerine erişmek için üye işlevleri sağlar veya kapsayan nesnenin `CDaoIndexInfo` `GetIndexInfo` üye işlevini çağırarak bir nesne ile tümüne tek seferde erişebilirsiniz. Daha sonra `m_pFieldInfos` `CDaoIndexFieldInfo`nesnesi, bir nesne dizisine işaret eden bir veri üyesine sahiptir. `CDaoIndexInfo`

Dizinler koleksiyonu ilgilendiğiniz dizin nesnesini depoladığınız içeren tabledef veya Recordset nesnesinin üyeişleviniçağırın.`GetIndexInfo` Ardından, `m_pFieldInfos` [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) nesnesinin üyesine erişin. `m_pFieldInfos` Dizinin uzunluğu içinde `m_nFields`depolanır. `CDaoIndexFieldInfo`Ayrıca, hata `Dump` ayıklama yapılarında bir üye işlevi tanımlar. `Dump` Bir`CDaoIndexFieldInfo` nesnenin içeriğini dökmek için kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef:: GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset:: GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)
