---
title: CHeapPtr Sınıfı
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
ms.openlocfilehash: a512aa974cb57072915f887f0c2a20ed1263ffa3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326912"
---
# <a name="cheapptr-class"></a>CHeapPtr Sınıfı

Yığın işaretçileri yönetmek için akıllı bir işaretçi sınıfı.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
template<typename T, class Allocator=CCRTAllocator>
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Yığında depolanacak nesne türü.

*Ayırıcı*<br/>
Kullanılacak bellek ayırma sınıfı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CHeapPtr::CHeapPtr](#cheapptr)|Oluşturucu.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CHeapPtr::Ayırma](#allocate)|Nesneleri depolamak için yığın üzerinde bellek ayırmak için bu yöntemi arayın.|
|[CHeapPtr::Yer tahsisi](#reallocate)|Yığındaki belleği yeniden tahsis etmek için bu yöntemi arayın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CHeapPtr::operatör =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

`CHeapPtr`[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) türetilmiştir ve varsayılan olarak crt yordamları kullanır [(CCRTAllocator)](../../atl/reference/ccrtallocator-class.md)ayırmak ve ücretsiz bellek. [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) sınıfı yığın işaretçilerin listesini oluşturmak için kullanılabilir. [Ayrıca](../../atl/reference/ccomheapptr-class.md)bkz.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)

`CHeapPtr`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcore.h

## <a name="cheapptrallocate"></a><a name="allocate"></a>CHeapPtr::Ayırma

Nesneleri depolamak için yığın üzerinde bellek ayırmak için bu yöntemi arayın.

```
bool Allocate(size_t nElements = 1) throw();
```

### <a name="parameters"></a>Parametreler

*nElements*<br/>
Ayrılacak bellek miktarını hesaplamak için kullanılan öğe sayısı. Varsayılan değer 1’dir.

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ayrıldıysa doğru döndürür, hata yanlış.

### <a name="remarks"></a>Açıklamalar

Ayırıcı yordamları, oluşturucuda tanımlanan bir türün *nElement* nesnelerini depolamak için yığında yeterli bellek ayırmak için kullanılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]

## <a name="cheapptrcheapptr"></a><a name="cheapptr"></a>CHeapPtr::CHeapPtr

Oluşturucu.

```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Varolan bir yığın `CHeapPtr`işaretçi veya .

### <a name="remarks"></a>Açıklamalar

Yığın işaretçisi isteğe bağlı olarak varolan `CHeapPtr` bir işaretçi veya bir nesne kullanılarak oluşturulabilir. Bu nedenle, `CHeapPtr` yeni nesne yeni işaretçi ve kaynakları yönetmek için sorumluluk üstlenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]

## <a name="cheapptroperator-"></a><a name="operator_eq"></a>CHeapPtr::operatör =

Atama işleci.

```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Varolan bir `CHeapPtr` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CHeapPtr`bir başvuru verir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]

## <a name="cheapptrreallocate"></a><a name="reallocate"></a>CHeapPtr::Yer tahsisi

Yığındaki belleği yeniden tahsis etmek için bu yöntemi arayın.

```
bool Reallocate(size_t nElements) throw();
```

### <a name="parameters"></a>Parametreler

*nElements*<br/>
Ayrılacak bellek miktarını hesaplamak için kullanılan yeni öğe sayısı.

### <a name="return-value"></a>Dönüş Değeri

Bellek başarıyla ayrıldıysa doğru döndürür, hata yanlış.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CHeapPtrBase Sınıfı](../../atl/reference/cheapptrbase-class.md)<br/>
[CCRTAllocator Sınıfı](../../atl/reference/ccrtallocator-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
