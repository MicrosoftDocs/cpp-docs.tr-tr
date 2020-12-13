---
description: 'Daha fazla bilgi edinin: CObList sınıfı'
title: CObList sınıfı
ms.date: 11/04/2016
f1_keywords:
- CObList
- AFXCOLL/CObList
- AFXCOLL/CObList::CObList
- AFXCOLL/CObList::AddHead
- AFXCOLL/CObList::AddTail
- AFXCOLL/CObList::Find
- AFXCOLL/CObList::FindIndex
- AFXCOLL/CObList::GetAt
- AFXCOLL/CObList::GetCount
- AFXCOLL/CObList::GetHead
- AFXCOLL/CObList::GetHeadPosition
- AFXCOLL/CObList::GetNext
- AFXCOLL/CObList::GetPrev
- AFXCOLL/CObList::GetSize
- AFXCOLL/CObList::GetTail
- AFXCOLL/CObList::GetTailPosition
- AFXCOLL/CObList::InsertAfter
- AFXCOLL/CObList::InsertBefore
- AFXCOLL/CObList::IsEmpty
- AFXCOLL/CObList::RemoveAll
- AFXCOLL/CObList::RemoveAt
- AFXCOLL/CObList::RemoveHead
- AFXCOLL/CObList::RemoveTail
- AFXCOLL/CObList::SetAt
helpviewer_keywords:
- CObList [MFC], CObList
- CObList [MFC], AddHead
- CObList [MFC], AddTail
- CObList [MFC], Find
- CObList [MFC], FindIndex
- CObList [MFC], GetAt
- CObList [MFC], GetCount
- CObList [MFC], GetHead
- CObList [MFC], GetHeadPosition
- CObList [MFC], GetNext
- CObList [MFC], GetPrev
- CObList [MFC], GetSize
- CObList [MFC], GetTail
- CObList [MFC], GetTailPosition
- CObList [MFC], InsertAfter
- CObList [MFC], InsertBefore
- CObList [MFC], IsEmpty
- CObList [MFC], RemoveAll
- CObList [MFC], RemoveAt
- CObList [MFC], RemoveHead
- CObList [MFC], RemoveTail
- CObList [MFC], SetAt
ms.assetid: 80699c93-33d8-4f8b-b8cf-7b58aeab64ca
ms.openlocfilehash: edfa476780e07b41f4f1e0abede24244ad837578
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331447"
---
# <a name="coblist-class"></a>CObList sınıfı

`CObject`Ardışık olarak veya işaretçi değerine göre erişilebilen, benzersiz olmayan işaretçilerin sıralı listesini destekler.

## <a name="syntax"></a>Syntax

```
class CObList : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CObList:: CObList](#coblist)|İşaretçiler için boş bir liste oluşturur `CObject` .|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CObList:: AddHead](#addhead)|Listenin baş bir bir öğesini (veya başka bir listedeki tüm öğeleri) ekler (yeni bir baş oluşturur).|
|[CObList:: AddTail](#addtail)|Bir öğeyi (veya başka bir listedeki tüm öğeleri) listenin sonuna ekler (yeni bir kuyruk oluşturur).|
|[CObList:: Find](#find)|İşaretçi değeri tarafından belirtilen öğenin konumunu alır.|
|[CObList:: FindIndex](#findindex)|Sıfır tabanlı bir dizin tarafından belirtilen öğenin konumunu alır.|
|[CObList:: GetAt](#getat)|Belirtilen konumdaki öğeyi alır.|
|[CObList:: GetCount](#getcount)|Bu listedeki öğe sayısını döndürür.|
|[CObList:: GetHead](#gethead)|Listenin baş öğesini döndürür (boş olamaz).|
|[CObList:: GetHeadPosition](#getheadposition)|Listenin baş öğesinin konumunu döndürür.|
|[CObList:: GetNext](#getnext)|Yineleme için bir sonraki öğeyi alır.|
|[CObList:: Getöncekini](#getprev)|Yineleme için önceki öğeyi alır.|
|[CObList:: GetSize](#getsize)|Bu listedeki öğe sayısını döndürür.|
|[CObList:: GetTail](#gettail)|Listenin tail öğesini döndürür (boş olamaz).|
|[CObList:: Getbir Position](#gettailposition)|Listenin tail öğesinin konumunu döndürür.|
|[CObList:: InsertAfter](#insertafter)|Belirli bir konumdan sonra yeni bir öğe ekler.|
|[CObList:: InsertBefore](#insertbefore)|Belirli bir konumdan önce yeni bir öğe ekler.|
|[CObList:: IsEmpty](#isempty)|Boş liste koşulunu sınar (öğe yok).|
|[CObList:: RemoveAll](#removeall)|Bu listedeki tüm öğeleri kaldırır.|
|[CObList:: RemoveAt](#removeat)|Bu listeden, konuma göre belirtilen bir öğeyi kaldırır.|
|[CObList:: RemoveHead](#removehead)|Öğeyi listenin Başndan kaldırır.|
|[CObList:: RemoveTail](#removetail)|Öğeyi listenin tail öğesinden kaldırır.|
|[CObList:: SetAt](#setat)|Belirtilen konumdaki öğeyi ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CObList` listeler, benzer şekilde bağlantılı listeler gibi davranır.

