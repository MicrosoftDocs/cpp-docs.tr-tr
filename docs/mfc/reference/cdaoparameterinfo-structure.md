---
description: 'Daha fazla bilgi edinin: CDaoParameterInfo yapısı'
title: CDaoParameterInfo Yapısı
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: b4cd1916bb30c3b646e9b0892e2bdcdf5ade30b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250730"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo Yapısı

`CDaoParameterInfo`Yapı, veri erişim nesneleri (DAO) için tanımlanan bir parametre nesnesi hakkında bilgiler içerir. DAO 3,6 son sürümdür ve artık kullanılmıyor olarak kabul edilir.

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

Yukarıdaki birincil ve Ikincil başvurular, bilgilerin sınıfında [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) üye işlevi tarafından nasıl döndürüleceğini gösterir `CDaoQueryDef` .

MFC bir sınıftaki DAO parametre nesnelerini kapsüllemez. MFC nesnelerini temel alan DAO QueryDef nesneleri parametre `CDaoQueryDef` koleksiyonlarında parametreleri depolar. Bir [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) nesnesindeki parametre nesnelerine erişmek için, `GetParameterInfo` belirli bir parametre adı için querydef nesnesinin üye işlevini veya parametreler koleksiyonuna bir dizin çağırın. , Parameters koleksiyonunu döngüye almak için, ' yle birlikte [CDaoQueryDef:: GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) üye işlevini kullanabilirsiniz `GetParameterInfo` .

[CDaoQueryDef:: GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) üye işlevi tarafından alınan bilgiler bir `CDaoParameterInfo` yapıda depolanıyor. Parametre `GetParameterInfo` koleksiyonundaki parametre nesnesinin depolandığı QueryDef nesnesi için çağrı.

> [!NOTE]
> Yalnızca bir parametre değerini almak veya ayarlamak istiyorsanız, sınıfının [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) ve [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) üye işlevlerini kullanın `CDaoRecordset` .

`CDaoParameterInfo` Ayrıca `Dump` , hata ayıklama yapılarında bir üye işlevi tanımlar. `Dump`Bir nesnenin içeriğini dökmek için kullanabilirsiniz `CDaoParameterInfo` .

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxdao. h

## <a name="see-also"></a>Ayrıca bkz.

[Yapılar, stiller, geri çağrılar ve Ileti haritaları](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef sınıfı](../../mfc/reference/cdaoquerydef-class.md)
