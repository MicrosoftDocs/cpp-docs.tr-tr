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
ms.openlocfilehash: 66cc4d28e20ced498e4a434efbe41c3f5db59370
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605211"
---
# <a name="coblist-class"></a>CObList sınıfı

Sipariş edilen listelerini listeler fSupports `CObject` işaretçileri erişilebilir sırayla veya işaretçinin değerine göre.

## <a name="syntax"></a>Sözdizimi

```
class CObList : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CObList::CObList](#coblist)|İçin boş bir liste oluşturur `CObject` işaretçileri.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CObList::AddHead](#addhead)|Bir öğenin (veya başka bir listedeki tüm öğeleri) (yeni head sağlar) listenin başındaki ekler.|
|[CObList::AddTail](#addtail)|Bir öğenin (veya başka bir listedeki tüm öğeleri) (yeni bir kuyruk sağlar) listesi kuyruğu için ekler.|
|[CObList::Find](#find)|İşaretçi değeri tarafından belirtilen bir öğenin konumunu alır.|
|[CObList::FindIndex](#findindex)|Sıfır tabanlı bir dizin tarafından belirtilen bir öğenin konumunu alır.|
|[CObList::GetAt](#getat)|Öğesini, belirli bir konumda alır.|
|[CObList::GetCount](#getcount)|Bu listedeki öğelerin sayısını döndürür.|
|[CObList::GetHead](#gethead)|Head öğesi (boş olamaz) listesi döndürür.|
|[CObList::GetHeadPosition](#getheadposition)|Head öğesi listesinin konumunu döndürür.|
|[CObList::GetNext](#getnext)|Yineleme için sonraki öğeyi alır.|
|[CObList::GetPrev](#getprev)|Yineleme için önceki öğeyi alır.|
|[CObList::GetSize](#getsize)|Bu listedeki öğelerin sayısını döndürür.|
|[CObList::GetTail](#gettail)|Kuyruk öğesini (boş olamaz) listesi döndürür.|
|[CObList::GetTailPosition](#gettailposition)|Listenin tail öğenin konumunu döndürür.|
|[CObList::InsertAfter](#insertafter)|Belirli bir pozisyon sonra yeni bir öğe ekler.|
|[CObList::InsertBefore](#insertbefore)|Belirli bir pozisyon önce yeni bir öğe ekler.|
|[CObList::IsEmpty](#isempty)|(Öğe yok) boş liste koşulu sınar.|
|[CObList::RemoveAll](#removeall)|Bu listeden tüm öğeleri kaldırır.|
|[CObList::RemoveAt](#removeat)|Belirtilen konuma göre bu listeden bir öğeyi kaldırır.|
|[CObList::RemoveHead](#removehead)|Öğe listesinin başından kaldırır.|
|[CObList::RemoveTail](#removetail)|Öğe listesinin kuyruğunu kaldırır.|
|[CObList::SetAt](#setat)|Öğe, belirli bir konumda ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CObList` listeleri karakteriyle bağlantılı liste gibi davranır.

KONUM türünde bir değişken listesi için bir anahtardır. Bir konumu değişkeni listesini sırayla geçiş için bir yineleyici olarak hem bir yerde tutmak için bir yer işareti olarak kullanabilirsiniz. Bir konum bir dizin aynı ancak değildir.

Öğe ekleme listesi sonunda, kuyruk ve bilinen bir konuma çok hızlı olması. Sıralı bir arama değeri veya dizin tarafından bir öğesini aramak gereklidir. Bu arama liste uzunsa yavaş olabilir.

`CObList` Serileştirme ve alt öğeleri dökme desteklemek için ımplement_serıal makrosu içerir. Bir listesini, `CObject` işaretçiler veya aşırı yüklenmiş bir ekleme operatörü ile birlikte bir arşivden depolandığı `Serialize` her üye işlev `CObject` öğesi sırayla seri.

Tek bir dökümü gerekiyorsa `CObject` listesindeki öğeleri, ayarlamalısınız döküm bağlam derinliğini 1 veya daha büyük.

Olduğunda bir `CObList` nesnesi silindiğinde veya ne zaman öğeleri kaldırılır, yalnızca `CObject` işaretçileri kaldırılır, nesneleri başvuruyor.

Kendi sınıfları türetebilirsiniz `CObList`. Öğesinden türetilen nesnelerine işaretçiler tutmak için tasarlanmış yeni liste sınıfınızı `CObject`, yeni veri üyeleri ve yeni üye işlevleri ekler. Herhangi bir ekleme izin verdiğinden sonuç listesini kesinlikle türü güvenli olmadığını unutmayın `CObject` işaretçi.

