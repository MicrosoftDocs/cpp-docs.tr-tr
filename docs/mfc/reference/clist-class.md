---
title: CList sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 25337104da2f1ff397d3c61170ab6ad5a8817130
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37039147"
---
# <a name="clist-class"></a>CList sınıfı
Sıralı olarak veya değere göre sıralı listeler erişilebilir verildiğinden nesnelerin destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class TYPE, class ARG_TYPE = const TYPE&>  
class CList : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CList::CList](#clist)|Boş bir sıralı liste oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CList::AddHead](#addhead)|Bir öğenin (veya başka bir listedeki tüm öğelerin) (yeni head yapmaz) listenin başında ekler.|  
|[CList::AddTail](#addtail)|Bir öğenin (veya başka bir listedeki tüm öğelerin) (yeni bir kuyruk yapmaz) listesi kuyruğu için ekler.|  
|[CList::Find](#find)|İşaretçi değeri tarafından belirtilen bir öğenin konumunu alır.|  
|[CList::FindIndex](#findindex)|Bir öğenin sıfır tabanlı dizini tarafından belirtilen konumunu alır.|  
|[CList::GetAt](#getat)|Öğe verilen konumunda alır.|  
|[CList::GetCount](#getcount)|Bu listedeki öğe sayısını döndürür.|  
|[CList::GetHead](#gethead)|(Boş olamaz) listesinin head öğesi döndürür.|  
|[CList::GetHeadPosition](#getheadposition)|Head öğesi listesinin konumunu döndürür.|  
|[CList::GetNext](#getnext)|Yineleme için sonraki öğeyi alır.|  
|[CList::GetPrev](#getprev)|Yineleme için önceki öğesi alır.|  
|[CList::GetSize](#getsize)|Bu listedeki öğe sayısını döndürür.|  
|[CList::GetTail](#gettail)|(Boş olamaz) listesinin kuyruk öğesi döndürür.|  
|[CList::GetTailPosition](#gettailposition)|Tail öğenin listesinin konumunu döndürür.|  
|[CList::InsertAfter](#insertafter)|Verilen bir konuma sonra yeni bir öğe ekler.|  
|[CList::InsertBefore](#insertbefore)|Verilen bir konuma önce yeni bir öğe ekler.|  
|[CList::IsEmpty](#isempty)|Testler için boş liste koşul (öğe yok).|  
|[CList::RemoveAll](#removeall)|Tüm öğeleri bu listeden kaldırır.|  
|[CList::RemoveAt](#removeat)|Bu listeden konumu tarafından belirtilen bir öğeyi kaldırır.|  
|[CList::RemoveHead](#removehead)|Listenin başından öğeyi kaldırır.|  
|[CList::RemoveTail](#removetail)|Öğeyi listenin tail kaldırır.|  
|[CList::SetAt](#setat)|Öğe verilen konumunda ayarlar.|  
  
#### <a name="parameters"></a>Parametreler  
 `TYPE`  
 Listede depolanan nesnenin türü.  
  
 `ARG` *_* `TYPE`  
 Listede depolanan nesneler başvurmak için kullanılan türü. Bir başvuru olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 `CList` listeleri karakteriyle bağlı listeleri gibi davranır.  
  
 Türünde bir değişken **konumu** bir anahtar listesi. Kullanabileceğiniz bir **konumu** yineleyici listesini sırayla çapraz geçiş ve bir yerde saklamak için bir yer işareti olarak değişken. Bir konuma bir dizin aynı ancak değildir.  
  
 Öğe ekleme olduğundan çok listesi head en hızlı, kuyruk ve bilinen bir **konumu**. Sıralı bir ara değer veya dizin göre bir öğeyi aramak gereklidir. Bu arama listesi uzunsa yavaş olabilir.  
  
 Ayrı ayrı öğeler listesinde, bir dökümü gerekiyorsa, 1 veya daha büyük döküm bağlam derinliği ayarlamanız gerekir.  
  
 Genel yardımcı işlevleri sınıfı çağrısı belirli üye işlevleri için çoğu kullanımlarını özelleştirilmelidir `CList` sınıfı. Bkz: [koleksiyon sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) "Makroları ve genel öğeleri" bölümünde.  
  
 Kullanma hakkında daha fazla bilgi için `CList`, makaleye bakın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtempl.h  
  
##  <a name="addhead"></a>  CList::AddHead  
 Bu listenin başında yeni bir öğe veya öğe listesi ekler.  
  
```  
POSITION AddHead(ARG_TYPE newElement);  
void AddHead(CList* pNewList);
```  
  
### <a name="parameters"></a>Parametreler  
 *ARG_TYPE*  
 Şablon parametresi (bir başvuru olabilir) liste öğesi türünü belirtme.  
  
 *newElement*  
 Yeni öğe.  
  
 *pNewList*  
 Başka bir işaretçi `CList` listesi. Öğeleri *pNewList* bu listeye eklenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürüm döndürür **konumu** yeni eklenen öğesinin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste işlemi önce boş olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]  
  
##  <a name="addtail"></a>  CList::AddTail  
 Bu liste kuyruk için yeni bir öğe veya öğelerin listesi ekler.  
  
```  
POSITION AddTail(ARG_TYPE newElement);  
void AddTail(CList* pNewList);
```  
  
### <a name="parameters"></a>Parametreler  
 *ARG_TYPE*  
 Şablon parametresi (bir başvuru olabilir) liste öğesi türünü belirtme.  
  
 *newElement*  
 Bu listeye eklenecek öğe.  
  
 *pNewList*  
 Başka bir işaretçi `CList` listesi. Öğeleri *pNewList* bu listeye eklenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürüm döndürür **konumu** yeni eklenen öğesinin değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste işlemi önce boş olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#37](../../mfc/codesnippet/cpp/clist-class_3.cpp)]  
  
##  <a name="clist"></a>  CList::CList  
 Boş bir sıralı liste oluşturur.  
  
```  
CList(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Parametreler  
 *nBlockSize*  
 Listenin genişletmek için bellek ayırma ayrıntı düzeyi.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin büyüdükçe, bellek, biriminde ayrılır *nBlockSize* girişleri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]  
  
##  <a name="find"></a>  CList::Find  
 Sıralı olarak belirtilen eşleşen ilk öğe bulmak için listeyi arar *searchValue*.  
  
```  
POSITION Find(
    ARG_TYPE searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *ARG_TYPE*  
 Şablon parametresi (bir başvuru olabilir) liste öğesi türünü belirtme.  
  
 *searchValue*  
 Listede bulunacak değer.  
  
 *startAfter*  
 Arama için başlangıç konumu. Herhangi bir değer belirtilirse, arama head öğesi ile başlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya nesne işaretçi alma; için kullanılan değer **NULL** nesne bulunmazsa.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#39](../../mfc/codesnippet/cpp/clist-class_5.cpp)]  
  
##  <a name="findindex"></a>  CList::FindIndex  
 Değerini kullanır *nIndex* listesine bir dizin olarak.  
  
```  
POSITION FindIndex(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Bulunacak liste öğesinin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya nesne işaretçi alma; için kullanılan değer **NULL** varsa *nIndex* negatif veya çok büyük.  
  
### <a name="remarks"></a>Açıklamalar  
 Durduruluyor listenin başındaki gelen sıralı bir tarama başlamadan *n*th öğesi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]  
  
##  <a name="getat"></a>  CList::GetAt  
 Liste öğesinin belirli bir konumda alır.  
  
```  
TYPE& GetAt(POSITION position);  
const TYPE& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede nesne türünü belirten bir şablon parametre.  
  
 *Konumu*  
 Alınacak öğenin konumu listesinde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri açıklamasına bakın `GetHead`.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetAt` öğenin (veya öğeye başvuru) verilen bir konumu ile ilişkili döndürür. Bu dizin ile aynı değildir ve üzerinde çalışamaz bir **konumu** kendiniz değeri. Türünde bir değişken **konumu** bir anahtar listesi.  
  
 Emin olmanız gerekir, **konumu** değer listesinde geçerli bir konumu temsil eder. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CList::GetHeadPosition](#getheadposition).  
  
##  <a name="getcount"></a>  CList::GetCount  
 Bu listede öğe sayısını alır.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe sayısını içeren bir tamsayı değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin çağrılması aynı sonucu oluşturacağını [CList::GetSize](#getsize) yöntemi.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CList::RemoveHead](#removehead).  
  
##  <a name="gethead"></a>  CList::GetHead  
 Bu listenin head öğesi (veya head öğesi Başvurusu) alır.  
  
```  
const TYPE& GetHead() const;  
  
TYPE& GetHead();
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede nesne türünü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste ise **const**, `GetHead` listenin başındaki öğenin bir kopyasını döndürür. Bu işlevi yalnızca sağ tarafta Atama ifadesinin kullanılacak verir ve liste değiştirilmeye karşı korur.  
  
 Listede değilse **const**, `GetHead` listenin başındaki öğeye bir başvuru döndürür. Bu atama ifadesinin iki tarafında kullanılacak işlevi sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `GetHead`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]  
  
##  <a name="getheadposition"></a>  CList::GetHeadPosition  
 Head öğesi, bu listenin konumunu alır.  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya nesne işaretçi alma; için kullanılan değer **NULL** liste boşsa.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]  
  
##  <a name="getnext"></a>  CList::GetNext  
 Tarafından tanımlanan liste öğesi alır *rPosition*, ardından ayarlar *rPosition* için **konumu** listesinde sonraki girdisinin değeri.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
const TYPE& GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listedeki öğelerin türü belirten bir şablon parametre.  
  
 *rPosition*  
 Bir başvuru bir **konumu** önceki tarafından döndürülen değer `GetNext`, [GetHeadPosition](#getheadposition), ya da diğer üye işlev çağrısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste ise **const**, `GetNext` listedeki bir öğeye kopyasını döndürür. Bu işlevi yalnızca sağ tarafta Atama ifadesinin kullanılacak verir ve liste değiştirilmeye karşı korur.  
  
 Listede değilse **const**, `GetNext` liste öğesi için bir başvuru döndürür. Bu atama ifadesinin iki tarafında kullanılacak işlevi sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `GetNext` çağrısıyla ilk konum kurarsanız ileriye doğru yineleme döngü `GetHeadPosition` veya `Find`.  
  
 Emin olmanız gerekir, **konumu** değer listesinde geçerli bir konumu temsil eder. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Alınan öğe listesinde, son sonra yeni değeri ise `rPosition` ayarlanır **NULL**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]  
  
##  <a name="getprev"></a>  CList::GetPrev  
 Tarafından tanımlanan liste öğesi alır `rPosition`, ardından ayarlar `rPosition` için **konumu** listesinde önceki girdisinin değeri.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
const TYPE& GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listedeki öğelerin türü belirten bir şablon parametre.  
  
 *rPosition*  
 Bir başvuru bir **konumu** önceki tarafından döndürülen değer `GetPrev` veya diğer üye işlev çağrısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste ise **const**, `GetPrev` listenin başındaki öğenin bir kopyasını döndürür. Bu işlevi yalnızca sağ tarafta Atama ifadesinin kullanılacak verir ve liste değiştirilmeye karşı korur.  
  
 Listede değilse **const**, `GetPrev` liste öğesi için bir başvuru döndürür. Bu atama ifadesinin iki tarafında kullanılacak işlevi sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `GetPrev` çağrısıyla ilk konum kurarsanız geriye doğru yineleme döngü `GetTailPosition` veya `Find`.  
  
 Emin olmanız gerekir, **konumu** değer listesinde geçerli bir konumu temsil eder. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Alınan öğe listede ilk sonra yeni değeri ise *rPosition* ayarlanır **NULL**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]  
  
##  <a name="getsize"></a>  CList::GetSize  
 Liste öğelerinin sayısını döndürür.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listedeki öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Listedeki öğe sayısını almak için bu yöntemi çağırın.  Bu yöntemin çağrılması aynı sonucu oluşturacağını [CList::GetCount](#getcount) yöntemi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]  
  
##  <a name="gettail"></a>  CList::GetTail  
 Alır `CObject` bu listenin kuyruğu öğesinin temsil ettiği işaretçi.  
  
```  
TYPE& GetTail();  
const TYPE& GetTail() const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listedeki öğelerin türü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri açıklamasına bakın [GetHead](../../mfc/reference/coblist-class.md#gethead).  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `GetTail`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](../../mfc/reference/coblist-class.md#isempty) liste öğeleri içerdiğini doğrulayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]  
  
##  <a name="gettailposition"></a>  CList::GetTailPosition  
 Bu listenin kuyruğu öğesinin konumu alır; **NULL** liste boşsa.  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya nesne işaretçi alma; için kullanılan değer **NULL** liste boşsa.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]  
  
##  <a name="insertafter"></a>  CList::InsertAfter  
 Bir öğeyi, belirli bir konumda öğesinden sonra bu listeye ekler.  
  
```  
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *Konumu*  
 A **konumu** önceki tarafından döndürülen değer `GetNext`, `GetPrev`, veya `Find` üye işlev çağrısı.  
  
 *ARG_TYPE*  
 Liste öğesi türünü belirten bir şablon parametre.  
  
 *newElement*  
 Bu listeye eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya liste öğesi alma işlemi için kullanılan bir değer.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]  
  
##  <a name="insertbefore"></a>  CList::InsertBefore  
 Bu liste öğe belirli bir konumda bir öğe ekler.  
  
```  
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *Konumu*  
 A **konumu** önceki tarafından döndürülen değer `GetNext`, `GetPrev`, veya `Find` üye işlev çağrısı.  
  
 *ARG_TYPE*  
 Şablon parametresi (bir başvuru olabilir) liste öğesi türünü belirtme.  
  
 *newElement*  
 Bu listeye eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** yineleme veya liste öğesi alma işlemi için kullanılan bir değer.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *konumu* olan **NULL**, öğeyi listenin head eklenir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]  
  
##  <a name="isempty"></a>  CList::IsEmpty  
 Bu listede öğe içerip içermediğini belirtir.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu liste boşsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]  
  
##  <a name="removeall"></a>  CList::RemoveAll  
 Bu listeden tüm öğeleri kaldırır ve ilişkili belleği serbest bırakır.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Liste boş ise bir hata oluşturulmaz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]  
  
##  <a name="removeat"></a>  CList::RemoveAt  
 Belirtilen öğe bu listeden kaldırır.  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>Parametreler  
 *Konumu*  
 Listeden kaldırılacak öğe konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 Emin olmanız gerekir, **konumu** değer listesinde geçerli bir konumu temsil eder. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]  
  
##  <a name="removehead"></a>  CList::RemoveHead  
 Listenin başından öğeyi kaldırır ve bir işaretçi döndürür.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listedeki öğelerin türü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce listenin başındaki konumundaki öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `RemoveHead`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]  
  
##  <a name="removetail"></a>  CList::RemoveTail  
 Öğeyi listenin tail kaldırır ve bir işaretçi döndürür.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listedeki öğelerin türü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listenin tail öğesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `RemoveTail`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]  
  
##  <a name="setat"></a>  CList::SetAt  
 Türünde bir değişken **konumu** bir anahtar listesi.  
  
```  
void SetAt(POSITION pos, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *POS*  
 **Konumu** ayarlanacak öğenin.  
  
 *ARG_TYPE*  
 Şablon parametresi (bir başvuru olabilir) liste öğesi türünü belirtme.  
  
 *newElement*  
 Listeye eklenecek öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu dizin ile aynı değildir ve üzerinde çalışamaz bir **konumu** kendiniz değeri. `SetAt` öğe, listede belirtilen konuma yazar.  
  
 Emin olmanız gerekir, **konumu** değer listesinde geçerli bir konumu temsil eder. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek Topla](../../visual-cpp-samples.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CMap sınıfı](../../mfc/reference/cmap-class.md)   
 [CArray Sınıfı](../../mfc/reference/carray-class.md)
