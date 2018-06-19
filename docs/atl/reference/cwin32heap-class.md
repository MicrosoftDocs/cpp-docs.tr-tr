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
ms.openlocfilehash: 9b26d979ccb99d3d99bc91af03c4836603d31c01
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363942"
---
# <a name="cwin32heap-class"></a>CWin32Heap sınıfı
Bu sınıf uygulayan [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md) Win32 yığın ayırma işlevleri kullanarak.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CWin32Heap : public IAtlMemMgr
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWin32Heap::CWin32Heap](#cwin32heap)|Oluşturucu.|  
|[CWin32Heap:: ~ CWin32Heap](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWin32Heap::Allocate](#allocate)|Bir bellek bloğu yığın nesnesinden ayırır.|  
|[CWin32Heap::Attach](#attach)|Yığın nesnesi için var olan bir yığın ekler.|  
|[CWin32Heap::Detach](#detach)|Varolan bir yığın yığın nesneden çıkarır.|  
|[CWin32Heap::Free](#free)|Daha önce yığınından ayrılan belleği serbest bırakır.|  
|[CWin32Heap::GetSize](#getsize)|Yığın nesnesinden ayrılan bellek bloğu boyutu döndürür.|  
|[CWin32Heap::Reallocate](#reallocate)|Bir bellek bloğu yığın nesnesinden yeniden ayırır.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWin32Heap::m_bOwnHeap](#m_bownheap)|Yığın tanıtıcısı geçerli sahipliğini belirlemek için kullanılan bir bayrak.|  
|[CWin32Heap::m_hHeap](#m_hheap)|Yığın nesnesi işleyin.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CWin32Heap` bellek ayırma yöntemlerini de dahil olmak üzere Win32 yığın ayırma işlevleri kullanarak uygulayan [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597) ve [HeapFree](http://msdn.microsoft.com/library/windows/desktop/aa366701). Diğer yığın sınıfları aksine `CWin32Heap` bellek tahsis önce sağlanacak geçerli yığın tanıtıcısı gerektirir: işlem yığın kullanmanın diğer sınıflar varsayılan. Tanıtıcı Oluşturucusu ya da çok sağlanan [CWin32Heap::Attach](#attach) yöntemi. Bkz: [CWin32Heap::CWin32Heap](#cwin32heap) daha fazla ayrıntı için yöntem.  
  
## <a name="example"></a>Örnek  
 Örneğin bkz [IAtlMemMgr](../../atl/reference/iatlmemmgr-class.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `IAtlMemMgr`  
  
 `CWin32Heap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlmem.h  
  
##  <a name="allocate"></a>  CWin32Heap::Allocate  
 Bir bellek bloğu yığın nesnesinden ayırır.  
  
```
virtual __declspec(allocator) void* Allocate(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBytes`  
 İstenen yeni bellek bloğu içindeki bayt sayısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi yeni ayrılan bellek bloğuna döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı [CWin32Heap::Free](#free) veya [CWin32Heap::Reallocate](#reallocate) bu yöntem tarafından ayrılan bellek boşaltmak için.  
  
 Kullanılarak uygulanan [HeapAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366597).  
  
##  <a name="attach"></a>  CWin32Heap::Attach  
 Yığın nesnesi için var olan bir yığın ekler.  
  
```
void Attach(HANDLE hHeap, bool bTakeOwnership) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `hHeap`  
 Varolan bir yığın tanıtıcısı.  
  
 `bTakeOwnership`  
 Bayrak belirten IF `CWin32Heap` nesnesidir öbek kaynaklar sahipliği.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `bTakeOwnership` doğru ise, `CWin32Heap` nesnesidir yığın tanıtıcısı silmek için sorumlu.  
  
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
 `hHeap`  
 Varolan bir yığın nesnesi.  
  
 `dwFlags`  
 Yığını oluşturmak için kullanılan bayraklar.  
  
 *nInitialSize*  
 Yığının ilk boyutu.  
  
 `nMaxSize`  
 Yığının maksimum boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bellek ayırma önce sağlamak ise gerekli `CWin32Heap` geçerli yığın işleyici ile nesne. Bunu başarmanın en kolay yolu, işlem yığınını kullanmaktır:  
  
 [!code-cpp[NVC_ATL_Utilities#92](../../atl/codesnippet/cpp/cwin32heap-class_1.cpp)]  
  
 Oluşturucuya varolan bir yığın tanıtıcısını sağlamak da mümkündür, fakat bu durumda yeni nesne yığının sahipliğini üstlenmez. Özgün yığın tanıtıcısı ne zaman geçerli olmaya devam edecektir `CWin32Heap` nesne silinir.  
  
 Varolan bir yığın ayrıca yeni eklenebilecek nesnesi, kullanarak [CWin32Heap::Attach](#attach).  
  
 Tüm işlemlerin tek bir iş parçacığından gerçekleştirildiği durumda yığın gerekliyse, nesneyi oluşturmanın en iyi yolu şudur:  
  
 [!code-cpp[NVC_ATL_Utilities#93](../../atl/codesnippet/cpp/cwin32heap-class_2.cpp)]  
  
 Parametre **HEAP_NO_SERIALIZE** heap işlevleri ayırma ve serbest bellek performans according artan'ın karşılıklı dışlama kullanılmayacak belirtir.  
  
 Üçüncü parametre varsayılan olarak 0'a ayarlanır ve bu da yığının istenen şekilde büyümesine izin verir. Bkz: [HeapCreate](http://msdn.microsoft.com/library/windows/desktop/aa366599\(v=vs.85\).aspx) bellek boyutları ve bayrakları hakkında bir açıklama için.  
  
##  <a name="dtor"></a>  CWin32Heap:: ~ CWin32Heap  
 Yok Edicisi.  
  
```
~CWin32Heap() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yığın tanıtıcısı varsa bozar `CWin32Heap` nesnesi öbek sahipliğini sahiptir.  
  
##  <a name="detach"></a>  CWin32Heap::Detach  
 Varolan bir yığın yığın nesneden çıkarır.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Nesne daha önce iliştirildiği yığın işleyicisini döndürür.  
  
##  <a name="free"></a>  CWin32Heap::Free  
 Gelen öbek tarafından önceden ayrılmış bellek boşaltır [CWin32Heap::Allocate](#allocate) veya [CWin32Heap::Reallocate](#reallocate).  
  
```
virtual void Free(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Boş bellek bloğuna yönelik işaretçi. NULL geçerli bir değer ve hiçbir şey yapmaz.  
  
##  <a name="getsize"></a>  CWin32Heap::GetSize  
 Yığın nesnesinden ayrılan bellek bloğu boyutu döndürür.  
  
```
virtual size_t GetSize(void* p) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Bellek Blok boyutu yöntemi alacak işaretçi. Bu tarafından döndürülen bir işaretçidir [CWin32Heap::Allocate](#allocate) veya [CWin32Heap::Reallocate](#reallocate).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Ayrılmış bellek bloğu bayt cinsinden boyutu döndürür.  
  
##  <a name="m_bownheap"></a>  CWin32Heap::m_bOwnHeap  
 Geçerli sahipliği depolanan yığın tanıtıcının belirlemek için kullanılan bir bayrak [m_hHeap](#m_hheap).  
  
```
bool m_bOwnHeap;
```  
  
##  <a name="m_hheap"></a>  CWin32Heap::m_hHeap  
 Yığın nesnesi işleyin.  
  
```
HANDLE m_hHeap;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yığın nesnesi için bir tanıtıcı depolamak için kullanılan bir değişken.  
  
##  <a name="reallocate"></a>  CWin32Heap::Reallocate  
 Bir bellek bloğu yığın nesnesinden yeniden ayırır.  
  
```
virtual __declspec(allocator) void* Reallocate(void* p, size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `p`  
 Ayrılacak bellek bloğuna yönelik işaretçi.  
  
 `nBytes`  
 Yeni ayrılmış blok bayt boyutu. Blok daha büyük ya da daha küçük hale getirilebilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi yeni ayrılan bellek bloğuna döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `p` null, bellek bloğu henüz ayrılmadı olduğunu kabul edilir ve [CWin32Heap::Allocate](#allocate) bağımsız değişkeninin ile adlandırılır `nBytes`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [IAtlMemMgr sınıfı](../../atl/reference/iatlmemmgr-class.md)   
 [CLocalHeap sınıfı](../../atl/reference/clocalheap-class.md)   
 [CGlobalHeap sınıfı](../../atl/reference/cglobalheap-class.md)   
 [CCRTHeap sınıfı](../../atl/reference/ccrtheap-class.md)   
 [CComHeap Sınıfı](../../atl/reference/ccomheap-class.md)
