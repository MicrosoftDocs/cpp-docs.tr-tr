---
title: CAtlList Sınıfı
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
ms.openlocfilehash: 0e4ea8eef51431c100f5d3119d7f75e9673e276e
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748742"
---
# <a name="catllist-class"></a>CAtlList Sınıfı

Bu sınıf, bir liste nesnesi oluşturma ve yönetme yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlList
```

#### <a name="parameters"></a>Parametreler

*E*<br/>
Öğe türü.

*EÖzellikler*<br/>
Öğeleri kopyalamak veya taşımak için kullanılan kod. Daha fazla bilgi için [CElementTraits Sınıfına](../../atl/reference/celementtraits-class.md) bakın.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CAtlList::INARGTYPE](#inargtype)||

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlList::CAtlList](#catllist)|Oluşturucu.|
|[CAtlList::~CAtlList](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlList::AddHead](#addhead)|Listenin başına bir öğe eklemek için bu yöntemi arayın.|
|[CAtlList::AddHeadList](#addheadlist)|Varolan bir listeyi listenin başına eklemek için bu yöntemi arayın.|
|[CAtlList::AddTail](#addtail)|Bu listenin kuyruğuna bir öğe eklemek için bu yöntemi arayın.|
|[CAtlList::AddTailList](#addtaillist)|Varolan bir listeyi bu listenin kuyruğuna eklemek için bu yöntemi arayın.|
|[CAtlList::AssertValid](#assertvalid)|Listenin geçerli olduğunu doğrulamak için bu yöntemi arayın.|
|[CAtlList::Bul](#find)|Belirtilen öğeyi listeyi aramak için bu yöntemi arayın.|
|[CAtlList::FindIndex](#findindex)|Dizin değeri verilen bir öğenin konumunu elde etmek için bu yöntemi çağırın.|
|[CAtlList::GetAt](#getat)|Öğeyi listede belirtilen bir konumda döndürmek için bu yöntemi çağırın.|
|[CAtlList::GetCount](#getcount)|Listedeki nesne sayısını döndürmek için bu yöntemi arayın.|
|[CAtlList::GetHead](#gethead)|Listenin başındaki öğeyi döndürmek için bu yöntemi arayın.|
|[CAtlList::GetHeadPosition](#getheadposition)|Listenin başkanının konumunu elde etmek için bu yöntemi arayın.|
|[CAtlList::GetNext](#getnext)|Sonraki öğeyi listeden döndürmek için bu yöntemi arayın.|
|[CAtlList::GetPrev](#getprev)|Önceki öğeyi listeden döndürmek için bu yöntemi çağırın.|
|[CAtlList::GetTail](#gettail)|Listenin kuyruğundaki öğeyi döndürmek için bu yöntemi arayın.|
|[CAtlList::GetTailPosition](#gettailposition)|Listenin kuyruğunun konumunu elde etmek için bu yöntemi arayın.|
|[CAtlList::InsertAfter](#insertafter)|Belirtilen konumdan sonra listeye yeni bir öğe eklemek için bu yöntemi çağırın.|
|[CAtlList::EkleBefore](#insertbefore)|Belirtilen konumdan önce listeye yeni bir öğe eklemek için bu yöntemi çağırın.|
|[CAtlList::Boş](#isempty)|Listenin boş olup olmadığını belirlemek için bu yöntemi arayın.|
|[CAtlList::MoveToHead](#movetohead)|Belirtilen öğeyi listenin başına taşımak için bu yöntemi çağırın.|
|[CAtlList::MoveToTail](#movetotail)|Belirtilen öğeyi listenin kuyruğuna taşımak için bu yöntemi arayın.|
|[CAtlList::RemoveAll](#removeall)|Tüm öğeleri listeden kaldırmak için bu yöntemi arayın.|
|[CAtlList::RemoveAt](#removeat)|Tek bir öğeyi listeden kaldırmak için bu yöntemi çağırın.|
|[CAtlList::RemoveHead](#removehead)|Listenin başındaki öğeyi kaldırmak için bu yöntemi arayın.|
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|Bir değer döndürmeden listenin başındaki öğeyi kaldırmak için bu yöntemi arayın.|
|[CAtlList::RemoveTail](#removetail)|Listenin kuyruğundaki öğeyi kaldırmak için bu yöntemi arayın.|
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|Bir değer döndürmeden listenin kuyruğundaki öğeyi kaldırmak için bu yöntemi arayın.|
|[CAtlList::SetAt](#setat)|Listede belirli bir konumda öğenin değerini ayarlamak için bu yöntemi arayın.|
|[CAtlList::SwapElements](#swapelements)|Listedeki öğeleri değiştirmek için bu yöntemi arayın.|

## <a name="remarks"></a>Açıklamalar

Sınıf, `CAtlList` sırayla veya değere göre erişilebilen benzersiz olmayan nesnelerin sıralı listelerini destekler. `CAtlList`listeler iki kat bağlantılı listeler gibi olur. Her listenin bir kafası ve kuyruğu vardır ve listenin sonuna yeni öğeler (veya bazı durumlarda listeler) eklenebilir veya belirli öğelerden önce veya sonra eklenebilir.

Yöntemlerin `CAtlList` çoğu bir konum değerini kullanır. Bu değer, öğelerin depolandığı gerçek bellek konumuna başvurmak için yöntemlerle kullanılır ve doğrudan hesaplanmamalı veya öngörülmemeli. Listedeki *n*th öğesine erişmek gerekiyorsa, [CAtlList::FindIndex](#findindex) yöntemi belirli bir dizin için karşılık gelen konum değerini döndürür. [CAtlList::GetNext](#getnext) ve [CAtlList::GetPrev,](#getprev) listedeki nesneler aracılığıyla yinelemek için kullanılabilir.

ATL ile kullanılabilen toplama sınıfları hakkında daha fazla bilgi için [ATL Toplama Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="catllistaddhead"></a><a name="addhead"></a>CAtlList::AddHead

Listenin başına bir öğe eklemek için bu yöntemi arayın.

```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*Öğe*<br/>
Yeni eleman.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğenin konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm kullanılırsa, kopya oluşturucusu yerine varsayılan oluşturucusu kullanılarak boş bir öğe oluşturulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]

