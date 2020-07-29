---
title: CList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CList
- AFXTEMPL/CList
- AFXTEMPL/CList::CList
- AFXTEMPL/CList::AddHead
- AFXTEMPL/CList::AddTail
- AFXTEMPL/CList::Find
- AFXTEMPL/CList::FindIndex
- AFXTEMPL/CList::GetAt
- AFXTEMPL/CList::GetCount
- AFXTEMPL/CList::GetHead
- AFXTEMPL/CList::GetHeadPosition
- AFXTEMPL/CList::GetNext
- AFXTEMPL/CList::GetPrev
- AFXTEMPL/CList::GetSize
- AFXTEMPL/CList::GetTail
- AFXTEMPL/CList::GetTailPosition
- AFXTEMPL/CList::InsertAfter
- AFXTEMPL/CList::InsertBefore
- AFXTEMPL/CList::IsEmpty
- AFXTEMPL/CList::RemoveAll
- AFXTEMPL/CList::RemoveAt
- AFXTEMPL/CList::RemoveHead
- AFXTEMPL/CList::RemoveTail
- AFXTEMPL/CList::SetAt
helpviewer_keywords:
- CList [MFC], CList
- CList [MFC], AddHead
- CList [MFC], AddTail
- CList [MFC], Find
- CList [MFC], FindIndex
- CList [MFC], GetAt
- CList [MFC], GetCount
- CList [MFC], GetHead
- CList [MFC], GetHeadPosition
- CList [MFC], GetNext
- CList [MFC], GetPrev
- CList [MFC], GetSize
- CList [MFC], GetTail
- CList [MFC], GetTailPosition
- CList [MFC], InsertAfter
- CList [MFC], InsertBefore
- CList [MFC], IsEmpty
- CList [MFC], RemoveAll
- CList [MFC], RemoveAt
- CList [MFC], RemoveHead
- CList [MFC], RemoveTail
- CList [MFC], SetAt
ms.assetid: 6f6273c3-c8f6-47f5-ac2a-0a950379ae5d
ms.openlocfilehash: 7ba85445e3aba1df853d7d3666c92fdabdfa3970
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87182882"
---
# <a name="clist-class"></a>CList sınıfı

Ardışık olarak veya değere göre erişilebilen, benzersiz olmayan nesnelerin sıralı listesini destekler.

## <a name="syntax"></a>Sözdizimi

