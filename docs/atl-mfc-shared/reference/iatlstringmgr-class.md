---
title: IAtlStringMgr Sınıfı
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
ms.openlocfilehash: 49ef7850edb18cd51092f282644973376abd4c7c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317489"
---
# <a name="iatlstringmgr-class"></a>IAtlStringMgr Sınıfı

Bu sınıf, bir `CStringT` bellek yöneticisiiçin arabirimi temsil eder.

## <a name="syntax"></a>Sözdizimi

```
__interface IAtlStringMgr
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Ayırmak](#allocate)|Yeni bir dize veri yapısı ayırmak için bu yöntemi arayın.|
|[Kopyalama](#clone)|Başka bir örnekle kullanılmak üzere yeni bir dize `CSimpleStringT`yöneticisine bir işaretçi döndürmek için bu yöntemi çağırın.|
|[Ücretsiz](#free)|Dize veri yapısını serbest yapmak için bu yöntemi arayın.|
|[GetNilString](#getnilstring)|Bir işaretçiyi `CStringData` boş dize nesneleri tarafından kullanılan nesneye döndürür.|
|[Yeniden tahsis](#reallocate)|Dize veri yapısını yeniden tahsis etmek için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

Bu arabirim, MFC'den bağımsız dize sınıfları tarafından kullanılan belleği yönetir; [CSimpleStringT,](../../atl-mfc-shared/reference/csimplestringt-class.md) [CStringT](../../atl-mfc-shared/reference/cstringt-class.md)ve [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md)gibi.

Özel dize sınıfınız için özel bir bellek yöneticisi uygulamak için bu sınıfı da kullanabilirsiniz. Daha fazla bilgi için [Bellek Yönetimi ve CStringT'e](../../atl-mfc-shared/memory-management-with-cstringt.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpstr.h

## <a name="iatlstringmgrallocate"></a><a name="allocate"></a>IAtlStringMgr::Ayırma

Yeni bir dize veri yapısı ayırır.

```
CStringData* Allocate(int nAllocLength,int nCharSize) throw();
```

### <a name="parameters"></a>Parametreler

*nAllocLength*<br/>
Yeni bellek bloğundaki karakter sayısı.

*nCharSize*<br/>
Dize yöneticisi tarafından kullanılan karakter türünün boyutu (baytlarda).

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçiyi yeni ayrılan bellek bloğuna döndürür.

> [!NOTE]
> Bir özel durum oluşturarak başarısız bir ayırma sinyali yapmayın. Bunun yerine, null döndürerek başarısız bir ayırma sinyali verilmelidir.

### <a name="remarks"></a>Açıklamalar

Çağrı [IAtlStringMgr::Ücretsiz](#free) veya [IAtlStringMgr::Bu](#reallocate) yöntem tarafından ayrılan belleği serbest leştirmek için yeniden ayırın.

> [!NOTE]
> Kullanım örnekleri için [bkz.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="iatlstringmgrclone"></a><a name="clone"></a>IAtlStringMgr::Klon

Başka bir örnekle kullanılmak üzere yeni bir `CSimpleStringT`dize yöneticisine bir işaretçi döndürür.

```
IAtlStringMgr* Clone() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin bir `IAtlStringMgr` kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Yeni bir dize için bir dize yöneticisi gerektiğinde genellikle çerçeve tarafından çağrılır. Çoğu durumda, **bu** işaretçi döndürülür.

Ancak, bellek yöneticisi birden çok örnek tarafından kullanılmasını `CSimpleStringT`desteklemiyorsa, sharable dize yöneticisiiçin bir işaretçi döndürülmelidir.

> [!NOTE]
> Kullanım örnekleri için [bkz.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="iatlstringmgrfree"></a><a name="free"></a>IAtlStringMgr::Ücretsiz

Dize veri yapısını boşaltıyor.

```
void Free(CStringData* pData) throw();
```

### <a name="parameters"></a>Parametreler

*Pdata*<br/>
Serbest bırakılacak bellek bloğuna işaretçi.

### <a name="remarks"></a>Açıklamalar

Daha önce [Ayırma](#allocate) veya [Tahsis'le](../../atl/reference/iatlmemmgr-class.md#reallocate)ayrılan belirtilen bellek bloğunu boşaltıyor.

> [!NOTE]
> Kullanım örnekleri için [bkz.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="iatlstringmgrgetnilstring"></a><a name="getnilstring"></a>IAtlStringMgr::GetNilString

Boş bir dize için bir işaretçiyi dize veri yapısına döndürür.

```
CStringData* GetNilString() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Boş bir `CStringData` dizeyi temsil etmek için kullanılan nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Boş bir dize temsili dönmek için bu işlevi çağırın.

> [!NOTE]
> Özel bir dize yöneticisi uygularken, bu işlev hiçbir zaman başarısız olmamalıdır. Bunu, dize yöneticisi sınıfına `CNilStringData` bir örnek katıştırarak sağlayabilir ve bu örne bir işaretçi döndürebilirsiniz.

> [!NOTE]
> Kullanım örnekleri için [bkz.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="iatlstringmgrreallocate"></a><a name="reallocate"></a>IAtlStringMgr::Yeniden tahsis

Dize veri yapısını yeniden tahsis eder.

```
CStringData* Reallocate(
    CStringData* pData,
    int nAllocLength,
    int nCharSize) throw();
```

### <a name="parameters"></a>Parametreler

*Pdata*<br/>
Bu bellek yöneticisi tarafından daha önce ayrılan belleğe işaretçi.

*nAllocLength*<br/>
Yeni bellek bloğundaki karakter sayısı.

*nCharSize*<br/>
Dize yöneticisi tarafından kullanılan karakter türünün boyutu (baytlarda).

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğunun başlangıcına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

*pData*tarafından belirtilen varolan bellek bloğunu yeniden boyutlandırmak için bu işlevi arayın.

Çağrı [IAtlStringMgr::Bu](#free) yöntem tarafından ayrılan belleği serbest ücretsiz.

> [!NOTE]
> Kullanım örnekleri için [bkz.](../../atl-mfc-shared/memory-management-with-cstringt.md)

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC Paylaşılan Sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
