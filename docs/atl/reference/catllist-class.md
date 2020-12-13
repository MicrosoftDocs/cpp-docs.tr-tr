---
description: 'Daha fazla bilgi edinin: CAtlList sınıfı'
title: CAtlList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlList
- ATLCOLL/ATL::CAtlList
- ATLCOLL/ATL::CAtlList::INARGTYPE
- ATLCOLL/ATL::CAtlList::CAtlList
- ATLCOLL/ATL::CAtlList::AddHead
- ATLCOLL/ATL::CAtlList::AddHeadList
- ATLCOLL/ATL::CAtlList::AddTail
- ATLCOLL/ATL::CAtlList::AddTailList
- ATLCOLL/ATL::CAtlList::AssertValid
- ATLCOLL/ATL::CAtlList::Find
- ATLCOLL/ATL::CAtlList::FindIndex
- ATLCOLL/ATL::CAtlList::GetAt
- ATLCOLL/ATL::CAtlList::GetCount
- ATLCOLL/ATL::CAtlList::GetHead
- ATLCOLL/ATL::CAtlList::GetHeadPosition
- ATLCOLL/ATL::CAtlList::GetNext
- ATLCOLL/ATL::CAtlList::GetPrev
- ATLCOLL/ATL::CAtlList::GetTail
- ATLCOLL/ATL::CAtlList::GetTailPosition
- ATLCOLL/ATL::CAtlList::InsertAfter
- ATLCOLL/ATL::CAtlList::InsertBefore
- ATLCOLL/ATL::CAtlList::IsEmpty
- ATLCOLL/ATL::CAtlList::MoveToHead
- ATLCOLL/ATL::CAtlList::MoveToTail
- ATLCOLL/ATL::CAtlList::RemoveAll
- ATLCOLL/ATL::CAtlList::RemoveAt
- ATLCOLL/ATL::CAtlList::RemoveHead
- ATLCOLL/ATL::CAtlList::RemoveHeadNoReturn
- ATLCOLL/ATL::CAtlList::RemoveTail
- ATLCOLL/ATL::CAtlList::RemoveTailNoReturn
- ATLCOLL/ATL::CAtlList::SetAt
- ATLCOLL/ATL::CAtlList::SwapElements
helpviewer_keywords:
- CAtlList class
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
ms.openlocfilehash: 79ad0ab8e1a3cd1fb528776fa868aa806746b9da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97147361"
---
# <a name="catllist-class"></a>CAtlList sınıfı

