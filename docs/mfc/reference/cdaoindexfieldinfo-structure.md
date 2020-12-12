---
description: 'Şu konuda daha fazla bilgi edinin: CDaoIndexFieldInfo yapısı'
title: CDaoIndexFieldInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: fe2d6bef3ce44e7418474b7f2c004942935968c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250796"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo Yapısı

`CDaoIndexFieldInfo`Yapı, veri erişim nesneleri (DAO) için tanımlanan bir dizin alanı nesnesi hakkında bilgiler içerir.

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

Bir dizin nesnesi, bir TableDef (veya bir tabloya dayalı bir kayıt kümesi) için hangi alanların dizine alınacağını gösteren bir dizi alana sahip olabilir. Yukarıdaki birincil başvurular, bu bilgilerin, `m_pFieldInfos` [](../../mfc/reference/cdaoindexinfo-structure.md) `GetIndexInfo` [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) veya [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)sınıfının üye işlevini çağırarak elde edilen bir CDaoIndexInfo nesnesinin üyesinde nasıl döndürüldüğünü gösterir.

Dizin nesneleri ve Dizin alanı nesneleri bir MFC sınıfıyla temsil edilmez. Bunun yerine, [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) veya [CDAORECORDSET](../../mfc/reference/cdaorecordset-class.md) sınıfının MFC nesnelerini temel alan DAO nesneleri, dizinler koleksiyonu olarak adlandırılan dizin nesnelerinin bir koleksiyonunu içerir. Her dizin nesnesi, sırasıyla alan nesnelerinin bir koleksiyonunu içerir. Bu sınıflar, dizin bilgilerinin tek tek öğelerine erişmek için üye işlevleri sağlar veya `CDaoIndexInfo` `GetIndexInfo` kapsayan nesnenin üye işlevini çağırarak bir nesne ile tümüne tek seferde erişebilirsiniz. `CDaoIndexInfo`Daha sonra nesnesi, bir nesne dizisine işaret eden bir veri üyesine sahiptir `m_pFieldInfos` `CDaoIndexFieldInfo` .

`GetIndexInfo`Dizinler koleksiyonu ilgilendiğiniz dizin nesnesini depoladığınız içeren tabledef veya Recordset nesnesinin üye işlevini çağırın. Ardından, `m_pFieldInfos` [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) nesnesinin üyesine erişin. `m_pFieldInfos`Dizinin uzunluğu içinde depolanır `m_nFields` . `CDaoIndexFieldInfo` Ayrıca `Dump` , hata ayıklama yapılarında bir üye işlevi tanımlar. `Dump`Bir nesnenin içeriğini dökmek için kullanabilirsiniz `CDaoIndexFieldInfo` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef:: GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset:: GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)
