---
title: CComUnkArray Sınıfı
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
ms.openlocfilehash: c1d2f0296394d3979ef4f152e3f902c89adf5b45
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327299"
---
# <a name="ccomunkarray-class"></a>CComUnkArray Sınıfı

Bu sınıf `IUnknown` işaretçileri depolar ve [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) şablon sınıfına parametre olarak kullanılmak üzere tasarlanmıştır.

## <a name="syntax"></a>Sözdizimi

```
template<unsigned int nMaxSize>
class CComUnkArray
```

#### <a name="parameters"></a>Parametreler

*nMaxSize*<br/>
Statik dizide `IUnknown` tutulabilecek maksimum işaretçi sayısı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComUnkArray::CComUnkArray](#ccomunkarray)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComUnkArray::Ekle](#add)|Diziye işaretçi `IUnknown` eklemek için bu yöntemi çağırın.|
|[CComUnkArray::başla](#begin)|Koleksiyondaki ilk `IUnknown` işaretçiye bir işaretçi döndürür.|
|[CComUnkArray::sonu](#end)|Bir işaretçiyi koleksiyondaki `IUnknown` son işaretçiyi geçmiş bir işaretçiye döndürür.|
|[CComUnkArray::GetCookie](#getcookie)|Belirli `IUnknown` bir işaretçiyle ilişkili çerezalmak için bu yöntemi arayın.|
|[CComUnkArray::GetUnknown](#getunknown)|İşaretçiyi `IUnknown` belirli bir çerezle ilişkilendirmek için bu yöntemi arayın.|
|[CComUnkArray::Kaldır](#remove)|Bir `IUnknown` işaretçiyi diziden kaldırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CComUnkArray`her biri bir `IUnknown` bağlantı noktasında bir arabirim olan sabit sayıda işaretçi tutar. `CComUnkArray`[iConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) şablon sınıfına parametre olarak kullanılabilir. `CComUnkArray<1>`bir bağlantı noktası `CComUnkArray` için en iyi duruma getirilmiş bir şablon uzmanlık alanıdır.

Başlar `CComUnkArray` [begin](#begin) ve [biter](#end) (örneğin, bir olay ateşlendiğinde) tüm bağlantı noktaları arasında döngü için kullanılabilir.

Bağlantı noktası yakınlıklarının oluşturulmasını otomatikleştirmekle ilgili ayrıntılar için [Nesneye Bağlantı Noktaları Ekleme'ye](../../atl/adding-connection-points-to-an-object.md) bakın.

> [!NOTE]
> **Not** [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) sınıfı, Bağlantı Noktaları olan bir denetim oluştururken **Sınıf Ekle** sihirbazı tarafından kullanılır. Bağlantı Noktalarının sayısını el ile belirtmek isterseniz, başvuruyu `CComUnkArray<` *n'den* `>` `CComDynamicUnkArray` *n'ye* değiştirin, n gereken bağlantı noktası sayısıdır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomunkarrayadd"></a><a name="add"></a>CComUnkArray::Ekle

Diziye işaretçi `IUnknown` eklemek için bu yöntemi çağırın.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
Diziye işaretçi `IUnknown` eklemek için bu yöntemi çağırın.

### <a name="return-value"></a>Dönüş Değeri

Dizi yeni işaretçiyi içerecek kadar büyük değilse, yeni eklenen işaretçiyle ilişkili tanımlama bilgisini veya 0'ı döndürür.

## <a name="ccomunkarraybegin"></a><a name="begin"></a>CComUnkArray::başla

`IUnknown` Arabirim işaretçileri koleksiyonunun başına bir işaretçi döndürür.

```
IUnknown**
    begin();
```

### <a name="return-value"></a>Dönüş Değeri

`IUnknown` Arabirim işaretçisine işaretçi.

### <a name="remarks"></a>Açıklamalar

Koleksiyon, yerel olarak `IUnknown`depolanan arabirimlere işaretçiler içerir. Her `IUnknown` arabirimi gerçek arayüz türüne atarsınız ve sonra onu ararsınız. Önce arabirim için sorgulama yapmanız gerekmez.

Arabirimi `IUnknown` kullanmadan önce NULL olup olmadığını kontrol etmelisiniz.

## <a name="ccomunkarrayccomunkarray"></a><a name="ccomunkarray"></a>CComUnkArray::CComUnkArray

Oluşturucu.

```
CComUnkArray();
```

### <a name="remarks"></a>Açıklamalar

Topluluğu işaretçileri `nMaxSize` `IUnknown` tutacak şekilde ayarlar ve işaretçileri NULL'a başharfe ayarlar.

## <a name="ccomunkarrayend"></a><a name="end"></a>CComUnkArray::sonu

Bir işaretçiyi koleksiyondaki `IUnknown` son işaretçiyi geçmiş bir işaretçiye döndürür.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Dönüş Değeri

`IUnknown` Arabirim işaretçisine işaretçi.

### <a name="remarks"></a>Açıklamalar

Yöntemler `CComUnkArray` `begin` ve `end` bir olay ateşlendiğinde, örneğin, tüm bağlantı noktaları arasında döngü için kullanılabilir.

[!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]

## <a name="ccomunkarraygetcookie"></a><a name="getcookie"></a>CComUnkArray::GetCookie

Belirli `IUnknown` bir işaretçiyle ilişkili çerezalmak için bu yöntemi arayın.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parametreler

*ppBul*<br/>
İlişkili çerezin gerekli olduğu `IUnknown` işaretçi.

### <a name="return-value"></a>Dönüş Değeri

`IUnknown` Eşleç bulunmazsa işaretçiyle ilişkili `IUnknown` tanımlama bilgisi veya 0 döndürür.

### <a name="remarks"></a>Açıklamalar

Aynı `IUnknown` işaretçibirden fazla örnek varsa, bu işlev ilki için çerez döndürür.

## <a name="ccomunkarraygetunknown"></a><a name="getunknown"></a>CComUnkArray::GetUnknown

İşaretçiyi `IUnknown` belirli bir çerezle ilişkilendirmek için bu yöntemi arayın.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
İlişkili `IUnknown` işaretçi için gerekli olan çerez.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen `IUnknown` bir çerez bulunamazsa işaretçiyi veya NULL'u döndürür.

## <a name="ccomunkarrayremove"></a><a name="remove"></a>CComUnkArray::Kaldır

Bir `IUnknown` işaretçiyi diziden kaldırmak için bu yöntemi çağırın.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
Diziden `IUnknown` kaldırılacak işaretçiye başvuran çerez.

### <a name="return-value"></a>Dönüş Değeri

İşaretçi kaldırılırsa TRUE döndürür, aksi takdirde FALSE.

## <a name="see-also"></a>Ayrıca bkz.

[CComDynamicUnkArray Sınıfı](../../atl/reference/ccomdynamicunkarray-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