## <a name="catllistaddheadlist"></a><a name="addheadlist"></a>CAtlList::AddHeadList

Varolan bir listeyi listenin başına eklemek için bu yöntemi arayın.

```cpp
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Parametreler

*plYeni*<br/>
Eklenecek liste.

### <a name="remarks"></a>Açıklamalar

*plNew* tarafından işaret edilen liste varolan listenin başına eklenir. Hata ayıklama oluştururda, *plNew* NULL'a eşitse bir tasnif hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]

## <a name="catllistaddtail"></a><a name="addtail"></a>CAtlList::AddTail

Bu listenin kuyruğuna bir öğe eklemek için bu yöntemi arayın.

```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*Öğe*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğenin KONUMUNU döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm kullanılırsa, kopya oluşturucusu yerine varsayılan oluşturucusu kullanılarak boş bir öğe oluşturulur. Öğe listenin sonuna eklenir ve böylece artık kuyruk olur. Bu yöntem boş bir liste ile kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]

## <a name="catllistaddtaillist"></a><a name="addtaillist"></a>CAtlList::AddTailList

Varolan bir listeyi bu listenin kuyruğuna eklemek için bu yöntemi arayın.

```cpp
void AddTailList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Parametreler

*plYeni*<br/>
Eklenecek liste.

### <a name="remarks"></a>Açıklamalar

*plNew* tarafından işaret edilen liste, liste nesnesindeki son öğeden (varsa) sonra eklenir. *PlNew* listesindeki son öğe bu nedenle kuyruk olur. Hata ayıklama oluştururda, *plNew* NULL'a eşitse bir tasnif hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]

## <a name="catllistassertvalid"></a><a name="assertvalid"></a>CAtlList::AssertValid

Listenin geçerli olduğunu doğrulamak için bu yöntemi arayın.

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, liste nesnesi geçerli değilse bir sedama hatası oluşur. Geçerli olabilmesi için, boş bir listenin hem başı hem de kuyruğu NULL'u işaret etmeli ve boş olmayan bir listenin hem baş hem de kuyruk geçerli adresleri işaret etmesi gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]

## <a name="catllistcatllist"></a><a name="catllist"></a>CAtlList::CAtlList

Oluşturucu.

```
CAtlList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

Nesnenin oluşturucusu. `CAtlList` Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarının ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]

## <a name="catllistcatllist"></a><a name="dtor"></a>CAtlList::~CAtlList

Yıkıcı.

```
~CAtlList() throw();
```

### <a name="remarks"></a>Açıklamalar

CAtlList'e yapılan çağrı da dahil olmak üzere ayrılan tüm kaynakları serbest [sağlar::Listeden](#removeall) tüm öğeleri kaldırmak için RemoveAll.

