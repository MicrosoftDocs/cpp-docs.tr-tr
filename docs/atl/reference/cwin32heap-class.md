---
title: CWin32Heap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CWin32Heap class
ms.assetid: 69176022-ed98-4e3b-96d8-116b0c58ac95
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d3b10648a3251a705085e31559a98b6ee4957c72
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088481"
---
# <a name="cwin32heap-class"></a>CWin32Heap sınıfı

Bu sınıfın uyguladığı [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md) Win32 yığın ayırma işlevleri kullanarak.

> [!IMPORTANT]
>  Bu sınıf ve üyelerine, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz.

## <a name="syntax"></a>Sözdizimi

```
class CWin32Heap : public IAtlMemMgr
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CWin32Heap::CWin32Heap](#cwin32heap)|Oluşturucu.|
|[CWin32Heap:: ~ CWin32Heap](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CWin32Heap::Allocate](#allocate)|Yığın nesneden bir bellek bloğu ayırır.|
|[CWin32Heap::Attach](#attach)|Yığın nesnesi bir mevcut yığına ekler.|
|[CWin32Heap::Detach](#detach)|Varolan bir yığın yığın nesneden çıkarır.|
|[CWin32Heap::Free](#free)|Daha önce yığından ayrılan belleği serbest bırakır.|
|[CWin32Heap::GetSize](#getsize)|Yığın nesneden ayrılan bir bellek bloğu boyutu döndürür.|
|[CWin32Heap::Reallocate](#reallocate)|Bir bellek bloğu yığın nesneden yeniden ayırır.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CWin32Heap::m_bOwnHeap](#m_bownheap)|Geçerli yığın tanıtıcısı sahipliğini belirlemek için kullanılan bayrak.|
|[CWin32Heap::m_hHeap](#m_hheap)|Yığın nesnesi için işler.|

## <a name="remarks"></a>Açıklamalar

`CWin32Heap` bellek ayırma yöntemleri dahil olmak üzere Win32 yığın ayırma işlevleri kullanarak uygulayan [HeapAlloc](/windows/desktop/api/heapapi/nf-heapapi-heapalloc) ve [HeapFree](/windows/desktop/api/heapapi/nf-heapapi-heapfree). Diğer yığın sınıfları aksine `CWin32Heap` bellek tahsis önce sağlanması için geçerli bir yığın tanıtıcısı gerektirir: işlem yığınını kullanmanın diğer sınıflar varsayılan. Oluşturucuya veya çok işleyici sağlanabilir [CWin32Heap::Attach](#attach) yöntemi. Bkz: [CWin32Heap::CWin32Heap](#cwin32heap) daha fazla ayrıntı için yöntemi.

## <a name="example"></a>Örnek

Örneğin bakın [Iatlmemmgr](../../atl/reference/iatlmemmgr-class.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`IAtlMemMgr`

`CWin32Heap`

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlmem.h

##  <a name="allocate"></a>  CWin32Heap::Allocate

Yığın nesneden bir bellek bloğu ayırır.

```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*nBytes*<br/>
İstenen bayt yeni bellek bloğu sayısı.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğu için bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Çağrı [CWin32Heap::Free](#free) veya [CWin32Heap::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.

Kullanılarak uygulanan [HeapAlloc](/windows/desktop/api/heapapi/nf-heapapi-heapalloc).

##  <a name="attach"></a>  CWin32Heap::Attach

Yığın nesnesi bir mevcut yığına ekler.

```
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```

### <a name="parameters"></a>Parametreler

*hHeap*<br/>
Varolan bir yığın tanıtıcısı.

*bTakeOwnership*<br/>
Bayrağı belirten bir IF `CWin32Heap` nesne yığının kaynaklarının sahipliğini etmektir.

### <a name="remarks"></a>Açıklamalar

Varsa *bTakeOwnership* TRUE ise `CWin32Heap` nesnedir yığın tanıtıcısı silmekten sorumlu.

##  <a name="cwin32heap"></a>  CWin32Heap::CWin32Heap

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

*CertOpenStore*<br/>
Yığını oluşturmak için kullanılan bayraklar.

*nInitialSize*<br/>
Yığının ilk boyutu.

*nMaxSize*<br/>
Yığının maksimum boyutu.

### <a name="remarks"></a>Açıklamalar

Bellek ayrılmadan önce bunu sağlamak gerekli olan `CWin32Heap` nesnesi ile geçerli bir yığın tanıtıcısı. Bunu başarmanın en kolay yolu, işlem yığınını kullanmaktır:

[!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]

Oluşturucuya varolan bir yığın tanıtıcısını sağlamak da mümkündür, fakat bu durumda yeni nesne yığının sahipliğini üstlenmez. Özgün yığın tanıtıcısı hala ne zaman geçerli olacak `CWin32Heap` nesnesi silinir.

Varolan bir yığın ayrıca yeni eklenebilecek nesnesini kullanarak [CWin32Heap::Attach](#attach).

Tüm işlemlerin tek bir iş parçacığından gerçekleştirildiği durumda yığın gerekliyse, nesneyi oluşturmanın en iyi yolu şudur:

[!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]

' % S'parametre heap_no_serıalıze, yığın işlevleri bellek, performans artış ile ayırıp olduğunda'nın karşılıklı dışlama kullanılmayacak belirtir.

Üçüncü parametre varsayılan olarak 0'a ayarlanır ve bu da yığının istenen şekilde büyümesine izin verir. Bkz: [HeapCreate](/windows/desktop/api/heapapi/nf-heapapi-heapcreate) bellek boyutlarının ve bayraklarının açıklaması için.

##  <a name="dtor"></a>  CWin32Heap:: ~ CWin32Heap

Yıkıcı.

```
~CWin32Heap() throw();
```

### <a name="remarks"></a>Açıklamalar

Yığın tanıtıcısı, yok eder `CWin32Heap` nesne yığının sahipliğini sahiptir.

##  <a name="detach"></a>  CWin32Heap::Detach

Varolan bir yığın yığın nesneden çıkarır.

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesne daha önce bağlı yığın tanıtıcısını döndürür.

##  <a name="free"></a>  CWin32Heap::Free

Daha önce gelen yığın tarafından ayrılan bellek serbest bırakma [CWin32Heap::Allocate](#allocate) veya [CWin32Heap::Reallocate](#reallocate).

```
virtual void Free(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Ücretsiz bellek bloğuna işaretçi. NULL, geçerli bir değer ve hiçbir şey yapmaz.

##  <a name="getsize"></a>  CWin32Heap::GetSize

Yığın nesneden ayrılan bir bellek bloğu boyutu döndürür.

```
virtual size_t GetSize(void* p) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Bellek Blok boyutu yöntemi elde edersiniz işaretçidir. Tarafından döndürülen bir işaretçi budur [CWin32Heap::Allocate](#allocate) veya [CWin32Heap::Reallocate](#reallocate).

### <a name="return-value"></a>Dönüş Değeri

Ayrılmış bellek bloğu bayt cinsinden boyutunu döndürür.

##  <a name="m_bownheap"></a>  CWin32Heap::m_bOwnHeap

Depolanan yığın tanıtıcısı geçerli sahipliğini belirlemek için kullanılan bayrak [m_hHeap](#m_hheap).

```
bool m_bOwnHeap;
```

##  <a name="m_hheap"></a>  CWin32Heap::m_hHeap

Yığın nesnesi için işler.

```
HANDLE m_hHeap;
```

### <a name="remarks"></a>Açıklamalar

Yığın nesnesi için bir tanıtıcı depolamak için kullanılan bir değişken.

##  <a name="reallocate"></a>  CWin32Heap::Reallocate

Bir bellek bloğu yığın nesneden yeniden ayırır.

```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
Ayrılacak bellek bloğuna işaretçi.

*nBytes*<br/>
Yeni boyutu bayt cinsinden ayrılan bloğu. Daha büyük veya küçük blok yapılabilir.

### <a name="return-value"></a>Dönüş Değeri

Yeni ayrılan bellek bloğu için bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Varsa *p* NULL ise bellek bloğu henüz ayrılmadı olduğunu kabul edilir ve [CWin32Heap::Allocate](#allocate) bir bağımsız değişkenle çağrıldığında *nBytes*.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)<br/>
[IAtlMemMgr Sınıfı](../../atl/reference/iatlmemmgr-class.md)<br/>
[CLocalHeap Sınıfı](../../atl/reference/clocalheap-class.md)<br/>
[CGlobalHeap Sınıfı](../../atl/reference/cglobalheap-class.md)<br/>
[CCRTHeap Sınıfı](../../atl/reference/ccrtheap-class.md)<br/>
[CComHeap Sınıfı](../../atl/reference/ccomheap-class.md)