Bu sınıf, bir liste nesnesi oluşturmak ve yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template<typename E, class ETraits = CElementTraits<E>>
class CAtlList
```

### <a name="parameters"></a>Parametreler

*E*<br/>
Öğe türü.

*Oy*<br/>
Öğeleri kopyalamak veya taşımak için kullanılan kod. Daha fazla ayrıntı için bkz. [Celementnitelikler sınıfı](../../atl/reference/celementtraits-class.md) .

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CAtlList:: ıNARGTYPE](#inargtype)||

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlList:: CAtlList](#catllist)|Oluşturucu.|
|[CAtlList:: ~ CAtlList](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlList:: AddHead](#addhead)|Listenin baş bir öğesini bir öğe eklemek için bu yöntemi çağırın.|
|[CAtlList:: AddHeadList](#addheadlist)|Listenin baş bir listesini varolan bir listeyi eklemek için bu yöntemi çağırın.|
|[CAtlList:: AddTail](#addtail)|Bu listenin sonuna bir öğe eklemek için bu yöntemi çağırın.|
|[CAtlList:: Addbir List](#addtaillist)|Bu listenin sonuna var olan bir liste eklemek için bu yöntemi çağırın.|
|[CAtlList:: AssertValid](#assertvalid)|Listenin geçerli olduğunu doğrulamak için bu yöntemi çağırın.|
|[CAtlList:: Find](#find)|Belirtilen öğe için listeyi aramak üzere bu yöntemi çağırın.|
|[CAtlList:: FindIndex](#findindex)|Bir dizin değeri verilen bir öğenin konumunu almak için bu yöntemi çağırın.|
|[CAtlList:: GetAt](#getat)|Öğeyi listedeki belirli bir konumda döndürmek için bu yöntemi çağırın.|
|[CAtlList:: GetCount](#getcount)|Listedeki nesne sayısını döndürmek için bu yöntemi çağırın.|
|[CAtlList:: GetHead](#gethead)|Listenin baş tarafında öğesini döndürmek için bu yöntemi çağırın.|
|[CAtlList:: GetHeadPosition](#getheadposition)|Listenin baş konumunu almak için bu yöntemi çağırın.|
|[CAtlList:: GetNext](#getnext)|Listeden sonraki öğeyi döndürmek için bu yöntemi çağırın.|
|[CAtlList:: Getöncekini](#getprev)|Önceki öğeyi listeden döndürmek için bu yöntemi çağırın.|
|[CAtlList:: GetTail](#gettail)|Öğeyi listenin sonunda döndürmek için bu yöntemi çağırın.|
|[CAtlList:: Getbir Position](#gettailposition)|Listenin tail konumunu almak için bu yöntemi çağırın.|
|[CAtlList:: InsertAfter](#insertafter)|Belirtilen konumdan sonra listeye yeni bir öğe eklemek için bu yöntemi çağırın.|
|[CAtlList:: InsertBefore](#insertbefore)|Belirtilen konumdan önce listeye yeni bir öğe eklemek için bu yöntemi çağırın.|
|[CAtlList:: IsEmpty](#isempty)|Listenin boş olup olmadığını anlamak için bu yöntemi çağırın.|
|[CAtlList:: MoveToHead](#movetohead)|Belirtilen öğeyi listenin baş öğesine taşımak için bu yöntemi çağırın.|
|[CAtlList:: MoveToTail](#movetotail)|Belirtilen öğeyi listenin kuyruğu 'na taşımak için bu yöntemi çağırın.|
|[CAtlList:: RemoveAll](#removeall)|Tüm öğeleri listeden kaldırmak için bu yöntemi çağırın.|
|[CAtlList:: RemoveAt](#removeat)|Listeden tek bir öğeyi kaldırmak için bu yöntemi çağırın.|
|[CAtlList:: RemoveHead](#removehead)|Listenin başında öğesini kaldırmak için bu yöntemi çağırın.|
|[CAtlList:: RemoveHeadNoReturn](#removeheadnoreturn)|Bir değer döndürmeden listenin baş tarafındaki öğeyi kaldırmak için bu yöntemi çağırın.|
|[CAtlList:: RemoveTail](#removetail)|Listenin sırasındaki öğesini kaldırmak için bu yöntemi çağırın.|
|[CAtlList:: Removebir noreturn](#removetailnoreturn)|Bir değer döndürmeden listenin sırasındaki öğeyi kaldırmak için bu yöntemi çağırın.|
|[CAtlList:: SetAt](#setat)|Bu yöntemi, listenin belirli bir konumundaki öğesinin değerini ayarlamak için çağırın.|
|[CAtlList:: SwapElements](#swapelements)|Listedeki öğeleri değiştirmek için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CAtlList`Sınıfı, ardışık olarak veya değere göre erişilebilen, benzersiz olmayan nesnelerin sıralı listesini destekler. `CAtlList` listeler, benzer bağlantılı listeler gibi davranır. Her listede bir baş ve kuyruk bulunur ve yeni öğeler (veya bazı durumlarda listeler) listenin sonuna veya belirli öğelerden önce ya da sonra eklenebilir.

`CAtlList`Yöntemlerin çoğu bir konum değeri kullanır. Bu değer, öğelerin depolandığı gerçek bellek konumuna başvurmak ve doğrudan hesaplanmaması ya da tahmin olmaması gereken yöntemler tarafından kullanılır. Listedeki *n*. öğeye erişmeniz gerekiyorsa, [CAtlList:: FindIndex](#findindex) yöntemi belirli bir dizin için karşılık gelen konum değerini döndürür. [CAtlList:: GetNext](#getnext) ve [CAtlList:: getöncekini](#getprev) yöntemleri, listedeki nesneler arasında yinelemek için kullanılabilir.

ATL ile kullanılabilen koleksiyon sınıfları hakkında daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="catllistaddhead"></a><a name="addhead"></a> CAtlList:: AddHead

Listenin baş bir öğesini bir öğe eklemek için bu yöntemi çağırın.

```cpp
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*dosyalarında*<br/>
Yeni öğe.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğenin konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm kullanılırsa, kopya Oluşturucusu yerine varsayılan Oluşturucusu kullanılarak boş bir öğe oluşturulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]

## <a name="catllistaddheadlist"></a><a name="addheadlist"></a> CAtlList:: AddHeadList

Listenin baş bir listesini varolan bir listeyi eklemek için bu yöntemi çağırın.

```cpp
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Parametreler

*plNew*<br/>
Eklenecek liste.

### <a name="remarks"></a>Açıklamalar

*PlNew* tarafından işaret edilen liste, var olan listenin başına eklenir. Hata ayıklama yapılarında, *plNew* , null değerine eşitse bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]

