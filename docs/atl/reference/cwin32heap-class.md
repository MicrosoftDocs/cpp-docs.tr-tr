---
title: CWin32Heap Sınıfı
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
ms.openlocfilehash: 2d79de308b1afb3059cf04ad40b63b6e603073c8
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746036"
---
# <a name="cwin32heap-class"></a>CWin32Heap Sınıfı

Bu sınıf Win32 yığın ayırma işlevlerini kullanarak [IAtlMemmgr](../../atl/reference/iatlmemmgr-class.md) uygular.

> [!IMPORTANT]
> Bu sınıf ve üyeleri, Windows Runtime'da çalıştırılan uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CWin32Heap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CWin32Heap::CWin32Heap](#cwin32heap)|Oluşturucu.|
|[CWin32Heap::~CWin32Heap](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CWin32Heap::Ayırma](#allocate)|Yığın nesnesinden bir bellek bloğu ayırır.|
|[CWin32Heap::Ekle](#attach)|Yığın nesnesini varolan bir yığına bağlar.|
|[CWin32Heap::Detach](#detach)|Yığın nesnesini varolan bir yığından ayırır.|
|[CWin32Heap::Ücretsiz](#free)|Daha önce yığından ayrılan belleği boşaltıyor.|
|[CWin32Heap::GetSize](#getsize)|Yığın nesnesinden ayrılan bellek bloğunun boyutunu döndürür.|
|[CWin32Heap::Yer tahsisi](#reallocate)|Yığın nesnesinden bellek bloğunu yeniden tahsis eder.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CWin32Heap::m_bOwnHeap](#m_bownheap)|Yığın tutamacının geçerli sahipliğini belirlemek için kullanılan bir bayrak.|
|[CWin32Heap::m_hHeap](#m_hheap)|Yığın nesnesine işle.|

## <a name="remarks"></a>Açıklamalar

`CWin32Heap`[HeapAlloc](/windows/win32/api/heapapi/nf-heapapi-heapalloc) ve [HeapFree](/windows/win32/api/heapapi/nf-heapapi-heapfree)dahil olmak üzere Win32 yığın ayırma işlevlerini kullanarak bellek ayırma yöntemleri uygular. Diğer Yığın sınıflarının `CWin32Heap` aksine, bellek ayrılmadan önce sağlanacak geçerli bir yığın tutamacı gerektirir: diğer sınıflar işlem yığınını kullanmaktan varsayılan olarak. Tutamaç oluşturucuya veya [CWin32Heap'a sağlanabilir::Ekle](#attach) yöntemi. Daha fazla bilgi için [CWin32Heap::CWin32Heap](#cwin32heap) yöntemine bakın.

## <a name="example"></a>Örnek

[IAtlMemmgr](../../atl/reference/iatlmemmgr-class.md)örneğine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CWin32Heap`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlmem.h

## <a name="cwin32heapallocate"></a><a name="allocate"></a>CWin32Heap::Ayırma

Yığın nesnesinden bir bellek bloğu ayırır.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBayt*<br/>
Yeni bellek bloğunda istenen bayt sayısı.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçiyi yeni ayrılan bellek bloğuna döndürür.

### <a name="remarks"></a>Açıklamalar

[CWin32Heap'ı Arayın::Ücretsiz](#free) veya [CWin32Heap::Bu](#reallocate) yöntemle ayrılan belleği serbest etmek için yeniden bulunun.

[HeapAlloc](/windows/win32/api/heapapi/nf-heapapi-heapalloc)kullanılarak uygulanır.

## <a name="cwin32heapattach"></a><a name="attach"></a>CWin32Heap::Ekle

Yığın nesnesini varolan bir yığına bağlar.

```cpp
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```

### <a name="parameters"></a>Parametreler

*hHeap*<br/>
Varolan bir yığın tutamacı.

*bTakeOwnership*<br/>
Nesnenin yığının `CWin32Heap` kaynakları üzerinde sahiplik almak olup olmadığını belirten bir bayrak.

### <a name="remarks"></a>Açıklamalar

*bTakeOwnership* TRUE ise, `CWin32Heap` nesne yığın tutamacını silmesinden sorumludur.

## <a name="cwin32heapcwin32heap"></a><a name="cwin32heap"></a>CWin32Heap::CWin32Heap

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

*Dwflags*<br/>
Yığını oluşturmak için kullanılan bayraklar.

*nInitialSize*<br/>
Yığının ilk boyutu.

*nMaxSize*<br/>
Yığının maksimum boyutu.

### <a name="remarks"></a>Açıklamalar

Belleği ayırmadan önce, `CWin32Heap` nesneye geçerli bir yığın tutamacı sağlamak gerekir. Bunu başarmanın en kolay yolu, işlem yığınını kullanmaktır:

[!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]

Oluşturucuya varolan bir yığın tanıtıcısını sağlamak da mümkündür, fakat bu durumda yeni nesne yığının sahipliğini üstlenmez. `CWin32Heap` Nesne silindiğinde özgün yığın tutamacı yine de geçerli olacaktır.

Varolan bir yığın da [CWin32Heap](#attach)kullanarak, yeni nesneye eklenebilir::Ekle.

Tüm işlemlerin tek bir iş parçacığından gerçekleştirildiği durumda yığın gerekliyse, nesneyi oluşturmanın en iyi yolu şudur:

[!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]

Parametre HEAP_NO_SERIALIZE, yığın işlevleri tahsis edildiğinde karşılıklı dışlamanın kullanılmayacağını ve performansta buna göre bir artış olacağını belirtir.

Üçüncü parametre varsayılan olarak 0'a ayarlanır ve bu da yığının istenen şekilde büyümesine izin verir. Bellek boyutları ve bayraklarıhakkında bir açıklama için [HeapCreate'e](/windows/win32/api/heapapi/nf-heapapi-heapcreate) bakın.

## <a name="cwin32heapcwin32heap"></a><a name="dtor"></a>CWin32Heap::~CWin32Heap

Yıkıcı.

```
~CWin32Heap() throw();
```

### <a name="remarks"></a>Açıklamalar

Nesne yığının mülkiyetine `CWin32Heap` sahipse yığın tutamacını yok eder.

## <a name="cwin32heapdetach"></a><a name="detach"></a>CWin32Heap::Detach

Yığın nesnesini varolan bir yığından ayırır.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tutamacı nesnenin daha önce eklendiği yığına döndürür.

## <a name="cwin32heapfree"></a><a name="free"></a>CWin32Heap::Ücretsiz

Daha önce [CWin32Heap](#allocate) tarafından yığın dan ayrılan belleği boşaltıyor::Allocate veya [CWin32Heap::Yer.](#reallocate)

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Özgür bellek bloğuna işaretçi. NULL geçerli bir değerdir ve hiçbir şey yapmaz.

## <a name="cwin32heapgetsize"></a><a name="getsize"></a>CWin32Heap::GetSize

Yığın nesnesinden ayrılan bellek bloğunun boyutunu döndürür.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Yöntemin alacağı boyutu bellek bloğuna işaretçi. Bu [CWin32Heap](#allocate) tarafından döndürülen bir işaretçi::Allocate veya [CWin32Heap::Emlakçılık](#reallocate).

### <a name="return-value"></a>Dönüş Değeri

Ayrılan bellek bloğunun boyutunu baytolarak döndürür.

## <a name="cwin32heapm_bownheap"></a><a name="m_bownheap"></a>CWin32Heap::m_bOwnHeap

[m_hHeap](#m_hheap)depolanan yığın tutamacının geçerli sahipliğini belirlemek için kullanılan bir bayrak.

```
bool m_bOwnHeap;
```

## <a name="cwin32heapm_hheap"></a><a name="m_hheap"></a>CWin32Heap::m_hHeap

Yığın nesnesine işle.

```
HANDLE m_hHeap;
```

### <a name="remarks"></a>Açıklamalar

Bir tutamacı yığın nesnesine depolamak için kullanılan bir değişken.

## <a name="cwin32heapreallocate"></a><a name="reallocate"></a>CWin32Heap::Yer tahsisi

Yığın nesnesinden bellek bloğunu yeniden tahsis eder.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Yeniden tahsis etmek için bellek bloğuna işaretçi.

*nBayt*<br/>
Ayrılan bloğun baytlarında yeni boyut. Blok daha büyük veya daha küçük yapılabilir.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçiyi yeni ayrılan bellek bloğuna döndürür.

### <a name="remarks"></a>Açıklamalar

*p* NULL ise, bellek bloğu henüz tahsis edilmemiştir ve [CWin32Heap varsayılır::Ayırma](#allocate) *nBytes*bir argüman ile çağrılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)<br/>
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)<br/>
[CLocalHeap Sınıfı](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap Sınıfı](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap Sınıfı](../../atl/reference/ccrtheap-class.md)<br/>
[CComHeap Sınıfı](../../atl/reference/ccomheap-class.md)
