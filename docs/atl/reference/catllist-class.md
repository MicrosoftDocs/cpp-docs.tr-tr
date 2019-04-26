---
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
ms.openlocfilehash: faed99197eb14da8ea095bef81d0d1a9845b18ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62247020"
---
# <a name="catllist-class"></a>CAtlList sınıfı

Bu sınıf, oluşturmak ve bir liste nesnesi yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlList
```

#### <a name="parameters"></a>Parametreler

*E*<br/>
Öğe türü.

*ETraits*<br/>
Kopyalama veya öğeleri taşıma için kullanılan kod. Bkz: [CElementTraits sınıfı](../../atl/reference/celementtraits-class.md) daha fazla ayrıntı için.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlList::INARGTYPE](#inargtype)||

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlList::CAtlList](#catllist)|Oluşturucu.|
|[CAtlList:: ~ CAtlList](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlList::AddHead](#addhead)|Listenin başındaki öğeyi eklemek için bu yöntemi çağırın.|
|[CAtlList::AddHeadList](#addheadlist)|Listenin başındaki mevcut bir listeyi eklemek için bu yöntemi çağırın.|
|[CAtlList::AddTail](#addtail)|Bu liste kuyruğu için bir öğe eklemek için bu yöntemi çağırın.|
|[CAtlList::AddTailList](#addtaillist)|Bu liste kuyruğu için mevcut bir listeyi eklemek için bu yöntemi çağırın.|
|[CAtlList::AssertValid](#assertvalid)|Listenin geçerli olup olmadığını onaylamak için bu yöntemi çağırın.|
|[CAtlList::Find](#find)|Belirtilen öğe listesi aramak için bu yöntemi çağırın.|
|[CAtlList::FindIndex](#findindex)|Bir dizin değeri belirtilen bir öğenin konumunu almak için bu yöntemi çağırın.|
|[CAtlList::GetAt](#getat)|Listesinde belirtilen konumda bir öğeyi döndürmek için bu yöntemi çağırın.|
|[CAtlList::GetCount](#getcount)|Listede nesne sayısını döndürmek için bu yöntemi çağırın.|
|[CAtlList::GetHead](#gethead)|Listenin başındaki öğeyi döndürmek için bu yöntemi çağırın.|
|[CAtlList::GetHeadPosition](#getheadposition)|Listenin başındaki konumunu almak için bu yöntemi çağırın.|
|[CAtlList::GetNext](#getnext)|Sonraki öğeyi listeden döndürmek için bu yöntemi çağırın.|
|[CAtlList::GetPrev](#getprev)|Önceki öğeyle listeden döndürmek için bu yöntemi çağırın.|
|[CAtlList::GetTail](#gettail)|Liste sonu öğe döndürmek için bu yöntemi çağırın.|
|[CAtlList::GetTailPosition](#gettailposition)|Liste sonu konumunu almak için bu yöntemi çağırın.|
|[CAtlList::InsertAfter](#insertafter)|Yeni bir öğe belirtilen konuma sonra listeye eklemek için bu yöntemi çağırın.|
|[CAtlList::InsertBefore](#insertbefore)|Yeni bir öğe belirtilen konuma önce listeye eklemek için bu yöntemi çağırın.|
|[CAtlList::IsEmpty](#isempty)|Listesinin boş olup olmadığını belirlemek için bu yöntemi çağırın.|
|[CAtlList::MoveToHead](#movetohead)|Listenin başında belirtilen öğe taşımak için bu yöntemi çağırın.|
|[CAtlList::MoveToTail](#movetotail)|Belirtilen öğe listesinin kuyruk için taşımak için bu yöntemi çağırın.|
|[CAtlList::RemoveAll](#removeall)|Tüm öğeler listeden kaldırmak için bu yöntemi çağırın.|
|[CAtlList::RemoveAt](#removeat)|Listeden tek bir öğe kaldırmak için bu yöntemi çağırın.|
|[CAtlList::RemoveHead](#removehead)|Listenin başındaki öğeyi kaldırmak için bu yöntemi çağırın.|
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|Bir değer döndüren olmadan listenin başındaki öğeyi kaldırmak için bu yöntemi çağırın.|
|[CAtlList::RemoveTail](#removetail)|Liste sonu öğe kaldırmak için bu yöntemi çağırın.|
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|Bir değer döndüren olmadan listenin sonu öğe kaldırmak için bu yöntemi çağırın.|
|[CAtlList::SetAt](#setat)|Listede verilen konumda öğenin değerini ayarlamak için bu yöntemi çağırın.|
|[CAtlList::SwapElements](#swapelements)|Listedeki öğeleri değiştirmek için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

`CAtlList` Sınıfı sırayla veya değere göre sıralı listeler erişilebilir benzersiz olmayan nesnelerin destekler. `CAtlList` listeleri karakteriyle bağlantılı liste gibi davranır. Her liste head ve bir kuyruk sahip ve yeni öğeler (veya bazı durumlarda listeleri) ya da listenin sonuna eklenebilir, veya önce veya sonra belirli öğeleri eklenir.

Çoğu `CAtlList` yöntemleri olun konum değeri kullanın. Bu değer, burada öğeleri depolanan ve hesaplanan veya doğrudan tahmin edilen gerçek bellek konumunu başvurmak için yöntemleri tarafından kullanılır. Erişim için gerekirse *n*öğedeki yöntemi listesinde [CAtlList::FindIndex](#findindex) belirtilen dizin için karşılık gelen konum değerini döndürür. Yöntemleri [CAtlList::GetNext](#getnext) ve [CAtlList::GetPrev](#getprev) liste içindeki nesneler aracılığıyla yineleme yapmak için kullanılabilir.

İle ATL koleksiyon sınıfları hakkında daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="addhead"></a>  CAtlList::AddHead

Listenin başındaki öğeyi eklemek için bu yöntemi çağırın.

```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*Öğesi*<br/>
Yeni öğe.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğenin konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm kullanılıyorsa, kopya Oluşturucu yerine kendi varsayılan oluşturucusunu kullanarak boş bir öğe oluşturulur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]

