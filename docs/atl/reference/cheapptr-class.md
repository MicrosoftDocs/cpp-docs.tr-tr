---
description: 'Daha fazla bilgi edinin: CHeapPtr sınıfı'
title: CHeapPtr sınıfı
ms.date: 11/04/2016
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
ms.openlocfilehash: dc795c199562fa423a160b053c96983651d0812d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141654"
---
# <a name="cheapptr-class"></a>CHeapPtr sınıfı

Yığın işaretçilerini yönetmek için bir akıllı işaretçi sınıfı.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<typename T, class Allocator=CCRTAllocator>
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Yığında depolanacak nesne türü.

*Öğe*<br/>
Kullanılacak bellek ayırma sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtr:: CHeapPtr](#cheapptr)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtr:: allocate](#allocate)|Nesneleri depolamak için yığında bellek ayırmak için bu yöntemi çağırın.|
|[CHeapPtr:: yeniden tahsis](#reallocate)|Yığındaki belleği yeniden ayırmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtr:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

`CHeapPtr` , [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) öğesinden türetilir ve varsayılan olarak, bellek ayırmak ve boşaltmak için CRT yordamlarını ( [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)içinde) kullanır. [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) sınıfı, yığın işaretçilerinin bir listesini oluşturmak için kullanılabilir. Ayrıca bkz. COM bellek ayırma yordamlarını kullanan [CComHeapPtr](../../atl/reference/ccomheapptr-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

`CHeapPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore. h

## <a name="cheapptrallocate"></a><a name="allocate"></a> CHeapPtr:: allocate

Nesneleri depolamak için yığında bellek ayırmak için bu yöntemi çağırın.

```
bool Allocate(size_t nElements = 1) throw();
```

### <a name="parameters"></a>Parametreler

*nElements*<br/>
Ayrılacak bellek miktarını hesaplamak için kullanılan öğe sayısı. Varsayılan değer 1’dir.

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ayrıldıysa true, hatada false döndürür.

### <a name="remarks"></a>Açıklamalar

Ayırıcı yordamları, oluşturucuda tanımlanan bir türün *nElement* nesnelerini depolamak için yığında yeterli bellek ayırmak için kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]

## <a name="cheapptrcheapptr"></a><a name="cheapptr"></a> CHeapPtr:: CHeapPtr

Oluşturucu.

```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Var olan bir yığın işaretçisi veya `CHeapPtr` .

### <a name="remarks"></a>Açıklamalar

Yığın işaretçisi, isteğe bağlı olarak var olan bir işaretçi veya bir nesne kullanılarak oluşturulabilir `CHeapPtr` . Bu durumda, yeni `CHeapPtr` nesne yeni işaretçi ve kaynakları yönetme sorumluluğunu kabul eder.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]

## <a name="cheapptroperator-"></a><a name="operator_eq"></a> CHeapPtr:: operator =

Atama işleci.

```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Varolan bir `CHeapPtr` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş öğesine bir başvuru döndürür `CHeapPtr` .

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]

## <a name="cheapptrreallocate"></a><a name="reallocate"></a> CHeapPtr:: yeniden tahsis

Yığındaki belleği yeniden ayırmak için bu yöntemi çağırın.

```
bool Reallocate(size_t nElements) throw();
```

### <a name="parameters"></a>Parametreler

*nElements*<br/>
Ayrılacak bellek miktarını hesaplamak için kullanılan yeni öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ayrıldıysa true, hatada false döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtrBase sınıfı](../../atl/reference/cheapptrbase-class.md)<br/>
[CCRTAllocator sınıfı](../../atl/reference/ccrtallocator-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
