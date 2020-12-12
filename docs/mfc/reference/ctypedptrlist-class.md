---
description: 'Daha fazla bilgi edinin: CTypedPtrList sınıfı'
title: CTypedPtrList sınıfı
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
ms.openlocfilehash: 353e9af00b1366b260ce3cb3689018a8e4e370c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318539"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList sınıfı

Sınıfının nesneleri için tür açısından güvenli bir "sarmalayıcı" sağlar `CPtrList` .

## <a name="syntax"></a>Sözdizimi

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrList : public BASE_CLASS
```

#### <a name="parameters"></a>Parametreler

*BASE_CLASS*<br/>
Türü belirtilmiş işaretçi listesi sınıfının temel sınıfı; bir işaretçi listesi sınıfı ( `CObList` veya) olmalıdır `CPtrList` .

*TÜR*<br/>
Temel sınıf listesinde depolanan öğelerin türü.

## <a name="members"></a>Üyeler

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CTypedPtrList:: AddHead](#addhead)|Listenin baş bir bir öğesini (veya başka bir listedeki tüm öğeleri) ekler (yeni bir baş oluşturur).|
|[CTypedPtrList:: AddTail](#addtail)|Bir öğeyi (veya başka bir listedeki tüm öğeleri) listenin sonuna ekler (yeni bir kuyruk oluşturur).|
|[CTypedPtrList:: GetAt](#getat)|Belirtilen konumdaki öğeyi alır.|
|[CTypedPtrList:: GetHead](#gethead)|Listenin baş öğesini döndürür (boş olamaz).|
|[CTypedPtrList:: GetNext](#getnext)|Yineleme için bir sonraki öğeyi alır.|
|[CTypedPtrList:: Getöncekini](#getprev)|Yineleme için önceki öğeyi alır.|
|[CTypedPtrList:: GetTail](#gettail)|Listenin tail öğesini döndürür (boş olamaz).|
|[CTypedPtrList:: RemoveHead](#removehead)|Öğeyi listenin Başndan kaldırır.|
|[CTypedPtrList:: RemoveTail](#removetail)|Öğeyi listenin tail öğesinden kaldırır.|
|[CTypedPtrList:: SetAt](#setat)|Belirtilen konumdaki öğeyi ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CTypedPtrList`Ya da yerine kullandığınızda `CObList` `CPtrList` , C++ tür denetimi özelliği eşleşmeyen işaretçi türleri nedeniyle oluşan hataları ortadan kaldırmaya yardımcı olur.

Ayrıca `CTypedPtrList` sarmalayıcı, veya kullandıysanız gerekli olacak çok sayıda atama gerçekleştirir `CObList` `CPtrList` .

Tüm `CTypedPtrList` işlevler satır içi olduğundan, bu şablonun kullanımı kodunuzun boyutunu veya hızını önemli ölçüde etkilemez.

Öğesinden türetilen listeler `CObList` seri hale getirilebilir, ancak öğesinden türetiliyor `CPtrList` .

Bir `CTypedPtrList` nesne silindiğinde veya öğeleri kaldırıldığında, başvurdukları varlıkların değil yalnızca işaretçiler kaldırılır.

Kullanma hakkında daha fazla bilgi için `CTypedPtrList` bkz. Makale [koleksiyonları](../../mfc/collections.md) ve [şablon tabanlı sınıflar](../../mfc/template-based-classes.md).

## <a name="example"></a>Örnek

Bu örnek, bir örneği oluşturur `CTypedPtrList` , bir nesnesi ekler, listeyi diske serileştirir ve sonra nesneyi siler:

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxtempl. h

## <a name="ctypedptrlistaddhead"></a><a name="addhead"></a> CTypedPtrList:: AddHead

Bu üye işlevi `BASE_CLASS` **:: AddHead** çağırır.

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Temel sınıf listesinde depolanan öğelerin türü.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi. NULL değere izin verilir.

*BASE_CLASS*<br/>
Türü belirtilmiş işaretçi listesi sınıfının temel sınıfı; bir işaretçi listesi sınıfı ( [CObList](../../mfc/reference/coblist-class.md) veya [CPtrList](../../mfc/reference/cptrlist-class.md)) olmalıdır.

*pNewList*<br/>
Başka bir [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) nesnesine yönelik bir işaretçi. *PNewList* içindeki öğeler bu listeye eklenecektir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni takılan öğenin konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm, listenin başından önce yeni bir öğe ekler. İkinci sürüm, başından önceki bir öğe listesi ekler.

## <a name="ctypedptrlistaddtail"></a><a name="addtail"></a> CTypedPtrList:: AddTail