```
template<class TYPE, class ARG_TYPE = const TYPE&>
class CList : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CList:: CList](#clist)|Boş bir sıralı liste oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CList:: AddHead](#addhead)|Listenin baş bir bir öğesini (veya başka bir listedeki tüm öğeleri) ekler (yeni bir baş oluşturur).|
|[CList:: AddTail](#addtail)|Bir öğeyi (veya başka bir listedeki tüm öğeleri) listenin sonuna ekler (yeni bir kuyruk oluşturur).|
|[CList:: Find](#find)|İşaretçi değeri tarafından belirtilen öğenin konumunu alır.|
|[CList:: FindIndex](#findindex)|Sıfır tabanlı bir dizin tarafından belirtilen öğenin konumunu alır.|
|[CList:: GetAt](#getat)|Belirtilen konumdaki öğeyi alır.|
|[CList:: GetCount](#getcount)|Bu listedeki öğe sayısını döndürür.|
|[CList:: GetHead](#gethead)|Listenin baş öğesini döndürür (boş olamaz).|
|[CList:: GetHeadPosition](#getheadposition)|Listenin baş öğesinin konumunu döndürür.|
|[CList:: GetNext](#getnext)|Yineleme için bir sonraki öğeyi alır.|
|[CList:: Getöncekini](#getprev)|Yineleme için önceki öğeyi alır.|
|[CList:: GetSize](#getsize)|Bu listedeki öğe sayısını döndürür.|
|[CList:: GetTail](#gettail)|Listenin tail öğesini döndürür (boş olamaz).|
|[CList:: Getbir Position](#gettailposition)|Listenin tail öğesinin konumunu döndürür.|
|[CList:: InsertAfter](#insertafter)|Belirli bir konumdan sonra yeni bir öğe ekler.|
|[CList:: InsertBefore](#insertbefore)|Belirli bir konumdan önce yeni bir öğe ekler.|
|[CList:: IsEmpty](#isempty)|Boş liste koşulunu sınar (öğe yok).|
|[CList:: RemoveAll](#removeall)|Bu listedeki tüm öğeleri kaldırır.|
|[CList:: RemoveAt](#removeat)|Bu listeden, konuma göre belirtilen bir öğeyi kaldırır.|
|[CList:: RemoveHead](#removehead)|Öğeyi listenin Başndan kaldırır.|
|[CList:: RemoveTail](#removetail)|Öğeyi listenin tail öğesinden kaldırır.|
|[CList:: SetAt](#setat)|Belirtilen konumdaki öğeyi ayarlar.|

#### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan nesnenin türü.

*ARG_TYPE*<br/>
Listede depolanan nesnelere başvurmak için kullanılan tür. Bir başvuru olabilir.

## <a name="remarks"></a>Açıklamalar

`CList`listeler, benzer şekilde bağlantılı listeler gibi davranır.

POSITION türünde bir değişken, listenin bir anahtarıdır. Bir listeyi bir yerde ve bir yer tutacak bir yer işareti olarak çapraz bir şekilde geçirmek için bir yineleyici olarak konum değişkeni kullanabilirsiniz. Ancak bir konum bir dizinle aynı değildir.

Öğe ekleme, kuyruklu ve bilinen bir konumda liste başıyla çok hızlıdır. Bir öğeyi değere veya dizine göre aramak için sıralı bir arama gerekir. Liste uzunsa bu arama yavaş olabilir.

Listedeki ayrı öğelerin bir dökümünden birine ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bu sınıfın bazı üye işlevleri, sınıfının çoğu kullanımları için özelleştirilmek zorunda olan genel yardımcı işlevlerini çağırır `CList` . "Makrolar ve genel" bölümünde [koleksiyon sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) bölümüne bakın.

Kullanma hakkında daha fazla bilgi için `CList` bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtempl. h

## <a name="clistaddhead"></a><a name="addhead"></a>CList:: AddHead

Bu listenin başından yeni bir öğe veya öğe listesi ekler.

```
POSITION AddHead(ARG_TYPE newElement);
void AddHead(CList* pNewList);
```

### <a name="parameters"></a>Parametreler

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi (bir başvuru olabilir).

*newElement*<br/>
Yeni öğe.

*pNewList*<br/>
Başka bir liste işaretçisi `CList` . *PNewList* içindeki öğeler bu listeye eklenecektir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni takılan öğenin konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İşlem öncesinde liste boş olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]

## <a name="clistaddtail"></a><a name="addtail"></a>CList:: AddTail

Bu listenin kuyruğu için yeni bir öğe veya öğe listesi ekler.

```
POSITION AddTail(ARG_TYPE newElement);
void AddTail(CList* pNewList);
```

### <a name="parameters"></a>Parametreler

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi (bir başvuru olabilir).

*newElement*<br/>
Bu listeye eklenecek öğe.

*pNewList*<br/>
Başka bir liste işaretçisi `CList` . *PNewList* içindeki öğeler bu listeye eklenecektir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni takılan öğenin konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İşlem öncesinde liste boş olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]

## <a name="clistclist"></a><a name="clist"></a>CList:: CList

Boş bir sıralı liste oluşturur.

```
CList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Listeyi genişletmek için bellek ayırma ayrıntı düzeyi.

### <a name="remarks"></a>Açıklamalar

Liste büyüdükçe, bellek *nBlockSize* girdileri birimlerinde ayrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]

## <a name="clistfind"></a><a name="find"></a>CList:: Find

Belirtilen *searchValue*ile eşleşen ilk öğeyi bulmak için listeyi sıralı olarak arar.

```
POSITION Find(
    ARG_TYPE searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>Parametreler

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi (bir başvuru olabilir).

*searchValue*<br/>
Listede bulunan değer.

*startAfter*<br/>
Arama için başlangıç konumu. Hiçbir değer belirtilmemişse, arama Head öğesiyle başlar.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; Nesne bulunamazsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]

## <a name="clistfindindex"></a><a name="findindex"></a>CList:: FindIndex

Listede dizin olarak *nindex* değerini kullanır.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Bulunamayan liste öğesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; *NIndex* negatifse veya çok büyükse null.

### <a name="remarks"></a>Açıklamalar

Bu, *n*. öğesinde durdurulan, listenin başlarından sıralı bir tarama başlatır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]

## <a name="clistgetat"></a><a name="getat"></a>CList:: GetAt

Belirtilen konumdaki liste öğesini alır.

```
TYPE& GetAt(POSITION position);
const TYPE& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki nesne türünü belirten şablon parametresi.

