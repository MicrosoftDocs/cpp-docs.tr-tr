---
description: 'Daha fazla bilgi edinin: CStringData sınıfı'
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
ms.openlocfilehash: 74bf3563cb5dca506498ceef05ddc84f13c44f41
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166596"
---
# <a name="cstringdata-class"></a>CStringData sınıfı

Bu sınıf, bir dize nesnesinin verilerini temsil eder.

## <a name="syntax"></a>Syntax

```
struct CStringData
```

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|Ad|Açıklama|
|-|-|
|[AddRef](#addref)|Dize veri nesnesinin başvuru sayısını artırır.|
|[data](#data)|Bir dize nesnesinin karakter verisini alır.|
|[IsLocked](#islocked)|İlişkili dize nesnesinin arabelleğinin kilitli olup olmadığını belirler.|
|[IsShared](#isshared)|İlişkili dize nesnesinin arabelleğinin Şu anda paylaşılıp paylaşılamayacağını belirler.|
|[Kilitle](#lock)|İlişkili dize nesnesinin arabelleğini kilitler.|
|[Sürüm](#release)|Belirtilen dize nesnesini serbest bırakır.|
|[Kaldırın](#unlock)|İlişkili dize nesnesinin arabelleğini kaldırır.|

### <a name="data-members"></a>Veri üyeleri

|Ad|Açıklama|
|-|-|
|[nAllocLength](#nalloclength)|İçindeki ayrılmış verilerin uzunluğu `XCHAR` (Sonlandırıcı null değeri dahil değil)|
|[nDataLength](#ndatalength)|Şu anda kullanılan verilerin uzunluğu `XCHAR` (Sonlandırıcı null değeri dahil değil)|
|[nRefs](#nrefs)|Nesnenin geçerli başvuru sayısı.|
|[pStringMgr](#pstringmgr)|Bu dize nesnesinin dize yöneticisine yönelik bir işaretçi.|

## <a name="remarks"></a>Açıklamalar

Bu sınıf yalnızca özel dize yöneticileri uygulayan geliştiriciler tarafından kullanılmalıdır. Özel dize yöneticileri hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md)

Bu sınıf, [CStringT](../../atl-mfc-shared/reference/cstringt-class.md), [CSimpleStringT](../../atl-mfc-shared/reference/csimplestringt-class.md)veya [CFixedStringT](../../atl-mfc-shared/reference/cfixedstringt-class.md) nesneleri gibi daha yüksek bir dize nesnesiyle ilişkili çeşitli bilgi türlerini ve verileri kapsar. Her iki dize nesnesi, ilişkili nesnesine bir işaretçi içerir `CStringData` ve birden çok dize nesnesinin aynı dize veri nesnesine işaret kurmasına izin verir. Bu ilişki, nesnesinin başvuru sayısı () ile temsil edilir `nRefs` `CStringData` .

> [!NOTE]
> Belirli durumlarda, bir dize türü (gibi) birden `CFixedString` çok daha yüksek dize nesnesiyle bir dize veri nesnesi paylaşmaz. Bunun hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

Bu veriler şunlardan oluşur:

- Dizenin bellek Yöneticisi ( [IAtlStringMgr](../../atl-mfc-shared/reference/iatlstringmgr-class.md)türü).

- Dizenin geçerli uzunluğu ( [nDataLength](#ndatalength)).

- Dizenin ayrılan uzunluğu ( [nAllocLength](#nalloclength)). Performans nedenleriyle bu, geçerli dize uzunluğundan farklı olabilir

- Nesnenin geçerli başvuru sayısı ( [nRefs](#nrefs)) `CStringData` . Bu değer, aynı nesneyi kaç tane dize nesnesinin paylaştığını belirlemek için kullanılır `CStringData` .

- Dizenin gerçek karakter arabelleği ( [veri](#data)).

   > [!NOTE]
   > Dize nesnesinin gerçek karakter arabelleği, dize Yöneticisi tarafından ayrılır ve `CStringData` nesnesine eklenir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpstr. h

## <a name="cstringdataaddref"></a><a name="addref"></a> CStringData:: AddRef

Dize nesnesinin başvuru sayısını artırır.

```cpp
void AddRef() throw();
```

### <a name="remarks"></a>Açıklamalar

Dize nesnesinin başvuru sayısını artırır.

> [!NOTE]
> Negatif bir sayı dize arabelleğinin kilitli olduğunu gösterdiği için, bu yöntemi negatif başvuru sayısı olan bir dize üzerinde çağırmayın.

## <a name="cstringdatadata"></a><a name="data"></a> CStringData::d ata

Dize nesnesinin karakter arabelleğine yönelik bir işaretçi döndürür.

```cpp
void* data() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dize nesnesinin karakter arabelleğine yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

İlişkili dize nesnesinin geçerli karakter arabelleğini döndürmek için bu işlevi çağırın.

> [!NOTE]
> Bu arabellek nesne tarafından, `CStringData` ancak gerektiğinde dize Yöneticisi tarafından ayrılmaz. Ayrıldığınızda, arabellek dize veri nesnesine eklenir.

## <a name="cstringdataislocked"></a><a name="islocked"></a> CStringData:: ıskilitlendi

Karakter arabelleğinin kilitlenip kilitlenmediğini belirler.

```
bool IsLocked() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Arabellek kilitliyse doğru döndürür; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bir dize nesnesinin karakter arabelleğinin Şu anda kilitli olup olmadığını öğrenmek için bu işlevi çağırın.

## <a name="cstringdataisshared"></a><a name="isshared"></a> CStringData:: IsShared

Karakter arabelleğinin paylaşılıp paylaşılamayacağını belirler.

```
bool IsShared() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Arabellek paylaşılmışsa, doğru döndürür; Aksi halde yanlış.

### <a name="remarks"></a>Açıklamalar

Bir dize veri nesnesinin karakter arabelleğinin, şu anda birden çok dize nesnesi arasında paylaşılıp paylaşılmadığını öğrenmek için bu işlevi çağırın.

## <a name="cstringdatalock"></a><a name="lock"></a> CStringData:: Lock

İlişkili dize nesnesinin karakter arabelleğini kilitler.

```cpp
void Lock() throw();
```

### <a name="remarks"></a>Açıklamalar

Dize veri nesnesinin karakter arabelleğini kilitlemek için bu işlevi çağırın. Geliştirici için karakter arabelleğine doğrudan erişim gerektiğinde kilitleme ve kilit açma kullanılır. Kilitleme için iyi bir örnek, [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) yöntemleri tarafından gösterilmiştir `CSimpleStringT` .

> [!NOTE]
> Bir karakter arabelleği yalnızca arabellek daha yüksek dize nesneleri arasında paylaşılmaması durumunda kilitlenebilir.

## <a name="cstringdatanalloclength"></a><a name="nalloclength"></a> CStringData:: nAllocLength

Ayrılan karakter arabelleğinin uzunluğu.

```
int nAllocLength;
```

### <a name="remarks"></a>Açıklamalar

Ayrılan veri arabelleğinin uzunluğunu `XCHAR` (Sonlandırıcı null değeri dahil değil) depolar.

## <a name="cstringdatandatalength"></a><a name="ndatalength"></a> CStringData:: nDataLength

Dize nesnesinin geçerli uzunluğu.

```
int nDataLength;
```

### <a name="remarks"></a>Açıklamalar

Kullanılmakta olan verilerin uzunluğunu depolar `XCHAR` (Sonlandırıcı null dahil değil).

## <a name="cstringdatanrefs"></a><a name="nrefs"></a> CStringData:: nRefs

Dize veri nesnesinin başvuru sayısı.

```
long nRefs;
```

### <a name="remarks"></a>Açıklamalar

Dize veri nesnesinin başvuru sayısını depolar. Bu sayı, dize veri nesnesiyle ilişkili daha yüksek dize nesnelerinin sayısını gösterir. Negatif bir değer, dize veri nesnesinin Şu anda kilitli olduğunu gösterir.

## <a name="cstringdatapstringmgr"></a><a name="pstringmgr"></a> CStringData::p StringMgr

İlişkili dize nesnesinin bellek Yöneticisi.

```
IAtlStringMgr* pStringMgr;
```

### <a name="remarks"></a>Açıklamalar

İlişkili dize nesnesi için bellek yöneticisini depolar. Bellek yöneticileri ve dizeler hakkında daha fazla bilgi için bkz. [bellek yönetimi ve CStringT](../../atl-mfc-shared/memory-management-with-cstringt.md).

## <a name="cstringdatarelease"></a><a name="release"></a> CStringData:: Release

Dize veri nesnesinin başvuru sayısını azaltır.

```cpp
void Release() throw();
```

### <a name="remarks"></a>Açıklamalar

Başvuru sayısını azaltmak için bu işlevi çağırın, `CStringData` başvuru sayısı sıfır olursa yapıyı serbest bırakır. Bu genellikle bir dize nesnesi silindiğinde ve bu nedenle dize veri nesnesine başvurulması gerekmiyorsa yapılır.

Örneğin, aşağıdaki kod `CStringData::Release` ile ilişkili dize veri nesnesi için çağrı yapılır `str1` :

[!code-cpp[NVC_ATLMFC_Utilities#104](../../atl-mfc-shared/codesnippet/cpp/cstringdata-class_1.cpp)]

## <a name="cstringdataunlock"></a><a name="unlock"></a> CStringData:: unlock

İlişkili dize nesnesinin karakter arabelleğini kaldırır.

```cpp
void Unlock() throw();
```

### <a name="remarks"></a>Açıklamalar

Dize veri nesnesinin karakter arabelleğinin kilidini açmak için bu işlevi çağırın. Bir arabelleğin kilidi açıldıktan sonra paylaşılabilir ve başvuru sayılabilir.

> [!NOTE]
> Her çağrısının `Lock` öğesine karşılık gelen çağrısıyla eşleşmesi gerekir `Unlock` .

Geliştirici dize verilerinin paylaşılmadığından emin olması gerektiğinde kilitleme ve kilit açma kullanılır. Kilitleme için iyi bir örnek, [LockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#lockbuffer) ve [UnlockBuffer](../../atl-mfc-shared/reference/csimplestringt-class.md#unlockbuffer) yöntemleri tarafından gösterilmiştir `CSimpleStringT` .

## <a name="see-also"></a>Ayrıca bkz.

[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[ATL/MFC paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md)
