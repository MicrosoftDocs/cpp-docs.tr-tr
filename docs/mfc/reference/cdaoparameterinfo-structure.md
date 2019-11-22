---
title: CDaoParameterInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 9f96cba8ea43db7e24e834b1de4ffb593b2c6e0d
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303493"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo Yapısı

`CDaoParameterInfo` yapısı, veri erişim nesneleri (DAO) için tanımlanan bir parametre nesnesi hakkında bilgi içerir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

## <a name="syntax"></a>Sözdizimi

```
struct CDaoParameterInfo
{
    CString m_strName;       // Primary
    short m_nType;           // Primary
    ColeVariant m_varValue;  // Secondary
};
```

#### <a name="parameters"></a>Parametreler

*m_strName*<br/>
Parametre nesnesini benzersiz olarak adlandırır. Daha fazla bilgi için, DAO yardımı 'nda "ad özelliği" konusuna bakın.

*m_nType*<br/>
Bir parametre nesnesinin veri türünü gösteren bir değer. Olası değerlerin listesi için bkz. [Cdadofielınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısının *m_nType* üyesi. Daha fazla bilgi için, DAO yardımı 'nda "tür özelliği" konusuna bakın.

*m_varValue*<br/>
Parametrenin değeri [Colonvariant](../../mfc/reference/colevariant-class.md) nesnesinde saklanır.

## <a name="remarks"></a>Açıklamalar

Yukarıdaki birincil ve Ikincil başvurular, bilgilerin `CDaoQueryDef`sınıfında [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) üye işlevi tarafından nasıl döndürüleceğini gösterir.

MFC bir sınıftaki DAO parametre nesnelerini kapsüllemez. MFC `CDaoQueryDef` nesneleri temel alan DAO QueryDef nesneleri parametre koleksiyonlarındaki parametreleri depolar. Bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesnesindeki parametre nesnelerine erişmek için, belirli bir parametre adı için querydef nesnesinin `GetParameterInfo` member Işlevini veya parametreler koleksiyonuna bir dizin çağırın. Parametre koleksiyonu aracılığıyla döngü yapmak için, `GetParameterInfo` ile birlikte [CDaoQueryDef:: GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) üye işlevini kullanabilirsiniz.

[CDaoQueryDef:: GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) üye işlevi tarafından alınan bilgiler `CDaoParameterInfo` bir yapıda depolanıyor. Parametre koleksiyonundaki parametre nesnesinin depolandığı QueryDef nesnesi için `GetParameterInfo` çağırın.

> [!NOTE]
>  Yalnızca bir parametre değerini almak veya ayarlamak istiyorsanız `CDaoRecordset`sınıfının [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) ve [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) üye işlevlerini kullanın.

`CDaoParameterInfo` Ayrıca hata ayıklama yapılarında bir `Dump` member işlevi tanımlar. Bir `CDaoParameterInfo` nesnesinin içeriğini dökmek için `Dump` kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)
