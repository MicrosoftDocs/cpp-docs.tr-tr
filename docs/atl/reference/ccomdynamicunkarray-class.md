---
description: 'Daha fazla bilgi edinin: CComDynamicUnkArray sınıfı'
title: CComDynamicUnkArray sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
ms.openlocfilehash: fe817b097bbb75c7d09bffdb6883e5ac4a76f966
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152093"
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray sınıfı

Bu sınıf bir işaretçiler dizisi depolar `IUnknown` .

## <a name="syntax"></a>Syntax

```
class CComDynamicUnkArray
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComDynamicUnkArray:: CComDynamicUnkArray](#ccomdynamicunkarray)|Oluşturucu. Koleksiyon değerlerini NULL ve koleksiyon boyutunu sıfıra olarak başlatır.|
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComDynamicUnkArray:: Add](#add)|Diziye bir işaretçi eklemek için bu yöntemi çağırın `IUnknown` .|
|[CComDynamicUnkArray:: Begin](#begin)|Koleksiyondaki ilk işaretçiye bir işaretçi döndürür `IUnknown` .|
|[CComDynamicUnkArray:: Clear](#clear)|Diziyi boşaltır.|
|[CComDynamicUnkArray:: End](#end)|Koleksiyondaki son işaretçiyi aşan bir işaretçi döndürür `IUnknown` .|
|[CComDynamicUnkArray:: GetAt](#getat)|Belirtilen dizindeki öğeyi alır.|
|[CComDynamicUnkArray:: GetCookie](#getcookie)|Belirli bir işaretçi ile ilişkili tanımlama bilgisini almak için bu yöntemi çağırın `IUnknown` .|
|[CComDynamicUnkArray:: GetSize](#getsize)|Bir dizinin uzunluğunu döndürür.|
|[CComDynamicUnkArray:: GetUnknown](#getunknown)|`IUnknown`Belirli bir tanımlama bilgisiyle ilişkili işaretçiyi almak için bu yöntemi çağırın.|
|[CComDynamicUnkArray:: Remove](#remove)|Diziden bir işaretçiyi kaldırmak için bu yöntemi çağırın `IUnknown` .|

## <a name="remarks"></a>Açıklamalar

`CComDynamicUnkArray``IUnknown`bir bağlantı noktasındaki her bir arabirim olan, dinamik olarak ayrılmış bir işaretçiler dizisi tutar. `CComDynamicUnkArray`[ınewctionpointımpl](../../atl/reference/iconnectionpointimpl-class.md) şablon sınıfına bir parametre olarak kullanılabilir.

`CComDynamicUnkArray` [Begin](#begin) ve [End](#end) yöntemleri tüm bağlantı noktalarında (örneğin, bir olay tetiklendiğinde) döngü uygulamak için kullanılabilir.

Bağlantı noktası proxy 'lerinin oluşturulmasını otomatikleştirme hakkında ayrıntılar için bkz. [bir nesneye bağlantı noktaları ekleme](../../atl/adding-connection-points-to-an-object.md) .

> [!NOTE]
> **Göz önünde** Sınıfı, `CComDynamicUnkArray` bağlantı noktaları olan bir denetim oluştururken **sınıf ekleme** Sihirbazı tarafından kullanılır. Bağlantı noktalarının sayısını el ile belirtmek isterseniz, başvurusunu `CComDynamicUnkArray` n olarak değiştirin `CComUnkArray<`  `>` ; burada *n* , gereken bağlantı noktası sayısıdır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="ccomdynamicunkarrayadd"></a><a name="add"></a> CComDynamicUnkArray:: Add

Diziye bir işaretçi eklemek için bu yöntemi çağırın `IUnknown` .

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
`IUnknown`Diziye eklenecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen işaretçiyle ilişkili tanımlama bilgisini döndürür.

## <a name="ccomdynamicunkarraybegin"></a><a name="begin"></a> CComDynamicUnkArray:: Begin

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

## <a name="ccomdynamicunkarrayclear"></a><a name="clear"></a> CComDynamicUnkArray:: Clear

Diziyi boşaltır.

```cpp
void clear();
```

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="ccomdynamicunkarray"></a> CComDynamicUnkArray:: CComDynamicUnkArray

Oluşturucu.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>Açıklamalar

Koleksiyon boyutunu sıfıra ayarlar ve değerleri NULL olarak başlatır. Gerekirse, yıkıcı koleksiyonu serbest bırakır.

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="dtor"></a> CComDynamicUnkArray:: ~ CComDynamicUnkArray

Yok edicisi.

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>Açıklamalar

Sınıf oluşturucusu tarafından ayrılan kaynakları boşaltır.

## <a name="ccomdynamicunkarrayend"></a><a name="end"></a> CComDynamicUnkArray:: End

Koleksiyondaki son işaretçiyi aşan bir işaretçi döndürür `IUnknown` .

```
IUnknown**
    end();
```

### <a name="return-value"></a>Dönüş Değeri

Arabirim işaretçisine yönelik bir işaretçi `IUnknown` .

## <a name="ccomdynamicunkarraygetat"></a><a name="getat"></a> CComDynamicUnkArray:: GetAt

Belirtilen dizindeki öğeyi alır.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Alınacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabirimine yönelik bir işaretçi.

## <a name="ccomdynamicunkarraygetcookie"></a><a name="getcookie"></a> CComDynamicUnkArray:: GetCookie

Belirli bir işaretçi ile ilişkili tanımlama bilgisini almak için bu yöntemi çağırın `IUnknown` .

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parametreler

*ppFind*<br/>
`IUnknown`İlişkili tanımlama bilgisinin gerekli olduğu işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İşaretçiyle ilişkili tanımlama bilgisini `IUnknown` , eşleşen bir işaretçi bulunmazsa sıfır değerini döndürür `IUnknown` .

### <a name="remarks"></a>Açıklamalar

Aynı işaretçinin birden fazla örneği varsa `IUnknown` , bu işlev ilki için tanımlama bilgisini döndürür.

## <a name="ccomdynamicunkarraygetsize"></a><a name="getsize"></a> CComDynamicUnkArray:: GetSize

Bir dizinin uzunluğunu döndürür.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin uzunluğu.

## <a name="ccomdynamicunkarraygetunknown"></a><a name="getunknown"></a> CComDynamicUnkArray:: GetUnknown

`IUnknown`Belirli bir tanımlama bilgisiyle ilişkili işaretçiyi almak için bu yöntemi çağırın.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
İlişkili `IUnknown` işaretçinin gerekli olduğu tanımlama bilgisi.

### <a name="return-value"></a>Dönüş Değeri

`IUnknown`Eşleşen tanımlama bilgisi bulunmazsa, işaretçiyi veya null değerini döndürür.

## <a name="ccomdynamicunkarrayremove"></a><a name="remove"></a> CComDynamicUnkArray:: Remove

Diziden bir işaretçiyi kaldırmak için bu yöntemi çağırın `IUnknown` .

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
Diziden kaldırılacak olan işaretçiye başvuran tanımlama bilgisi `IUnknown` .

### <a name="return-value"></a>Dönüş Değeri

İşaretçi kaldırılırsa TRUE döndürür; Aksi halde yanlış.

## <a name="see-also"></a>Ayrıca bkz.

[CComUnkArray sınıfı](../../atl/reference/ccomunkarray-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
