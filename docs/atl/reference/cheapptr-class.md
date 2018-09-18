---
title: CHeapPtr sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ea4fd429395fc78f36d1f9b3244068c737be49a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46033985"
---
# <a name="cheapptr-class"></a>CHeapPtr sınıfı

Yığın işaretçileri yönetmek için bir akıllı işaretçi sınıfının.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<typename T, class Allocator=CCRTAllocator>
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Yığın üzerinde depolanan nesne türü.

*Ayırıcı*<br/>
Bellek ayırma kullanmak için sınıf.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtr::CHeapPtr](#cheapptr)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtr::Allocate](#allocate)|Nesneleri depolamak için yığında bellek ayırmak için bu yöntemi çağırın.|
|[CHeapPtr::Reallocate](#reallocate)|Yığın belleği yeniden tahsis etmek için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CHeapPtr::operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

`CHeapPtr` türetilen [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) ve varsayılan olarak CRT yordamlarını kullanır (içinde [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) ayırmak ve belleği boşaltmak için. Sınıf [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) yığın işaretçileri listesini oluşturmak için kullanılabilir. Ayrıca bkz: [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), COM bellek ayırma yordamlarını kullanır.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

`CHeapPtr`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcore.h

##  <a name="allocate"></a>  CHeapPtr::Allocate

Nesneleri depolamak için yığında bellek ayırmak için bu yöntemi çağırın.

```
bool Allocate(size_t nElements = 1) throw();
```

### <a name="parameters"></a>Parametreler

*nElements*<br/>
Ayrılacak bellek miktarını hesaplamak için kullanılan öğelerin sayısı. Varsayılan değer 1’dir.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek başarılı olduysa true değerini döndürür, başarısız olduğunda false.

### <a name="remarks"></a>Açıklamalar

Yığında depolamak için yeterli bellek ayırmak için kullanılan ayırıcı yordamları *nElement* oluşturucu içinde tanımlanan bir türden nesneleri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]

##  <a name="cheapptr"></a>  CHeapPtr::CHeapPtr

Oluşturucu.

```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Varolan bir yığın işaretçisi veya `CHeapPtr`.

### <a name="remarks"></a>Açıklamalar

Yığın işaretçisi isteğe bağlı olarak var olan bir işaretçi kullanılarak oluşturulabilir veya `CHeapPtr` nesne. Bu durumda, yeni `CHeapPtr` nesne yeni işaretçi ve kaynaklarını yönetme sorumluluğunu varsayar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]

##  <a name="operator_eq"></a>  CHeapPtr::operator =

Atama işleci.

```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Varolan bir `CHeapPtr` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş bir başvuru döndürür `CHeapPtr`.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]

##  <a name="reallocate"></a>  CHeapPtr::Reallocate

Yığın belleği yeniden tahsis etmek için bu yöntemi çağırın.

```
bool Reallocate(size_t nElements) throw();
```

### <a name="parameters"></a>Parametreler

*nElements*<br/>
Ayrılacak bellek miktarını hesaplamak için kullanılan öğelerin yeni sayısı.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek başarılı olduysa true değerini döndürür, başarısız olduğunda false.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[CHeapPtrBase Sınıfı](../../atl/reference/cheapptrbase-class.md)<br/>
[CCRTAllocator Sınıfı](../../atl/reference/ccrtallocator-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