##  <a name="addheadlist"></a>  CAtlList::AddHeadList

Listenin başındaki mevcut bir listeyi eklemek için bu yöntemi çağırın.

```
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Parametreler

*plNew*<br/>
Eklenecek listesi.

### <a name="remarks"></a>Açıklamalar

Listenin tarafından işaret edilen *plNew* mevcut listenin başında eklenir. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *plNew* NULL değerine eşittir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]

##  <a name="addtail"></a>  CAtlList::AddTail

Bu liste kuyruğu için bir öğe eklemek için bu yöntemi çağırın.

```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*Öğesi*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yeni eklenen öğenin KONUMUNU döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm kullanılıyorsa, kopya Oluşturucu yerine kendi varsayılan oluşturucusunu kullanarak boş bir öğe oluşturulur. Öğe listesinin sonuna eklenir ve böylece artık kuyruk olur. Bu yöntem boş bir liste ile kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]

##  <a name="addtaillist"></a>  CAtlList::AddTailList

Bu liste kuyruğu için mevcut bir listeyi eklemek için bu yöntemi çağırın.

```
void AddTailList(const CAtlList<E, ETraits>* plNew);
```

### <a name="parameters"></a>Parametreler

*plNew*<br/>
Eklenecek listesi.

### <a name="remarks"></a>Açıklamalar

Listenin tarafından işaret edilen *plNew* (varsa) bir liste nesnesi son öğeden sonra eklenir. İçindeki son öğeden *plNew* liste bu nedenle kuyruğunu olur. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *plNew* NULL değerine eşittir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]

##  <a name="assertvalid"></a>  CAtlList::AssertValid

Listenin geçerli olup olmadığını onaylamak için bu yöntemi çağırın.

```
void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

Liste nesnesi geçerli değil. hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir. Geçerli olması için boş bir liste head ve kuyruk NULL değerini gösteriyor olmalıdır ve boş olmayan bir listesi head ve kuyruk işaret eden geçerli bir adresi olmalıdır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]

##  <a name="catllist"></a>  CAtlList::CAtlList

Oluşturucu.

```
CAtlList(UINT nBlockSize = 10) throw();
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

Oluşturucusu `CAtlList` nesne. Blok boyutu, yeni bir öğe gerektiğinde ayrılan bellek miktarını ölçüsüdür. Büyük blok boyutları için bellek ayırma yordamlarını aramalarını azaltır, ancak daha fazla kaynağı kullanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]

