---
description: 'Daha fazla bilgi edinin: CWin32Heap Class'
title: CWin32Heap sınıfı
ms.date: 11/04/2016
f1_keywords:
- CWin32Heap
- ATLMEM/ATL::CWin32Heap
- ATLMEM/ATL::CWin32Heap::CWin32Heap
- ATLMEM/ATL::CWin32Heap::Allocate
- ATLMEM/ATL::CWin32Heap::Attach
- ATLMEM/ATL::CWin32Heap::Detach
- ATLMEM/ATL::CWin32Heap::Free
- ATLMEM/ATL::CWin32Heap::GetSize
- ATLMEM/ATL::CWin32Heap::Reallocate
- ATLMEM/ATL::CWin32Heap::m_bOwnHeap
- ATLMEM/ATL::CWin32Heap::m_hHeap
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
ms.openlocfilehash: a19c7f01a572bad46dbbab2925104d4dfcf569be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140211"
---
# <a name="cwin32heap-class"></a>CWin32Heap sınıfı

Bu sınıf, Win32 yığın ayırma işlevlerini kullanarak [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Syntax

```
class CWin32Heap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWin32Heap:: CWin32Heap](#cwin32heap)|Oluşturucu.|
|[CWin32Heap:: ~ CWin32Heap](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWin32Heap:: allocate](#allocate)|Yığın nesnesinden bir bellek bloğu ayırır.|
|[CWin32Heap:: Attach](#attach)|Yığın nesnesini var olan bir yığına iliştirir.|
|[CWin32Heap::D etach](#detach)|Yığın nesnesini var olan bir yığından ayırır.|
|[CWin32Heap:: Free](#free)|Daha önce yığından ayrılmış belleği serbest bırakır.|
|[CWin32Heap:: GetSize](#getsize)|Yığın nesnesinden ayrılan bellek bloğunun boyutunu döndürür.|
|[CWin32Heap:: yeniden tahsis](#reallocate)|Yığın nesnesinden bir bellek bloğunu yeniden konumlandırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CWin32Heap:: m_bOwnHeap](#m_bownheap)|Yığın tanıtıcısının geçerli sahipliğini belirlemede kullanılan bayrak.|
|[CWin32Heap:: m_hHeap](#m_hheap)|Yığın nesnesine işleyin.|

## <a name="remarks"></a>Açıklamalar

`CWin32Heap` , [heapallocation](/windows/win32/api/heapapi/nf-heapapi-heapalloc) ve [HeapFree](/windows/win32/api/heapapi/nf-heapapi-heapfree)dahil olmak üzere Win32 yığın ayırma işlevlerini kullanarak bellek ayırma yöntemlerini uygular. Diğer yığın sınıflarının aksine, `CWin32Heap` bellek ayrıönüne alınmadan önce geçerli bir yığın tanıtıcısının sağlanması gerekir: diğer sınıflar işlem yığınını kullanmak için varsayılan değer. Tanıtıcı oluşturucuya veya [CWin32Heap:: Attach](#attach) yöntemine sağlanabilir. Daha fazla ayrıntı için [CWin32Heap:: CWin32Heap](#cwin32heap) yöntemine bakın.

## <a name="example"></a>Örnek

[IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md)örneğine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CWin32Heap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlmem. h

## <a name="cwin32heapallocate"></a><a name="allocate"></a> CWin32Heap:: allocate

Yığın nesnesinden bir bellek bloğu ayırır.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
Yeni bellek bloğunda istenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğuna bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem tarafından ayrılan belleği serbest bırakmak için [CWin32Heap:: Free](#free) veya [CWin32Heap::](#reallocate) Call olarak yeniden tahsis edin.

[Heapayırma](/windows/win32/api/heapapi/nf-heapapi-heapalloc)kullanılarak uygulanır.

## <a name="cwin32heapattach"></a><a name="attach"></a> CWin32Heap:: Attach

Yığın nesnesini var olan bir yığına iliştirir.

```cpp
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```

### <a name="parameters"></a>Parametreler

*hHeap*<br/>
Var olan bir yığın tanıtıcısı.

*Btakesahiplik*<br/>
`CWin32Heap`Nesnenin, yığının kaynakları üzerinde sahiplik alıp atlamadığını belirten bir bayrak.

### <a name="remarks"></a>Açıklamalar

*Btakesahiplik* true ise `CWin32Heap` nesne, yığın tanıtıcısının silinmesinden sorumludur.

## <a name="cwin32heapcwin32heap"></a><a name="cwin32heap"></a> CWin32Heap:: CWin32Heap

Oluşturucu.

```
CWin32Heap() throw();
CWin32Heap( HANDLE  hHeap) throw();
CWin32Heap(
    DWORD  dwFlags,
    size_t nInitialSize,
    size_t nMaxSize = 0);
```

### <a name="parameters"></a>Parametreler

*hHeap*<br/>
Varolan bir yığın nesnesi.

*dwFlags*<br/>
Yığını oluşturmak için kullanılan bayraklar.

*Nınitialsize*<br/>
Yığının ilk boyutu.

*nMaxSize*<br/>
Yığının maksimum boyutu.

### <a name="remarks"></a>Açıklamalar

Belleği ayırmadan önce, `CWin32Heap` nesnenin geçerli bir yığın tanıtıcısı sağlaması gerekir. Bunu başarmanın en kolay yolu, işlem yığınını kullanmaktır:

[!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]

Oluşturucuya varolan bir yığın tanıtıcısını sağlamak da mümkündür, fakat bu durumda yeni nesne yığının sahipliğini üstlenmez. Özgün yığın tanıtıcısı, nesne silindiğinde geçerli olmaya devam edecektir `CWin32Heap` .

Var olan bir yığın, [CWin32Heap:: Attach](#attach)kullanılarak yeni nesneye de iliştirilebilir.

Tüm işlemlerin tek bir iş parçacığından gerçekleştirildiği durumda yığın gerekliyse, nesneyi oluşturmanın en iyi yolu şudur:

[!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]

HEAP_NO_SERIALIZE parametresi, yığın işlevleri bir performans artışına göre bellek ayırır ve serbest bırakıldığında karşılıklı dışlamanın kullanılmayacağını belirtir.

Üçüncü parametre varsayılan olarak 0'a ayarlanır ve bu da yığının istenen şekilde büyümesine izin verir. Bellek boyutlarının ve bayrakların açıklaması için bkz. [HeapCreate](/windows/win32/api/heapapi/nf-heapapi-heapcreate) .

## <a name="cwin32heapcwin32heap"></a><a name="dtor"></a> CWin32Heap:: ~ CWin32Heap

Yok edicisi.

```
~CWin32Heap() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesne yığının sahipliğini içeriyorsa yığın tanıtıcısını yok eder `CWin32Heap` .

## <a name="cwin32heapdetach"></a><a name="detach"></a> CWin32Heap::D etach

Yığın nesnesini var olan bir yığından ayırır.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnenin daha önce eklendiği yığına olan tanıtıcıyı döndürür.

## <a name="cwin32heapfree"></a><a name="free"></a> CWin32Heap:: Free

[CWin32Heap:: allocate](#allocate) veya [CWin32Heap::](#reallocate)allocate tarafından yığından daha önce ayrılan belleği boşaltır.

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Boşaltılacak bellek bloğunun işaretçisi. NULL geçerli bir değerdir ve hiçbir şey yapmaz.

## <a name="cwin32heapgetsize"></a><a name="getsize"></a> CWin32Heap:: GetSize

Yığın nesnesinden ayrılan bellek bloğunun boyutunu döndürür.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Yöntemi yöntemin elde edileceği bellek bloğunun işaretçisi. Bu, [CWin32Heap:: allocate](#allocate) veya [CWin32Heap:: yeniden tahsis](#reallocate)tarafından döndürülen bir işaretçisidir.

### <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek bloğunun bayt cinsinden boyutunu döndürür.

## <a name="cwin32heapm_bownheap"></a><a name="m_bownheap"></a> CWin32Heap:: m_bOwnHeap

[M_hHeap](#m_hheap)içinde depolanan yığın tanıtıcısının geçerli sahipliğini belirlemede kullanılan bayrak.

```
bool m_bOwnHeap;
```

## <a name="cwin32heapm_hheap"></a><a name="m_hheap"></a> CWin32Heap:: m_hHeap

Yığın nesnesine işleyin.

```
HANDLE m_hHeap;
```

### <a name="remarks"></a>Açıklamalar

Yığın nesnesine bir tutamacı depolamak için kullanılan değişken.

## <a name="cwin32heapreallocate"></a><a name="reallocate"></a> CWin32Heap:: yeniden tahsis

Yığın nesnesinden bir bellek bloğunu yeniden konumlandırır.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
Yeniden ayrılacak bellek bloğunun işaretçisi.

*nBytes*<br/>
Ayrılan bloğun bayt cinsinden yeni boyutu. Blok daha büyük veya daha küçük olabilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğuna bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

*P* null ise, bellek bloğunun henüz ayrılmadığı varsayılır ve [CWin32Heap:: allocate](#allocate) , *nBytes* bağımsız değişkeniyle birlikte çağırılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)<br/>
[IAtlMemMgr sınıfı](../../atl/reference/iatlmemmgr-class.md)<br/>
[CLocalHeap sınıfı](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap sınıfı](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap sınıfı](../../atl/reference/ccrtheap-class.md)<br/>
[CComHeap sınıfı](../../atl/reference/ccomheap-class.md)