POSITION türünde bir değişken, listenin bir anahtarıdır. Bir konum değişkenini hem bir yineleyici olarak hem de bir yeri tutacak bir yer işareti olarak çapraz bir şekilde gezmek için kullanabilirsiniz. Ancak bir konum bir dizinle aynı değildir.

Öğe ekleme, kuyruklu ve bilinen bir konumda liste başıyla çok hızlıdır. Bir öğeyi değere veya dizine göre aramak için sıralı bir arama gerekir. Liste uzunsa bu arama yavaş olabilir.

`CObList` öğelerinin serileştirilmesi ve dökümünü desteklemek için IMPLEMENT_SERIAL makrosunu ekler. Bir `CObject` işaretçiler listesi, aşırı yüklenmiş bir ekleme işleci veya üye işlevi ile bir arşive depolanıyorsa, `Serialize` her `CObject` öğe sırayla serileştirilir.

Listedeki ayrı öğelerin bir dökümünden birine ihtiyacınız varsa `CObject` , döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bir `CObList` nesne silindiğinde veya öğeleri kaldırıldığında, `CObject` başvurdukları nesneler değil yalnızca işaretçiler kaldırılır.

İçindeki kendi sınıflarınızı türetebilirsiniz `CObList` . Yeni liste sınıfınız, öğesinden türetilmiş nesnelere işaretçiler tutmak için tasarlanan yeni `CObject` veri üyeleri ve yeni üye işlevleri ekler. Sonuçta ortaya çıkan listenin, herhangi bir işaretçinin eklenmesine izin verdiğinden kesinlikle güvenli bir şekilde tür olmadığını unutmayın `CObject` .