##  <a name="dtor"></a>  CAtlList:: ~ CAtlList

Yıkıcı.

```
~CAtlList() throw();
```

### <a name="remarks"></a>Açıklamalar

Bir çağrı dahil olmak üzere, ayrılan tüm kaynakları serbest bırakan [CAtlList::RemoveAll](#removeall) tüm öğeler listeden kaldırılacak.

Liste, bazı öğeler çağrısından sonra hala içeriyorsa, hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir `RemoveAll`.

##  <a name="find"></a>  CAtlList::Find

Belirtilen öğe listesi aramak için bu yöntemi çağırın.

```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```

### <a name="parameters"></a>Parametreler

*Öğesi*<br/>
Listesinde bulunacak öğe.

*posStartAfter*<br/>
Arama için başlangıç konumu. Hiçbir değer belirtilmemişse arama head öğesi ile başlar.

### <a name="return-value"></a>Dönüş Değeri

Öğenin KONUMUNU değerini döndürür bulundu, aksi takdirde NULL değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama derlemelerinde, liste nesnesi geçerli değilse veya bir onaylama işlemi hatası meydana gelir *posStartAfter* değer aralık dışında.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]

##  <a name="findindex"></a>  CAtlList::FindIndex

Bir dizin değeri belirtilen bir öğenin konumunu almak için bu yöntemi çağırın.

```
POSITION FindIndex(size_t iElement) const throw();
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Gerekli bir liste öğesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Karşılık gelen konum değeri ya da NULL döndürür *IElement* je mimo rozsah.

### <a name="remarks"></a>Açıklamalar

Bu yöntem erişimine izin verilen dizin değerine karşılık gelen KONUMUNU döndürür *n*öğedeki listesinde.

Liste nesnesi geçerli değil. hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]

##  <a name="getat"></a>  CAtlList::GetAt

Listesinde belirtilen konumda bir öğeyi döndürmek için bu yöntemi çağırın.

```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Belirli bir öğenin belirten konum değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru veya, öğenin kopyasını.

### <a name="remarks"></a>Açıklamalar

Liste **const**, `GetAt` öğenin bir kopyasını döndürür. Bu yöntemi yalnızca sağ tarafta Atama ifadesinin kullanılacak sağlar ve listenin değişikliklere karşı korur.

