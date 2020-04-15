---
title: CTypedPtrList Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
ms.openlocfilehash: 40dbfb822e71309e9675aba14d46d333ffa4ee06
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373271"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList Sınıfı

Sınıf `CPtrList`nesneleri için tür güvenli bir "sarmalayıcı" sağlar.

## <a name="syntax"></a>Sözdizimi

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrList : public BASE_CLASS
```

#### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Yazılan işaretçi listesi sınıfının taban sınıfı; işaretçi listesi sınıfı `CObList` (veya) `CPtrList`olmalıdır.

*TÜR*<br/>
Taban sınıf listesinde depolanan öğelerin türü.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CTypedPtrList::AddHead](#addhead)|Listenin başına bir öğe (veya başka bir listedeki tüm öğeler) ekler (yeni bir kafa yapar).|
|[CTypedPtrList::AddTail](#addtail)|Listenin kuyruğuna bir öğe (veya başka bir listedeki tüm öğeler) ekler (yeni bir kuyruk yapar).|
|[CTypedPtrList::GetAt](#getat)|Öğeyi belirli bir konumda alır.|
|[CTypedPtrList::GetHead](#gethead)|Listenin baş öğesini verir (boş olamaz).|
|[CTypedPtrList::GetNext](#getnext)|Yinelenmenin bir sonraki öğesini alır.|
|[CTypedPtrList::GetPrev](#getprev)|Yinelenmeiçin önceki öğeyi alır.|
|[CTypedPtrList::GetTail](#gettail)|Listenin kuyruk öğesini verir (boş olamaz).|
|[CTypedPtrList::RemoveHead](#removehead)|Öğeyi listenin başından kaldırır.|
|[CTypedPtrList::RemoveTail](#removetail)|Öğeyi listenin kuyruğundan kaldırır.|
|[CTypedPtrList::SetAt](#setat)|Öğeyi belirli bir konumda ayarlar.|

## <a name="remarks"></a>Açıklamalar

C++ `CTypedPtrList` yazı `CObList` denetimi `CPtrList`tesisi yerine veya yerine kullandığınızda, eşleşmeyan işaretçi türlerinin neden olduğu hataların giderilmesine yardımcı olur.

Buna ek `CTypedPtrList` olarak, sarıcı kullandıysanız `CObList` veya `CPtrList`gerekli olacak döküm çok gerçekleştirir.

Tüm `CTypedPtrList` işlevler satır lı olduğundan, bu şablonun kullanımı kodunuzun boyutunu veya hızını önemli ölçüde etkilemez.

Türetilen `CObList` listeler seri hale getirilebilir, `CPtrList` ancak türetilenler serileştirilemez.

Bir `CTypedPtrList` nesne silindiğinde veya öğeleri kaldırıldığında, başvurulan varlıklar değil, yalnızca işaretçiler kaldırılır.

Kullanma `CTypedPtrList`hakkında daha fazla bilgi için [Koleksiyonlar](../../mfc/collections.md) ve [Şablon Tabanlı Sınıflar](../../mfc/template-based-classes.md)makalelerine bakın.

## <a name="example"></a>Örnek

Bu örnek, bir `CTypedPtrList`nesne ekler, listeyi diske serileştirir ve sonra nesneyi siler:

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtempl.h

## <a name="ctypedptrlistaddhead"></a><a name="addhead"></a>CTypedPtrList::AddHead

Bu üye `BASE_CLASS`işlev **::AddHead**.

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Taban sınıf listesinde depolanan öğelerin türü.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi. NULL değerine izin verilir.

*BASE_CLASS*<br/>
Yazılan işaretçi listesi sınıfının taban sınıfı; işaretçi listesi sınıfı [(CObList](../../mfc/reference/coblist-class.md) veya [CPtrList)](../../mfc/reference/cptrlist-class.md)olmalıdır.

*pNewList*<br/>
Başka bir [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) nesnesine işaretçi. *pNewList'teki* öğeler bu listeye eklenir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni eklenen öğenin KONUM değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm, listenin başına yeni bir öğe ekler. İkinci sürüm, kafadan önce başka bir öğe listesi ekler.

## <a name="ctypedptrlistaddtail"></a><a name="addtail"></a>CTypedPtrList::AddTail

Bu üye `BASE_CLASS`işlev **::AddTail**.

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Taban sınıf listesinde depolanan öğelerin türü.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi. NULL değerine izin verilir.

*BASE_CLASS*<br/>
Yazılan işaretçi listesi sınıfının taban sınıfı; işaretçi listesi sınıfı [(CObList](../../mfc/reference/coblist-class.md) veya [CPtrList)](../../mfc/reference/cptrlist-class.md)olmalıdır.

*pNewList*<br/>
Başka bir [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) nesnesine işaretçi. *pNewList'teki* öğeler bu listeye eklenir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni eklenen öğenin KONUM değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm, listenin kuyruğundan sonra yeni bir öğe ekler. İkinci sürüm, listenin kuyruğundan sonra başka bir öğe listesi ekler.

## <a name="ctypedptrlistgetat"></a><a name="getat"></a>CTypedPtrList::GetAt

Tür POZISYON değişkeni liste için bir anahtardır.

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan öğelerin türünü belirten şablon parametresi.

*Konum*<br/>
Önceki `GetHeadPosition` veya `Find` üye işlev çağrısı yla döndürülen BIR POSITION değeri.

### <a name="return-value"></a>Dönüş Değeri

Listeye bir `const CTypedPtrList`işaretçi aracılığıyla erişilirse, şablon parametresi `GetAt` *TYPE*tarafından belirtilen türün işaretçisini döndürür. Bu, işlevin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve böylece listeyi değişiklikten korur.

Listeye doğrudan veya bir işaretçi aracılığıyla `CTypedPtrList`erişilirse, şablon `GetAt` parametre *TÜRÜ*tarafından belirtilen türdeki bir işaretçiye başvuru verir. Bu, işlevin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Bu bir dizin ile aynı değildir ve bir POSITION değeri üzerinde kendiniz çalışamazsınız. `GetAt`belirli bir `CObject` konumla ilişkili işaretçiyi alır.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Bu satır satırlı fonksiyon çağırır `BASE_CLASS` **::GetAt**.

## <a name="ctypedptrlistgethead"></a><a name="gethead"></a>CTypedPtrList::GetHead

Bu listenin baş öğesini temsil eden işaretçiyi alır.

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Listeye bir `const CTypedPtrList`işaretçi aracılığıyla erişilirse, şablon parametresi `GetHead` *TYPE*tarafından belirtilen türün işaretçisini döndürür. Bu, işlevin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve böylece listeyi değişiklikten korur.

Listeye doğrudan veya bir işaretçi aracılığıyla `CTypedPtrList`erişilirse, şablon `GetHead` parametre *TÜRÜ*tarafından belirtilen türdeki bir işaretçiye başvuru verir. Bu, işlevin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Aramadan `GetHead`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](../../mfc/reference/coblist-class.md#isempty) kullanın.

## <a name="ctypedptrlistgetnext"></a><a name="getnext"></a>CTypedPtrList::GetNext

*rPosition*tarafından tanımlanan liste öğesini alır, ardından listedeki bir sonraki girişin KONUM değerine *rPosition'ı* ayarlar.

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Bu listede yer alan öğelerin türünü belirten şablon parametresi.

*Rposition*<br/>
Önceki `GetNext`, `GetHeadPosition`veya diğer üye işlev çağrısı tarafından döndürülen bir POSITION değerine yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Listeye bir `const CTypedPtrList`işaretçi aracılığıyla erişilirse, şablon parametresi `GetNext` *TYPE*tarafından belirtilen türün işaretçisini döndürür. Bu, işlevin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve böylece listeyi değişiklikten korur.

Listeye doğrudan veya bir işaretçi aracılığıyla `CTypedPtrList`erişilirse, şablon `GetNext` parametre *TÜRÜ*tarafından belirtilen türdeki bir işaretçiye başvuru verir. Bu, işlevin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Bir çağrı `GetNext` `GetHeadPosition` veya [CPtrList](../../mfc/reference/coblist-class.md#find)ile ilk konumu kurarsanız bir ileri yineleme döngüsü kullanabilirsiniz::Bul .

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Alınan öğe listenin son öğesiyse, *rPosition'un* yeni değeri NULL olarak ayarlanır.

Bir yineleme sırasında bir öğeyi kaldırmak mümkündür. CObList için örneğe [bakın:RemoveAt](../../mfc/reference/coblist-class.md#removeat).

## <a name="ctypedptrlistgetprev"></a><a name="getprev"></a>CTypedPtrList::GetPrev

*rPosition*tarafından tanımlanan liste öğesini alır, ardından listedeki önceki girişin KONUM değerine *rPosition'ı* ayarlar.

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Bu listede yer alan öğelerin türünü belirten şablon parametresi.

*Rposition*<br/>
Önceki `GetPrev` veya diğer bir üye işlev çağrısı tarafından döndürülen POSITION değerine yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

Listeye bir `const CTypedPtrList`işaretçi aracılığıyla erişilirse, şablon parametresi `GetPrev` *TYPE*tarafından belirtilen türün işaretçisini döndürür. Bu, işlevin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve böylece listeyi değişiklikten korur.

Listeye doğrudan veya bir işaretçi aracılığıyla `CTypedPtrList`erişilirse, şablon `GetPrev` parametre *TÜRÜ*tarafından belirtilen türdeki bir işaretçiye başvuru verir. Bu, işlevin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Bir çağrı `GetPrev` ile ilk konumu kurarsanız ters yineleme döngüsünde `GetTailPosition` kullanabilirsiniz veya `Find`.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Alınan öğe listede ilk sıradaysa, *rPosition'un* yeni değeri NULL olarak ayarlanır.

## <a name="ctypedptrlistgettail"></a><a name="gettail"></a>CTypedPtrList::GetTail

Bu listenin baş öğesini temsil eden işaretçiyi alır.

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Listeye bir `const CTypedPtrList`işaretçi aracılığıyla erişilirse, şablon parametresi `GetTail` *TYPE*tarafından belirtilen türün işaretçisini döndürür. Bu, işlevin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve böylece listeyi değişiklikten korur.

Listeye doğrudan veya bir işaretçi aracılığıyla `CTypedPtrList`erişilirse, şablon `GetTail` parametre *TÜRÜ*tarafından belirtilen türdeki bir işaretçiye başvuru verir. Bu, işlevin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Aramadan `GetTail`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](../../mfc/reference/coblist-class.md#isempty) kullanın.

## <a name="ctypedptrlistremovehead"></a><a name="removehead"></a>CTypedPtrList::RemoveHead

Öğeyi listenin başından kaldırır ve döndürür.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

İşaretçi daha önce listenin başında. Bu işaretçi, şablon parametresi *TYPE*tarafından belirtilen türdendir.

### <a name="remarks"></a>Açıklamalar

Aramadan `RemoveHead`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](../../mfc/reference/coblist-class.md#isempty) kullanın.

## <a name="ctypedptrlistremovetail"></a><a name="removetail"></a>CTypedPtrList::RemoveTail

Öğeyi listenin kuyruğundan kaldırır ve döndürür.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

İşaretçi daha önce listenin kuyruğunda. Bu işaretçi, şablon parametresi *TYPE*tarafından belirtilen türdendir.

### <a name="remarks"></a>Açıklamalar

Aramadan `RemoveTail`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](../../mfc/reference/coblist-class.md#isempty) kullanın.

## <a name="ctypedptrlistsetat"></a><a name="setat"></a>CTypedPtrList::SetAt

Bu üye `BASE_CLASS`işlev **::SetAt.**

```
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Ayarlanacak öğenin KONUMU.

*TÜR*<br/>
Taban sınıf listesinde depolanan öğelerin türü.

*newElement*<br/>
Listeye yazılacak nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

Tür POZISYON değişkeni liste için bir anahtardır. Bu bir dizin ile aynı değildir ve bir POSITION değeri üzerinde kendiniz çalışamazsınız. `SetAt`nesne işaretçisini listede belirtilen konuma yazar.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Daha ayrıntılı açıklamalar için [CObList::SetAt'a](../../mfc/reference/coblist-class.md#setat)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek TOPLAMA](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPtrList Sınıfı](../../mfc/reference/cptrlist-class.md)<br/>
[CObList Sınıfı](../../mfc/reference/coblist-class.md)
