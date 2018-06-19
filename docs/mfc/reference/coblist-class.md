---
title: CObList sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 35217ee967554332002d8597a00dc21df928306d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33378424"
---
# <a name="coblist-class"></a>CObList sınıfı
sıralı listeler verildiğinden, fSupports `CObject` işaretçileri erişilebilir sırayla veya işaretçisi değeri.  
  
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
|[CObList::AddHead](#addhead)|Bir öğenin (veya başka bir listedeki tüm öğelerin) (yeni head yapmaz) listenin başında ekler.|  
|[CObList::AddTail](#addtail)|Bir öğenin (veya başka bir listedeki tüm öğelerin) (yeni bir kuyruk yapmaz) listesi kuyruğu için ekler.|  
|[CObList::Find](#find)|İşaretçi değeri tarafından belirtilen bir öğenin konumunu alır.|  
|[CObList::FindIndex](#findindex)|Bir öğenin sıfır tabanlı dizini tarafından belirtilen konumunu alır.|  
|[CObList::GetAt](#getat)|Öğe verilen konumunda alır.|  
|[CObList::GetCount](#getcount)|Bu listedeki öğe sayısını döndürür.|  
|[CObList::GetHead](#gethead)|(Boş olamaz) listesinin head öğesi döndürür.|  
|[CObList::GetHeadPosition](#getheadposition)|Head öğesi listesinin konumunu döndürür.|  
|[CObList::GetNext](#getnext)|Yineleme için sonraki öğeyi alır.|  
|[CObList::GetPrev](#getprev)|Yineleme için önceki öğesi alır.|  
|[CObList::GetSize](#getsize)|Bu listedeki öğe sayısını döndürür.|  
|[CObList::GetTail](#gettail)|(Boş olamaz) listesinin kuyruk öğesi döndürür.|  
|[CObList::GetTailPosition](#gettailposition)|Tail öğenin listesinin konumunu döndürür.|  
|[CObList::InsertAfter](#insertafter)|Verilen bir konuma sonra yeni bir öğe ekler.|  
|[CObList::InsertBefore](#insertbefore)|Verilen bir konuma önce yeni bir öğe ekler.|  
|[CObList::IsEmpty](#isempty)|Testler için boş liste koşul (öğe yok).|  
|[CObList::RemoveAll](#removeall)|Tüm öğeleri bu listeden kaldırır.|  
|[CObList::RemoveAt](#removeat)|Bu listeden konumu tarafından belirtilen bir öğeyi kaldırır.|  
|[CObList::RemoveHead](#removehead)|Listenin başından öğeyi kaldırır.|  
|[CObList::RemoveTail](#removetail)|Öğeyi listenin tail kaldırır.|  
|[CObList::SetAt](#setat)|Öğe verilen konumunda ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CObList` listeleri karakteriyle bağlı listeleri gibi davranır.  
  
 Türünde bir değişken **konumu** bir anahtar listesi. Kullanabileceğiniz bir **konumu** hem yineleyici listesini sırayla geçiş için de bir yerde saklamak için bir yer işareti olarak değişken. Bir konuma bir dizin aynı ancak değildir.  
  
 Öğe ekleme olduğundan çok listesi head en hızlı, kuyruk ve bilinen bir **konumu**. Sıralı bir ara değer veya dizin göre bir öğeyi aramak gereklidir. Bu arama listesi uzunsa yavaş olabilir.  
  
 `CObList` bir araya getirir `IMPLEMENT_SERIAL` makrosu seri hale getirme ve alt öğeleri dökme desteklemek için. Bir listesi, `CObject` işaretçileri aşırı yüklenmiş ekleme işleciyle veya ile bir arşivde saklanır `Serialize` her üye işlev `CObject` öğenin sırayla sıralandığı.  
  
 Tek bir dökümü gerekiyorsa `CObject` listesindeki öğeler, ayarlamalısınız döküm içerik derinliği 1 veya daha büyük.  
  
 Zaman bir `CObList` Nesne silindiğinden veya ne zaman öğeleri kaldırılır, yalnızca `CObject` işaretçileri kaldırılır, nesneleri başvuruyor.  
  
 Kendi sınıflardan türetilemeyeceğini `CObList`. Türetilen nesnelerine işaretçiler tutmak için tasarlanan yeni liste sınıfınızı `CObject`, yeni veri üyeleri ve yeni üye işlevleri ekler. Ekleme herhangi izin verdiğinden sonuç listesi kesinlikle türü güvenli değildir `CObject` işaretçi.  
  
> [!NOTE]
>  Kullanmalısınız [ımplement_serıal](run-time-object-model-services.md#implement_serial) makrosu listesi seri hale getirmek istiyorsanız, türetilmiş sınıf uygulamasında.  
  
 Kullanma hakkında daha fazla bilgi için `CObList`, makaleye bakın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
##  <a name="addhead"></a>  CObList::AddHead  
 Bu listenin başında yeni bir öğe veya öğe listesi ekler.  
  
```  
POSITION AddHead(CObject* newElement);  
void AddHead(CObList* pNewList);
```  
  
### <a name="parameters"></a>Parametreler  
 `newElement`  
 `CObject` Bu listeye eklenecek işaretçi.  
  
 `pNewList`  
 Başka bir işaretçi `CObList` listesi. Öğeleri `pNewList` bu listeye eklenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürüm döndürür **konumu** yeni eklenen öğesinin değeri.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::AddHead`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum AddHead (void\***  `newElement` **);**<br /><br /> **void AddHead (CPtrList\***  `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum AddHead (const CString &** `newElement` **);**<br /><br /> **Konum AddHead (LPCTSTR** `newElement` **);**<br /><br /> **void AddHead (CStringList\***  `pNewList` **);**|  
  
### <a name="remarks"></a>Açıklamalar  
 Liste işlemi önce boş olabilir.  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#89](../../mfc/codesnippet/cpp/coblist-class_1.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `AddHead example: A CObList with 2 elements`  
  
 `a CAge at $44A8 40`  
  
 `a CAge at $442A 21`  
  
##  <a name="addtail"></a>  CObList::AddTail  
 Bu liste kuyruk için yeni bir öğe veya öğelerin listesi ekler.  
  
```  
POSITION AddTail(CObject* newElement);  
void AddTail(CObList* pNewList);
```  
  
### <a name="parameters"></a>Parametreler  
 `newElement`  
 `CObject` Bu listeye eklenecek işaretçi.  
  
 `pNewList`  
 Başka bir işaretçi `CObList` listesi. Öğeleri `pNewList` bu listeye eklenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürüm döndürür **konumu** yeni eklenen öğesinin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste işlemi önce boş olabilir.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::AddTail`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum AddTail (void\***  `newElement` **);**<br /><br /> **void AddTail (CPtrList\***  `pNewList` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum AddTail (const CString &** `newElement` **);**<br /><br /> **Konum AddTail (LPCTSTR** `newElement` **);**<br /><br /> **void AddTail (CStringList\***  `pNewList` **);**|  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#90](../../mfc/codesnippet/cpp/coblist-class_2.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `AddTail example: A CObList with 2 elements`  
  
 `a CAge at $444A 21`  
  
 `a CAge at $4526 40`  
  
##  <a name="coblist"></a>  CObList::CObList  
 Boş bir yapıları `CObject` işaretçi liste.  
  
```  
CObList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Parametreler  
 `nBlockSize`  
 Listenin genişletmek için bellek ayırma ayrıntı düzeyi.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin büyüdükçe, bellek, biriminde ayrılır `nBlockSize` girişleri. Bellek ayırma başarısız olursa, bir `CMemoryException` oluşturulur.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::CObList`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**CPtrList (INT_PTR** `nBlockSize` **= 10);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CStringList (INT_PTR** `nBlockSize` **= 10);**|  
  
### <a name="example"></a>Örnek  
  Bir listesi aşağıda verilmiştir `CObject`-türetilmiş sınıf `CAge` tüm koleksiyon örneklerde kullanılan:  
  
 [!code-cpp[NVC_MFCCollections#91](../../mfc/codesnippet/cpp/coblist-class_3.h)]  
  
 Bir örneği aşağıdadır `CObList` Oluşturucusu kullanımı:  
  
 [!code-cpp[NVC_MFCCollections#92](../../mfc/codesnippet/cpp/coblist-class_4.cpp)]  
  
##  <a name="find"></a>  CObList::Find  
 Sıralı olarak ilk bulmak için listeyi arar `CObject` belirtilen eşleşen işaretçi `CObject` işaretçi.  
  
```  
POSITION Find(
    CObject* searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `searchValue`  
 Bu listede bulunacak nesne işaretçisi.  
  
 `startAfter`  
 Arama için başlangıç konumu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya nesne işaretçi alma; için kullanılan değer **NULL** nesne bulunmazsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Kayan nokta değerlerini karşılaştırılır Not, nesneleri içeriğini.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::Find`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum Bul (void\***  `searchValue` **, konumu** `startAfter` **= NULL) const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum Bul (LPCTSTR** `searchValue` **, konumu** `startAfter` **= NULL) const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#93](../../mfc/codesnippet/cpp/coblist-class_5.cpp)]  
  
##  <a name="findindex"></a>  CObList::FindIndex  
 Değerini kullanır `nIndex` listesine bir dizin olarak.  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Bulunacak liste öğesinin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya nesne işaretçi alma; için kullanılan değer **NULL** varsa `nIndex` çok büyük. (Framework bir onaylama oluşturur `nIndex` negatiftir.)  
  
### <a name="remarks"></a>Açıklamalar  
 Durduruluyor listenin başındaki gelen sıralı bir tarama başlamadan *n*th öğesi.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::FindIndex`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum findIndex (INT_PTR** `nIndex` **) const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum findIndex (INT_PTR** `nIndex` **) const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#94](../../mfc/codesnippet/cpp/coblist-class_6.cpp)]  
  
##  <a name="getat"></a>  CObList::GetAt  
 Türünde bir değişken **konumu** bir anahtar listesi.  
  
```  
CObject*& GetAt(POSITION position);  
const CObject*& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *Konumu*  
 A **konumu** önceki tarafından döndürülen değer `GetHeadPosition` veya **Bul** üye işlev çağrısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri açıklamasına bakın [GetHead](#gethead).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu dizin ile aynı değildir ve üzerinde çalışamaz bir **konumu** kendiniz değeri. `GetAt` alır `CObject` verilen bir konumu ile ilişkili işaretçi.  
  
 Emin olmanız gerekir, **konumu** değer listesinde geçerli bir konumu temsil eder. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::GetAt`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetAt (konum** *konumu* **) const;**<br /><br /> **void\*& GetAt (konum** *konumu* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetAt (konum** *konumu* **) const;**<br /><br /> **CString & GetAt (konum** *konumu* **);**|  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [findIndex](#findindex).  
  
##  <a name="getcount"></a>  CObList::GetCount  
 Bu listede öğe sayısını alır.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe sayısını içeren bir tamsayı değeri.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::GetCount`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetCount () const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetCount () const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#95](../../mfc/codesnippet/cpp/coblist-class_7.cpp)]  
  
##  <a name="gethead"></a>  CObList::GetHead  
 Alır `CObject` head öğesi, bu listenin gösteren bir işaretçi.  
  
```  
CObject*& GetHead();  
const CObject*& GetHead() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste için bir işaretçi üzerinden erişilen varsa bir **const CObList**, ardından `GetHead` döndürür bir `CObject` işaretçi. Bu yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece listenin değiştirilmeye karşı korur.  
  
 Listenin doğrudan veya bir işaretçi üzerinden erişiliyorsa bir `CObList`, ardından `GetHead` bir başvuru döndürür bir `CObject` işaretçi. Bu atama ifadesinin iki tarafında kullanılacak işlevi sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `GetHead`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::GetHead`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetHead () const; void\*& GetHead ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetHead () const; CString & GetHead ();**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 Aşağıdaki örnek kullanımını göstermektedir `GetHead` Atama ifadesinin sol tarafındaki.  
  
 [!code-cpp[NVC_MFCCollections#96](../../mfc/codesnippet/cpp/coblist-class_8.cpp)]  
  
##  <a name="getheadposition"></a>  CObList::GetHeadPosition  
 Head öğesi, bu listenin konumunu alır.  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya nesne işaretçi alma; için kullanılan değer **NULL** liste boşsa.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::GetHeadPosition`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum GetHeadPosition () const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum GetHeadPosition () const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#97](../../mfc/codesnippet/cpp/coblist-class_9.cpp)]  
  
##  <a name="getnext"></a>  CObList::GetNext  
 Tarafından tanımlanan liste öğesi alır `rPosition`, ardından ayarlar `rPosition` için `POSITION` listesinde sonraki girdisinin değeri.  
  
```  
CObject*& GetNext(POSITION& rPosition);  
const CObject* GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `rPosition`  
 Bir başvuru bir `POSITION` önceki tarafından döndürülen değer `GetNext`, `GetHeadPosition`, ya da diğer üye işlev çağrısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri açıklamasına bakın [GetHead](#gethead).  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `GetNext` çağrısıyla ilk konum kurarsanız ileriye doğru yineleme döngü `GetHeadPosition` veya `Find`.  
  
 Emin olmanız gerekir, `POSITION` değer listesinde geçerli bir konumu temsil eder. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Alınan öğe listesinde, son sonra yeni değeri ise `rPosition` ayarlanır `NULL`.  
  
 Yineleme sırasında bir öğeyi kaldırın mümkündür. Örneğin bkz [RemoveAt](#removeat).  
  
> [!NOTE]
>  MFC 8.0 itibariyle döndürmek için bu yöntem const sürümü değişti `const CObject*` yerine `const CObject*&`.  Bu değişiklik derleyici standart C++ ile uyum sağlamak için yapılmıştır.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::GetNext`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const void* GetNext( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetNext( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetNext( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#98](../../mfc/codesnippet/cpp/coblist-class_10.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `a CAge at $479C 40`  
  
 `a CAge at $46C0 21`  
  
##  <a name="getprev"></a>  CObList::GetPrev  
 Tarafından tanımlanan liste öğesi alır `rPosition`, ardından ayarlar `rPosition` için `POSITION` listesinde önceki girdisinin değeri.  
  
```  
CObject*& GetPrev(POSITION& rPosition);  
const CObject* GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `rPosition`  
 Bir başvuru bir `POSITION` önceki tarafından döndürülen değer `GetPrev` veya diğer üye işlev çağrısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri açıklamasına bakın [GetHead](#gethead).  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `GetPrev` çağrısıyla ilk konum kurarsanız geriye doğru yineleme döngü `GetTailPosition` veya `Find`.  
  
 Emin olmanız gerekir, `POSITION` değer listesinde geçerli bir konumu temsil eder. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Alınan öğe listede ilk sonra yeni değeri ise `rPosition` ayarlanır `NULL`.  
  
> [!NOTE]
>  MFC 8.0 itibariyle döndürmek için bu yöntem const sürümü değişti `const CObject*` yerine `const CObject*&`.  Bu değişiklik derleyici standart C++ ile uyum sağlamak için yapılmıştır.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::GetPrev`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|`void*& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const void* GetPrev( POSITION&` `rPosition` `) const;`|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|`CString& GetPrev( POSITION&` `rPosition` `);`<br /><br /> `const CString& GetPrev( POSITION&` `rPosition` `) const;`|  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#99](../../mfc/codesnippet/cpp/coblist-class_11.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `a CAge at $421C 21`  
  
 `a CAge at $421C 40`  
  
##  <a name="getsize"></a>  CObList::GetSize  
 Liste öğelerinin sayısını döndürür.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listedeki öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Listedeki öğe sayısını almak için bu yöntemi çağırın.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::GetSize`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**INT_PTR GetSize () const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**INT_PTR GetSize () const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#100](../../mfc/codesnippet/cpp/coblist-class_12.cpp)]  
  
##  <a name="gettail"></a>  CObList::GetTail  
 Alır `CObject` bu listenin kuyruğu öğesinin temsil ettiği işaretçi.  
  
```  
CObject*& GetTail();  
const CObject*& GetTail() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri açıklamasına bakın [GetHead](#gethead).  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `GetTail`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::GetTail`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**const void\*& GetTail () const; void\*& GetTail ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**const CString & GetTail () const; CString & GetTail ();**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#101](../../mfc/codesnippet/cpp/coblist-class_13.cpp)]  
  
##  <a name="gettailposition"></a>  CObList::GetTailPosition  
 Bu listenin kuyruğu öğesinin konumu alır; **NULL** liste boşsa.  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya nesne işaretçi alma; için kullanılan değer **NULL** liste boşsa.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::GetTailPosition`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum GetTailPosition () const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum GetTailPosition () const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#102](../../mfc/codesnippet/cpp/coblist-class_14.cpp)]  
  
##  <a name="insertafter"></a>  CObList::InsertAfter  
 Bir öğeyi, belirli bir konumda öğesinden sonra bu listeye ekler.  
  
```  
POSITION InsertAfter(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *Konumu*  
 A **konumu** önceki tarafından döndürülen değer `GetNext`, `GetPrev`, veya **Bul** üye işlev çağrısı.  
  
 `newElement`  
 Bu listeye eklenecek nesne işaretçisi.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::InsertAfter`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum InsertAfter (konum** *konumu* **, void\***  `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum InsertAfter (konum** *konumu* **, const CString &** `newElement` **);**<br /><br /> **Konum InsertAfter (konum** *konumu* **, LPCTSTR** `newElement` **);**|  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** aynı değer olarak *konumu* parametresi.  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#103](../../mfc/codesnippet/cpp/coblist-class_15.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `InsertAfter example: A CObList with 3 elements`  
  
 `a CAge at $4A44 40`  
  
 `a CAge at $4A64 65`  
  
 `a CAge at $4968 21`  
  
##  <a name="insertbefore"></a>  CObList::InsertBefore  
 Bu liste öğe belirli bir konumda bir öğe ekler.  
  
```  
POSITION InsertBefore(
    POSITION position,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *Konumu*  
 A **konumu** önceki tarafından döndürülen değer `GetNext`, `GetPrev`, veya **Bul** üye işlev çağrısı.  
  
 `newElement`  
 Bu listeye eklenecek nesne işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya nesne işaretçi alma; için kullanılan değer **NULL** liste boşsa.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::InsertBefore`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**Konum Insertbefore (konum** *konumu* **, void\***  `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**Konum Insertbefore (konum** *konumu* **, const CString &** `newElement` **);**<br /><br /> **Konum Insertbefore (konum** *konumu* **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#104](../../mfc/codesnippet/cpp/coblist-class_16.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `InsertBefore example: A CObList with 3 elements`  
  
 `a CAge at $4AE2 40`  
  
 `a CAge at $4B02 65`  
  
 `a CAge at $49E6 21`  
  
##  <a name="isempty"></a>  CObList::IsEmpty  
 Bu listede öğe içerip içermediğini belirtir.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu liste boşsa, sıfır olmayan; Aksi takdirde 0.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::IsEmpty`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**BOOL IsEmpty () const;**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**BOOL IsEmpty () const;**|  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [RemoveAll](#removeall).  
  
##  <a name="removeall"></a>  CObList::RemoveAll  
 Bu listeden tüm öğeleri kaldırır ve ilişkili boşaltır `CObList` bellek.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Liste boş ise bir hata oluşturulmaz.  
  
 Öğelerden kaldırdığınızda bir `CObList`, nesne işaretçileri listeden kaldırın. Bu nesneleri silmek için sorumluluğundadır.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::RemoveAll`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAll( );**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAll( );**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#105](../../mfc/codesnippet/cpp/coblist-class_17.cpp)]  
  
##  <a name="removeat"></a>  CObList::RemoveAt  
 Belirtilen öğe bu listeden kaldırır.  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>Parametreler  
 *Konumu*  
 Listeden kaldırılacak öğe konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğeyi kaldırdığınızda bir `CObList`, nesne işaretçisi listeden kaldırın. Bu nesneleri silmek için sorumluluğundadır.  
  
 Emin olmanız gerekir, **konumu** değer listesinde geçerli bir konumu temsil eder. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::RemoveAt`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void RemoveAt (konum** *konumu* **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void RemoveAt (konum** *konumu* **);**|  
  
### <a name="example"></a>Örnek  
  Bir öğe listesi yineleme sırasında kaldırırken dikkatli olun. Aşağıdaki örnek, geçerli bir garanti bir temizleme teknik gösterir **konumu** değerini [GetNext](#getnext).  
  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#106](../../mfc/codesnippet/cpp/coblist-class_18.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `RemoveAt example: A CObList with 2 elements`  
  
 `a CAge at $4C1E 65`  
  
 `a CAge at $4B22 21`  
  
##  <a name="removehead"></a>  CObList::RemoveHead  
 Listenin başından öğeyi kaldırır ve bir işaretçi döndürür.  
  
```  
CObject* RemoveHead();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 `CObject` Listenin başındaki önceden bıraktığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `RemoveHead`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::RemoveHead`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveHead ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveHead ();**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#107](../../mfc/codesnippet/cpp/coblist-class_19.cpp)]  
  
##  <a name="removetail"></a>  CObList::RemoveTail  
 Öğeyi listenin tail kaldırır ve bir işaretçi döndürür.  
  
```  
CObject* RemoveTail();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listenin tail olan nesne için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `RemoveTail`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::RemoveTail`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void\* RemoveTail ();**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**CString RemoveTail ();**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#108](../../mfc/codesnippet/cpp/coblist-class_20.cpp)]  
  
##  <a name="setat"></a>  CObList::SetAt  
 Öğe verilen konumunda ayarlar.  
  
```  
void SetAt(
    POSITION pos,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 **Konumu** ayarlanacak öğenin.  
  
 `newElement`  
 `CObject` Listeye yazılacak işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Türünde bir değişken **konumu** bir anahtar listesi. Bu dizin ile aynı değildir ve üzerinde çalışamaz bir **konumu** kendiniz değeri. `SetAt` Yazar `CObject` listede belirtilen konuma işaretçi.  
  
 Emin olmanız gerekir, **konumu** değer listesinde geçerli bir konumu temsil eder. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObList::SetAt`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CPtrList](../../mfc/reference/cptrlist-class.md)|**void SetAt (konum** `pos` **, const CString &** `newElement` **);**|  
|[CStringList](../../mfc/reference/cstringlist-class.md)|**void SetAt (konum** `pos` **, LPCTSTR** `newElement` **);**|  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](#coblist) listesini `CAge` sınıfı.  
  
 [!code-cpp[NVC_MFCCollections#109](../../mfc/codesnippet/cpp/coblist-class_21.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `SetAt example: A CObList with 2 elements`  
  
 `a CAge at $4D98 40`  
  
 `a CAge at $4DB8 65`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CStringList sınıfı](../../mfc/reference/cstringlist-class.md)   
 [CPtrList Sınıfı](../../mfc/reference/cptrlist-class.md)
