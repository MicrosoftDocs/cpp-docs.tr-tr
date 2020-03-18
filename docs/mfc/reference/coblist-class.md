---
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
ms.openlocfilehash: 2fc3a3643c675394de555f1411030e278bcee775
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79416874"
---
# <a name="coblist-class"></a>CObList sınıfı

, ardışık olmayan `CObject` işaretçilerin sıralı listesini sıralı olarak veya işaretçi değerine göre erişilebilir olarak destekler.

## <a name="syntax"></a>Sözdizimi

```
class CObList : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Name|Açıklama|
|----------|-----------------|
|[CObList:: CObList](#coblist)|`CObject` işaretçileri için boş bir liste oluşturur.|

### <a name="public-methods"></a>Ortak Yöntemler

|Name|Açıklama|
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

`CObList`, öğelerinin serileştirilmesi ve dökümünü desteklemek için IMPLEMENT_SERIAL makrosunu içerir. `CObject` işaretçileri listesi, aşırı yüklenmiş bir ekleme işleci veya `Serialize` member işlevi ile bir arşive depolanıyorsa, her bir `CObject` öğesi sırasıyla serileştirilir.

Listedeki ayrı `CObject` öğelerinin bir dökümünden birine ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

`CObList` nesne silindiğinde veya öğeleri kaldırıldığında, başvurdukları nesneler değil yalnızca `CObject` işaretçileri kaldırılır.

`CObList`, kendi sınıflarınızı türetebilirsiniz. `CObject`türetilen nesnelerin işaretçilerini tutmak için tasarlanan yeni liste sınıfınız, yeni veri üyeleri ve yeni üye işlevleri ekler. `CObject` işaretçisinin eklenmesine izin verdiğinden, sonuçta elde edilen listenin kesinlikle güvenli olmadığını unutmayın.

> [!NOTE]
>  Listeyi seri hale getirmek istiyorsanız türetilmiş sınıfınızın uygulamasındaki [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makrosunu kullanmanız gerekir.

`CObList`kullanma hakkında daha fazla bilgi için bkz. Makale [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll. h

##  <a name="addhead"></a>CObList:: AddHead

Bu listenin başından yeni bir öğe veya öğe listesi ekler.

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>Parametreler

*newElement*<br/>
Bu listeye eklenecek `CObject` işaretçisi.

*pNewList*<br/>
Başka bir `CObList` listesine yönelik bir işaretçi. *PNewList* içindeki öğeler bu listeye eklenecektir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni takılan öğenin konum değerini döndürür.

Aşağıdaki tabloda, `CObList::AddHead`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum AddHead (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddHead (CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum AddHead (const CString &** `newElement` **);**<br /><br /> **Konum AddHead (LPCTSTR** `newElement` **);**<br /><br /> **void AddHead (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="remarks"></a>Açıklamalar

İşlem öncesinde liste boş olabilir.

### <a name="example"></a>Örnek

  `CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

##  <a name="addtail"></a>CObList:: AddTail

Bu listenin kuyruğu için yeni bir öğe veya öğe listesi ekler.

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>Parametreler

*newElement*<br/>
Bu listeye eklenecek `CObject` işaretçisi.

*pNewList*<br/>
Başka bir `CObList` listesine yönelik bir işaretçi. *PNewList* içindeki öğeler bu listeye eklenecektir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni takılan öğenin konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

İşlem öncesinde liste boş olabilir.