Hata ayıklama oluşturur, liste hala çağrıdan sonra bazı öğeleri içeriyorsa `RemoveAll`bir sedama hatası oluşacaktır.

## <a name="catllistfind"></a><a name="find"></a>CAtlList::Bul

Belirtilen öğeyi listeyi aramak için bu yöntemi arayın.

```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*Öğe*<br/>
Listede bulunacak öğe.

*posStartAfter*<br/>
Arama için başlangıç konumu. Değer belirtilmemişse, arama baş öğesi ile başlar.

### <a name="return-value"></a>Dönüş Değeri

Bulunursa öğenin POZISYON değerini verir, aksi takdirde NULL döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, liste nesnesi geçerli değilse veya *posStartAfter* değeri kapsama alanı dışındaysa bir hata hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]

## <a name="catllistfindindex"></a><a name="findindex"></a>CAtlList::FindIndex

Dizin değeri verilen bir öğenin konumunu elde etmek için bu yöntemi çağırın.

```
POSITION FindIndex(size_t iElement) const throw();
```

### <a name="parameters"></a>Parametreler

*ıelement*<br/>
Gerekli liste öğesinin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Karşılık gelen POSITION değerini veya *iElement* kapsama alanı dışındaysa NULL değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, listedeki *n*th öğesine erişim sağlayan, belirli bir dizin değerine karşılık gelen POSITION'ı döndürür.

Hata ayıklama oluştururda, liste nesnesi geçerli değilse bir sedama hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]

## <a name="catllistgetat"></a><a name="getat"></a>CAtlList::GetAt

Öğeyi listede belirtilen bir konumda döndürmek için bu yöntemi çağırın.

```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Belirli bir öğeyi belirten POSITION değeri.

### <a name="return-value"></a>Dönüş Değeri

Öğeye başvuru veya bir kopyası.

### <a name="remarks"></a>Açıklamalar

Liste **const**ise, `GetAt` öğenin bir kopyasını döndürür. Bu, yöntemin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve listeyi değişiklikten korur.

Liste **const**değilse, `GetAt` öğeye bir başvuru döndürür. Bu, yöntemin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

Hata ayıklama oluştururda, *pos* NULL'a eşitse bir tasnif hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList örneğine bakın:FindIndex.](#findindex)

## <a name="catllistgetcount"></a><a name="getcount"></a>CAtlList::GetCount

Listedeki nesne sayısını döndürmek için bu yöntemi arayın.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki öğe sayısını verir.

### <a name="example"></a>Örnek