Bu üye işlevi `BASE_CLASS` **:: AddTail** çağırır.

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Temel sınıf listesinde depolanan öğelerin türü.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi. NULL değere izin verilir.

*BASE_CLASS*<br/>
Türü belirtilmiş işaretçi listesi sınıfının temel sınıfı; bir işaretçi listesi sınıfı ( [CObList](../../mfc/reference/coblist-class.md) veya [CPtrList](../../mfc/reference/cptrlist-class.md)) olmalıdır.

*pNewList*<br/>
Başka bir [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) nesnesine yönelik bir işaretçi. *PNewList* içindeki öğeler bu listeye eklenecektir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni takılan öğenin konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İlk sürüm, listenin kuyruğunu tamamladıktan sonra yeni bir öğe ekler. İkinci sürüm, listenin kuyruğunu ardına bir öğe listesi ekler.

## <a name="ctypedptrlistgetat"></a><a name="getat"></a> CTypedPtrList:: GetAt

POSITION türünde bir değişken, listenin bir anahtarıdır.

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan öğelerin türünü belirten şablon parametresi.

*yerine*<br/>
Önceki `GetHeadPosition` veya üye işlev çağrısı tarafından döndürülen BIR konum değeri `Find` .

### <a name="return-value"></a>Dönüş Değeri

Listeye bir işaretçi aracılığıyla erişiliyorsa `const CTypedPtrList` , `GetAt` şablon parametre *türü* tarafından belirtilen türün bir işaretçisini döndürür. Bu, işlevin atama ifadesinin sağ tarafında kullanılmasına izin verir ve bu nedenle listenin değiştirilmesini önler.

Listeye doğrudan veya bir işaretçisi aracılığıyla erişiliyorsa `CTypedPtrList` , `GetAt` şablon parametre *türü* tarafından belirtilen türün işaretçisine bir başvuru döndürür. Bu, işlevin atama ifadesinin her iki tarafında kullanılmasına izin verir ve bu nedenle liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Bir dizin ile aynı değildir ve bir konum değerinde kendiniz işlem yapılamaz. `GetAt``CObject`belirli bir konumla ilişkili işaretçiyi alır.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Bu satır içi işlev `BASE_CLASS` **:: GetAt** çağırır.

## <a name="ctypedptrlistgethead"></a><a name="gethead"></a> CTypedPtrList:: GetHead

Bu listenin baş öğesini temsil eden işaretçiyi alır.

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Listeye bir işaretçi aracılığıyla erişiliyorsa `const CTypedPtrList` , `GetHead` şablon parametre *türü* tarafından belirtilen türün bir işaretçisini döndürür. Bu, işlevin atama ifadesinin sağ tarafında kullanılmasına izin verir ve bu nedenle listenin değiştirilmesini önler.

