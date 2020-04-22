---
title: CStringData Sınıfı
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
ms.openlocfilehash: f14f1d9c269f06099bd224f582de1f55da33ff0f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81746845"
---
# <a name="cstringdata-class"></a>CStringData Sınıfı

Bu sınıf bir dize nesnesinin verilerini temsil eder.

## <a name="syntax"></a>Sözdizimi

```
struct CStringData
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Addref](#addref)|Dize veri nesnesinin başvuru sayısını artırımına eder.|
|[Veri](#data)|Bir dize nesnesinin karakter verilerini alır.|
|[ıslocked](#islocked)|İlişkili dize nesnesinin arabelleği kilitli olup olmadığını belirler.|
|[ısshared](#isshared)|İlişkili dize nesnesinin arabelleği şu anda paylaşılır mı belirler.|
|[Kilit](#lock)|İlişkili dize nesnesinin arabelleği kilitler.|
|[Yayınla](#release)|Belirtilen dize nesnesini salar.|
|[Kilidini](#unlock)|İlişkili dize nesnesinin arabelleği açılır.|

### <a name="data-members"></a>Veri Üyeleri

|||
|-|-|
|[nAllocLength](#nalloclength)|S'de `XCHAR`ayrılan verilerin uzunluğu (null sonlandırma dahil değildir)|
|[nDataLength](#ndatalength)|Şu anda kullanılan `XCHAR`verilerin s'de uzunluğu (sonlandırma null dahil değildir)|
|[nRefs](#nrefs)|Nesnenin geçerli başvuru sayısı.|
|[pStringMgr](#pstringmgr)|Bu dize nesnesinin dize yöneticisine bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf yalnızca özel dize yöneticileri uygulayan geliştiriciler tarafından kullanılmalıdır. Özel dize yöneticileri hakkında daha fazla bilgi için Memory [Management ve CStringT'e](../../atl-mfc-shared/memory-management-with-cstringt.md) bakın

Bu sınıf, [CStringT,](../../atl-mfc-shared/reference/cstringt-class.md) [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)veya [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) nesneleri gibi daha yüksek bir dize nesnesi ile ilişkili çeşitli bilgi ve veri türlerini kapsüller. Her yüksek dize nesnesi, birden çok dize nesnesinin aynı dize veri nesnesini işaret etmesine izin veren ilişkili `CStringData` nesneye bir işaretçi içerir. Bu ilişki`nRefs` `CStringData` nesnenin başvuru sayısı ( ) ile temsil edilir.

> [!NOTE]
> Bazı durumlarda, bir dize `CFixedString`türü (gibi) birden fazla yüksek dize nesnesi ile bir dize veri nesnesi paylaşmaz. Bu konuda daha fazla bilgi için [Bellek Yönetimi ve CStringT'e](../../atl-mfc-shared/memory-management-with-cstringt.md)bakın.

Bu veriler şu verilerden oluşur:

- Dize bellek yöneticisi (tip [IAtlStringMgr).](../../atl-mfc-shared/reference/iatlstringmgr-class.md)

- Dizenin geçerli uzunluğu [(nDataLength).](#ndatalength)

- Dize ayrılan uzunluk [(nAllocLength)](#nalloclength) Performans nedenleriyle, bu geçerli dize uzunluğundan farklı olabilir

- Nesnenin `CStringData` geçerli başvuru sayısı [(nRefs).](#nrefs) Bu değer, aynı `CStringData` nesneyi paylaşan kaç dize nesnesinin olduğunu belirlemede kullanılır.

- Dize gerçek karakter arabelleği ( [veri).](#data)

   > [!NOTE]
   > Dize nesnesinin gerçek karakter arabelleği dize yöneticisi tarafından ayrılır `CStringData` ve nesneye eklenir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpstr.h

## <a name="cstringdataaddref"></a><a name="addref"></a>CStringData::Addref

Dize nesnesinin başvuru sayısını artırımına eder.

```cpp
void AddRef() throw();
```

### <a name="remarks"></a>Açıklamalar

Dize nesnesinin başvuru sayısını artırımına eder.

> [!NOTE]
> Negatif bir sayı dize arabelleği kilitli olduğunu gösterir, çünkü negatif bir başvuru sayısı ile bir dize bu yöntemi aramayın.

## <a name="cstringdatadata"></a><a name="data"></a>CStringData::data

Bir dize nesnesinin karakter arabelleği için bir işaretçi döndürür.

```cpp
void* data() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dize nesnesinin karakter arabelleği için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İlişkili dize nesnesinin geçerli karakter arabelleği döndürmek için bu işlevi çağırın.

> [!NOTE]
> Bu arabellek `CStringData` nesne tarafından değil, gerektiğinde dize yöneticisi tarafından tahsis edilir. Tahsis edildiğinde, arabellek dize veri nesnesine eklenir.

