---
description: 'Daha fazla bilgi edinin: CComUnkArray sınıfı'
title: CComUnkArray sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
ms.openlocfilehash: e03022fb751b487debb9f81d9e3d99ce46f1b9e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142148"
---
# <a name="ccomunkarray-class"></a>CComUnkArray sınıfı

Bu sınıf `IUnknown` işaretçileri depolar ve [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) şablon sınıfına bir parametre olarak kullanılmak üzere tasarlanmıştır.

## <a name="syntax"></a>Sözdizimi

```
template<unsigned int nMaxSize>
class CComUnkArray
```

#### <a name="parameters"></a>Parametreler

*nMaxSize*<br/>
`IUnknown`Statik dizide tutulabilecek en fazla işaretçi sayısı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComUnkArray:: CComUnkArray](#ccomunkarray)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComUnkArray:: Add](#add)|Diziye bir işaretçi eklemek için bu yöntemi çağırın `IUnknown` .|
|[CComUnkArray:: Begin](#begin)|Koleksiyondaki ilk işaretçiye bir işaretçi döndürür `IUnknown` .|
|[CComUnkArray:: End](#end)|Koleksiyondaki son işaretçiyi aşan bir işaretçi döndürür `IUnknown` .|
|[CComUnkArray:: GetCookie](#getcookie)|Belirli bir işaretçi ile ilişkili tanımlama bilgisini almak için bu yöntemi çağırın `IUnknown` .|
|[CComUnkArray:: GetUnknown](#getunknown)|`IUnknown`Belirli bir tanımlama bilgisiyle ilişkili işaretçiyi almak için bu yöntemi çağırın.|
|[CComUnkArray:: Remove](#remove)|Diziden bir işaretçiyi kaldırmak için bu yöntemi çağırın `IUnknown` .|

## <a name="remarks"></a>Açıklamalar

`CComUnkArray``IUnknown`bir bağlantı noktasındaki her bir arabirim olan sabit sayıda işaretçiyi tutar. `CComUnkArray`[ınewctionpointımpl](../../atl/reference/iconnectionpointimpl-class.md) şablon sınıfına bir parametre olarak kullanılabilir. `CComUnkArray<1>` , `CComUnkArray` bir bağlantı noktası için en iyi duruma getirilmiş bir şablon özelleştirmesi.

`CComUnkArray` [Begin](#begin) ve [End](#end) yöntemleri tüm bağlantı noktalarında (örneğin, bir olay tetiklendiğinde) döngü uygulamak için kullanılabilir.

Bağlantı noktası proxy 'lerinin oluşturulmasını otomatikleştirme hakkında ayrıntılar için bkz. [bir nesneye bağlantı noktaları ekleme](../../atl/adding-connection-points-to-an-object.md) .

> [!NOTE]
> **Göz önünde** [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) sınıfı, bağlantı noktaları olan bir denetim oluştururken **sınıf ekleme** Sihirbazı tarafından kullanılır. Bağlantı noktalarının sayısını el ile belirtmek isterseniz, başvurusunu `CComDynamicUnkArray` n olarak değiştirin `CComUnkArray<`  `>` ; burada *n* , gereken bağlantı noktası sayısıdır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomunkarrayadd"></a><a name="add"></a> CComUnkArray:: Add

Diziye bir işaretçi eklemek için bu yöntemi çağırın `IUnknown` .

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
Diziye bir işaretçi eklemek için bu yöntemi çağırın `IUnknown` .

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen işaretçiyle ilişkili tanımlama bilgisini veya dizi yeni işaretçiyi içerecek kadar büyük değilse 0 değerini döndürür.

## <a name="ccomunkarraybegin"></a><a name="begin"></a> CComUnkArray:: Begin

Arabirim işaretçileri koleksiyonunun başlangıcına bir işaretçi döndürür `IUnknown` .

```
IUnknown**
    begin();
```

### <a name="return-value"></a>Dönüş Değeri

Arabirim işaretçisine yönelik bir işaretçi `IUnknown` .

### <a name="remarks"></a>Açıklamalar

Koleksiyon, yerel olarak depolanan arabirimlere işaretçiler içerir `IUnknown` . Her bir `IUnknown` arabirimi gerçek arabirim türüne saçın ve sonra bunu çağırabilirsiniz. Önce arabirim için sorgu yapmanız gerekmez.

Arabirimini kullanmadan önce `IUnknown` , null olmadığını denetlemeniz gerekir.

## <a name="ccomunkarrayccomunkarray"></a><a name="ccomunkarray"></a> CComUnkArray:: CComUnkArray

Oluşturucu.

```
CComUnkArray();
```

### <a name="remarks"></a>Açıklamalar

Bir koleksiyonu işaretçileri tutacak şekilde ayarlar `nMaxSize` `IUnknown` ve işaretçileri null olarak başlatır.

## <a name="ccomunkarrayend"></a><a name="end"></a> CComUnkArray:: End

Koleksiyondaki son işaretçiyi aşan bir işaretçi döndürür `IUnknown` .

```
IUnknown**
    end();
```

### <a name="return-value"></a>Dönüş Değeri

Arabirim işaretçisine yönelik bir işaretçi `IUnknown` .

### <a name="remarks"></a>Açıklamalar

`CComUnkArray`Yöntemler `begin` ve, `end` Örneğin bir olay harekete geçirildiğinde tüm bağlantı noktalarında döngü uygulamak için kullanılabilir.

[!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]

## <a name="ccomunkarraygetcookie"></a><a name="getcookie"></a> CComUnkArray:: GetCookie

Belirli bir işaretçi ile ilişkili tanımlama bilgisini almak için bu yöntemi çağırın `IUnknown` .

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parametreler

*ppFind*<br/>
`IUnknown`İlişkili tanımlama bilgisinin gerekli olduğu işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşaretçiyle ilişkili tanımlama bilgisini `IUnknown` , eşleşen bir işaretçi bulunmazsa 0 değerini döndürür `IUnknown` .

### <a name="remarks"></a>Açıklamalar

Aynı işaretçinin birden fazla örneği varsa `IUnknown` , bu işlev ilki için tanımlama bilgisini döndürür.

## <a name="ccomunkarraygetunknown"></a><a name="getunknown"></a> CComUnkArray:: GetUnknown

`IUnknown`Belirli bir tanımlama bilgisiyle ilişkili işaretçiyi almak için bu yöntemi çağırın.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
İlişkili `IUnknown` işaretçinin gerekli olduğu tanımlama bilgisi.

### <a name="return-value"></a>Dönüş Değeri

`IUnknown`Eşleşen tanımlama bilgisi bulunmazsa, işaretçiyi veya null değerini döndürür.

## <a name="ccomunkarrayremove"></a><a name="remove"></a> CComUnkArray:: Remove

Diziden bir işaretçiyi kaldırmak için bu yöntemi çağırın `IUnknown` .

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
Diziden kaldırılacak olan işaretçiye başvuran tanımlama bilgisi `IUnknown` .

### <a name="return-value"></a>Dönüş Değeri

İşaretçi kaldırılırsa TRUE, aksi takdirde FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[CComDynamicUnkArray sınıfı](../../atl/reference/ccomdynamicunkarray-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