## <a name="catllistaddtail"></a><a name="addtail"></a> CAtlList:: AddTail

Bu listenin sonuna bir öğe eklemek için bu yöntemi çağırın.

```cpp
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*dosyalarında*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğenin konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm kullanılırsa, kopya Oluşturucusu yerine varsayılan Oluşturucusu kullanılarak boş bir öğe oluşturulur. Öğesi, listenin sonuna eklenir ve bu nedenle artık kuyruk olur. Bu yöntem boş bir liste ile kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]

## <a name="catllistaddtaillist"></a><a name="addtaillist"></a> CAtlList:: Addbir List

Bu listenin sonuna var olan bir liste eklemek için bu yöntemi çağırın.

```cpp
void AddTailList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Parametreler

*plNew*<br/>
Eklenecek liste.

### <a name="remarks"></a>Açıklamalar

*PlNew* tarafından işaret edilen liste, liste nesnesindeki son öğeden (varsa) sonra eklenir. Bu nedenle, *plNew* listesindeki son öğe kuyruk haline gelir. Hata ayıklama yapılarında, *plNew* , null değerine eşitse bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]

## <a name="catllistassertvalid"></a><a name="assertvalid"></a> CAtlList:: AssertValid

Listenin geçerli olduğunu doğrulamak için bu yöntemi çağırın.

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, liste nesnesi geçerli değilse bir onaylama hatası oluşur. Geçerli olması için, boş bir listede hem baş hem de kuyruklu NULL değeri olmalı ve boş olmayan bir liste, geçerli adreslere işaret eden baş ve kuyruklu her ikisine de sahip olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]

## <a name="catllistcatllist"></a><a name="catllist"></a> CAtlList:: CAtlList

Oluşturucu.

```cpp
CAtlList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

Nesne için Oluşturucu `CAtlList` . Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarının bir ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]

## <a name="catllistcatllist"></a><a name="dtor"></a> CAtlList:: ~ CAtlList

Yok edicisi.

```cpp
~CAtlList() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm öğeleri listeden kaldırmak için [CAtlList:: RemoveAll](#removeall) öğesine yapılan bir çağrı dahil olmak üzere tüm ayrılmış kaynakları serbest bırakır.

Hata ayıklama yapılarında, listede çağrısından sonra hala bazı öğeler varsa, bir onaylama hatası oluşur `RemoveAll` .

## <a name="catllistfind"></a><a name="find"></a> CAtlList:: Find

Belirtilen öğe için listeyi aramak üzere bu yöntemi çağırın.

```cpp
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*dosyalarında*<br/>
Listede bulunan öğe.

*posStartAfter*<br/>
Arama için başlangıç konumu. Hiçbir değer belirtilmemişse, arama Head öğesiyle başlar.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa, öğenin konum değerini döndürür, aksi takdirde NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, liste nesnesi geçerli değilse veya *posStartAfter* değeri aralığın dışında olduğunda bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]

## <a name="catllistfindindex"></a><a name="findindex"></a> CAtlList:: FindIndex

Bir dizin değeri verilen bir öğenin konumunu almak için bu yöntemi çağırın.

```cpp
POSITION FindIndex(size_t iElement) const throw();
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Gerekli liste öğesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Karşılık gelen konum değerini döndürür veya *IElement* Aralık dışında olduğunda null değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, listedeki *n*. öğeye erişime izin veren belirli bir dizin değerine KARŞıLıK gelen konumu döndürür.

Hata ayıklama yapılarında, liste nesnesi geçerli değilse bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]

## <a name="catllistgetat"></a><a name="getat"></a> CAtlList:: GetAt

Öğeyi listedeki belirli bir konumda döndürmek için bu yöntemi çağırın.

