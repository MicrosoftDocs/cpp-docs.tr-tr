---
title: CComDynamicUnkArray Sınıfı
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
ms.openlocfilehash: 57383823897a434f649c6c4af78e71fe6ff66a6a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327905"
---
# <a name="ccomdynamicunkarray-class"></a>CComDynamicUnkArray Sınıfı

Bu sınıf bir `IUnknown` dizi işaretçi depolar.

## <a name="syntax"></a>Sözdizimi

```
class CComDynamicUnkArray
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Oluşturucu. Koleksiyon değerlerini NULL'a, koleksiyon boyutunu sıfıra doğru başlar.|
|[CComDynamicUnkArray::~CComDynamicUnkArray](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComDynamicUnkArray::Ekle](#add)|Diziye işaretçi `IUnknown` eklemek için bu yöntemi çağırın.|
|[CComDynamicUnkArray::başla](#begin)|Koleksiyondaki ilk `IUnknown` işaretçiye bir işaretçi döndürür.|
|[CComDynamicUnkArray::açık](#clear)|Diziyi boşaltır.|
|[CComDynamicUnkArray::sonu](#end)|Bir işaretçiyi koleksiyondaki `IUnknown` son işaretçiyi geçmiş bir işaretçiye döndürür.|
|[CComDynamicUnkArray::GetAt](#getat)|Belirtilen dizindeki öğeyi alır.|
|[CComDynamicUnkArray::GetCookie](#getcookie)|Belirli `IUnknown` bir işaretçiyle ilişkili çerezalmak için bu yöntemi arayın.|
|[CComDynamicUnkArray::GetSize](#getsize)|Bir dizinin uzunluğunu döndürür.|
|[CComDynamicUnkArray::GetUnknown](#getunknown)|İşaretçiyi `IUnknown` belirli bir çerezle ilişkilendirmek için bu yöntemi arayın.|
|[CComDynamicUnkArray::Kaldır](#remove)|Bir `IUnknown` işaretçiyi diziden kaldırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CComDynamicUnkArray`her biri bir bağlantı `IUnknown` noktasında bir arabirim olan dinamik olarak ayrılmış bir işaretçi dizisi tutar. `CComDynamicUnkArray`[iConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) şablon sınıfına parametre olarak kullanılabilir.