Aşağıdaki tabloda, `CObList::AddTail`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum AddTail (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddTail (CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum AddTail (const CString &** `newElement` **);**<br /><br /> **Konum AddTail (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="example"></a>Örnek

  `CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

##  <a name="coblist"></a>CObList:: CObList

Boş bir `CObject` işaretçi listesi oluşturur.

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Listeyi genişletmek için bellek ayırma ayrıntı düzeyi.

### <a name="remarks"></a>Açıklamalar

Liste büyüdükçe, bellek *nBlockSize* girdileri birimlerinde ayrılır. Bir bellek ayırma başarısız olursa, bir `CMemoryException` oluşturulur.

Aşağıdaki tabloda, `CObList::CObList`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>Örnek

  Aşağıda, tüm koleksiyon örneklerinde kullanılan `CAge` `CObject`türetilmiş sınıfın bir listesi verilmiştir:

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

Aşağıda `CObList` Oluşturucu kullanımı örneği verilmiştir:

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

##  <a name="find"></a>CObList:: Find

Belirtilen `CObject` işaretçiyle eşleşen ilk `CObject` işaretçiyi bulmak için listeyi sıralı olarak arar.

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

Aşağıdaki tabloda, `CObList::Find`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum bulma (void** <strong>\*</strong> `searchValue` **, konum** `startAfter` **= null) sabit;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum bulma (LPCTSTR** `searchValue` **, konum** `startAfter` **= null) sabit;**|

### <a name="example"></a>Örnek

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

##  <a name="findindex"></a>CObList:: FindIndex

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

Aşağıdaki tabloda, `CObList::FindIndex`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum FindIndex (INT_PTR** `nIndex` **) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum FindIndex (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>Örnek

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

##  <a name="getat"></a>CObList:: GetAt

POSITION türünde bir değişken, listenin bir anahtarıdır.

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parametreler

*yerine*<br/>
Önceki bir `GetHeadPosition` veya `Find` üye işlev çağrısı tarafından döndürülen bir konum değeri.

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için dönüş değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Bir dizin ile aynı değildir ve bir konum değerinde kendiniz işlem yapılamaz. `GetAt`, belirli bir konumla ilişkili `CObject` işaretçisini alır.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Aşağıdaki tabloda, `CObList::GetAt`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetAt (konum** *konumu* **) const;**<br /><br /> **\*& GetAt (konum** *konumu* **) void;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetAt (konum** *konumu* **) const;**<br /><br /> **CString & GetAt (konum** *konumu* **);**|

### <a name="example"></a>Örnek

  [FindIndex](#findindex)örneğine bakın.

##  <a name="getcount"></a>CObList:: GetCount

Bu listedeki öğelerin sayısını alır.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısını içeren bir tamsayı değeri.

Aşağıdaki tabloda, `CObList::GetCount`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetCount () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>Örnek

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

##  <a name="gethead"></a>CObList:: GetHead

Bu listenin baş öğesini temsil eden `CObject` işaretçisini alır.

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listeye bir `const CObList`işaretçi aracılığıyla erişiliyorsa `GetHead` `CObject` bir işaretçi döndürür. Bu, işlevin atama ifadesinin sağ tarafında kullanılmasına izin verir ve bu nedenle listenin değiştirilmesini önler.

Listeye doğrudan veya bir `CObList`işaretçisi aracılığıyla erişiliyorsa `GetHead` `CObject` işaretçisine bir başvuru döndürür. Bu, işlevin atama ifadesinin her iki tarafında kullanılmasına izin verir ve bu nedenle liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

`GetHead`çağrılmadan önce listenin boş olmadığından emin olmanız gerekir. Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](#isempty) kullanın.

Aşağıdaki tabloda, `CObList::GetHead`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetHead () const; void\*& GetHead ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetHead () const; CString & GetHead ();**|

### <a name="example"></a>Örnek

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

Aşağıdaki örnek, bir atama ifadesinin sol tarafında `GetHead` kullanımını gösterir.

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

##  <a name="getheadposition"></a>CObList:: GetHeadPosition

Bu listenin baş öğesinin konumunu alır.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; Liste boşsa NULL.

Aşağıdaki tabloda, `CObList::GetHeadPosition`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum GetHeadPosition () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum GetHeadPosition () const;**|

### <a name="example"></a>Örnek

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

##  <a name="getnext"></a>CObList:: GetNext

*RPosition*tarafından tanımlanan liste öğesini alır ve ardından listedeki bir sonraki girdinin `POSITION` değerini *rPosition* olarak ayarlar.

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*rPosition*<br/>
Önceki bir `GetNext`, `GetHeadPosition`veya diğer üye işlev çağrısı tarafından döndürülen bir konum değerine başvuru.

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için dönüş değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

İlk konumu `GetHeadPosition` veya `Find`çağrısıyla birlikte ayarlarsanız, bir iletme yineleme döngüsünde `GetNext` kullanabilirsiniz.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Alınan öğe listedeki son ise, yeni *rPosition* değeri null olarak ayarlanır.

Yineleme sırasında bir öğeyi kaldırmak mümkündür. Bkz. [RemoveAt](#removeat)örneği.

> [!NOTE]
>  MFC 8,0 itibariyle bu yöntemin const sürümü `const CObject*&`yerine `const CObject*` döndürecek şekilde değiştirilmiştir.  Bu değişiklik, derleyicinin C++ standartta uyum sağlamak için yapılmıştır.

Aşağıdaki tabloda, `CObList::GetNext`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Örnek

  `CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

##  <a name="getprev"></a>CObList:: Getöncekini

*RPosition*tarafından tanımlanan liste öğesini alır ve ardından listedeki ÖNCEKI girdinin konum değerine *rPosition* değerini ayarlar.

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*rPosition*<br/>
Önceki bir `GetPrev` veya diğer üye işlev çağrısı tarafından döndürülen bir konum değerine başvuru.

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için dönüş değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

İlk konumu `GetTailPosition` veya `Find`çağrısıyla birlikte ayarlarsanız, ters yineleme döngüsünde `GetPrev` kullanabilirsiniz.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Alınan öğe listedeki ilk ise, yeni *rPosition* değeri null olarak ayarlanır.

> [!NOTE]
>  MFC 8,0 itibariyle bu yöntemin const sürümü `const CObject*&`yerine `const CObject*` döndürecek şekilde değiştirilmiştir.  Bu değişiklik, derleyicinin C++ standartta uyum sağlamak için yapılmıştır.

Aşağıdaki tabloda, `CObList::GetPrev`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Örnek

  `CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
a CAge at $421C 21
a CAge at $421C 40
```

##  <a name="getsize"></a>CObList:: GetSize

Liste öğelerinin sayısını döndürür.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Listedeki öğe sayısını almak için bu yöntemi çağırın.

Aşağıdaki tabloda, `CObList::GetSize`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetSize () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>Örnek

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

##  <a name="gettail"></a>CObList:: GetTail

Bu listenin tail öğesini temsil eden `CObject` işaretçisini alır.

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için dönüş değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

`GetTail`çağrılmadan önce listenin boş olmadığından emin olmanız gerekir. Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](#isempty) kullanın.

Aşağıdaki tabloda, `CObList::GetTail`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetTail () const; void\*& GetTail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetTail () const; CString & GetTail ();**|

### <a name="example"></a>Örnek

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

##  <a name="gettailposition"></a>CObList:: Getbir Position

Bu listenin tail öğesinin konumunu alır; Liste boşsa **null** .

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; Liste boşsa NULL.

Aşağıdaki tabloda, `CObList::GetTailPosition`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum Getbir position () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum Getbir position () const;**|

### <a name="example"></a>Örnek

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

##  <a name="insertafter"></a>CObList:: InsertAfter

Belirtilen konumdaki öğeden sonra bu listeye bir öğe ekler.

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*yerine*<br/>
Önceki bir `GetNext`, `GetPrev`veya `Find` üye işlev çağrısı tarafından döndürülen bir konum değeri.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi.

Aşağıdaki tabloda, `CObList::InsertAfter`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Pozisyon InsertAfter (konum** *konumu* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum InsertAfter (konum** *konumu* **, const CString &** `newElement` **);**<br /><br /> **Pozisyon InsertAfter (konum** *konumu* **, LPCTSTR** `newElement` **);**|

### <a name="return-value"></a>Dönüş Değeri

*Konum* parametresiyle aynı olan bir konum değeri.

### <a name="example"></a>Örnek

  `CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

##  <a name="insertbefore"></a>CObList:: InsertBefore

Bu listeye, belirtilen konumdaki öğeden önce bir öğe ekler.

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*yerine*<br/>
Önceki bir `GetNext`, `GetPrev`veya `Find` üye işlev çağrısı tarafından döndürülen bir konum değeri.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilen bir konum değeri; Liste boşsa NULL.

Aşağıdaki tabloda, `CObList::InsertBefore`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**InsertBefore konumu (konum** *konumu* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**InsertBefore konumu (konum** *konumu* **, const CString &** `newElement` **);**<br /><br /> **InsertBefore konumu (konum** *konumu* **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Örnek

  `CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

##  <a name="isempty"></a>CObList:: IsEmpty

Bu listenin hiç öğe içerip içermediğini gösterir.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu liste boşsa sıfır dışı; Aksi takdirde 0.

Aşağıdaki tabloda, `CObList::IsEmpty`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty () const;**|

### <a name="example"></a>Örnek

  [RemoveAll](#removeall)için örneğe bakın.

##  <a name="removeall"></a>CObList:: RemoveAll

Bu listedeki tüm öğeleri kaldırır ve ilişkili `CObList` belleği serbest bırakır.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Liste zaten boşsa bir hata oluşturulmaz.

Öğeleri `CObList`kaldırdığınızda, nesne işaretçilerini listeden kaldırırsınız. Nesnelerin kendilerini silme sorumluluğu sizin sorumluluğunuzdadır.

Aşağıdaki tabloda, `CObList::RemoveAll`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAll ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll ();**|

### <a name="example"></a>Örnek

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

##  <a name="removeat"></a>CObList:: RemoveAt

Belirtilen öğeyi bu listeden kaldırır.

```
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Parametreler

*yerine*<br/>
Listeden kaldırılacak öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Bir öğeyi `CObList`kaldırdığınızda, nesne işaretçisini listeden kaldırırsınız. Nesnelerin kendilerini silme sorumluluğu sizin sorumluluğunuzdadır.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Aşağıdaki tabloda, `CObList::RemoveAt`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (konum** *konumu* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (konum** *konumu* **);**|

### <a name="example"></a>Örnek

  Liste yinelemesi sırasında bir öğeyi kaldırırken dikkatli olun. Aşağıdaki örnek, [GetNext](#getnext)için geçerli bir **konum** değerini garanti eden bir kaldırma tekniği gösterir.

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

##  <a name="removehead"></a>CObList:: RemoveHead

Öğeyi listenin baş öğesinden kaldırır ve ona bir işaretçi döndürür.

```
CObject* RemoveHead();
```

### <a name="return-value"></a>Dönüş Değeri

`CObject` işaretçi daha önce listenin başbaşında.

### <a name="remarks"></a>Açıklamalar

`RemoveHead`çağrılmadan önce listenin boş olmadığından emin olmanız gerekir. Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](#isempty) kullanın.

Aşağıdaki tabloda, `CObList::RemoveHead`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**RemoveHead ()\* void;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|

### <a name="example"></a>Örnek

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

##  <a name="removetail"></a>CObList:: RemoveTail

Öğeyi listenin kuyruğunu kaldırır ve ona bir işaretçi döndürür.

```
CObject* RemoveTail();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin sonunda olan nesneye yönelik bir işaretçi.

### <a name="remarks"></a>Açıklamalar

`RemoveTail`çağrılmadan önce listenin boş olmadığından emin olmanız gerekir. Liste boşsa Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Listenin öğeler içerdiğini doğrulamak için [IsEmpty](#isempty) kullanın.

Aşağıdaki tabloda, `CObList::RemoveTail`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**RemoveTail ()\* void;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|

### <a name="example"></a>Örnek

`CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

##  <a name="setat"></a>CObList:: SetAt

Belirtilen konumdaki öğeyi ayarlar.

```
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Ayarlanacak öğenin konumu.

*newElement*<br/>
Listeye yazılacak `CObject` işaretçisi.

### <a name="remarks"></a>Açıklamalar

POSITION türünde bir değişken, listenin bir anahtarıdır. Bir dizin ile aynı değildir ve bir konum değerinde kendiniz işlem yapılamaz. `SetAt` `CObject` işaretçisini listede belirtilen konuma yazar.

KONUM değerinin listede geçerli bir konumu temsil ettiğinden emin olmanız gerekir. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.

Aşağıdaki tabloda, `CObList::SetAt`benzer diğer üye işlevleri gösterilmektedir.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**SetAt void (konum** `pos` **, const CString &** `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**SetAt void (konum** `pos` **, lpctstr** `newElement` **);**|

### <a name="example"></a>Örnek

  `CAge` sınıfının listesi için bkz. [CObList:: CObList](#coblist) .

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CStringList Sınıfı](../../mfc/reference/cstringlist-class.md)<br/>
[CPtrList Sınıfı](../../mfc/reference/cptrlist-class.md)
