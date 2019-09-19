---
title: CDaoParameterInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 4f0ee7ebe1d5d4eff50194c2d5c5cccf8f373c61
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2019
ms.locfileid: "71096078"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo Yapısı

Yapı `CDaoParameterInfo` , veri erişim nesneleri (DAO) için tanımlanan bir parametre nesnesi hakkında bilgiler içerir.
DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.


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
Bir parametre nesnesinin veri türünü gösteren bir değer. Olası değerlerin bir listesi için bkz. *m_nType* üyesi [Cdadofielınfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısı. Daha fazla bilgi için, DAO yardımı 'nda "tür özelliği" konusuna bakın.

*m_varValue*<br/>
Parametrenin değeri [Colonvariant](../../mfc/reference/colevariant-class.md) nesnesinde saklanır.

## <a name="remarks"></a>Açıklamalar

Yukarıdaki birincil ve Ikincil başvurular, bilgilerin sınıfında `CDaoQueryDef` [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) üye işlevi tarafından nasıl döndürüleceğini gösterir.

MFC bir sınıftaki DAO parametre nesnelerini kapsüllemez. MFC `CDaoQueryDef` nesnelerini temel alan DAO QueryDef nesneleri parametre koleksiyonlarında parametreleri depolar. Bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesnesindeki parametre nesnelerine erişmek için, belirli bir parametre adı için querydef nesnesinin `GetParameterInfo` üye işlevini veya parametreler koleksiyonuna bir dizin çağırın. , Parameters koleksiyonunu döngüye almak için, ' yle `GetParameterInfo` birlikte [CDaoQueryDef:: GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) üye işlevini kullanabilirsiniz.

[CDaoQueryDef:: GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) üye işlevi tarafından alınan bilgiler bir `CDaoParameterInfo` yapıda depolanıyor. Parametre `GetParameterInfo` koleksiyonundaki parametre nesnesinin depolandığı QueryDef nesnesi için çağrı.

> [!NOTE]
>  Yalnızca bir parametre değerini almak veya ayarlamak istiyorsanız, sınıfının `CDaoRecordset` [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) ve [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) üye işlevlerini kullanın.

`CDaoParameterInfo`Ayrıca, hata `Dump` ayıklama yapılarında bir üye işlevi tanımlar. `Dump` Bir`CDaoParameterInfo` nesnenin içeriğini dökmek için kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Çağrılar ve İleti Eşlemeleri](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)