```cpp
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Belirli bir öğeyi belirten konum değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğesinin öğesine veya kopyasına bir başvuru.

### <a name="remarks"></a>Açıklamalar

Liste ise, **`const`** `GetAt` öğesinin bir kopyasını döndürür. Bu yöntem, yöntemin yalnızca bir atama ifadesinin sağ tarafında kullanılmasını sağlar ve listenin değiştirilmesini önler.

Liste yoksa **`const`** , `GetAt` öğesine bir başvuru döndürür. Bu yöntem, bir atama ifadesinin her iki tarafında da kullanılmasına izin verir ve bu sayede liste girişlerinin değiştirilmesine izin verir.

Hata ayıklama yapılarında, *POS* null değerine eşitse bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList:: FindIndex](#findindex)örneğine bakın.

## <a name="catllistgetcount"></a><a name="getcount"></a> CAtlList:: GetCount

Listedeki nesne sayısını döndürmek için bu yöntemi çağırın.

```cpp
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki öğe sayısını döndürür.

### <a name="example"></a>Örnek

[CAtlList:: Find](#find)örneğine bakın.

## <a name="catllistgethead"></a><a name="gethead"></a> CAtlList:: GetHead

Listenin baş tarafında öğesini döndürmek için bu yöntemi çağırın.

```cpp
E& GetHead() throw();
const E& GetHead() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin başında öğesi veya bir kopyasına bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Liste ise **`const`** , listenin başında `GetHead` öğesinin bir kopyasını döndürür. Bu yöntem, yöntemin yalnızca bir atama ifadesinin sağ tarafında kullanılmasını sağlar ve listenin değiştirilmesini önler.

Liste yoksa **`const`** , `GetHead` listenin başında öğesine bir başvuru döndürür. Bu yöntem, bir atama ifadesinin her iki tarafında da kullanılmasına izin verir ve bu sayede liste girişlerinin değiştirilmesine izin verir.

Hata ayıklama yapılarında, listenin başı değeri NULL olduğunda bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList:: AddHead](#addhead)örneğine bakın.

## <a name="catllistgetheadposition"></a><a name="getheadposition"></a> CAtlList:: GetHeadPosition

Listenin baş konumunu almak için bu yöntemi çağırın.

```cpp
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin başında öğesine karşılık gelen konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Liste boşsa döndürülen değer NULL olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]

## <a name="catllistgetnext"></a><a name="getnext"></a> CAtlList:: GetNext

Listeden sonraki öğeyi döndürmek için bu yöntemi çağırın.