*yerine*<br/>
Alınacak öğe listesindeki konum.

### <a name="return-value"></a>Dönüş Değeri

İçin dönüş değeri açıklamasına bakın `GetHead` .

### <a name="remarks"></a>Açıklamalar

`GetAt`verilen bir konumla ilişkili öğeyi (veya öğenin başvurusunu) döndürür. Bir dizin ile aynı değildir ve bir konum değerinde kendiniz işlem yapılamaz. POSITION türünde bir değişken, listenin bir anahtarıdır.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

### <a name="example"></a>Örnek

  [CList:: GetHeadPosition](#getheadposition)örneğine bakın.

## <a name="clistgetcount"></a><a name="getcount"></a>CList:: GetCount

Bu listedeki öğelerin sayısını alır.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısını içeren bir tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntemin çağrılması [CList:: GetSize](#getsize) yöntemiyle aynı sonucu oluşturacaktır.

### <a name="example"></a>Örnek

  [CList:: RemoveHead](#removehead)örneğine bakın.

## <a name="clistgethead"></a><a name="gethead"></a>CList:: GetHead

Bu listenin baş öğesini (veya bir baş öğesine bir başvuru) alır.

```
const TYPE& GetHead() const;

TYPE& GetHead();
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki nesne türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Liste ise **`const`** , listenin başında `GetHead` öğesinin bir kopyasını döndürür. Bu, işlevin atama ifadesinin sağ tarafında kullanılmasına ve listenin değiştirilmesini korumasının olanaklı olmasını sağlar.

Liste yoksa **`const`** , `GetHead` listenin başında öğesine bir başvuru döndürür. Bu, işlevin atama ifadesinin her iki tarafında kullanılmasına izin verir ve bu nedenle liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `GetHead` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](#isempty) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]

## <a name="clistgetheadposition"></a><a name="getheadposition"></a>CList:: GetHeadPosition

Bu listenin baş öğesinin konumunu alır.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; Liste boşsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]

## <a name="clistgetnext"></a><a name="getnext"></a>CList:: GetNext

*RPosition*tarafından tanımlanan liste öğesini alır ve ardından listedeki bir sonrakı girdinin konum değerine *rPosition* değerini ayarlar.

```
TYPE& GetNext(POSITION& rPosition);
const TYPE& GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki öğelerin türünü belirten şablon parametresi.

*rPosition*<br/>
Previous `GetNext` , [GetHeadPosition](#getheadposition)veya diğer üye işlev çağrısı tarafından döndürülen bir konum değerine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Liste ise **`const`** , listenin bir `GetNext` öğesinin bir kopyasını döndürür. Bu, işlevin atama ifadesinin sağ tarafında kullanılmasına ve listenin değiştirilmesini korumasının olanaklı olmasını sağlar.

Liste yoksa **`const`** , `GetNext` listenin bir öğesine bir başvuru döndürür. Bu, işlevin atama ifadesinin her iki tarafında kullanılmasına izin verir ve bu nedenle liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Bir `GetNext` veya çağrısı ile ilk konumu oluşturursanız, bir ileri yineleme döngüsünde kullanabilirsiniz `GetHeadPosition` `Find` .

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Alınan öğe listedeki son ise, yeni değeri `rPosition` null olarak ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]

## <a name="clistgetprev"></a><a name="getprev"></a>CList:: Getöncekini

Tarafından tanımlanan liste öğesini alır `rPosition` , ardından `rPosition` listedeki ÖNCEKI girdinin konum değerine ayarlanır.

```
TYPE& GetPrev(POSITION& rPosition);
const TYPE& GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki öğelerin türünü belirten şablon parametresi.

*rPosition*<br/>
Önceki `GetPrev` veya diğer üye işlev çağrısı tarafından döndürülen BIR konum değerine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Liste ise **`const`** , listenin başında `GetPrev` öğesinin bir kopyasını döndürür. Bu, işlevin atama ifadesinin sağ tarafında kullanılmasına ve listenin değiştirilmesini korumasının olanaklı olmasını sağlar.

Liste yoksa **`const`** , `GetPrev` listenin bir öğesine bir başvuru döndürür. Bu, işlevin atama ifadesinin her iki tarafında kullanılmasına izin verir ve bu nedenle liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

`GetPrev`Bir veya çağrısı ile ilk konumu ayarlarsanız, bir ters yineleme döngüsünde kullanabilirsiniz `GetTailPosition` `Find` .

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Alınan öğe listedeki ilk ise, yeni *rPosition* değeri null olarak ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]

## <a name="clistgetsize"></a><a name="getsize"></a>CList:: GetSize

Liste öğelerinin sayısını döndürür.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Listedeki öğe sayısını almak için bu yöntemi çağırın.  Bu yöntemin çağrılması [CList:: GetCount](#getcount) yöntemiyle aynı sonucu oluşturacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]

## <a name="clistgettail"></a><a name="gettail"></a>CList:: GetTail

`CObject`Bu listenin tail öğesini temsil eden işaretçiyi alır.

```
TYPE& GetTail();
const TYPE& GetTail() const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

[GetHead](../../mfc/reference/coblist-class.md#gethead)için dönüş değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `GetTail` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](../../mfc/reference/coblist-class.md#isempty) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]

## <a name="clistgettailposition"></a><a name="gettailposition"></a>CList:: Getbir Position

Bu listenin tail öğesinin konumunu alır; Liste boşsa NULL.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; Liste boşsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]

## <a name="clistinsertafter"></a><a name="insertafter"></a>CList:: InsertAfter

Belirtilen konumdaki öğeden sonra bu listeye bir öğe ekler.

```
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*yerine*<br/>
Previous `GetNext` , `GetPrev` veya `Find` member Function çağrısı tarafından döndürülen bir konum değeri.

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi.

*newElement*<br/>
Bu listeye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya liste öğesi alımı için kullanılabilen bir konum değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]

## <a name="clistinsertbefore"></a><a name="insertbefore"></a>CList:: InsertBefore

Bu listeye, belirtilen konumdaki öğeden önce bir öğe ekler.

```
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*yerine*<br/>
Previous `GetNext` , `GetPrev` veya `Find` member Function çağrısı tarafından döndürülen bir konum değeri.

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi (bir başvuru olabilir).

*newElement*<br/>
Bu listeye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya liste öğesi alımı için kullanılabilen bir konum değeri.

### <a name="remarks"></a>Açıklamalar

*Konum* null ise, öğe listenin baş altına eklenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]

## <a name="clistisempty"></a><a name="isempty"></a>CList:: IsEmpty

Bu listenin hiç öğe içerip içermediğini gösterir.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu liste boşsa sıfır dışı; Aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]

## <a name="clistremoveall"></a><a name="removeall"></a>CList:: RemoveAll

Bu listedeki tüm öğeleri kaldırır ve ilişkili belleği serbest bırakır.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Liste zaten boşsa bir hata oluşturulmaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]

