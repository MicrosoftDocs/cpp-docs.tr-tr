---
title: CList Sınıfı
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
ms.openlocfilehash: adc065687f0c2c40b7e66326ff9d1e6210a6962c
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754138"
---
# <a name="clist-class"></a>CList Sınıfı

Sırayla veya değere göre erişilebilen benzersiz olmayan nesnelerin sıralı listelerini destekler.

## <a name="syntax"></a>Sözdizimi

```
template<class TYPE, class ARG_TYPE = const TYPE&>
class CList : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CList::CList](#clist)|Boş bir sıralı liste oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CList::AddHead](#addhead)|Listenin başına bir öğe (veya başka bir listedeki tüm öğeler) ekler (yeni bir kafa yapar).|
|[CList::AddTail](#addtail)|Listenin kuyruğuna bir öğe (veya başka bir listedeki tüm öğeler) ekler (yeni bir kuyruk yapar).|
|[CList::Bul](#find)|İşaretçi değeriyle belirtilen bir öğenin konumunu alır.|
|[CList::FindIndex](#findindex)|Sıfır tabanlı dizin tarafından belirtilen bir öğenin konumunu alır.|
|[CList::Getat](#getat)|Öğeyi belirli bir konumda alır.|
|[CList::GetCount](#getcount)|Bu listedeki öğe sayısını verir.|
|[CList::GetHead](#gethead)|Listenin baş öğesini verir (boş olamaz).|
|[CList::GetHeadPosition](#getheadposition)|Listenin baş öğesinin konumunu döndürür.|
|[CList::GetNext](#getnext)|Yinelenmenin bir sonraki öğesini alır.|
|[CList::GetPrev](#getprev)|Yinelenmeiçin önceki öğeyi alır.|
|[CList::GetSize](#getsize)|Bu listedeki öğe sayısını verir.|
|[CList::GetTail](#gettail)|Listenin kuyruk öğesini verir (boş olamaz).|
|[CList::GetTailPosition](#gettailposition)|Listenin kuyruk öğesinin konumunu döndürür.|
|[CList::InsertAfter](#insertafter)|Belirli bir konumdan sonra yeni bir öğe ekler.|
|[CList::EkleBefore](#insertbefore)|Belirli bir konumdan önce yeni bir öğe ekler.|
|[CList::Boş](#isempty)|Boş liste koşulu için testler (öğe yok).|
|[CList::RemoveAll](#removeall)|Bu listeden tüm öğeleri kaldırır.|
|[CList::Removeat](#removeat)|Konuma göre belirtilen bir öğeyi bu listeden kaldırır.|
|[CList::RemoveHead](#removehead)|Öğeyi listenin başından kaldırır.|
|[CList::RemoveTail](#removetail)|Öğeyi listenin kuyruğundan kaldırır.|
|[CList::Setat](#setat)|Öğeyi belirli bir konumda ayarlar.|

#### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan nesne türü.

*ARG_TYPE*<br/>
Listede depolanan nesnelere başvurmak için kullanılan yazı. Bir referans olabilir.

## <a name="remarks"></a>Açıklamalar

`CList`listeler iki kat bağlantılı listeler gibi olur.

Tür POZISYON değişkeni liste için bir anahtardır. Bir yeri tutmak için listeyi sırayla ve yer imi olarak geçmek için POSITION değişkenini yineleyici olarak kullanabilirsiniz. Ancak, bir konum dizinle aynı değildir.

Eleman ekleme liste başında çok hızlı, kuyruk, ve bilinen bir POZISYONDA. Bir öğeyi değere veya dizine göre aramak için sıralı arama gereklidir. Liste uzunsa bu arama yavaş olabilir.

Listede tek tek öğelerin dökümüne ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bu sınıfın belirli üye işlevleri, `CList` sınıfın çoğu kullanımı için özelleştirilmiş olması gereken genel yardımcı işlevleri çağırır. "Makrolar ve Geneller" [bölümündeki Koleksiyon Sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) bölümüne bakın.

Kullanma `CList`hakkında daha fazla bilgi için [Koleksiyonlar](../../mfc/collections.md)makalesine bakın.

## <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtempl.h

## <a name="clistaddhead"></a><a name="addhead"></a>CList::AddHead

Bu listenin başına yeni bir öğe veya öğe listesi ekler.

```
POSITION AddHead(ARG_TYPE newElement);
void AddHead(CList* pNewList);
```

### <a name="parameters"></a>Parametreler

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi (başvuru olabilir).

*newElement*<br/>
Yeni eleman.

*pNewList*<br/>
Başka bir `CList` listeye işaretçi. *pNewList'teki* öğeler bu listeye eklenir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni eklenen öğenin KONUM değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Liste işlemden önce boş olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]

## <a name="clistaddtail"></a><a name="addtail"></a>CList::AddTail

Bu listenin kuyruğuna yeni bir öğe veya öğe listesi ekler.

```
POSITION AddTail(ARG_TYPE newElement);
void AddTail(CList* pNewList);
```

### <a name="parameters"></a>Parametreler

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi (başvuru olabilir).

*newElement*<br/>
Bu listeye eklenecek öğe.

*pNewList*<br/>
Başka bir `CList` listeye işaretçi. *pNewList'teki* öğeler bu listeye eklenir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni eklenen öğenin KONUM değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Liste işlemden önce boş olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]

## <a name="clistclist"></a><a name="clist"></a>CList::CList

Boş bir sıralı liste oluşturuyor.

```
CList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Listeyi genişletmek için bellek ayırma parçalı.