```cpp
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Önceki bir çağrı tarafından döndürülen bir konum değeri, `GetNext` [CAtlList:: GetHeadPosition](#getheadposition)veya diğer `CAtlList` Yöntem.

### <a name="return-value"></a>Dönüş Değeri

Liste ise **`const`** , `GetNext` listenin bir sonraki öğesinin bir kopyasını döndürür. Bu yöntem, yöntemin yalnızca bir atama ifadesinin sağ tarafında kullanılmasını sağlar ve listenin değiştirilmesini önler.

Liste yoksa **`const`** , `GetNext` listenin bir sonraki öğesine bir başvuru döndürür. Bu yöntem, bir atama ifadesinin her iki tarafında da kullanılmasına izin verir ve bu sayede liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

POZISYON sayacı, *POS*, listedeki bir sonraki öğeyi işaret etmek üzere güncelleştirilir veya daha fazla öğe yoksa null olur. Hata ayıklama yapılarında, *POS* null değerine eşitse bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList:: GetHeadPosition](#getheadposition)örneğine bakın.

## <a name="catllistgetprev"></a><a name="getprev"></a> CAtlList:: Getöncekini

Önceki öğeyi listeden döndürmek için bu yöntemi çağırın.

```cpp
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Önceki bir çağrı tarafından döndürülen bir konum değeri, `GetPrev` [CAtlList:: getwebcontrol Position](#gettailposition)veya diğer `CAtlList` Yöntem.

### <a name="return-value"></a>Dönüş Değeri

Liste ise **`const`** , listenin bir `GetPrev` öğesinin bir kopyasını döndürür. Bu yöntem, yöntemin yalnızca bir atama ifadesinin sağ tarafında kullanılmasını sağlar ve listenin değiştirilmesini önler.

Liste yoksa **`const`** , `GetPrev` listenin bir öğesine bir başvuru döndürür. Bu yöntem, bir atama ifadesinin her iki tarafında da kullanılmasına izin verir ve bu sayede liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

POZISYON sayacı, *POS*, listedeki önceki öğeyi işaret etmek üzere güncelleştirilir veya daha fazla öğe yoksa null olur. Hata ayıklama yapılarında, *POS* null değerine eşitse bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList:: Getbir Position](#gettailposition)örneğine bakın.

## <a name="catllistgettail"></a><a name="gettail"></a> CAtlList:: GetTail

Öğeyi listenin sonunda döndürmek için bu yöntemi çağırın.

```cpp
E& GetTail() throw();
const E& GetTail() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin kuyruklu öğesine veya bir kopyasına bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Liste ise **`const`** , listenin başında `GetTail` öğesinin bir kopyasını döndürür. Bu yöntem, yöntemin yalnızca bir atama ifadesinin sağ tarafında kullanılmasını sağlar ve listenin değiştirilmesini önler.

Liste yoksa **`const`** , `GetTail` listenin başında öğesine bir başvuru döndürür. Bu yöntem, bir atama ifadesinin her iki tarafında da kullanılmasına izin verir ve bu sayede liste girişlerinin değiştirilmesine izin verir.

Hata ayıklama yapılarında, listenin kuyruğu NULL ' a işaret ediyorsa bir onaylama hatası meydana gelir.

### <a name="example"></a>Örnek

[CAtlList:: AddTail](#addtail)örneğine bakın.

## <a name="catllistgettailposition"></a><a name="gettailposition"></a> CAtlList:: Getbir Position

Listenin tail konumunu almak için bu yöntemi çağırın.

```cpp
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin kuyruklu öğesine karşılık gelen konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Liste boşsa döndürülen değer NULL olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]

## <a name="catllistinargtype"></a><a name="inargtype"></a> CAtlList:: ıNARGTYPE

Bir öğe giriş bağımsız değişkeni olarak geçirildiğinde kullanılan tür.

```cpp
typedef ETraits::INARGTYPE INARGTYPE;
```

## <a name="catllistinsertafter"></a><a name="insertafter"></a> CAtlList:: InsertAfter

Belirtilen konumdan sonra listeye yeni bir öğe eklemek için bu yöntemi çağırın.

```cpp
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Yeni öğenin eklendiği konum değeri.

*dosyalarında*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yeni öğenin konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, liste geçerli değilse, ekleme başarısız olursa veya kuyruk sonrasında öğeyi eklemek için bir girişim yapılırsa bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]

## <a name="catllistinsertbefore"></a><a name="insertbefore"></a> CAtlList:: InsertBefore

Belirtilen konumdan önce listeye yeni bir öğe eklemek için bu yöntemi çağırın.

```cpp
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Yeni öğe, bu konum değerinden önce listeye eklenecektir.

*dosyalarında*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yeni öğenin konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, liste geçerli değilse, ekleme başarısız olursa veya öğeyi baş bir önüne eklemek için bir girişim yapılırsa bir onaylama hatası meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]

## <a name="catllistisempty"></a><a name="isempty"></a> CAtlList:: IsEmpty

Listenin boş olup olmadığını anlamak için bu yöntemi çağırın.

```cpp
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Liste hiç nesne içermiyorsa true, değilse false döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]

## <a name="catllistmovetohead"></a><a name="movetohead"></a> CAtlList:: MoveToHead

Belirtilen öğeyi listenin baş öğesine taşımak için bu yöntemi çağırın.

```cpp
void MoveToHead(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Taşınacak öğenin konum değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen öğe geçerli konumundan listenin adına taşınır. Hata ayıklama yapılarında, *POS* null değerine eşitse bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]

## <a name="catllistmovetotail"></a><a name="movetotail"></a> CAtlList:: MoveToTail

Belirtilen öğeyi listenin kuyruğu 'na taşımak için bu yöntemi çağırın.