## <a name="clistremoveat"></a><a name="removeat"></a>CList:: RemoveAt

Belirtilen öğeyi bu listeden kaldırır.

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Parametreler

*yerine*<br/>
Listeden kaldırılacak öğenin konumu.

### <a name="remarks"></a>Açıklamalar

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]

## <a name="clistremovehead"></a><a name="removehead"></a>CList:: RemoveHead

Öğeyi listenin baş öğesinden kaldırır ve ona bir işaretçi döndürür.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Daha önce listenin başında öğesi.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `RemoveHead` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](#isempty) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]

## <a name="clistremovetail"></a><a name="removetail"></a>CList:: RemoveTail

Öğeyi listenin kuyruğunu kaldırır ve ona bir işaretçi döndürür.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Listenin kuyruklu olan öğe.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `RemoveTail` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](#isempty) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]

## <a name="clistsetat"></a><a name="setat"></a>CList:: SetAt

POSITION türünde bir değişken, listenin bir anahtarıdır.

```cpp
void SetAt(POSITION pos, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Ayarlanacak öğenin konumu.

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi (bir başvuru olabilir).

*newElement*<br/>
Listeye eklenecek öğe.

### <a name="remarks"></a>Açıklamalar

Bir dizin ile aynı değildir ve bir konum değerinde kendiniz işlem yapılamaz. `SetAt`öğeyi listede belirtilen konuma yazar.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek toplama](../../overview/visual-cpp-samples.md)<br/>
[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMap sınıfı](../../mfc/reference/cmap-class.md)<br/>
[CArray sınıfı](../../mfc/reference/carray-class.md)