## <a name="cstringdataislocked"></a><a name="islocked"></a>CStringData::Kilitli

Karakter arabelleği kilitli olup olmadığını belirler.

```
bool IsLocked() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Arabellek kilitliyse TRUE döndürür; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Dize nesnesinin karakter arabelleği şu anda kilitli olup olmadığını belirlemek için bu işlevi arayın.

## <a name="cstringdataisshared"></a><a name="isshared"></a>CStringData::Paylaşılan

Karakter arabelleği paylaşılır mı belirler.

```
bool IsShared() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Arabellek paylaşılırsa TRUE döndürür; aksi takdirde YANLIŞ.

### <a name="remarks"></a>Açıklamalar

Bir dize veri nesnesinin karakter arabelleği şu anda birden çok dize nesneleri arasında paylaşılır olup olmadığını belirlemek için bu işlevi arayın.

## <a name="cstringdatalock"></a><a name="lock"></a>CStringData::Kilitle

İlişkili dize nesnesinin karakter arabelleği kilitler.

```cpp
void Lock() throw();
```

### <a name="remarks"></a>Açıklamalar

Dize veri nesnesinin karakter arabelleği kilitlemek için bu işlevi arayın. Karakter arabelleği doğrudan erişim geliştirici tarafından gerekli olduğunda kilitleme ve kilidini açma kullanılır. Kilitleme iyi bir örnek [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) yöntemleri `CSimpleStringT`ile gösterilmiştir.

> [!NOTE]
> Bir karakter arabelleği yalnızca arabellek daha yüksek dize nesneleri arasında paylaşılmazken kilitlenebilir.

## <a name="cstringdatanalloclength"></a><a name="nalloclength"></a>CStringData::nAllocLength

Ayrılan karakter arabelleği uzunluğu.

```
int nAllocLength;
```

### <a name="remarks"></a>Açıklamalar

Ayrılan veri arabelleği uzunluğunu `XCHAR`s'de depolar (null sonlandırma dahil değildir).

## <a name="cstringdatandatalength"></a><a name="ndatalength"></a>CStringData::nDataLength

Dize nesnesinin geçerli uzunluğu.

```
int nDataLength;
```

### <a name="remarks"></a>Açıklamalar

Şu anda kullanılan verilerin `XCHAR`uzunluğunu s olarak depolar (null sonlandırma dahil değildir).

## <a name="cstringdatanrefs"></a><a name="nrefs"></a>CStringData::nRefs

Dize veri nesnesinin başvuru sayısı.

```
long nRefs;
```

### <a name="remarks"></a>Açıklamalar

Dize veri nesnesinin başvuru sayısını depolar. Bu sayı, dize veri nesnesi ile ilişkili daha yüksek dize nesnelerinin sayısını gösterir. Negatif değer, dize veri nesnesinin şu anda kilitli olduğunu gösterir.

## <a name="cstringdatapstringmgr"></a><a name="pstringmgr"></a>CStringData::pStringMgr

İlişkili dize nesnesinin bellek yöneticisi.

```
IAtlStringMgr* pStringMgr;
```

### <a name="remarks"></a>Açıklamalar

İlişkili dize nesnesinin bellek yöneticisini depolar. Bellek yöneticileri ve dizeleri hakkında daha fazla bilgi için Bellek [Yönetimi ve CStringT'e](../../atl-mfc-shared/memory-management-with-cstringt.md)bakın.

## <a name="cstringdatarelease"></a><a name="release"></a>CStringData::Sürüm

Dize veri nesnesinin başvuru sayısını eriter.

```cpp
void Release() throw();
```

### <a name="remarks"></a>Açıklamalar

Başvuru sayısını azalmak için bu işlevi çağırın ve başvuru sayısı sıfıra ulaştığında yapıyı `CStringData` serbest çeştirin. Bu genellikle bir dize nesnesi silindiğinde yapılır ve bu nedenle artık dize veri nesnesine başvurması gerekmez.

Örneğin, aşağıdaki kod ile `CStringData::Release` `str1`ilişkili dize veri nesnesi için çağırır:

[!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]

## <a name="cstringdataunlock"></a><a name="unlock"></a>CStringData::Kilidini Aç

İlişkili dize nesnesinin karakter arabelleği kilidini açar.

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>Açıklamalar

Dize veri nesnesinin karakter arabelleği kilidini açmak için bu işlevi arayın. Bir arabellek kilidi açıldıktan sonra, paylaşılabilir ve referans sayılır olabilir.

> [!NOTE]
> Yapılacak `Lock` her çağrı, `Unlock`''ye karşılık gelen bir çağrıyla eşlenmelidir.

Geliştirici dize verilerinin paylaşılmamasını sağlaması gerektiğinde kilitleme ve kilit açma kullanılır. Kilitleme iyi bir örnek [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) yöntemleri `CSimpleStringT`ile gösterilmiştir.

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC Paylaşılan Sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
