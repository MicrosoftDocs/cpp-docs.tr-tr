---
title: CObList Sınıfı
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
ms.openlocfilehash: cccd45bf5a97ae7dcc8369015e0a431b3a9e960f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360365"
---
# <a name="coblist-class"></a>CObList Sınıfı

fSıralı olarak veya `CObject` işaretçi değerine göre erişilebilen benzersiz olmayan işaretçilerin sıralı listelerini destekler.

## <a name="syntax"></a>Sözdizimi

```
class CObList : public CObject
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CObList::coblist](#coblist)|İşaretçiler için `CObject` boş bir liste oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CObList::AddHead](#addhead)|Listenin başına bir öğe (veya başka bir listedeki tüm öğeler) ekler (yeni bir kafa yapar).|
|[CObList::AddTail](#addtail)|Listenin kuyruğuna bir öğe (veya başka bir listedeki tüm öğeler) ekler (yeni bir kuyruk yapar).|
|[CObList::Bul](#find)|İşaretçi değeriyle belirtilen bir öğenin konumunu alır.|
|[CObList::FindIndex](#findindex)|Sıfır tabanlı dizin tarafından belirtilen bir öğenin konumunu alır.|
|[Coblist::Getat](#getat)|Öğeyi belirli bir konumda alır.|
|[CObList::GetCount](#getcount)|Bu listedeki öğe sayısını verir.|
|[CObList::GetHead](#gethead)|Listenin baş öğesini verir (boş olamaz).|
|[CObList::Getheadposition](#getheadposition)|Listenin baş öğesinin konumunu döndürür.|
|[CObList::GetNext](#getnext)|Yinelenmenin bir sonraki öğesini alır.|
|[CObList::GetPrev](#getprev)|Yinelenmeiçin önceki öğeyi alır.|
|[CObList::GetSize](#getsize)|Bu listedeki öğe sayısını verir.|
|[CObList::GetTail](#gettail)|Listenin kuyruk öğesini verir (boş olamaz).|
|[CObList::GetTailposition](#gettailposition)|Listenin kuyruk öğesinin konumunu döndürür.|
|[CObList::InsertAfter](#insertafter)|Belirli bir konumdan sonra yeni bir öğe ekler.|
|[CObList::EkleBefore](#insertbefore)|Belirli bir konumdan önce yeni bir öğe ekler.|
|[Coblist::Boş](#isempty)|Boş liste koşulu için testler (öğe yok).|
|[CObList::RemoveAll](#removeall)|Bu listeden tüm öğeleri kaldırır.|
|[Coblist::Removeat](#removeat)|Konuma göre belirtilen bir öğeyi bu listeden kaldırır.|
|[CObList::RemoveHead](#removehead)|Öğeyi listenin başından kaldırır.|
|[CObList::RemoveTail](#removetail)|Öğeyi listenin kuyruğundan kaldırır.|
|[Coblist::Setat](#setat)|Öğeyi belirli bir konumda ayarlar.|

## <a name="remarks"></a>Açıklamalar

`CObList`listeler iki kat bağlantılı listeler gibi olur.

Tür POZISYON değişkeni liste için bir anahtardır. Bir yer tutmak için bir listeyi sırayla ve yer imi olarak bir konum değişkeni hem yineleyici olarak kullanabilirsiniz. Ancak, bir konum dizinle aynı değildir.

Eleman ekleme liste başında çok hızlı, kuyruk, ve bilinen bir POZISYONDA. Bir öğeyi değere veya dizine göre aramak için sıralı arama gereklidir. Liste uzunsa bu arama yavaş olabilir.

`CObList`öğelerinin serileştirilmesini ve dampingini desteklemek için IMPLEMENT_SERIAL makroyu içerir. İşaretçilerin `CObject` listesi, aşırı yüklü bir ekleme işleci yle veya `Serialize` üye işlevle bir arşivde depolanırsa, her `CObject` öğe sırayla seri hale getirilir.

Listede tek tek `CObject` öğelerin dökümüne ihtiyacınız varsa, döküm bağlamının derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bir `CObList` nesne silindiğinde veya öğeleri kaldırıldığında, `CObject` başvurulan nesneler değil, yalnızca işaretçiler kaldırılır.

Kendi sınıflarınızı. `CObList` Türetilen nesnelere işaretçiler tutmak için tasarlanmış `CObject`yeni liste sınıfınız, yeni veri üyeleri ve yeni üye işlevleri ekler. Herhangi bir `CObject` işaretçi eklemeye izin verdiğinden, ortaya çıkan listenin kesinlikle güvenli olmadığını unutmayın.

> [!NOTE]
> Listeyi seri hale getirmek istiyorsanız, türemiş sınıfınuzun uygulanmasında [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) makroyu kullanmanız gerekir.

Kullanma `CObList`hakkında daha fazla bilgi için [Koleksiyonlar](../../mfc/collections.md)makalesine bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CObList`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxcoll.h