Başlar `CComDynamicUnkArray` [begin](#begin) ve [biter](#end) (örneğin, bir olay ateşlendiğinde) tüm bağlantı noktaları arasında döngü için kullanılabilir.

Bağlantı noktası yakınlıklarının oluşturulmasını otomatikleştirmekle ilgili ayrıntılar için [Nesneye Bağlantı Noktaları Ekleme'ye](../../atl/adding-connection-points-to-an-object.md) bakın.

> [!NOTE]
> **Not** Sınıf, `CComDynamicUnkArray` Bağlantı Noktaları olan bir denetim oluştururken **Sınıf Ekle** sihirbazı tarafından kullanılır. Bağlantı Noktalarının sayısını el ile belirtmek isterseniz, başvuruyu `CComUnkArray<` *n'den* `>` `CComDynamicUnkArray` *n'ye* değiştirin, n gereken bağlantı noktası sayısıdır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="ccomdynamicunkarrayadd"></a><a name="add"></a>CComDynamicUnkArray::Ekle

Diziye işaretçi `IUnknown` eklemek için bu yöntemi çağırın.

```
DWORD Add(IUnknown* pUnk);
```

### <a name="parameters"></a>Parametreler

*Punk*<br/>
Diziye `IUnknown` eklenecek işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen işaretçiyle ilişkili çerezi döndürür.

## <a name="ccomdynamicunkarraybegin"></a><a name="begin"></a>CComDynamicUnkArray::başla

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

## <a name="ccomdynamicunkarrayclear"></a><a name="clear"></a>CComDynamicUnkArray::açık

Diziyi boşaltır.

```
void clear();
```

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="ccomdynamicunkarray"></a>CComDynamicUnkArray::CComDynamicUnkArray

Oluşturucu.

```
CComDynamicUnkArray();
```

### <a name="remarks"></a>Açıklamalar

Koleksiyon boyutunu sıfıra ayarlar ve değerleri NULL'a başharfe ayarlar. Yıkıcı gerekirse koleksiyonu serbest kılar.

## <a name="ccomdynamicunkarrayccomdynamicunkarray"></a><a name="dtor"></a>CComDynamicUnkArray::~CComDynamicUnkArray

Yıkıcı.

```
~CComDynamicUnkArray();
```

### <a name="remarks"></a>Açıklamalar

Sınıf oluşturucu tarafından ayrılan kaynakları serbest sağlar.

## <a name="ccomdynamicunkarrayend"></a><a name="end"></a>CComDynamicUnkArray::sonu

Bir işaretçiyi koleksiyondaki `IUnknown` son işaretçiyi geçmiş bir işaretçiye döndürür.

```
IUnknown**
    end();
```

### <a name="return-value"></a>Dönüş Değeri

`IUnknown` Arabirim işaretçisine işaretçi.

## <a name="ccomdynamicunkarraygetat"></a><a name="getat"></a>CComDynamicUnkArray::GetAt

Belirtilen dizindeki öğeyi alır.

```
IUnknown* GetAt(int nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Alınacak öğenin dizini.

### <a name="return-value"></a>Dönüş Değeri

[IUnknown](/windows/win32/api/unknwn/nn-unknwn-iunknown) arabirimi için bir işaretçi.

## <a name="ccomdynamicunkarraygetcookie"></a><a name="getcookie"></a>CComDynamicUnkArray::GetCookie

Belirli `IUnknown` bir işaretçiyle ilişkili çerezalmak için bu yöntemi arayın.

```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```

### <a name="parameters"></a>Parametreler

*ppBul*<br/>
İlişkili çerezin gerekli olduğu `IUnknown` işaretçi.

### <a name="return-value"></a>Dönüş Değeri

`IUnknown` Eşleç `IUnknown` bir işaretçi bulunmazsa işaretçiyle ilişkili tanımlama bilgisini veya sıfırı döndürür.

### <a name="remarks"></a>Açıklamalar

Aynı `IUnknown` işaretçibirden fazla örnek varsa, bu işlev ilki için çerez döndürür.

## <a name="ccomdynamicunkarraygetsize"></a><a name="getsize"></a>CComDynamicUnkArray::GetSize

Bir dizinin uzunluğunu döndürür.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizinin uzunluğu.

## <a name="ccomdynamicunkarraygetunknown"></a><a name="getunknown"></a>CComDynamicUnkArray::GetUnknown

İşaretçiyi `IUnknown` belirli bir çerezle ilişkilendirmek için bu yöntemi arayın.

```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
İlişkili `IUnknown` işaretçi için gerekli olan çerez.

### <a name="return-value"></a>Dönüş Değeri

Eşleşen `IUnknown` bir çerez bulunamazsa işaretçiyi veya NULL'u döndürür.

## <a name="ccomdynamicunkarrayremove"></a><a name="remove"></a>CComDynamicUnkArray::Kaldır

Bir `IUnknown` işaretçiyi diziden kaldırmak için bu yöntemi çağırın.

```
BOOL Remove(DWORD dwCookie);
```

### <a name="parameters"></a>Parametreler

*dwCookie*<br/>
Diziden `IUnknown` kaldırılacak işaretçiye başvuran çerez.

### <a name="return-value"></a>Dönüş Değeri

İşaretçi kaldırılırsa TRUE döndürür; aksi takdirde YANLIŞ.

## <a name="see-also"></a>Ayrıca bkz.

[CComUnkArray Sınıfı](../../atl/reference/ccomunkarray-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