### <a name="remarks"></a>Açıklamalar

Liste büyüdükçe, bellek *nBlockSize* girişleri birimlerine ayrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]

## <a name="clistfind"></a><a name="find"></a>CList::Bul

Belirtilen *searchValue*eşleşen ilk öğeyi bulmak için listeyi sırayla arar.

```
POSITION Find(
    ARG_TYPE searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>Parametreler

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi (başvuru olabilir).

*searchValue*<br/>
Listede bulunacak değer.

*başlangıçAfter*<br/>
Arama için başlangıç konumu. Değer belirtilmemişse, arama baş öğesi ile başlar.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilecek bir POSITION değeri; Nesne bulunamazsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]

## <a name="clistfindindex"></a><a name="findindex"></a>CList::FindIndex

listeye dizin olarak *nIndex* değerini kullanır.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Bulunacak liste öğesinin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilecek bir POSITION değeri; *nIndex* negatif veya çok büyükse NULL.

### <a name="remarks"></a>Açıklamalar

Listenin başından sıralı bir tbmö başlar ve *n*th öğesi üzerinde durur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]

## <a name="clistgetat"></a><a name="getat"></a>CList::Getat

Liste öğesini belirli bir konumda alır.

```
TYPE& GetAt(POSITION position);
const TYPE& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki nesne türünü belirten şablon parametresi.

*Konum*<br/>
Eleman listesindeki konum.

### <a name="return-value"></a>Dönüş Değeri

`GetHead`'nin getiri değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

`GetAt`belirli bir konumla ilişkili öğeyi (veya öğeye bir başvuruyu) döndürür. Bu bir dizin ile aynı değildir ve bir POSITION değeri üzerinde kendiniz çalışamazsınız. Tür POZISYON değişkeni liste için bir anahtardır.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