## <a name="coblistaddhead"></a><a name="addhead"></a>CObList::AddHead

Bu listenin başına yeni bir öğe veya öğe listesi ekler.

```
POSITION AddHead(CObject* newElement);
void AddHead(CObList* pNewList);
```

### <a name="parameters"></a>Parametreler

*newElement*<br/>
Bu `CObject` listeye eklenecek işaretçi.

*pNewList*<br/>
Başka bir `CObList` listeye işaretçi. *pNewList'teki* öğeler bu listeye eklenir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni eklenen öğenin KONUM değerini döndürür.

Aşağıdaki tabloda `CObList::AddHead`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**POZİsYON AddHead (geçersiz);** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddHead(CPtrList);** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION AddHead(const CString** `newElement` **&);**<br /><br /> **POZISYON AddHead(LPCTSTR);** `newElement` **);**<br /><br /> **void AddHead(CStringList);** <strong>\*</strong> `pNewList` **);**|

### <a name="remarks"></a>Açıklamalar

Liste işlemden önce boş olabilir.

### <a name="example"></a>Örnek

  Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
AddHead example: A CObList with 2 elements
a CAge at $44A8 40
a CAge at $442A 21
```

## <a name="coblistaddtail"></a><a name="addtail"></a>CObList::AddTail

Bu listenin kuyruğuna yeni bir öğe veya öğe listesi ekler.

```
POSITION AddTail(CObject* newElement);
void AddTail(CObList* pNewList);
```

### <a name="parameters"></a>Parametreler

*newElement*<br/>
Bu `CObject` listeye eklenecek işaretçi.

*pNewList*<br/>
Başka bir `CObList` listeye işaretçi. *pNewList'teki* öğeler bu listeye eklenir.

### <a name="return-value"></a>Dönüş Değeri

İlk sürüm, yeni eklenen öğenin KONUM değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Liste işlemden önce boş olabilir.

Aşağıdaki tabloda `CObList::AddTail`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**POZISYON AddTail (void);** <strong>\*</strong> `newElement` **);**<br /><br /> **void AddTail (CPtrList);** <strong>\*</strong> `pNewList` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION AddTail( const CString&** `newElement` **);**<br /><br /> **POZISYON AddTail (LPCTSTR);** `newElement` **);**<br /><br /> **void AddTail (CStringList);** <strong>\*</strong> `pNewList` **);**|

### <a name="example"></a>Örnek

  Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
AddTail example: A CObList with 2 elements
a CAge at $444A 21
a CAge at $4526 40
```

## <a name="coblistcoblist"></a><a name="coblist"></a>CObList::coblist

Boş `CObject` bir işaretçi listesi oluşturuyor.

```
CObList(INT_PTR nBlockSize = 10);
```

### <a name="parameters"></a>Parametreler

*nBlockSize*<br/>
Listeyi genişletmek için bellek ayırma parçalı.

### <a name="remarks"></a>Açıklamalar

Liste büyüdükçe, bellek *nBlockSize* girişleri birimlerine ayrılır. Bellek ayırma başarısız olursa, a `CMemoryException` atılır.

Aşağıdaki tabloda `CObList::CObList`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**CPtrList( INT_PTR** `nBlockSize` **= 10 );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList( INT_PTR** `nBlockSize` **= 10 );**|

