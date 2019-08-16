---
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
ms.openlocfilehash: d55a6d6bfbcc6921fa0633753365f5799388dc27
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497240"
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray sınıfı

Bu sınıf bir `IUnknown` işaretçiler dizisi depolar.

## <a name="syntax"></a>Sözdizimi

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
|[CComDynamicUnkArray:: Add](#add)|Diziye bir `IUnknown` işaretçi eklemek için bu yöntemi çağırın.|
|[CComDynamicUnkArray:: Begin](#begin)|Koleksiyondaki ilk `IUnknown` işaretçiye bir işaretçi döndürür.|
|[CComDynamicUnkArray:: Clear](#clear)|Diziyi boşaltır.|
|[CComDynamicUnkArray:: End](#end)|Koleksiyondaki son `IUnknown` işaretçiyi aşan bir işaretçi döndürür.|
|[CComDynamicUnkArray:: GetAt](#getat)|Belirtilen dizindeki öğeyi alır.|
|[CComDynamicUnkArray:: GetCookie](#getcookie)|Belirli `IUnknown` bir işaretçi ile ilişkili tanımlama bilgisini almak için bu yöntemi çağırın.|
|[CComDynamicUnkArray:: GetSize](#getsize)|Bir dizinin uzunluğunu döndürür.|
|[CComDynamicUnkArray:: GetUnknown](#getunknown)|Belirli bir tanımlama bilgisiyle ilişkili `IUnknown` işaretçiyi almak için bu yöntemi çağırın.|
|[CComDynamicUnkArray:: Remove](#remove)|Diziden bir `IUnknown` işaretçiyi kaldırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CComDynamicUnkArray`bir bağlantı noktasındaki her bir arabirim `IUnknown` olan, dinamik olarak ayrılmış bir işaretçiler dizisi tutar. `CComDynamicUnkArray`[ınewctionpointımpl](../../atl/reference/iconnectionpointimpl-class.md) şablon sınıfına bir parametre olarak kullanılabilir.

Begin ve [](#begin) [End](#end) yöntemleri tüm bağlantı noktalarında (örneğin, bir olay tetiklendiğinde) döngü uygulamak için kullanılabilir. `CComDynamicUnkArray`

Bağlantı noktası proxy 'lerinin oluşturulmasını otomatikleştirme hakkında ayrıntılar için bkz. [bir nesneye bağlantı noktaları ekleme](../../atl/adding-connection-points-to-an-object.md) .

> [!NOTE]
> **Göz önünde** Sınıfı `CComDynamicUnkArray` , bağlantı noktaları olan bir denetim oluştururken **sınıf ekleme** Sihirbazı tarafından kullanılır. Bağlantı noktalarının sayısını el ile belirtmek isterseniz `CComDynamicUnkArray` , başvurusunu *n* `>`olarak `CComUnkArray<` değiştirin; burada *n* , gereken bağlantı noktası sayısıdır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

##  <a name="add"></a>CComDynamicUnkArray:: Add

Diziye bir `IUnknown` işaretçi eklemek için bu yöntemi çağırın.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*pUnk dili*<br/>
Diziye `IUnknown` eklenecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen işaretçiyle ilişkili tanımlama bilgisini döndürür.

##  <a name="begin"></a>CComDynamicUnkArray:: Begin

`IUnknown` Arabirim işaretçileri koleksiyonunun başlangıcına bir işaretçi döndürür.

```
IUnknown**
    begin();
```

### <a name="return-value"></a>Dönüş Değeri

`IUnknown` Arabirim işaretçisine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Koleksiyon, yerel `IUnknown`olarak depolanan arabirimlere işaretçiler içerir. Her `IUnknown` bir arabirimi gerçek arabirim türüne saçın ve sonra bunu çağırabilirsiniz. Önce arabirim için sorgu yapmanız gerekmez.

`IUnknown` Arabirimini kullanmadan önce, null olmadığını denetlemeniz gerekir.

##  <a name="clear"></a>CComDynamicUnkArray:: Clear

Diziyi boşaltır.

```
void clear();
```

##  <a name="ccomdynamicunkarray"></a>CComDynamicUnkArray:: CComDynamicUnkArray

Oluşturucu.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>Açıklamalar

Koleksiyon boyutunu sıfıra ayarlar ve değerleri NULL olarak başlatır. Gerekirse, yıkıcı koleksiyonu serbest bırakır.

##  <a name="dtor"></a>CComDynamicUnkArray:: ~ CComDynamicUnkArray

Yok edicisi.

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>Açıklamalar

Sınıf oluşturucusu tarafından ayrılan kaynakları boşaltır.

##  <a name="end"></a>CComDynamicUnkArray:: End

Koleksiyondaki son `IUnknown` işaretçiyi aşan bir işaretçi döndürür.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Dönüş Değeri

`IUnknown` Arabirim işaretçisine yönelik bir işaretçi.

##  <a name="getat"></a>CComDynamicUnkArray:: GetAt

Belirtilen dizindeki öğeyi alır.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Alınacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabirimine yönelik bir işaretçi.

##  <a name="getcookie"></a>CComDynamicUnkArray:: GetCookie

Belirli `IUnknown` bir işaretçi ile ilişkili tanımlama bilgisini almak için bu yöntemi çağırın.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parametreler

*ppFind*<br/>
İlişkili tanımlama bilgisinin gerekli olduğu işaretçi.`IUnknown`

### <a name="return-value"></a>Dönüş Değeri

`IUnknown` İşaretçiyle ilişkili tanımlama bilgisini, eşleşen `IUnknown` bir işaretçi bulunmazsa sıfır değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Aynı `IUnknown` işaretçinin birden fazla örneği varsa, bu işlev ilki için tanımlama bilgisini döndürür.

##  <a name="getsize"></a>CComDynamicUnkArray:: GetSize

Bir dizinin uzunluğunu döndürür.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin uzunluğu.

##  <a name="getunknown"></a>CComDynamicUnkArray:: GetUnknown

Belirli bir tanımlama bilgisiyle ilişkili `IUnknown` işaretçiyi almak için bu yöntemi çağırın.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
İlişkili `IUnknown` işaretçinin gerekli olduğu tanımlama bilgisi.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen tanımlama bilgisi bulunmazsa, işaretçiyiveyanulldeğerinidöndürür.`IUnknown`

##  <a name="remove"></a>CComDynamicUnkArray:: Remove

Diziden bir `IUnknown` işaretçiyi kaldırmak için bu yöntemi çağırın.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
Diziden kaldırılacak olan `IUnknown` işaretçiye başvuran tanımlama bilgisi.

### <a name="return-value"></a>Dönüş Değeri

İşaretçi kaldırılırsa TRUE döndürür; Aksi halde yanlış.

## <a name="see-also"></a>Ayrıca bkz.

[CComUnkArray Sınıfı](../../atl/reference/ccomunkarray-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
