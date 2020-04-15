---
title: CDaoParameterInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: 6d594bbeec34e400eb074c136e3467e78b35c4ee
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368975"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo Yapısı

Yapı, `CDaoParameterInfo` veri erişim nesneleri (DAO) için tanımlanan bir parametre nesnesi hakkında bilgi içerir. DAO 3.6 son sürümüdür ve eski miş olarak kabul edilir.

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
Parametre nesnesini benzersiz olarak adlandırır. Daha fazla bilgi için DAO Yardım'daki "Ad Özelliği" konusuna bakın.

*m_nType*<br/>
Parametre nesnesinin veri türünü gösteren bir değer. Olası değerlerin listesi için [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) yapısının *m_nType* üyesine bakın. Daha fazla bilgi için DAO Yardım'daki "Özellik Yazın" konusuna bakın.

*m_varValue*<br/>
[COleVariant](../../mfc/reference/colevariant-class.md) nesnesinde depolanan parametrenin değeri.

## <a name="remarks"></a>Açıklamalar

Yukarıdaki Birincil ve İkincil'e yapılan atıflar, bilgilerin sınıftaki `CDaoQueryDef` [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) üye işlevi tarafından nasıl döndürüldürün olduğunu gösterir.

MFC, DAO parametre nesnelerini bir sınıfa kapsüllemez. DaO querydef nesneleri, `CDaoQueryDef` MFC nesnelerinin altında yatan parametreleri Parametreler koleksiyonlarında depolar. [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesnesindeki parametre nesnelerine erişmek için, belirli `GetParameterInfo` bir parametre adı için querydef nesnesinin üye işlevini veya Parametreler koleksiyonuna bir dizin çağırın. [CDaoQueryDef::GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) üye işlevini parametreler koleksiyonunda `GetParameterInfo` döngü ye kullanabilirsiniz.

[CDaoQueryDef tarafından alınan bilgiler::GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) üye işlevi bir `CDaoParameterInfo` yapıda saklanır. Parametreleri parametre nesnesi depolanan querydef nesnesi için çağrı yapın. `GetParameterInfo`

> [!NOTE]
> Yalnızca bir parametrenin değerini almak veya ayarlamak istiyorsanız, sınıfın `CDaoRecordset` [GetParamValue ve SetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) üye işlevlerini kullanın. [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue)

`CDaoParameterInfo`ayrıca hata `Dump` ayıklama yapılarında bir üye işlev tanımlar. Bir `Dump` `CDaoParameterInfo` nesnenin içeriğini dökümü için kullanabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao.h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, Stiller, Geri Aramalar ve İleti Haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef Sınıfı](../../mfc/reference/cdaoquerydef-class.md)