### <a name="example"></a>Örnek

  Aşağıda tüm koleksiyon `CObject`örneklerinde `CAge` kullanılan -türemiş sınıfın bir listesi verilmiştir:

[!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]

Aşağıda `CObList` yapıcı kullanım bir örnektir:

[!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]

## <a name="coblistfind"></a><a name="find"></a>CObList::Bul

Belirtilen `CObject` `CObject` işaretçiyle eşleşen ilk işaretçiyi bulmak için listeyi sırayla arar.

```
POSITION Find(
    CObject* searchValue,
    POSITION startAfter = NULL) const;
```

### <a name="parameters"></a>Parametreler

*searchValue*<br/>
Bu listede bulunacak nesne işaretçisi.

*başlangıçAfter*<br/>
Arama için başlangıç konumu.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilecek bir POSITION değeri; Nesne bulunamazsa NULL.

### <a name="remarks"></a>Açıklamalar

İşaretçi değerlerinin nesnelerin içeriğini değil, karşılaştırılamadığını unutmayın.

Aşağıdaki tabloda `CObList::Find`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**POZİsYON Bul( void** <strong>\*</strong> `searchValue` **, POSITION** `startAfter` **= NULL ) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POZİsYON Bul( LPCTSTR** `searchValue` **, POSITION** `startAfter` **= NULL ) const;**|

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]

## <a name="coblistfindindex"></a><a name="findindex"></a>CObList::FindIndex

listeye dizin olarak *nIndex* değerini kullanır.

```
POSITION FindIndex(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Bulunacak liste öğesinin sıfır tabanlı dizin.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilecek bir POSITION değeri; *nIndex* çok büyükse NULL. (Çerçeve, *nIndex* negatif ise bir iddia oluşturur.)

### <a name="remarks"></a>Açıklamalar

Listenin başından sıralı bir tbmö başlar ve *n*th öğesi üzerinde durur.

Aşağıdaki tabloda `CObList::FindIndex`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**POSITION FindIndex ( INT_PTR** `nIndex` **) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION FindIndex ( INT_PTR** `nIndex` **) const;**|

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]

## <a name="coblistgetat"></a><a name="getat"></a>Coblist::Getat

Tür POZISYON değişkeni liste için bir anahtardır.

```
CObject*& GetAt(POSITION position);
const CObject*& GetAt(POSITION position) const;
```

### <a name="parameters"></a>Parametreler

*Konum*<br/>
Önceki `GetHeadPosition` veya `Find` üye işlev çağrısı yla döndürülen BIR POSITION değeri.

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için iade değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Bu bir dizin ile aynı değildir ve bir POSITION değeri üzerinde kendiniz çalışamazsınız. `GetAt`belirli bir `CObject` konumla ilişkili işaretçiyi alır.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Aşağıdaki tabloda `CObList::GetAt`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**const\* void& GetAt ( POZISYON** *pozisyonu)* **const;**<br /><br /> **void\*& GetAt** *(POZISYON);* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetAt ( POZISYON** *pozisyonu)* **const;**<br /><br /> **CString& GetAt** *(POZISYON);* **);**|

### <a name="example"></a>Örnek

  [FindIndex](#findindex)için örneğe bakın.

## <a name="coblistgetcount"></a><a name="getcount"></a>CObList::GetCount

Bu listedeki öğelerin sayısını alır.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eleman sayısını içeren bir sayıdeğeri.

Aşağıdaki tabloda `CObList::GetCount`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetCount( ) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetCount( ) const;**|

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]

## <a name="coblistgethead"></a><a name="gethead"></a>CObList::GetHead

Bu `CObject` listenin baş öğesini temsil eden işaretçiyi alır.

```
CObject*& GetHead();
const CObject*& GetHead() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listeye bir işaretçi aracılığıyla `const CObList`erişilirse, bir `GetHead` `CObject` işaretçi döndürür. Bu, işlevin yalnızca atama deyiminin sağ tarafında kullanılmasını sağlar ve böylece listeyi değişiklikten korur.