Listeye doğrudan veya bir işaretçisi aracılığıyla erişiliyorsa `CTypedPtrList` , `GetHead` şablon parametre *türü* tarafından belirtilen türün işaretçisine bir başvuru döndürür. Bu, işlevin atama ifadesinin her iki tarafında kullanılmasına izin verir ve bu nedenle liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `GetHead` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](../../mfc/reference/coblist-class.md#isempty) kullanın.

## <a name="ctypedptrlistgetnext"></a><a name="getnext"></a> CTypedPtrList:: GetNext

*RPosition* tarafından tanımlanan liste öğesini alır ve ardından listedeki bir sonrakı girdinin konum değerine *rPosition* değerini ayarlar.

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Bu listede yer alan öğelerin türünü belirten şablon parametresi.

*rPosition*<br/>
Önceki `GetNext` , `GetHeadPosition` veya diğer üye işlev çağrısı tarafından döndürülen bir konum değerine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Listeye bir işaretçi aracılığıyla erişiliyorsa `const CTypedPtrList` , `GetNext` şablon parametre *türü* tarafından belirtilen türün bir işaretçisini döndürür. Bu, işlevin atama ifadesinin sağ tarafında kullanılmasına izin verir ve bu nedenle listenin değiştirilmesini önler.

Listeye doğrudan veya bir işaretçisi aracılığıyla erişiliyorsa `CTypedPtrList` , `GetNext` şablon parametre *türü* tarafından belirtilen türün işaretçisine bir başvuru döndürür. Bu, işlevin atama ifadesinin her iki tarafında kullanılmasına izin verir ve bu nedenle liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

`GetNext`Başlangıç konumunu bir `GetHeadPosition` veya [CPtrList:: Find](../../mfc/reference/coblist-class.md#find)çağrısıyla ayarlarsanız, bir ileri yineleme döngüsünde kullanabilirsiniz.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Alınan öğe listedeki son ise, yeni *rPosition* değeri null olarak ayarlanır.

Yineleme sırasında bir öğeyi kaldırmak mümkündür. [CObList:: RemoveAt](../../mfc/reference/coblist-class.md#removeat)örneğine bakın.

## <a name="ctypedptrlistgetprev"></a><a name="getprev"></a> CTypedPtrList:: Getöncekini

*RPosition* tarafından tanımlanan liste öğesini alır ve ardından listedeki ÖNCEKI girdinin konum değerine *rPosition* değerini ayarlar.

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Bu listede yer alan öğelerin türünü belirten şablon parametresi.

*rPosition*<br/>
Önceki `GetPrev` veya diğer üye işlev çağrısı tarafından döndürülen BIR konum değerine başvuru.

### <a name="return-value"></a>Dönüş Değeri

Listeye bir işaretçi aracılığıyla erişiliyorsa `const CTypedPtrList` , `GetPrev` şablon parametre *türü* tarafından belirtilen türün bir işaretçisini döndürür. Bu, işlevin atama ifadesinin sağ tarafında kullanılmasına izin verir ve bu nedenle listenin değiştirilmesini önler.

Listeye doğrudan veya bir işaretçisi aracılığıyla erişiliyorsa `CTypedPtrList` , `GetPrev` şablon parametre *türü* tarafından belirtilen türün işaretçisine bir başvuru döndürür. Bu, işlevin atama ifadesinin her iki tarafında kullanılmasına izin verir ve bu nedenle liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

`GetPrev`Bir veya çağrısı ile ilk konumu ayarlarsanız, bir ters yineleme döngüsünde kullanabilirsiniz `GetTailPosition` `Find` .

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Alınan öğe listedeki ilk ise, yeni *rPosition* değeri null olarak ayarlanır.

## <a name="ctypedptrlistgettail"></a><a name="gettail"></a> CTypedPtrList:: GetTail

Bu listenin baş öğesini temsil eden işaretçiyi alır.

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Listeye bir işaretçi aracılığıyla erişiliyorsa `const CTypedPtrList` , `GetTail` şablon parametre *türü* tarafından belirtilen türün bir işaretçisini döndürür. Bu, işlevin atama ifadesinin sağ tarafında kullanılmasına izin verir ve bu nedenle listenin değiştirilmesini önler.

Listeye doğrudan veya bir işaretçisi aracılığıyla erişiliyorsa `CTypedPtrList` , `GetTail` şablon parametre *türü* tarafından belirtilen türün işaretçisine bir başvuru döndürür. Bu, işlevin atama ifadesinin her iki tarafında kullanılmasına izin verir ve bu nedenle liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `GetTail` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](../../mfc/reference/coblist-class.md#isempty) kullanın.

## <a name="ctypedptrlistremovehead"></a><a name="removehead"></a> CTypedPtrList:: RemoveHead

Öğeyi listenin Başndan kaldırır ve döndürür.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

İşaretçi daha önce listenin başbaşında. Bu işaretçi, şablon parametre *türü* tarafından belirtilen türdür.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `RemoveHead` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](../../mfc/reference/coblist-class.md#isempty) kullanın.

## <a name="ctypedptrlistremovetail"></a><a name="removetail"></a> CTypedPtrList:: RemoveTail

Öğeyi listenin kuyruğunu kaldırır ve döndürür.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Listede depolanan öğelerin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

İşaretçi daha önce listenin sonunda. Bu işaretçi, şablon parametre *türü* tarafından belirtilen türdür.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `RemoveTail` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](../../mfc/reference/coblist-class.md#isempty) kullanın.

## <a name="ctypedptrlistsetat"></a><a name="setat"></a> CTypedPtrList:: SetAt

Bu üye işlevi `BASE_CLASS` **:: SetAt** çağırır.

```cpp
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Ayarlanacak öğenin konumu.

*TÜR*<br/>
Temel sınıf listesinde depolanan öğelerin türü.

*newElement*<br/>
Listeye yazılacak nesne işaretçisi.

### <a name="remarks"></a>Açıklamalar

POSITION türünde bir değişken, listenin bir anahtarıdır. Bir dizin ile aynı değildir ve bir konum değerinde kendiniz işlem yapılamaz. `SetAt` nesne işaretçisini listede belirtilen konuma yazar.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Daha ayrıntılı açıklamalar için bkz. [CObList:: SetAt](../../mfc/reference/coblist-class.md#setat).

## <a name="see-also"></a>Ayrıca bkz.

[MFC örnek toplama](../../overview/visual-cpp-samples.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CPtrList sınıfı](../../mfc/reference/cptrlist-class.md)<br/>
[CObList sınıfı](../../mfc/reference/coblist-class.md)