> [!NOTE]
>  Kullanmalısınız [ımplement_serıal](run-time-object-model-services.md#implement_serial) uygulanmasında bir liste serileştirmek istiyorsanız, türetilmiş sınıfınızın makrosu.

Kullanma hakkında daha fazla bilgi için `CObList`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxcoll.h

##  <a name="addhead"></a>  CObList::AddHead

Bu listenin başındaki yeni bir öğe veya öğe listesi ekler.

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>Parametreler

*newElement*<br/>
`CObject` Bu listeye eklenmesi için işaretçi.

*pNewList*<br/>
Başka bir işaretçiye `CObList` listesi. Öğeleri *pNewList* bu listeye eklenir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürümü, yeni eklenen öğenin KONUMUNU değerini döndürür.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::AddHead`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum AddHead (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddHead (CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum AddHead (const CString &** `newElement` **);**<br /><br /> **Konum AddHead (LPCTSTR** `newElement` **);**<br /><br /> **void AddHead (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="remarks"></a>Açıklamalar

Liste işlemi önce boş olabilir.

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

##  <a name="addtail"></a>  CObList::AddTail

Bu liste kuyruğu için yeni bir öğe veya öğe listesi ekler.

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>Parametreler

*newElement*<br/>
`CObject` Bu listeye eklenmesi için işaretçi.

*pNewList*<br/>
Başka bir işaretçiye `CObList` listesi. Öğeleri *pNewList* bu listeye eklenir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürümü, yeni eklenen öğenin KONUMUNU değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Liste işlemi önce boş olabilir.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::AddTail`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum AddTail (void** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddTail (CPtrList** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum AddTail (const CString &** `newElement` **);**<br /><br /> **Konum AddTail (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail (CStringList** <strong>\*</strong> `pNewList` **);**|

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

##  <a name="coblist"></a>  CObList::CObList

Boş bir yapıları `CObject` işaretçi listesi.

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Listeyi genişletmek için bellek ayırma ayrıntı düzeyi.

### <a name="remarks"></a>Açıklamalar

Liste genişledikçe birimleri cinsinden ayrılan bellek *nBlockSize* girdileri. Bellek ayırma başarısız olursa bir `CMemoryException` oluşturulur.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::CObList`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|

### <a name="example"></a>Örnek

  Bir listesi aşağıdadır `CObject`-türetilmiş sınıf `CAge` tüm koleksiyon örneklerde kullanılan:

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

Bir örnek aşağıdadır `CObList` Oluşturucu Kullanım:

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

##  <a name="find"></a>  CObList::Find

Sıralı olarak ilk bulmak için liste arar `CObject` belirtilen eşleşen işaretçi `CObject` işaretçi.

```
POSITION Find(
    CObject* searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>Parametreler

*searchValue*<br/>
Bu listede bulunması nesne işaretçisi.

*startAfter*<br/>
Arama için başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılan konum değeri; Nesne bulunmazsa null değerini DÖNDÜRÜR.

### <a name="remarks"></a>Açıklamalar

İşaretçi değerlerin karşılaştırılmasını Not, nesneleri içeriğini.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::Find`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum Bul (void** <strong>\*</strong> `searchValue` **, konumu** `startAfter` **= NULL) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum Bul (LPCTSTR** `searchValue` **, konumu** `startAfter` **= NULL) const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

##  <a name="findindex"></a>  CObList::FindIndex

Değerini kullanır *nIndex* listesine bir dizin olarak.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*nIndex*<br/>
Bulunacak liste öğesinin sıfır tabanlı dizini.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılan konum değeri; NULL ise *nIndex* çok büyük. (Framework, bir onaylama işlemi oluşturur *nIndex* negatiftir.)

### <a name="remarks"></a>Açıklamalar

Üzerinde durdurma listenin başındaki sıralı bir tarama başlatılır *n*öğedeki.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::FindIndex`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**FindIndex konumu (INT_PTR** `nIndex` **) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**FindIndex konumu (INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

##  <a name="getat"></a>  CObList::GetAt

KONUM türünde bir değişken listesi için bir anahtardır.

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parametreler

*Konumu*<br/>
Bir önceki tarafından döndürülen bir konum değeri `GetHeadPosition` veya `Find` üye işlev çağrısı.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri açıklamasına bakın [GetHead](#gethead).

### <a name="remarks"></a>Açıklamalar

Bu dizin ile aynı değildir ve üzerinde bir konum değeri kendiniz çalışamaz. `GetAt` alır `CObject` işaretçi verilen bir konumu ile ilişkili.

KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::GetAt`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetAt (konum** *konumu* **) const;**<br /><br /> **void\*& GetAt (konum** *konumu* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetAt (konum** *konumu* **) const;**<br /><br /> **CString & GetAt (konum** *konumu* **);**|

### <a name="example"></a>Örnek

  Örneğin bakın [findIndex](#findindex).

##  <a name="getcount"></a>  CObList::GetCount

Bu listedeki öğe sayısını alır.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe sayısını içeren bir tamsayı değeri.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::GetCount`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetCount () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetCount () const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

##  <a name="gethead"></a>  CObList::GetHead

Alır `CObject` head öğesi, bu listenin temsil eden bir işaretçi.

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listenin işaretçi üzerinden erişiliyorsa bir `const CObList`, ardından `GetHead` döndürür bir `CObject` işaretçi. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece liste değişikliklere karşı korur.

Listeden doğrudan veya bir işaretçiyle çok erişildiği durumda bir `CObList`, ardından `GetHead` bir başvuru döndürür bir `CObject` işaretçi. Bu işlev, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.

### <a name="remarks"></a>Açıklamalar

Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `GetHead`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::GetHead`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetHead () const; void\*& GetHead ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetHead () const; CString & GetHead ();**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

Aşağıdaki örnek, kullanımını gösterir `GetHead` Atama ifadesinin sol tarafında.

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

##  <a name="getheadposition"></a>  CObList::GetHeadPosition

Bu listenin baş öğenin konumunu alır.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılan konum değeri; Liste boş ise NULL değerini DÖNDÜRÜR.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::GetHeadPosition`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**GetHeadPosition (const) getirin;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**GetHeadPosition (const) getirin;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

##  <a name="getnext"></a>  CObList::GetNext

Tarafından tanımlanan liste öğesi alır *rPosition*, ardından ayarlar *rPosition* için `POSITION` listedeki sonraki giriş değeri.

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*rPosition*<br/>
Bir önceki tarafından döndürülen bir konum değeri başvurusu `GetNext`, `GetHeadPosition`, ya da diğer üye işlev çağrısı.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri açıklamasına bakın [GetHead](#gethead).

### <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz `GetNext` çağrısıyla ilk konumunu kurarsanız ileriye doğru yineleme döngüsünde `GetHeadPosition` veya `Find`.

KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.

Alınan öğe listesinde, son öğesinin yeni değeri ise *rPosition* NULL olarak ayarlandı.

Bir yineleme sırasında bir öğe kaldırmak mümkündür. Örneğin bakın [RemoveAt](#removeat).

> [!NOTE]
>  MFC 8.0 itibarıyla döndürmek için bu yöntem const sürümü değişti `const CObject*` yerine `const CObject*&`.  Bu değişiklik, derleyici standart C++ ile uyumluluk için yapılmıştır.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::GetNext`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

##  <a name="getprev"></a>  CObList::GetPrev

Tarafından tanımlanan liste öğesi alır *rPosition*, ardından ayarlar *rPosition* konumu değerine listesinde önceki girişi.

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*rPosition*<br/>
Bir önceki tarafından döndürülen bir konum değeri başvurusu `GetPrev` veya diğer üye işlev çağrısı.

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri açıklamasına bakın [GetHead](#gethead).

### <a name="remarks"></a>Açıklamalar

Kullanabileceğiniz `GetPrev` çağrısıyla ilk konumunu kurarsanız geriye doğru yineleme döngüsünde `GetTailPosition` veya `Find`.

KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.

Alınan öğe listesinde ilk yeni değeri ise *rPosition* NULL olarak ayarlandı.

> [!NOTE]
>  MFC 8.0 itibarıyla döndürmek için bu yöntem const sürümü değişti `const CObject*` yerine `const CObject*&`.  Bu değişiklik, derleyici standart C++ ile uyumluluk için yapılmıştır.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::GetPrev`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
a CAge at $421C 21
a CAge at $421C 40
```

##  <a name="getsize"></a>  CObList::GetSize

Liste öğelerin sayısını döndürür.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Listedeki öğe sayısını almak için bu yöntemi çağırın.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::GetSize`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetSize () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetSize () const;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

##  <a name="gettail"></a>  CObList::GetTail

Alır `CObject` Kuyruk öğesi bu listenin temsil eden bir işaretçi.

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dönüş değeri açıklamasına bakın [GetHead](#gethead).

### <a name="remarks"></a>Açıklamalar

Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `GetTail`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::GetTail`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetTail () const; void\*& GetTail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetTail () const; CString & GetTail ();**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

##  <a name="gettailposition"></a>  CObList::GetTailPosition

Bu listenin tail öğenin konumunu alır; **NULL** liste boşsa.

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılan konum değeri; Liste boş ise NULL değerini DÖNDÜRÜR.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::GetTailPosition`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**GetTailPosition (const) getirin;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**GetTailPosition (const) getirin;**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

##  <a name="insertafter"></a>  CObList::InsertAfter

Belirli bir konumda öğesinden sonra bu listeye bir öğe ekler.

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*Konumu*<br/>
Bir önceki tarafından döndürülen bir konum değeri `GetNext`, `GetPrev`, veya `Find` üye işlev çağrısı.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::InsertAfter`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum InsertAfter (konum** *konumu* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum InsertAfter (konum** *konumu* **, const CString &** `newElement` **);**<br /><br /> **Konum InsertAfter (konum** *konumu* **, LPCTSTR** `newElement` **);**|

### <a name="return-value"></a>Dönüş Değeri

Aynı olan bir konum değeri olarak *konumu* parametresi.

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

##  <a name="insertbefore"></a>  CObList::InsertBefore

Belirli bir konumda öğesinden önce bu listeye bir öğe ekler.

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*Konumu*<br/>
Bir önceki tarafından döndürülen bir konum değeri `GetNext`, `GetPrev`, veya `Find` üye işlev çağrısı.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılan konum değeri; Liste boş ise NULL değerini DÖNDÜRÜR.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::InsertBefore`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum Insertbefore (konum** *konumu* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum Insertbefore (konum** *konumu* **, const CString &** `newElement` **);**<br /><br /> **Konum Insertbefore (konum** *konumu* **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

##  <a name="isempty"></a>  CObList::IsEmpty

Bu listeye öğe içerip içermediğini belirtir.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu listenin boş olduğunu olursa sıfır dışı; Aksi durumda 0.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::IsEmpty`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty () const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty () const;**|

### <a name="example"></a>Örnek

  Örneğin bakın [RemoveAll](#removeall).

##  <a name="removeall"></a>  CObList::RemoveAll

Tüm öğeleri bu listeden kaldırır ve ilişkili boşaltır `CObList` bellek.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Liste boş ise, bir hata oluşturulmaz.

Öğeleri kaldırdığınızda bir `CObList`, nesne işaretçileri listeden kaldırın. Bu nesneleri silmek için sizin sorumluluğunuzdur.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::RemoveAll`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAll( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll( );**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

##  <a name="removeat"></a>  CObList::RemoveAt

Belirtilen öğeyi listeden kaldırır.

```
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Parametreler

*Konumu*<br/>
Listeden kaldırılacak öğenin konumu.

### <a name="remarks"></a>Açıklamalar

Bir öğeyi kaldırdığınızda bir `CObList`, nesne işaretçisi listeden kaldırın. Bu nesneleri silmek için sizin sorumluluğunuzdur.

KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::RemoveAt`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (konum** *konumu* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (konum** *konumu* **);**|

### <a name="example"></a>Örnek

  Bir öğe listesi yineleme sırasında silerken dikkatli olun. Aşağıdaki örnek, geçerli bir garanti eden bir temizleme teknik gösterir **konumu** değerini [GetNext](#getnext).

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

Bu program sonuçları aşağıdaki gibidir:

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

##  <a name="removehead"></a>  CObList::RemoveHead

Öğe listesinin başından kaldırır ve bir işaretçi döndürür.

```
CObject* RemoveHead();
```

### <a name="return-value"></a>Dönüş Değeri

`CObject` Listenin başındaki işaretçisinde daha önce.

### <a name="remarks"></a>Açıklamalar

Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `RemoveHead`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::RemoveHead`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveHead ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

##  <a name="removetail"></a>  CObList::RemoveTail

Listenin kuyruğunu öğeyi kaldırır ve bir işaretçi döndürür.

```
CObject* RemoveTail();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin kuyruğunu nesnesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `RemoveTail`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::RemoveTail`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveTail ();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|

### <a name="example"></a>Örnek

Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

##  <a name="setat"></a>  CObList::SetAt

Öğe, belirli bir konumda ayarlar.

```
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Ayarlanacak öğenin konumu.

*newElement*<br/>
`CObject` Listesine yazılacak işaretçi.

### <a name="remarks"></a>Açıklamalar

KONUM türünde bir değişken listesi için bir anahtardır. Bu dizin ile aynı değildir ve üzerinde bir konum değeri kendiniz çalışamaz. `SetAt` Yazar `CObject` listede belirtilen konuma işaretçisi.

KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.

Aşağıdaki tablo diğer üye benzer işlevleri gösterir `CObList::SetAt`.

|örneği|Üye İşlevi|
|-----------|---------------------|
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void SetAt (konum** `pos` **, const CString &** `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt (konum** `pos` **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Örnek

  Bkz: [CObList::CObList](#coblist) bir listesi için `CAge` sınıfı.

[!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]

Bu program sonuçları aşağıdaki gibidir:

```Output
SetAt example: A CObList with 2 elements
a CAge at $4D98 40
a CAge at $4DB8 65
```

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CStringList Sınıfı](../../mfc/reference/cstringlist-class.md)<br/>
[CPtrList Sınıfı](../../mfc/reference/cptrlist-class.md)