Listeye doğrudan veya bir işaretçi aracılığıyla `CObList`erişilirse, `GetHead` bir `CObject` işaretçiye başvuru verir. Bu, işlevin atama deyiminin her iki tarafında da kullanılmasını sağlar ve böylece liste girişlerinin değiştirilmesine izin verir.

### <a name="remarks"></a>Açıklamalar

Aramadan `GetHead`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](#isempty) kullanın.

Aşağıdaki tabloda `CObList::GetHead`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**const\* void& GetHead( ) const; void\*& GetHead( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetHead( ) const; CString& GetHead( );**|

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

Aşağıdaki örnekte, atama `GetHead` deyiminin sol tarafında kullanımı gösterin.

[!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]

## <a name="coblistgetheadposition"></a><a name="getheadposition"></a>CObList::Getheadposition

Bu listenin baş öğesinin konumunu alır.

```
POSITION GetHeadPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilecek bir POSITION değeri; Liste boşsa NULL.

Aşağıdaki tabloda `CObList::GetHeadPosition`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**POSITION GetHeadPosition( ) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POSITION GetHeadPosition( ) const;**|

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]

## <a name="coblistgetnext"></a><a name="getnext"></a>CObList::GetNext

rPosition tarafından tanımlanan liste öğesini alır, `POSITION` ardından *rPosition'ı*listedeki bir sonraki girişin değerine ayarlar. *rPosition*

```
CObject*& GetNext(POSITION& rPosition);
const CObject* GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*Rposition*<br/>
Önceki `GetNext`, `GetHeadPosition`veya diğer üye işlev çağrısı tarafından döndürülen bir POSITION değerine yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için iade değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Bir çağrı `GetNext` ile ilk konumu kurarsanız, bir ileri yineleme `GetHeadPosition` döngüsünde kullanabilirsiniz veya `Find`.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Alınan öğe listenin son öğesiyse, *rPosition'un* yeni değeri NULL olarak ayarlanır.

Bir yineleme sırasında bir öğeyi kaldırmak mümkündür. [RemoveAt](#removeat)için örneğe bakın.

> [!NOTE]
> MFC 8.0 itibariyle bu yöntemin const sürümü `const CObject*` yerine `const CObject*&`dönmek için değiştirildi.  Bu değişiklik, derleyiciyi C++ standardına uygun hale getirmek için yapılmıştır.

Aşağıdaki tabloda `CObList::GetNext`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Örnek

  Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
a CAge at $479C 40
a CAge at $46C0 21
```

## <a name="coblistgetprev"></a><a name="getprev"></a>CObList::GetPrev

*rPosition*tarafından tanımlanan liste öğesini alır, ardından listedeki önceki girişin KONUM değerine *rPosition'ı* ayarlar.

```
CObject*& GetPrev(POSITION& rPosition);
const CObject* GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Parametreler

*Rposition*<br/>
Önceki `GetPrev` veya diğer bir üye işlev çağrısı tarafından döndürülen POSITION değerine yapılan başvuru.

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için iade değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Bir çağrı `GetPrev` ile ilk konumu kurarsanız ters yineleme döngüsünde `GetTailPosition` kullanabilirsiniz veya `Find`.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Alınan öğe listede ilk sıradaysa, *rPosition'un* yeni değeri NULL olarak ayarlanır.

> [!NOTE]
> MFC 8.0 itibariyle bu yöntemin const sürümü `const CObject*` yerine `const CObject*&`dönmek için değiştirildi.  Bu değişiklik, derleyiciyi C++ standardına uygun hale getirmek için yapılmıştır.

Aşağıdaki tabloda `CObList::GetPrev`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|

### <a name="example"></a>Örnek

  Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
a CAge at $421C 21
a CAge at $421C 40
```

## <a name="coblistgetsize"></a><a name="getsize"></a>CObList::GetSize

Liste öğelerinin sayısını verir.

```
INT_PTR GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Listedeki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Listedeki öğe sayısını almak için bu yöntemi arayın.

Aşağıdaki tabloda `CObList::GetSize`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetSize( ) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetSize( ) const;**|

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]

## <a name="coblistgettail"></a><a name="gettail"></a>CObList::GetTail

Bu `CObject` listenin kuyruk öğesini temsil eden işaretçiyi alır.

```
CObject*& GetTail();
const CObject*& GetTail() const;
```

### <a name="return-value"></a>Dönüş Değeri

[GetHead](#gethead)için iade değeri açıklamasına bakın.

### <a name="remarks"></a>Açıklamalar

Aramadan `GetTail`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](#isempty) kullanın.

Aşağıdaki tabloda `CObList::GetTail`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**const\* void& GetTail( ) const; void\*& GetTail();**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString& GetTail( ) const; CString& GetTail( );**|

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]

## <a name="coblistgettailposition"></a><a name="gettailposition"></a>CObList::GetTailposition

Bu listenin kuyruk elemanının konumunu alır; Liste boşsa **NULL.**

```
POSITION GetTailPosition() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilecek bir POSITION değeri; Liste boşsa NULL.

Aşağıdaki tabloda `CObList::GetTailPosition`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**POZISYON GetTailPosition( ) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POZISYON GetTailPosition( ) const;**|

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]

## <a name="coblistinsertafter"></a><a name="insertafter"></a>CObList::InsertAfter

Belirtilen konumdaöğe sonra bu listeye bir öğe ekler.

```
POSITION InsertAfter(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*Konum*<br/>
Önceki `GetNext`, `GetPrev`veya `Find` üye işlev çağrısı yla döndürülen bir POSITION değeri.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi.

Aşağıdaki tabloda `CObList::InsertAfter`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**POZİsYON EklemeSonra ( POZISYON** *pozisyonu* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POZİs&YON** *position* **, const CString&** `newElement` **);** İnG<br /><br /> **POZİsYON İnDİrMe ( POZISYON** *pozisyonu* **, LPCTSTR** `newElement` **);**|

### <a name="return-value"></a>Dönüş Değeri

*Pozisyon* parametresi ile aynı olan pozisyon değeri.

### <a name="example"></a>Örnek

  Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
InsertAfter example: A CObList with 3 elements
a CAge at $4A44 40
a CAge at $4A64 65
a CAge at $4968 21
```

## <a name="coblistinsertbefore"></a><a name="insertbefore"></a>CObList::EkleBefore

Belirtilen konumdaöğe önce bu listeye bir öğe ekler.

```
POSITION InsertBefore(
    POSITION position,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*Konum*<br/>
Önceki `GetNext`, `GetPrev`veya `Find` üye işlev çağrısı yla döndürülen bir POSITION değeri.

*newElement*<br/>
Bu listeye eklenecek nesne işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Yineleme veya nesne işaretçisi alımı için kullanılabilecek bir POSITION değeri; Liste boşsa NULL.

Aşağıdaki tabloda `CObList::InsertBefore`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**POZİsYON İnSERTATU( POZİsYON** *pozisyonu* **, void** <strong>\*</strong> `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**POZİsYON İnSERTATU(POZİsYON** *pozisyonu* **, const CString&);** `newElement` **);**<br /><br /> **POZİsYON EklemeÖnce ( POZISYON** *pozisyonu* **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Örnek

  Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

```Output
InsertBefore example: A CObList with 3 elements
a CAge at $4AE2 40
a CAge at $4B02 65
a CAge at $49E6 21
```

## <a name="coblistisempty"></a><a name="isempty"></a>Coblist::Boş

Bu listenin öğe içerip içermediğini gösterir.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bu liste boşsa sıfırolmayan; aksi takdirde 0.

Aşağıdaki tabloda `CObList::IsEmpty`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**BOOL Boş( ) const;**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL Boş( ) const;**|

### <a name="example"></a>Örnek

  [RemoveAll](#removeall)için örneğe bakın.

## <a name="coblistremoveall"></a><a name="removeall"></a>CObList::RemoveAll

Bu listeden tüm öğeleri kaldırır ve `CObList` ilişkili belleği serbest sağlar.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Liste zaten boşsa hata oluşturulmadı.

Öğeleri bir `CObList`, listeden nesne işaretçileri kaldırdığınızda. Nesneleri silmek sizin sorumluluğunuzdadır.

Aşağıdaki tabloda `CObList::RemoveAll`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**void RemoveAll( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll( );**|

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]

## <a name="coblistremoveat"></a><a name="removeat"></a>Coblist::Removeat

Belirtilen öğeyi bu listeden kaldırır.

```
void RemoveAt(POSITION position);
```

### <a name="parameters"></a>Parametreler

*Konum*<br/>
Öğenin listeden kaldırılacak konumu.

### <a name="remarks"></a>Açıklamalar

Bir öğeyi `CObList`, nesne işaretçisini listeden kaldırırsınız. Nesneleri silmek sizin sorumluluğunuzdadır.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Aşağıdaki tabloda `CObList::RemoveAt`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**void RemoveAt ( POZISYON** *pozisyonu);* **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt ( POZISYON** *pozisyonu);* **);**|

### <a name="example"></a>Örnek

  Bir liste yinelemesi sırasında bir öğeyi kaldırırken dikkatli olun. Aşağıdaki örnek, [GetNext](#getnext)için geçerli bir **KONUM** değerini garanti eden bir kaldırma tekniğini gösterir.

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]

Bu programın sonuçları aşağıdaki gibidir:

`RemoveAt example: A CObList with 2 elements`

`a CAge at $4C1E 65`

`a CAge at $4B22 21`

## <a name="coblistremovehead"></a><a name="removehead"></a>CObList::RemoveHead

Öğeyi listenin başından kaldırır ve bir işaretçi döndürür.

```
CObject* RemoveHead();
```

### <a name="return-value"></a>Dönüş Değeri

İşaretçi `CObject` daha önce listenin başında.

### <a name="remarks"></a>Açıklamalar

Aramadan `RemoveHead`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](#isempty) kullanın.

Aşağıdaki tabloda `CObList::RemoveHead`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**void\* RemoveHead( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead( );**|

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]

## <a name="coblistremovetail"></a><a name="removetail"></a>CObList::RemoveTail

Öğeyi listenin kuyruğundan kaldırır ve bir işaretçi döndürür.

```
CObject* RemoveTail();
```

### <a name="return-value"></a>Dönüş Değeri

Listenin kuyruğundaki nesneye işaretçi.

### <a name="remarks"></a>Açıklamalar

Aramadan `RemoveTail`önce listenin boş olmadığından emin olmalısınız. Liste boşsa, Microsoft Hazırlık Sınıfı Kitaplığı'nın Hata Ayıklama sürümü öne sürüler. Listenin öğeleri içerdiğini doğrulamak için [IsEmpty'ı](#isempty) kullanın.

Aşağıdaki tabloda `CObList::RemoveTail`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**void\* RemoveTail( );**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail( );**|

### <a name="example"></a>Örnek

Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

[!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]

## <a name="coblistsetat"></a><a name="setat"></a>Coblist::Setat

Öğeyi belirli bir konumda ayarlar.

```
void SetAt(
    POSITION pos,
    CObject* newElement);
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Ayarlanacak öğenin KONUMU.

*newElement*<br/>
Listeye `CObject` yazılacak işaretçi.

### <a name="remarks"></a>Açıklamalar

Tür POZISYON değişkeni liste için bir anahtardır. Bu bir dizin ile aynı değildir ve bir POSITION değeri üzerinde kendiniz çalışamazsınız. `SetAt`işaretçiyi `CObject` listede belirtilen konuma yazar.

POSITION değerinizin listede geçerli bir konumu temsil ettiğinden emin olmalısınız. Geçersizse, Microsoft Foundation Class Kitaplığı'nın Hata Ayıklama sürümü öne sürüler.

Aşağıdaki tabloda `CObList::SetAt`buna benzer diğer üye işlevler gösterilmektedir.

|Sınıf|Üye İşlevi|
|-----------|---------------------|
|[Cptrlist](../../mfc/reference/cptrlist-class.md)|**void SetAt( POSITION** `pos` **, const CString&);** `newElement` **);**|
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt( POZISYON** `pos` **, LPCTSTR** `newElement` **);**|

### <a name="example"></a>Örnek

  Bkz. [CObList::CObList](#coblist) sınıfının `CAge` bir listesi için.

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