Listede değilse **const**, `GetAt` öğeye bir başvuru döndürür. Bu yöntem, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pos* NULL değerine eşittir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlList::FindIndex](#findindex).

##  <a name="getcount"></a>  CAtlList::GetCount

Listede nesne sayısını döndürmek için bu yöntemi çağırın.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki öğe sayısını döndürür.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlList::Find](#find).

##  <a name="gethead"></a>  CAtlList::GetHead

Listenin başındaki öğeyi döndürmek için bu yöntemi çağırın.

```
E& GetHead() throw();
const E& GetHead() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru ya da bir kopyasını, listenin başındaki öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Liste **const**, `GetHead` listenin başındaki öğeyi bir kopyasını döndürür. Bu yöntemi yalnızca sağ tarafta Atama ifadesinin kullanılacak sağlar ve listenin değişikliklere karşı korur.

Listede değilse **const**, `GetHead` listenin başındaki öğeyi bir başvuru döndürür. Bu yöntem, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.

Listenin başındaki NULL olarak işaret ediyorsa hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlList::AddHead](#addhead).

##  <a name="getheadposition"></a>  CAtlList::GetHeadPosition

Listenin başındaki konumunu almak için bu yöntemi çağırın.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin başındaki öğeyi karşılık gelen konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Liste boşsa, döndürülen değer NULL olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]

##  <a name="getnext"></a>  CAtlList::GetNext

Sonraki öğeyi listeden döndürmek için bu yöntemi çağırın.

```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen bir konum değeri `GetNext`, [CAtlList::GetHeadPosition](#getheadposition), veya diğer `CAtlList` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Liste **const**, `GetNext` sonraki öğe listesinin bir kopyasını döndürür. Bu yöntemi yalnızca sağ tarafta Atama ifadesinin kullanılacak sağlar ve listenin değişikliklere karşı korur.

Listede değilse **const**, `GetNext` listesinin sonraki öğeye bir başvuru döndürür. Bu yöntem, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.

### <a name="remarks"></a>Açıklamalar

Konum sayacı *pos*, daha fazla öğe yoksa NULL veya listedeki sonraki öğeye işaret edecek şekilde güncelleştirilir. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pos* NULL değerine eşittir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlList::GetHeadPosition](#getheadposition).

##  <a name="getprev"></a>  CAtlList::GetPrev

Önceki öğeyle listeden döndürmek için bu yöntemi çağırın.

```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen bir konum değeri `GetPrev`, [CAtlList::GetTailPosition](#gettailposition), veya diğer `CAtlList` yöntemi.

### <a name="return-value"></a>Dönüş Değeri

Liste **const**, `GetPrev` listedeki bir öğe bir kopyasını döndürür. Bu yöntemi yalnızca sağ tarafta Atama ifadesinin kullanılacak sağlar ve listenin değişikliklere karşı korur.

Listede değilse **const**, `GetPrev` listedeki bir öğeye bir başvuru döndürür. Bu yöntem, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.

### <a name="remarks"></a>Açıklamalar

Konum sayacı *pos*, listesinde önceki öğeye işaret edin veya daha fazla öğe yoksa NULL şekilde güncelleştirilir. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pos* NULL değerine eşittir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlList::GetTailPosition](#gettailposition).

##  <a name="gettail"></a>  CAtlList::GetTail

Liste sonu öğe döndürmek için bu yöntemi çağırın.

```
E& GetTail() throw();
const E& GetTail() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir başvuru veya listenin sonu öğe, bir kopyasını döndürür.

### <a name="remarks"></a>Açıklamalar

Liste **const**, `GetTail` listenin başındaki öğeyi bir kopyasını döndürür. Bu yöntemi yalnızca sağ tarafta Atama ifadesinin kullanılacak sağlar ve listenin değişikliklere karşı korur.

Listede değilse **const**, `GetTail` listenin başındaki öğeyi bir başvuru döndürür. Bu yöntem, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.

Liste sonu NULL olarak işaret ediyorsa hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlList::AddTail](#addtail).

##  <a name="gettailposition"></a>  CAtlList::GetTailPosition

Liste sonu konumunu almak için bu yöntemi çağırın.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Öğe listesinin kuyruğunu karşılık gelen konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Liste boşsa, döndürülen değer NULL olur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]

##  <a name="inargtype"></a>  CAtlList::INARGTYPE

Bir giriş bağımsız değişkeni bir öğe geçirildiğinde kullanılan türü.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

##  <a name="insertafter"></a>  CAtlList::InsertAfter

Yeni bir öğe belirtilen konuma sonra listeye eklemek için bu yöntemi çağırın.

```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Sonra yeni öğenin ekleneceği konum değeri.

*Öğesi*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yeni öğe konumu değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Ekleme başarısız olursa veya sonra kuyruk öğe eklemek için bir girişimde listenin geçerli değilse, hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]

##  <a name="insertbefore"></a>  CAtlList::InsertBefore

Yeni bir öğe belirtilen konuma önce listeye eklemek için bu yöntemi çağırın.

```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Yeni bir öğe, bu konum değeri önce listeye eklenir.

*Öğesi*<br/>
Eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yeni öğe konumu değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Ekleme başarısız olursa veya önce head öğesi eklemek için bir girişimde listenin geçerli değilse, hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]

##  <a name="isempty"></a>  CAtlList::IsEmpty

Listesinin boş olup olmadığını belirlemek için bu yöntemi çağırın.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Liste nesne, aksi takdirde false içeriyorsa true döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]

##  <a name="movetohead"></a>  CAtlList::MoveToHead

Listenin başında belirtilen öğe taşımak için bu yöntemi çağırın.