### <a name="example"></a>Örnek

  CList örneğine [bakın:GetHeadPosition](#getheadposition).

## <a name="clistgetcount"></a><a name="getcount"></a>CList::GetCount

Bu listedeki öğelerin sayısını alır.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eleman sayısını içeren bir sayıdeğeri.

### <a name="remarks"></a>Açıklamalar

Bu yöntemi [çağırmak, CList::GetSize](#getsize) yöntemiyle aynı sonucu oluşturur.

### <a name="example"></a>Örnek

  CList örneğine [bakın:RemoveHead](#removehead).

## <a name="clistgethead"></a><a name="gethead"></a>CList::GetHead

Bu listenin baş öğesini (veya baş öğesine bir başvuruyu) alır.

```
const TYPE& GetHead() const;

TYPE& GetHead();
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki nesne türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Liste **const**ise, `GetHead` listenin başındaöğenin bir kopyasını döndürür. Bu, işlevin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve listeyi değişiklikten korur.

Liste **const**değilse, `GetHead` listenin başındaki öğeye bir başvuru verir. Bu, işlevin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Aramadan `GetHead`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](#isempty) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]

## <a name="clistgetheadposition"></a><a name="getheadposition"></a>CList::GetHeadPosition

Bu listenin baş öğesinin konumunu alır.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilecek bir POSITION değeri; Liste boşsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]

## <a name="clistgetnext"></a><a name="getnext"></a>CList::GetNext

*rPosition*tarafından tanımlanan liste öğesini alır, ardından listedeki bir sonraki girişin KONUM değerine *rPosition'ı* ayarlar.

```
TYPE& GetNext(POSITION& rPosition);
const TYPE& GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki öğelerin türünü belirten şablon parametresi.

*Rposition*<br/>
Önceki , [GetHeadPosition](#getheadposition)veya `GetNext`diğer üye işlev çağrısı tarafından döndürülen bir POSITION değerine yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Liste **const**ise, `GetNext` listenin bir öğesinin bir kopyasını döndürür. Bu, işlevin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve listeyi değişiklikten korur.

Liste **const**değilse, `GetNext` listenin bir öğesiiçin bir başvuru döndürür. Bu, işlevin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Bir çağrı `GetNext` ile ilk konumu kurarsanız, bir ileri yineleme `GetHeadPosition` döngüsünde kullanabilirsiniz veya `Find`.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Alınan öğe listenin son öğesiyse, yeni değeri `rPosition` NULL olarak ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]

## <a name="clistgetprev"></a><a name="getprev"></a>CList::GetPrev

Liste öğesini, `rPosition`listedeki `rPosition` önceki girişin KONUM değerine ayarlar, sonra da tanımlar.

```
TYPE& GetPrev(POSITION& rPosition);
const TYPE& GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki öğelerin türünü belirten şablon parametresi.

*Rposition*<br/>
Önceki `GetPrev` veya diğer bir üye işlev çağrısı tarafından döndürülen POSITION değerine yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Liste **const**ise, `GetPrev` listenin başındaöğenin bir kopyasını döndürür. Bu, işlevin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve listeyi değişiklikten korur.

Liste **const**değilse, `GetPrev` listenin bir öğesiiçin bir başvuru döndürür. Bu, işlevin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Bir çağrı `GetPrev` ile ilk konumu kurarsanız ters yineleme döngüsünde `GetTailPosition` kullanabilirsiniz veya `Find`.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Alınan öğe listede ilk sıradaysa, *rPosition'un* yeni değeri NULL olarak ayarlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]

## <a name="clistgetsize"></a><a name="getsize"></a>CList::GetSize

Liste öğelerinin sayısını verir.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Listedeki öğe sayısını almak için bu yöntemi arayın.  Bu yöntemi [çağırmak, CList::GetCount](#getcount) yöntemiyle aynı sonucu oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]

## <a name="clistgettail"></a><a name="gettail"></a>CList::GetTail

Bu `CObject` listenin kuyruk öğesini temsil eden işaretçiyi alır.

```
TYPE& GetTail();
const TYPE& GetTail() const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

[GetHead](../../mfc/reference/coblist-class.md#gethead)için iade değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Aramadan `GetTail`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](../../mfc/reference/coblist-class.md#isempty) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]

## <a name="clistgettailposition"></a><a name="gettailposition"></a>CList::GetTailPosition

Bu listenin kuyruk elemanının konumunu alır; Liste boşsa NULL.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilecek bir POSITION değeri; Liste boşsa NULL.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]

## <a name="clistinsertafter"></a><a name="insertafter"></a>CList::InsertAfter

Belirtilen konumdaöğe sonra bu listeye bir öğe ekler.

```
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*Konum*<br/>
Önceki `GetNext`, `GetPrev`veya `Find` üye işlev çağrısı yla döndürülen bir POSITION değeri.

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi.

*newElement*<br/>
Bu listeye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya liste öğesi alımı için kullanılabilecek bir POSITION değeri.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]

## <a name="clistinsertbefore"></a><a name="insertbefore"></a>CList::EkleBefore

Belirtilen konumdaöğe önce bu listeye bir öğe ekler.

```
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*Konum*<br/>
Önceki `GetNext`, `GetPrev`veya `Find` üye işlev çağrısı yla döndürülen bir POSITION değeri.

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi (başvuru olabilir).

*newElement*<br/>
Bu listeye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya liste öğesi alımı için kullanılabilecek bir POSITION değeri.

### <a name="remarks"></a>Açıklamalar

*Konum* NULL ise, öğe listenin başına eklenir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]

## <a name="clistisempty"></a><a name="isempty"></a>CList::Boş

Bu listenin öğe içerip içermediğini gösterir.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu liste boşsa sıfırolmayan; aksi takdirde 0.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]

## <a name="clistremoveall"></a><a name="removeall"></a>CList::RemoveAll

Bu listeden tüm öğeleri kaldırır ve ilişkili belleği serbest sağlar.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Liste zaten boşsa hata oluşturulmadı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]

## <a name="clistremoveat"></a><a name="removeat"></a>CList::Removeat

Belirtilen öğeyi bu listeden kaldırır.

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Parametreler

*Konum*<br/>
Öğenin listeden kaldırılacak konumu.

### <a name="remarks"></a>Açıklamalar

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]

## <a name="clistremovehead"></a><a name="removehead"></a>CList::RemoveHead

Öğeyi listenin başından kaldırır ve bir işaretçi döndürür.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Öğe daha önce listenin başında.

### <a name="remarks"></a>Açıklamalar

Aramadan `RemoveHead`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](#isempty) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]

## <a name="clistremovetail"></a><a name="removetail"></a>CList::RemoveTail

Öğeyi listenin kuyruğundan kaldırır ve bir işaretçi döndürür.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listedeki öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Listenin kuyruğundaki öğe.

### <a name="remarks"></a>Açıklamalar

Aramadan `RemoveTail`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](#isempty) kullanın.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]

## <a name="clistsetat"></a><a name="setat"></a>CList::Setat

Tür POZISYON değişkeni liste için bir anahtardır.

```cpp
void SetAt(POSITION pos, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Ayarlanacak öğenin KONUMU.

*ARG_TYPE*<br/>
Liste öğesinin türünü belirten şablon parametresi (başvuru olabilir).

*newElement*<br/>
Listeye eklenecek öğe.

### <a name="remarks"></a>Açıklamalar

Bu bir dizin ile aynı değildir ve bir POSITION değeri üzerinde kendiniz çalışamazsınız. `SetAt`öğeyi listede belirtilen konuma yazar.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek TOPLAMA](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CMap Sınıfı](../../mfc/reference/cmap-class.md)<br/>
[CArray Sınıfı](../../mfc/reference/carray-class.md)