CAtlList için örneğe [bakın::Bul](#find).

## <a name="catllistgethead"></a><a name="gethead"></a>CAtlList::GetHead

Listenin başındaki öğeyi döndürmek için bu yöntemi arayın.

```
E& GetHead() throw();
const E& GetHead() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin başındaki öğeye bir başvuru veya bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Liste **const**ise, `GetHead` listenin başındaöğenin bir kopyasını döndürür. Bu, yöntemin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve listeyi değişiklikten korur.

Liste **const**değilse, `GetHead` listenin başındaki öğeye bir başvuru verir. Bu, yöntemin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

Hata ayıklama oluştururda, listenin başı NULL'a işaret ederse bir sevehatası oluşur.

### <a name="example"></a>Örnek

[CAtlList örneğine bakın:AddHead](#addhead).

## <a name="catllistgetheadposition"></a><a name="getheadposition"></a>CAtlList::GetHeadPosition

Listenin başkanının konumunu elde etmek için bu yöntemi arayın.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin başındaki öğeye karşılık gelen POSITION değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Liste boşsa, döndürülen değer NULL'dur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]

## <a name="catllistgetnext"></a><a name="getnext"></a>CAtlList::GetNext

Sonraki öğeyi listeden döndürmek için bu yöntemi arayın.

```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Bir önceki arama tarafından döndürülen, [CAtlList:::GetHeadPosition](#getheadposition) `CAtlList` veya başka bir yöntem. `GetNext`

### <a name="return-value"></a>Dönüş Değeri

Liste **const**ise, `GetNext` listenin bir sonraki öğesinin bir kopyasını döndürür. Bu, yöntemin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve listeyi değişiklikten korur.

Liste **const**değilse, `GetNext` listenin bir sonraki öğesine bir başvuru döndürür. Bu, yöntemin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

POSITION sayacı, *pos*, listedeki bir sonraki öğeye işaret etmek için güncelleştirilir veya başka öğe yoksa NULL. Hata ayıklama oluştururda, *pos* NULL'a eşitse bir tasnif hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList örneğine bakın:GetHeadPosition](#getheadposition).

## <a name="catllistgetprev"></a><a name="getprev"></a>CAtlList::GetPrev

Önceki öğeyi listeden döndürmek için bu yöntemi çağırın.

```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Bir önceki arama tarafından döndürülen, [CAtlList:::GetTailPosition](#gettailposition) `CAtlList` veya başka bir yöntem. `GetPrev`

### <a name="return-value"></a>Dönüş Değeri

Liste **const**ise, `GetPrev` listenin bir öğesinin bir kopyasını döndürür. Bu, yöntemin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve listeyi değişiklikten korur.

Liste **const**değilse, `GetPrev` listenin bir öğesiiçin bir başvuru döndürür. Bu, yöntemin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

POSITION sayacı, *pos*, listedeönceki öğeye işaret etmek için güncelleştirilir veya başka öğe yoksa NULL. Hata ayıklama oluştururda, *pos* NULL'a eşitse bir tasnif hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList örneğine bakın::GetTailPosition](#gettailposition).

## <a name="catllistgettail"></a><a name="gettail"></a>CAtlList::GetTail

Listenin kuyruğundaki öğeyi döndürmek için bu yöntemi arayın.

```
E& GetTail() throw();
const E& GetTail() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin kuyruğundaki öğeye bir başvuru veya bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Liste **const**ise, `GetTail` listenin başındaöğenin bir kopyasını döndürür. Bu, yöntemin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve listeyi değişiklikten korur.

Liste **const**değilse, `GetTail` listenin başındaki öğeye bir başvuru verir. Bu, yöntemin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

Hata ayıklama oluştururda, listenin kuyruğu NULL'a işaret ederse bir tasnif hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList örneğine bakın:AddTail](#addtail).

## <a name="catllistgettailposition"></a><a name="gettailposition"></a>CAtlList::GetTailPosition

Listenin kuyruğunun konumunu elde etmek için bu yöntemi arayın.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin kuyruğundaki öğeye karşılık gelen POSITION değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Liste boşsa, döndürülen değer NULL'dur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]

## <a name="catllistinargtype"></a><a name="inargtype"></a>CAtlList::INARGTYPE

Bir öğe giriş bağımsız değişkeni olarak geçirildiğinde kullanılan tür.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

## <a name="catllistinsertafter"></a><a name="insertafter"></a>CAtlList::InsertAfter

Belirtilen konumdan sonra listeye yeni bir öğe eklemek için bu yöntemi çağırın.

```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Yeni öğenin eklendiği POSITION değeri.

*Öğe*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yeni öğenin POSITION değerini verir.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, liste geçerli değilse, ekleme başarısız olursa veya öğeyi kuyruktan sonra eklemegirişiminde bulunulmuşsa, bir hata hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]

## <a name="catllistinsertbefore"></a><a name="insertbefore"></a>CAtlList::EkleBefore

Belirtilen konumdan önce listeye yeni bir öğe eklemek için bu yöntemi çağırın.

```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Yeni öğe bu POSITION değerinden önce listeye eklenir.

*Öğe*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yeni öğenin POSITION değerini verir.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, liste geçerli değilse, ekleme başarısız olursa veya öğeyi kafadan önce ekleme girişiminde bulunulmuşsa, bir hata hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]

## <a name="catllistisempty"></a><a name="isempty"></a>CAtlList::Boş

Listenin boş olup olmadığını belirlemek için bu yöntemi arayın.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Liste hiçbir nesne içeriyorsa, aksi takdirde yanlış gerçek döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]

## <a name="catllistmovetohead"></a><a name="movetohead"></a>CAtlList::MoveToHead

Belirtilen öğeyi listenin başına taşımak için bu yöntemi çağırın.