```
void MoveToHead(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Öğeyi taşımak için konum değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen öğeyi listenin başındaki geçerli konumundan taşınır. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pos* NULL değerine eşittir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]

##  <a name="movetotail"></a>  CAtlList::MoveToTail

Belirtilen öğe listesinin kuyruk için taşımak için bu yöntemi çağırın.

```
void MoveToTail(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Öğeyi taşımak için konum değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen öğe listesinin kuyruk için geçerli konumundan taşınır. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pos* NULL değerine eşittir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlList::MoveToHead](#movetohead).

##  <a name="removeall"></a>  CAtlList::RemoveAll

Tüm öğeler listeden kaldırmak için bu yöntemi çağırın.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Bu yöntem, tüm öğeler listeden kaldırır ve ayrılan belleği serbest bırakır. Tüm öğeler silinmez veya liste yapısı bozuksa, hatalarını düzeltir yapılarında bir ATLASSERT gerçekleştirilecektir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlList::IsEmpty](#isempty).

##  <a name="removeat"></a>  CAtlList::RemoveAt

Listeden tek bir öğe kaldırmak için bu yöntemi çağırın.

```
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Kaldırılacak öğe konumu değeri.

### <a name="remarks"></a>Açıklamalar

Tarafından başvurulan öğenin *pos* kaldırılır ve bellek serbest. Kullanmak için kabul edilebilir `RemoveAt` kafası veya listenin kuyruğu kaldırmak için.

Hata ayıklama yapılarında, listenin geçerli değilse veya liste yapısı parçası olmayan bellek erişimi listeye öğe kaldırıldığında neden olursa, onaylama işlemi hatası meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]

##  <a name="removehead"></a>  CAtlList::RemoveHead

Listenin başındaki öğeyi kaldırmak için bu yöntemi çağırın.

```
E RemoveHead();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin başındaki öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Head öğesi listesinden silinir ve bellek serbest bırakılır. Öğenin bir kopyasını döndürülür. Liste boşsa, hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]

##  <a name="removeheadnoreturn"></a>  CAtlList::RemoveHeadNoReturn

Bir değer döndüren olmadan listenin başındaki öğeyi kaldırmak için bu yöntemi çağırın.

```
void RemoveHeadNoReturn() throw();
```

### <a name="remarks"></a>Açıklamalar

Head öğesi listesinden silinir ve bellek serbest bırakılır. Liste boşsa, hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlList::IsEmpty](#isempty).

##  <a name="removetail"></a>  CAtlList::RemoveTail

Liste sonu öğe kaldırmak için bu yöntemi çağırın.

```
E RemoveTail();
```

### <a name="return-value"></a>Dönüş Değeri

Liste sonu öğe döndürür.

### <a name="remarks"></a>Açıklamalar

Kuyruk öğesi listesinden silinir ve bellek serbest bırakılır. Öğenin bir kopyasını döndürülür. Liste boşsa, hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]

##  <a name="removetailnoreturn"></a>  CAtlList::RemoveTailNoReturn

Bir değer döndüren olmadan listenin sonu öğe kaldırmak için bu yöntemi çağırın.

```
void RemoveTailNoReturn() throw();
```

### <a name="remarks"></a>Açıklamalar

Kuyruk öğesi listesinden silinir ve bellek serbest bırakılır. Liste boşsa, hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlList::IsEmpty](#isempty).

##  <a name="setat"></a>  CAtlList::SetAt

Listede verilen konumda öğenin değerini ayarlamak için bu yöntemi çağırın.

```
void SetAt(POSITION pos, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
KONUMU değiştirmek için öğenin karşılık gelen değer.

*Öğesi*<br/>
Yeni öğe değeri.

### <a name="remarks"></a>Açıklamalar

Mevcut değerle değiştiren *öğesi*. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pos* NULL değerine eşittir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]

##  <a name="swapelements"></a>  CAtlList::SwapElements

Listedeki öğeleri değiştirmek için bu yöntemi çağırın.

```
void SwapElements(POSITION pos1, POSITION pos2) throw();
```

### <a name="parameters"></a>Parametreler

*pos1*<br/>
İlk konum değeri.

*pos2*<br/>
İkinci konum değeri.

### <a name="remarks"></a>Açıklamalar

Belirtilen iki konumlarda öğeleri değiştirir. Hata ayıklama derlemelerinde, ya konum değeri NULL değerine eşit olup olmadığını onaylama işlemi hatası meydana gelir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[CList Sınıfı](../../mfc/reference/clist-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