> [!NOTE]
> Listeyi seri hale getirmek istiyorsanız türetilmiş sınıfınızın uygulamasındaki [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makrosunu kullanmanız gerekir.

Kullanma hakkında daha fazla bilgi için `CObList` bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

## <a name="coblistaddhead"></a><a name="addhead"></a> CObList:: AddHead

Bu listenin başından yeni bir öğe veya öğe listesi ekler.

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>Parametreler

*newElement*<br/>
`CObject`Bu listeye eklenecek işaretçi.

*pNewList*<br/>
Başka bir liste işaretçisi `CObList` . *PNewList* içindeki öğeler bu listeye eklenecektir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni takılan öğenin konum değerini döndürür.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::AddHead` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum AddHead (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddHead (CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum AddHead (const CString&** `newElement` **);**<br /><br /> **Konum AddHead (LPCTSTR** `newElement` **);**<br /><br /> **void AddHead (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="remarks"></a>Açıklamalar

İşlem öncesinde liste boş olabilir.

### <a name="example"></a>Örnek

  Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

## <a name="coblistaddtail"></a><a name="addtail"></a> CObList:: AddTail

Bu listenin kuyruğu için yeni bir öğe veya öğe listesi ekler.

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>Parametreler

*newElement*<br/>
`CObject`Bu listeye eklenecek işaretçi.

*pNewList*<br/>
Başka bir liste işaretçisi `CObList` . *PNewList* içindeki öğeler bu listeye eklenecektir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni takılan öğenin konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İşlem öncesinde liste boş olabilir.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::AddTail` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum AddTail (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddTail (CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum AddTail (const CString&** `newElement` **);**<br /><br /> **Konum AddTail (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="example"></a>Örnek

  Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

## <a name="coblistcoblist"></a><a name="coblist"></a> CObList:: CObList

Boş bir `CObject` işaretçi listesi oluşturur.

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Listeyi genişletmek için bellek ayırma ayrıntı düzeyi.

### <a name="remarks"></a>Açıklamalar

Liste büyüdükçe, bellek *nBlockSize* girdileri birimlerinde ayrılır. Bir bellek ayırma başarısız olursa, bir `CMemoryException` oluşturulur.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::CObList` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>Örnek

  Aşağıda, `CObject` `CAge` tüm koleksiyon örneklerinde kullanılan türetilmiş sınıfın bir listesi verilmiştir:

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

Aşağıda Oluşturucu kullanımı örneği verilmiştir `CObList` :

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

## <a name="coblistfind"></a><a name="find"></a> CObList:: Find

`CObject`Belirtilen işaretçiyle eşleşen ilk işaretçiyi bulmak için listeyi sıralı olarak arar `CObject` .

```
POSITION Find(
    CObject* searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>Parametreler

*searchValue*<br/>
Bu listede bulunan nesne işaretçisi.

*startAfter*<br/>
Arama için başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; Nesne bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

İşaretçi değerlerinin, nesnelerin içeriği değil, karşılaştırıldığını unutmayın.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::Find` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum bul (void** <strong>\*</strong> `searchValue` **, Konum** `startAfter` **= Null) sabit;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum bulma (LPCTSTR** `searchValue` **, POSITION** `startAfter` **= null) const;**|

### <a name="example"></a>Örnek

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

## <a name="coblistfindindex"></a><a name="findindex"></a> CObList:: FindIndex

Listede dizin olarak *nindex* değerini kullanır.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Bulunamayan liste öğesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; *NIndex* çok büyükse null. (Framework, *nIndex* negatifse bir onaylama işlemi oluşturur.)

### <a name="remarks"></a>Açıklamalar

Bu, *n*. öğesinde durdurulan, listenin başlarından sıralı bir tarama başlatır.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::FindIndex` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum FindIndex (INT_PTR** `nIndex` **) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum FindIndex (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>Örnek

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

## <a name="coblistgetat"></a><a name="getat"></a> CObList:: GetAt

POSITION türünde bir değişken, listenin bir anahtarıdır.

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parametreler

*yerine*<br/>
Önceki `GetHeadPosition` veya üye işlev çağrısı tarafından döndürülen BIR konum değeri `Find` .

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için dönüş değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Bir dizin ile aynı değildir ve bir konum değerinde kendiniz işlem yapılamaz. `GetAt``CObject`belirli bir konumla ilişkili işaretçiyi alır.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::GetAt` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void \*& GetAt (konum** *konumu* **) const;**<br /><br /> **\*& GetAt (konum** *konumu* **) void;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetAt (konum** *konumu* **) const;**<br /><br /> **CString& GetAt (konum** *konumu* **);**|

### <a name="example"></a>Örnek

  [FindIndex](#findindex)örneğine bakın.

## <a name="coblistgetcount"></a><a name="getcount"></a> CObList:: GetCount

Bu listedeki öğelerin sayısını alır.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısını içeren bir tamsayı değeri.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::GetCount` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetCount () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>Örnek

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

## <a name="coblistgethead"></a><a name="gethead"></a> CObList:: GetHead

`CObject`Bu listenin baş öğesini temsil eden işaretçiyi alır.

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listeye bir işaretçi aracılığıyla erişiliyorsa `const CObList` , bir `GetHead` `CObject` işaretçi döndürür. Bu, işlevin atama ifadesinin sağ tarafında kullanılmasına izin verir ve bu nedenle listenin değiştirilmesini önler.

Listeye doğrudan veya bir işaretçisi aracılığıyla erişiliyorsa, bir işaretçiye bir `CObList` `GetHead` başvuru döndürür `CObject` . Bu, işlevin atama ifadesinin her iki tarafında kullanılmasına izin verir ve bu nedenle liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `GetHead` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](#isempty) kullanın.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::GetHead` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void \*& GetHead () const; void \*& GetHead ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetHead () const; CString& GetHead ();**|

### <a name="example"></a>Örnek

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

Aşağıdaki örnek, `GetHead` bir atama ifadesinin sol tarafında kullanımını gösterir.

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

## <a name="coblistgetheadposition"></a><a name="getheadposition"></a> CObList:: GetHeadPosition

Bu listenin baş öğesinin konumunu alır.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; Liste boşsa NULL.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::GetHeadPosition` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum GetHeadPosition () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum GetHeadPosition () const;**|

### <a name="example"></a>Örnek

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

## <a name="coblistgetnext"></a><a name="getnext"></a> CObList:: GetNext

*RPosition* tarafından tanımlanan liste öğesini alır ve ardından listedeki bir  `POSITION` sonraki girdinin değerine rPosition değerini ayarlar.

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*rPosition*<br/>
Önceki `GetNext` , `GetHeadPosition` veya diğer üye işlev çağrısı tarafından döndürülen bir konum değerine başvuru.

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için dönüş değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Bir `GetNext` veya çağrısı ile ilk konumu oluşturursanız, bir ileri yineleme döngüsünde kullanabilirsiniz `GetHeadPosition` `Find` .

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Alınan öğe listedeki son ise, yeni *rPosition* değeri null olarak ayarlanır.

Yineleme sırasında bir öğeyi kaldırmak mümkündür. Bkz. [RemoveAt](#removeat)örneği.

> [!NOTE]
> MFC 8,0 itibariyle bu yöntemin const sürümü yerine döndürecek şekilde değiştirilmiştir `const CObject*` `const CObject*&` .  Bu değişiklik, derleyicinin C++ standardına uyum sağlamak için yapılmıştır.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::GetNext` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Örnek

  Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

## <a name="coblistgetprev"></a><a name="getprev"></a> CObList:: Getöncekini

*RPosition* tarafından tanımlanan liste öğesini alır ve ardından listedeki ÖNCEKI girdinin konum değerine *rPosition* değerini ayarlar.

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*rPosition*<br/>
Önceki `GetPrev` veya diğer üye işlev çağrısı tarafından döndürülen BIR konum değerine başvuru.

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için dönüş değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

`GetPrev`Bir veya çağrısı ile ilk konumu ayarlarsanız, bir ters yineleme döngüsünde kullanabilirsiniz `GetTailPosition` `Find` .

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Alınan öğe listedeki ilk ise, yeni *rPosition* değeri null olarak ayarlanır.

> [!NOTE]
> MFC 8,0 itibariyle bu yöntemin const sürümü yerine döndürecek şekilde değiştirilmiştir `const CObject*` `const CObject*&` .  Bu değişiklik, derleyicinin C++ standardına uyum sağlamak için yapılmıştır.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::GetPrev` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Örnek

  Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
a CAge at $421C 21
a CAge at $421C 40
```

## <a name="coblistgetsize"></a><a name="getsize"></a> CObList:: GetSize

Liste öğelerinin sayısını döndürür.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Listedeki öğe sayısını almak için bu yöntemi çağırın.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::GetSize` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetSize () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>Örnek

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

## <a name="coblistgettail"></a><a name="gettail"></a> CObList:: GetTail

`CObject`Bu listenin tail öğesini temsil eden işaretçiyi alır.

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için dönüş değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `GetTail` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](#isempty) kullanın.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::GetTail` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void \*& GetTail () const; void \*& GetTail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetTail () const; CString& GetTail ();**|

### <a name="example"></a>Örnek

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

## <a name="coblistgettailposition"></a><a name="gettailposition"></a> CObList:: Getbir Position

Bu listenin tail öğesinin konumunu alır; Liste boşsa **null** .

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; Liste boşsa NULL.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::GetTailPosition` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum Getbir position () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum Getbir position () const;**|

### <a name="example"></a>Örnek

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

## <a name="coblistinsertafter"></a><a name="insertafter"></a> CObList:: InsertAfter

Belirtilen konumdaki öğeden sonra bu listeye bir öğe ekler.

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*yerine*<br/>
Previous `GetNext` , `GetPrev` veya `Find` member Function çağrısı tarafından döndürülen bir konum değeri.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::InsertAfter` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum InsertAfter (konum** *konumu* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Pozisyon InsertAfter (konum** *konumu* **, const CString&** `newElement` **);**<br /><br /> **Konum InsertAfter (konum** *konumu* **, LPCTSTR** `newElement` **);**|

### <a name="return-value"></a>Dönüş Değeri

*Konum* parametresiyle aynı olan bir konum değeri.

### <a name="example"></a>Örnek

  Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

## <a name="coblistinsertbefore"></a><a name="insertbefore"></a> CObList:: InsertBefore

Bu listeye, belirtilen konumdaki öğeden önce bir öğe ekler.

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*yerine*<br/>
Previous `GetNext` , `GetPrev` veya `Find` member Function çağrısı tarafından döndürülen bir konum değeri.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; Liste boşsa NULL.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::InsertBefore` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**InsertBefore konumu (konum** *konumu* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**InsertBefore konumu (konum** *konumu* **, const CString&** `newElement` **);**<br /><br /> **InsertBefore konumu (konum** *konumu* **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Örnek

  Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

## <a name="coblistisempty"></a><a name="isempty"></a> CObList:: IsEmpty

Bu listenin hiç öğe içerip içermediğini gösterir.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu liste boşsa sıfır dışı; Aksi takdirde 0.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::IsEmpty` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty () const;**|

### <a name="example"></a>Örnek

  [RemoveAll](#removeall)için örneğe bakın.

## <a name="coblistremoveall"></a><a name="removeall"></a> CObList:: RemoveAll

Bu listedeki tüm öğeleri kaldırır ve ilişkili belleği serbest bırakır `CObList` .

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Liste zaten boşsa bir hata oluşturulmaz.

Öğeleri bir öğesinden kaldırdığınızda `CObList` , nesne işaretçilerini listeden kaldırırsınız. Nesnelerin kendilerini silme sorumluluğu sizin sorumluluğunuzdadır.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::RemoveAll` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAll ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll ();**|

### <a name="example"></a>Örnek

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

## <a name="coblistremoveat"></a><a name="removeat"></a> CObList:: RemoveAt

Belirtilen öğeyi bu listeden kaldırır.

```cpp
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Parametreler

*yerine*<br/>
Listeden kaldırılacak öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Bir öğeyi bir öğesinden kaldırdığınızda `CObList` , nesne işaretçisini listeden kaldırırsınız. Nesnelerin kendilerini silme sorumluluğu sizin sorumluluğunuzdadır.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::RemoveAt` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (konum** *konumu* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (konum** *konumu* **);**|

### <a name="example"></a>Örnek

  Liste yinelemesi sırasında bir öğeyi kaldırırken dikkatli olun. Aşağıdaki örnek, [GetNext](#getnext)için geçerli bir **konum** değerini garanti eden bir kaldırma tekniği gösterir.

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

## <a name="coblistremovehead"></a><a name="removehead"></a> CObList:: RemoveHead

Öğeyi listenin baş öğesinden kaldırır ve ona bir işaretçi döndürür.

```
CObject* RemoveHead();
```

### <a name="return-value"></a>Dönüş Değeri

`CObject`İşaretçi daha önce listenin başbaşında.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `RemoveHead` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](#isempty) kullanın.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::RemoveHead` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void \* RemoveHead ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|

### <a name="example"></a>Örnek

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

## <a name="coblistremovetail"></a><a name="removetail"></a> CObList:: RemoveTail

Öğeyi listenin kuyruğunu kaldırır ve ona bir işaretçi döndürür.

```
CObject* RemoveTail();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin sonunda olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Çağrılmadan önce listenin boş olmadığından emin olmanız gerekir `RemoveTail` . Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](#isempty) kullanın.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::RemoveTail` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void \* RemoveTail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|

### <a name="example"></a>Örnek

Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

## <a name="coblistsetat"></a><a name="setat"></a> CObList:: SetAt

Belirtilen konumdaki öğeyi ayarlar.

```cpp
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Ayarlanacak öğenin konumu.

*newElement*<br/>
`CObject`Listeye yazılacak işaretçi.

### <a name="remarks"></a>Açıklamalar

POSITION türünde bir değişken, listenin bir anahtarıdır. Bir dizin ile aynı değildir ve bir konum değerinde kendiniz işlem yapılamaz. `SetAt``CObject`işaretçiyi listede belirtilen konuma yazar.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Aşağıdaki tabloda şuna benzer diğer üye işlevleri gösterilmektedir `CObList::SetAt` .

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**SetAt void (konum** `pos` **, const CString&** `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**SetAt void (konum** `pos` **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Örnek

  Sınıfın listesi için bkz. [CObList:: CObList](#coblist) `CAge` .

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CStringList sınıfı](../../mfc/reference/cstringlist-class.md)<br/>
[CPtrList sınıfı](../../mfc/reference/cptrlist-class.md)