```cpp
void MoveToHead(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Hareket etmek için öğenin KONUM değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen öğe geçerli konumundan listenin başına taşınır. Hata ayıklama oluştururda, *pos* NULL'a eşitse bir tasnif hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]

## <a name="catllistmovetotail"></a><a name="movetotail"></a>CAtlList::MoveToTail

Belirtilen öğeyi listenin kuyruğuna taşımak için bu yöntemi arayın.

```cpp
void MoveToTail(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Hareket etmek için öğenin KONUM değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen öğe geçerli konumundan listenin kuyruğuna taşınır. Hata ayıklama oluştururda, *pos* NULL'a eşitse bir tasnif hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList örneğine bakın::MoveToHead](#movetohead).

## <a name="catllistremoveall"></a><a name="removeall"></a>CAtlList::RemoveAll

Tüm öğeleri listeden kaldırmak için bu yöntemi arayın.

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tüm öğeleri listeden kaldırır ve ayrılan belleği serbest sağlar. Debugs oluştururda, tüm öğeler silinmezse veya liste yapısı bozulmuşsa bir ATLASSERT yükseltilir.

### <a name="example"></a>Örnek

[CAtlList örneğine bakın::Boş.](#isempty)

## <a name="catllistremoveat"></a><a name="removeat"></a>CAtlList::RemoveAt

Tek bir öğeyi listeden kaldırmak için bu yöntemi çağırın.

```cpp
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Kaldırılacak öğenin KONUM değeri.

### <a name="remarks"></a>Açıklamalar

*Pos* tarafından başvurulan öğe kaldırılır ve bellek serbest bırakılır. Listenin başını `RemoveAt` veya kuyruğunu çıkarmak için kullanılması kabul edilebilir.

Hata ayıklama yapılarda, liste geçerli değilse veya öğenin kaldırılması liste yapısının bir parçası olmayan belleğe erişmesine neden oluyorsa bir tasnif hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]

## <a name="catllistremovehead"></a><a name="removehead"></a>CAtlList::RemoveHead

Listenin başındaki öğeyi kaldırmak için bu yöntemi arayın.

```
E RemoveHead();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin başındaki öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Kafa öğesi listeden silinir ve bellek serbest bırakılır. Öğenin bir kopyası döndürülür. Hata ayıklama oluştururda, liste boşsa bir sancak hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]

## <a name="catllistremoveheadnoreturn"></a><a name="removeheadnoreturn"></a>CAtlList::RemoveHeadNoReturn

Bir değer döndürmeden listenin başındaki öğeyi kaldırmak için bu yöntemi arayın.

```cpp
void RemoveHeadNoReturn() throw();
```

### <a name="remarks"></a>Açıklamalar

Kafa öğesi listeden silinir ve bellek serbest bırakılır. Hata ayıklama oluştururda, liste boşsa bir sancak hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList örneğine bakın::Boş.](#isempty)

## <a name="catllistremovetail"></a><a name="removetail"></a>CAtlList::RemoveTail

Listenin kuyruğundaki öğeyi kaldırmak için bu yöntemi arayın.

```
E RemoveTail();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin kuyruğundaki öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Kuyruk öğesi listeden silinir ve bellek serbest bırakılır. Öğenin bir kopyası döndürülür. Hata ayıklama oluştururda, liste boşsa bir sancak hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]

## <a name="catllistremovetailnoreturn"></a><a name="removetailnoreturn"></a>CAtlList::RemoveTailNoReturn

Bir değer döndürmeden listenin kuyruğundaki öğeyi kaldırmak için bu yöntemi arayın.

```cpp
void RemoveTailNoReturn() throw();
```

### <a name="remarks"></a>Açıklamalar

Kuyruk öğesi listeden silinir ve bellek serbest bırakılır. Hata ayıklama oluştururda, liste boşsa bir sancak hatası oluşur.

### <a name="example"></a>Örnek

[CAtlList örneğine bakın::Boş.](#isempty)

## <a name="catllistsetat"></a><a name="setat"></a>CAtlList::SetAt

Listede belirli bir konumda öğenin değerini ayarlamak için bu yöntemi arayın.

```cpp
void SetAt(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Değişmek üzere öğeye karşılık gelen POSITION değeri.

*Öğe*<br/>
Yeni öğe değeri.

### <a name="remarks"></a>Açıklamalar

Varolan değeri *öğeyle*değiştirir. Hata ayıklama oluştururda, *pos* NULL'a eşitse bir tasnif hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]

## <a name="catllistswapelements"></a><a name="swapelements"></a>CAtlList::SwapElements

Listedeki öğeleri değiştirmek için bu yöntemi arayın.

```cpp
void SwapElements(POSITION pos1, POSITION pos2) throw();
```

### <a name="parameters"></a>Parametreler

*pos1*<br/>
İlk POSITION değeri.

*pos2*<br/>
İkinci POSITION değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen iki pozisyondaki öğeleri değiştirir. Hata ayıklama oluştururda, her iki konum değeri null'a eşitse bir tasnif hatası oluşur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CList Sınıfı](../../mfc/reference/clist-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
