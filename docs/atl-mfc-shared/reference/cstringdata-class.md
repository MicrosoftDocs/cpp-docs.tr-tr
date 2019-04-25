---
title: CStringData sınıfı
ms.date: 11/04/2016
f1_keywords:
- CStringData
- ATLSIMPSTR/ATL::CStringData
- ATLSIMPSTR/ATL::AddRef
- ATLSIMPSTR/ATL::data
- ATLSIMPSTR/ATL::IsLocked
- ATLSIMPSTR/ATL::IsShared
- ATLSIMPSTR/ATL::Lock
- ATLSIMPSTR/ATL::Release
- ATLSIMPSTR/ATL::Unlock
- ATLSIMPSTR/ATL::nAllocLength
- ATLSIMPSTR/ATL::nDataLength
- ATLSIMPSTR/ATL::nRefs
- ATLSIMPSTR/ATL::pStringMgr
helpviewer_keywords:
- CStringData class
- shared classes, CStringData
ms.assetid: 4e31b5ca-3dbe-4fd5-b692-8211fbfb2593
ms.openlocfilehash: 5977d26cade89f2e70453d5184323958e99e54c4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62198143"
---
# <a name="cstringdata-class"></a>CStringData sınıfı

Bu sınıf, bir dize nesnesi verilerini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
struct CStringData
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[AddRef](#addref)|Dize veri nesnesine başvuru sayısını artırır.|
|[Veri](#data)|Dizenin başlangıcının karakter verileri alır.|
|[IsLocked](#islocked)|Arabellek ilişkili dize nesnenin kilitli olduğunu belirler.|
|[IsShared](#isshared)|Arabelleğin ilişkilendirilmiş dize nesnesi şu anda paylaşılan belirler.|
|[Kilit](#lock)|İlişkilendirilmiş dize nesnesine arabelleğinin kilitler.|
|[Sürüm](#release)|Belirtilen dize nesnesine serbest bırakır.|
|[Kilit açma](#unlock)|Arabellek ilişkili dize nesnenin kilidini açar.|

### <a name="data-members"></a>Veri üyeleri

|||
|-|-|
|[nAllocLength](#nalloclength)|Ayrılmış veri uzunluğu `XCHAR`s (dahil değil Sonlandırıcı null)|
|[nDataLength](#ndatalength)|Şu anda kullanılan veri uzunluğu `XCHAR`s (dahil değil Sonlandırıcı null)|
|[nRefs](#nrefs)|Nesnenin geçerli başvuru sayısı.|
|[pStringMgr](#pstringmgr)|Bu dize nesnenin dize Yöneticisi için bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf yalnızca özel bir dize yöneticileri uygulama geliştiriciler tarafından kullanılması gerekir. Özel dize yöneticileri hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)

Bu sınıf çeşitli türlerde bilgiler ve daha yüksek bir dize nesnesi ile ilişkilendirilmiş veri kapsülleyen [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md), veya [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) nesneleri. Her daha yüksek bir dize nesnesi, ilişkili bir işaretçi içeren `CStringData` aynı dize veri nesnesine işaret edecek şekilde birden çok dize nesneleri sağlayan nesne. Bu ilişki başvuru sayısı tarafından temsil edilen (`nRefs`), `CStringData` nesne.

> [!NOTE]
>  Bazı durumlarda, bir dize türü (gibi `CFixedString`) bir dize veri nesnesi ile birden fazla yüksek dize nesnesi paylaşmaz. Bunun hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

Bu veriler, şunlardan oluşur:

- Bellek Yöneticisi (tür [Iatlstringmgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)) dizesi.

- Geçerli uzunluğu ( [nDataLength](#ndatalength)) dizesi.

- Ayrılan uzunluğu ( [nAllocLength](#nalloclength)) dizesi. Performansla ilgili nedenlerden dolayı bu geçerli bir dize uzunluğu farklı olabilir

- Geçerli bir başvuru sayısı ( [nRefs](#nrefs)), `CStringData` nesne. Bu değer, kaç dize nesnelerinin aynı paylaşıyor saptanırken kullanılır `CStringData` nesne.

- Gerçek karakter arabelleği ( [veri](#data)) dizesi.

   > [!NOTE]
   > Dize nesnesi gerçek karakter arabelleği dize Yöneticisi tarafından ayrılan ve eklenen `CStringData` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpstr.h

##  <a name="addref"></a>  CStringData::AddRef

Dize nesnesine başvuru sayısını artırır.

```
void AddRef() throw();
```

### <a name="remarks"></a>Açıklamalar

Dize nesnesine başvuru sayısını artırır.

> [!NOTE]
>  Negatif bir sayı dize arabelleğindeki kilitli olduğunu gösterir. bu yana bir dize bir eksi başvuru sayısı üzerinde bu yöntemi çağırmayın.

##  <a name="data"></a>  CStringData::data

Dizenin başlangıcının karakter arabelleği için bir işaretçi döndürür.

```
void* data() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Karakter arabelleği dize nesnesine bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Geçerli işlemi yetersiz karakter arabelleği ilişkili dize nesnesinin döndürmek için bu işlevi çağırın.

> [!NOTE]
>  Bu arabellek tarafından ayrılmamış `CStringData` nesne ancak gerektiğinde dize Yöneticisi tarafından. Ayrılan, arabellek dize veri nesnesine eklenir.

##  <a name="islocked"></a>  CStringData::IsLocked

Karakter arabelleği kilitli olduğunu belirler.

```
bool IsLocked() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Arabellek kilitliyse, TRUE döndürür; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Dizenin başlangıcının karakter arabelleği şu anda kilitli olduğunu belirlemek için bu işlevi çağırın.

##  <a name="isshared"></a>  CStringData::IsShared

Karakter arabelleği paylaşılıp paylaşılmadığını belirler.

```
bool IsShared() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Arabellek paylaşılıp paylaşılmadığını TRUE döndürür; Aksi durumda FALSE.

### <a name="remarks"></a>Açıklamalar

Dize veri nesnesinin karakter arabelleği şu anda birden çok dize nesneler arasında paylaşılıp paylaşılmadığını belirlemek için bu işlevi çağırın.

##  <a name="lock"></a>  CStringData::Lock

Karakter arabelleği ilişkili dize nesnesinin kilitler.

```
void Lock() throw();
```

### <a name="remarks"></a>Açıklamalar

Dize veri nesnesinin karakter arabelleği kilitlemek için bu işlevi çağırın. Kilitleme ve kilidini açma işlemi yetersiz karakter arabelleği doğrudan erişim geliştirici tarafından gerektiğinde kullanılır. Kilitleme iyi bir örnek tarafından gösterilen [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) yöntemlerinin `CSimpleStringT`.

> [!NOTE]
>  Arabellek dize nesneler arasında paylaşılan değil, bir karakter arabelleği yalnızca kilitlenebilir.

##  <a name="nalloclength"></a>  CStringData::nAllocLength

Ayrılmış karakter arabelleği uzunluğu.

```
int nAllocLength;
```

### <a name="remarks"></a>Açıklamalar

Ayrılmış veri arabellek uzunluğunu saklar `XCHAR`s (dahil değil Sonlandırıcı null).

##  <a name="ndatalength"></a>  CStringData::nDataLength

Dize nesnesi geçerli uzunluğu.

```
int nDataLength;
```

### <a name="remarks"></a>Açıklamalar

Şu anda kullanılan verileri uzunluğunu saklar `XCHAR`s (dahil değil Sonlandırıcı null).

##  <a name="nrefs"></a>  CStringData::nRefs

Dize veri nesnesine başvuru sayısı.

```
long nRefs;
```

### <a name="remarks"></a>Açıklamalar

Dize veri nesnesine başvuru sayısını depolar. Bu sayı, dize veri nesnesi ile ilişkili olan daha yüksek dize nesne sayısını gösterir. Dize veri nesnesi şu anda kilitli negatif bir değer belirtir.

##  <a name="pstringmgr"></a>  CStringData::pStringMgr

Bellek Yöneticisi, ilişkili dize nesnesi.

```
IAtlStringMgr* pStringMgr;
```

### <a name="remarks"></a>Açıklamalar

İlişkilendirilmiş dize nesnesi için bellek yöneticisi depolar. Bellek yöneticilerini ve dizeleri hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

##  <a name="release"></a>  CStringData::Release

Dize veri nesnesinin başvuru sayısını azaltır.

```
void Release() throw();
```

### <a name="remarks"></a>Açıklamalar

Başvuru sayısını azaltmak için bu işlevi çağırın boşaltma `CStringData` başvuru sayısı sıfır olursa yapılandırın. Bu, genellikle bir dize nesnesi silinir ve bu nedenle dize veri nesnesine başvuru artık ihtiyaç olduğunda gerçekleştirilir.

Örneğin, aşağıdaki kodu çağıracak `CStringData::Release` dize veri nesnesi ile ilişkili `str1`:

[!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]

##  <a name="unlock"></a>  CStringData::Unlock

Karakter arabelleği ilişkili dize nesnenin kilidini açar.

```
void Unlock() throw();
```

### <a name="remarks"></a>Açıklamalar

Dize veri nesnesinin karakter arabelleği kilidini açmak için bu işlevi çağırın. Arabellek açılmış paylaşılabilir ve başvuru sayılan.

> [!NOTE]
>  Her çağrı `Lock` yapılan çağrı ile eşleştirilmesi gerekir `Unlock`.

Geliştirici dize Paylaşılmaması gerektiğini emin olmanız gerekir, kilitleme ve kilidini açma kullanılır. Kilitleme iyi bir örnek tarafından gösterilen [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) yöntemlerinin `CSimpleStringT`.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