```cpp
void MoveToTail(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Taşınacak öğenin konum değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen öğe geçerli konumundan listenin sonuna taşınır. Hata ayıklama yapılarında, *POS* null değerine eşitse bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList:: MoveToHead](#movetohead)örneğine bakın.

## <a name="catllistremoveall"></a><a name="removeall"></a> CAtlList:: RemoveAll

Tüm öğeleri listeden kaldırmak için bu yöntemi çağırın.

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, listedeki tüm öğeleri kaldırır ve ayrılan belleği serbest bırakır. Hata ayıklama GS yapılarında, tüm öğeler silinmemişse veya liste yapısı bozulursa bir ATLASSERT tetiklenir.

### <a name="example"></a>Örnek

[CAtlList:: IsEmpty](#isempty)örneğine bakın.

## <a name="catllistremoveat"></a><a name="removeat"></a> CAtlList:: RemoveAt

Listeden tek bir öğeyi kaldırmak için bu yöntemi çağırın.

```cpp
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Kaldırılacak öğenin konum değeri.

### <a name="remarks"></a>Açıklamalar

*POS* tarafından başvurulan öğe kaldırılır ve bellek serbest bırakılır. `RemoveAt`Listenin baş veya kuyruğunu kaldırmak için kullanılması kabul edilebilir.

Hata ayıklama yapılarında, liste geçerli değilse veya öğenin kaldırılması listenin liste yapısının parçası olmayan belleğe erişmesine neden olursa bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]

## <a name="catllistremovehead"></a><a name="removehead"></a> CAtlList:: RemoveHead

Listenin başında öğesini kaldırmak için bu yöntemi çağırın.

```cpp
E RemoveHead();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin başında öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Baş öğe listeden silinir ve bellek serbest bırakılır. Öğesinin bir kopyası döndürülür. Hata ayıklama yapılarında, liste boşsa bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]

## <a name="catllistremoveheadnoreturn"></a><a name="removeheadnoreturn"></a> CAtlList:: RemoveHeadNoReturn

Bir değer döndürmeden listenin baş tarafındaki öğeyi kaldırmak için bu yöntemi çağırın.

```cpp
void RemoveHeadNoReturn() throw();
```

### <a name="remarks"></a>Açıklamalar

Baş öğe listeden silinir ve bellek serbest bırakılır. Hata ayıklama yapılarında, liste boşsa bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList:: IsEmpty](#isempty)örneğine bakın.

## <a name="catllistremovetail"></a><a name="removetail"></a> CAtlList:: RemoveTail

Listenin sırasındaki öğesini kaldırmak için bu yöntemi çağırın.

```cpp
E RemoveTail();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin sonundaki öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Tail öğesi listeden silinir ve bellek serbest bırakılır. Öğesinin bir kopyası döndürülür. Hata ayıklama yapılarında, liste boşsa bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]

## <a name="catllistremovetailnoreturn"></a><a name="removetailnoreturn"></a> CAtlList:: Removebir noreturn

Bir değer döndürmeden listenin sırasındaki öğeyi kaldırmak için bu yöntemi çağırın.

```cpp
void RemoveTailNoReturn() throw();
```

### <a name="remarks"></a>Açıklamalar

Tail öğesi listeden silinir ve bellek serbest bırakılır. Hata ayıklama yapılarında, liste boşsa bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList:: IsEmpty](#isempty)örneğine bakın.

## <a name="catllistsetat"></a><a name="setat"></a> CAtlList:: SetAt

Bu yöntemi, listenin belirli bir konumundaki öğesinin değerini ayarlamak için çağırın.

```cpp
void SetAt(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Değiştirilecek öğeye karşılık gelen konum değeri.

*dosyalarında*<br/>
Yeni öğe değeri.

### <a name="remarks"></a>Açıklamalar

Varolan değeri *öğesiyle* değiştirir. Hata ayıklama yapılarında, *POS* null değerine eşitse bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]

## <a name="catllistswapelements"></a><a name="swapelements"></a> CAtlList:: SwapElements

Listedeki öğeleri değiştirmek için bu yöntemi çağırın.

```cpp
void SwapElements(POSITION pos1, POSITION pos2) throw();
```

### <a name="parameters"></a>Parametreler

*pos1*<br/>
İlk konum değeri.

*pos2*<br/>
İkinci konum değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen iki konumda öğeleri değiştirir. Hata ayıklama yapılarında, konum değeri NULL değerine eşitse bir onaylama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CList sınıfı](../../mfc/reference/clist-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
