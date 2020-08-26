---
title: IAtlStringMgr sınıfı
ms.date: 10/18/2018
f1_keywords:
- IAtlStringMgr
- ATLSIMPSTR/ATL::IAtlStringMgr
- ATLSIMPSTR/ATL::Allocate
- ATLSIMPSTR/ATL::Clone
- ATLSIMPSTR/ATL::Free
- ATLSIMPSTR/ATL::GetNilString
- ATLSIMPSTR/ATL::Reallocate
helpviewer_keywords:
- shared classes, IAtlStringMgr
- memory, managing
- IAtlStringMgr class
ms.assetid: 722f0346-a770-4aa7-8f94-177be8dba823
ms.openlocfilehash: a617ba829999e9e5778bd7f0091cfb0d624dce71
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832015"
---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr sınıfı

Bu sınıf, bir bellek yöneticisinin arabirimini temsil eder `CStringT` .

## <a name="syntax"></a>Syntax

```
__interface IAtlStringMgr
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|-|-|
|[Allocate](#allocate)|Yeni bir dize veri yapısı ayırmak için bu yöntemi çağırın.|
|[Kopyalama](#clone)|Başka bir örneğiyle kullanmak üzere yeni bir dize yöneticisine bir işaretçi döndürmek için bu yöntemi çağırın `CSimpleStringT` .|
|[Ücretsiz](#free)|Bir dize veri yapısını serbest bırakmak için bu yöntemi çağırın.|
|[GetNilString](#getnilstring)|`CStringData`Boş dize nesneleri tarafından kullanılan nesneye bir işaretçi döndürür.|
|[Maddelerini](#reallocate)|Bir dize veri yapısını yeniden ayırmak için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, MFC 'nin bağımsız dize sınıfları tarafından kullanılan belleği yönetir; [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)ve [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)gibi.

Bu sınıfı, özel dize sınıfınız için özel bir bellek Yöneticisi uygulamak üzere de kullanabilirsiniz. Daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpstr. h

## <a name="iatlstringmgrallocate"></a><a name="allocate"></a> IAtlStringMgr:: allocate

Yeni bir dize veri yapısı ayırır.

```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```

### <a name="parameters"></a>Parametreler

*nAllocLength*<br/>
Yeni bellek bloğundaki karakterlerin sayısı.

*nCharSize*<br/>
Dize Yöneticisi tarafından kullanılan karakter türünün boyutu (bayt cinsinden).

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğuna bir işaretçi döndürür.

> [!NOTE]
> Özel durum oluşturarak başarısız ayırmayı sinyal vermeyin. Bunun yerine, başarısız bir ayırmaya NULL döndürülerek sinyal verilmelidir.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [IAtlStringMgr:: Free](#free) veya [IAtlStringMgr:: yeniden tahsis](#reallocate) edin.

> [!NOTE]
> Kullanım örnekleri için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="iatlstringmgrclone"></a><a name="clone"></a> IAtlStringMgr:: Clone

Yeni bir dize yöneticisinin başka bir örneğiyle kullanılmak üzere bir işaretçi döndürür `CSimpleStringT` .

```
IAtlStringMgr* Clone() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin bir kopyasını döndürür `IAtlStringMgr` .

### <a name="remarks"></a>Açıklamalar

Yeni bir dize için bir dize Yöneticisi gerektiğinde, yaygın olarak Framework tarafından çağırılır. Çoğu durumda, **`this`** işaretçi döndürülür.

Ancak, bellek Yöneticisi birden çok örneği tarafından kullanılmasını desteklemiyorsa `CSimpleStringT` , paylaşılabilir dize yöneticisine yönelik bir işaretçi döndürülmelidir.

> [!NOTE]
> Kullanım örnekleri için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="iatlstringmgrfree"></a><a name="free"></a> IAtlStringMgr:: ücretsiz

Bir dize veri yapısını serbest bırakır.

```cpp
void Free(CStringData* pData) throw();
```

### <a name="parameters"></a>Parametreler

*pData*<br/>
Boşaltılacak bellek bloğunun işaretçisi.

### <a name="remarks"></a>Açıklamalar

Ayrılmış veya yeniden [tahsis](../../atl/reference/iatlmemmgr-class.md#reallocate) [ederek önceden](#allocate) ayrılan belirtilen bellek bloğunu serbest bırakır.

> [!NOTE]
> Kullanım örnekleri için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="iatlstringmgrgetnilstring"></a><a name="getnilstring"></a> IAtlStringMgr:: GetNilString

Boş bir dize için dize veri yapısına yönelik bir işaretçi döndürür.

```
CStringData* GetNilString() throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CStringData`Boş bir dizeyi temsil etmek için kullanılan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Boş bir dizenin gösterimini döndürmek için bu işlevi çağırın.

> [!NOTE]
> Özel bir dize Yöneticisi uygularken, bu işlev hiçbir zaman başarısız olmamalıdır. Bunun için String Manager sınıfına bir örneği katıştırarak `CNilStringData` ve bu örneğe bir işaretçi döndürerek emin olabilirsiniz.

> [!NOTE]
> Kullanım örnekleri için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="iatlstringmgrreallocate"></a><a name="reallocate"></a> IAtlStringMgr:: yeniden tahsis

Bir dize veri yapısını yeniden konumlandırır.

```
CStringData* Reallocate(
    CStringData* pData,
    int nAllocLength,
    int nCharSize) throw();
```

### <a name="parameters"></a>Parametreler

*pData*<br/>
Bu bellek Yöneticisi tarafından daha önce ayrılan belleğe yönelik işaretçi.

*nAllocLength*<br/>
Yeni bellek bloğundaki karakterlerin sayısı.

*nCharSize*<br/>
Dize Yöneticisi tarafından kullanılan karakter türünün boyutu (bayt cinsinden).

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğunun başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

*PData*tarafından belirtilen mevcut bellek bloğunu yeniden boyutlandırmak için bu işlevi çağırın.

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [IAtlStringMgr:: Free](#free) çağrısı yapın.

> [!NOTE]
> Kullanım örnekleri için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
