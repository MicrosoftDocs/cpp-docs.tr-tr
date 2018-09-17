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
ms.openlocfilehash: 1007a0bc5d63f5836aaf8925bced6b5ef84b020f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45726212"
---
# <a name="clist-class"></a>CList sınıfı
Sırayla veya değere göre sıralı listeler erişilebilir benzersiz olmayan nesnelerin destekler.  
  
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
|[CList::AddHead](#addhead)|Bir öğenin (veya başka bir listedeki tüm öğeleri) (yeni head sağlar) listenin başındaki ekler.|  
|[CList::AddTail](#addtail)|Bir öğenin (veya başka bir listedeki tüm öğeleri) (yeni bir kuyruk sağlar) listesi kuyruğu için ekler.|  
|[CList::Find](#find)|İşaretçi değeri tarafından belirtilen bir öğenin konumunu alır.|  
|[CList::FindIndex](#findindex)|Sıfır tabanlı bir dizin tarafından belirtilen bir öğenin konumunu alır.|  
|[CList::GetAt](#getat)|Öğesini, belirli bir konumda alır.|  
|[CList::GetCount](#getcount)|Bu listedeki öğelerin sayısını döndürür.|  
|[CList::GetHead](#gethead)|Head öğesi (boş olamaz) listesi döndürür.|  
|[CList::GetHeadPosition](#getheadposition)|Head öğesi listesinin konumunu döndürür.|  
|[CList::GetNext](#getnext)|Yineleme için sonraki öğeyi alır.|  
|[CList::GetPrev](#getprev)|Yineleme için önceki öğeyi alır.|  
|[CList::GetSize](#getsize)|Bu listedeki öğelerin sayısını döndürür.|  
|[CList::GetTail](#gettail)|Kuyruk öğesini (boş olamaz) listesi döndürür.|  
|[CList::GetTailPosition](#gettailposition)|Listenin tail öğenin konumunu döndürür.|  
|[CList::InsertAfter](#insertafter)|Belirli bir pozisyon sonra yeni bir öğe ekler.|  
|[CList::InsertBefore](#insertbefore)|Belirli bir pozisyon önce yeni bir öğe ekler.|  
|[CList::IsEmpty](#isempty)|(Öğe yok) boş liste koşulu sınar.|  
|[CList::RemoveAll](#removeall)|Bu listeden tüm öğeleri kaldırır.|  
|[CList::RemoveAt](#removeat)|Belirtilen konuma göre bu listeden bir öğeyi kaldırır.|  
|[CList::RemoveHead](#removehead)|Öğe listesinin başından kaldırır.|  
|[CList::RemoveTail](#removetail)|Öğe listesinin kuyruğunu kaldırır.|  
|[CList::SetAt](#setat)|Öğe, belirli bir konumda ayarlar.|  
  
#### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede depolanan nesne türü.  
  
 *ARG_TYPE*  
 Nesneleri listesinde depolanan başvurmak için kullanılan tür. Bir başvuru olabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 `CList` listeleri karakteriyle bağlantılı liste gibi davranır.  
  
 KONUM türünde bir değişken listesi için bir anahtardır. Sıralı olarak ve bir yerde tutmak için yer işareti listesini geçirmek için bir yineleyici bir konumu değişkeni kullanabilirsiniz. Bir konum bir dizin aynı ancak değildir.  
  
 Öğe ekleme listesi sonunda, kuyruk ve bilinen bir konuma çok hızlı olması. Sıralı bir arama değeri veya dizin tarafından bir öğesini aramak gereklidir. Bu arama liste uzunsa yavaş olabilir.  
  
 Tek tek öğeleri listesinde bir dökümü gerekiyorsa, 1 veya daha büyük derinliği döküm bağlam ayarlamanız gerekir.  
  
 Bu sınıf, genel yardımcı işlevleri çağrının belirli üye işlevleri, çoğu kullanım için özelleştirilmelidir `CList` sınıfı. Bkz: [koleksiyon sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) "Makroları ve genel öğeleri" bölümünde.  
  
 Kullanma hakkında daha fazla bilgi için `CList`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#35](../../mfc/codesnippet/cpp/clist-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtempl.h  
  
##  <a name="addhead"></a>  CList::AddHead  
 Bu listenin başındaki yeni bir öğe veya öğe listesi ekler.  
  
```  
POSITION AddHead(ARG_TYPE newElement);  
void AddHead(CList* pNewList);
```  
  
### <a name="parameters"></a>Parametreler  
 *ARG_TYPE*  
 (Bir başvuru olabilir) liste öğesi türünü belirten bir şablon parametre.  
  
 *newElement*  
 Yeni öğe.  
  
 *pNewList*  
 Başka bir işaretçiye `CList` listesi. Öğeleri *pNewList* bu listeye eklenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürümü, yeni eklenen öğenin KONUMUNU değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste işlemi önce boş olabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#36](../../mfc/codesnippet/cpp/clist-class_2.cpp)]  
  
##  <a name="addtail"></a>  CList::AddTail  
 Bu liste kuyruğu için yeni bir öğe veya öğe listesi ekler.  
  
```  
POSITION AddTail(ARG_TYPE newElement);  
void AddTail(CList* pNewList);
```  
  
### <a name="parameters"></a>Parametreler  
 *ARG_TYPE*  
 (Bir başvuru olabilir) liste öğesi türünü belirten bir şablon parametre.  
  
 *newElement*  
 Bu listeye eklenecek öğe.  
  
 *pNewList*  
 Başka bir işaretçiye `CList` listesi. Öğeleri *pNewList* bu listeye eklenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürümü, yeni eklenen öğenin KONUMUNU değerini döndürür.  
  
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
 Listeyi genişletmek için bellek ayırma ayrıntı düzeyi.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste genişledikçe birimleri cinsinden ayrılan bellek *nBlockSize* girdileri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#38](../../mfc/codesnippet/cpp/clist-class_4.cpp)]  
  
##  <a name="find"></a>  CList::Find  
 Sıralı olarak belirtilen eşleşen ilk öğeyi bulmak için liste arar *searchValue*.  
  
```  
POSITION Find(
    ARG_TYPE searchValue,  
    POSITION startAfter = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *ARG_TYPE*  
 (Bir başvuru olabilir) liste öğesi türünü belirten bir şablon parametre.  
  
 *searchValue*  
 Listesinde bulunacak değer.  
  
 *startAfter*  
 Arama için başlangıç konumu. Hiçbir değer belirtilmemişse arama head öğesi ile başlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleme veya nesne işaretçisi alımı için kullanılan konum değeri; Nesne bulunmazsa null değerini DÖNDÜRÜR.  
  
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
 Yineleme veya nesne işaretçisi alımı için kullanılan konum değeri; NULL ise *nIndex* negatif veya çok büyük.  
  
### <a name="remarks"></a>Açıklamalar  
 Üzerinde durdurma listenin başındaki sıralı bir tarama başlatılır *n*öğedeki.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#40](../../mfc/codesnippet/cpp/clist-class_6.cpp)]  
  
##  <a name="getat"></a>  CList::GetAt  
 Liste öğesi, belirli bir konumda alır.  
  
```  
TYPE& GetAt(POSITION position);  
const TYPE& GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede nesne türünü belirten bir şablon parametre.  
  
 *Konumu*  
 Alınacak öğenin konumunu listesinde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri açıklamasına bakın `GetHead`.  
  
### <a name="remarks"></a>Açıklamalar  
 `GetAt` belirli bir konum öğesi (veya öğeye bir başvuru) ilişkilendirilmiş döndürür. Bu dizin ile aynı değildir ve üzerinde bir konum değeri kendiniz çalışamaz. KONUM türünde bir değişken listesi için bir anahtardır.  
  
 KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CList::GetHeadPosition](#getheadposition).  
  
##  <a name="getcount"></a>  CList::GetCount  
 Bu listedeki öğe sayısını alır.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe sayısını içeren bir tamsayı değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemin çağrılması aynı sonucu üretir [CList::GetSize](#getsize) yöntemi.  
  
### <a name="example"></a>Örnek  
  Örneğin bakın [CList::RemoveHead](#removehead).  
  
##  <a name="gethead"></a>  CList::GetHead  
 Bu listenin head öğesi (veya bir başvuru head öğesi) alır.  
  
```  
const TYPE& GetHead() const;  
  
TYPE& GetHead();
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede nesne türünü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste **const**, `GetHead` listenin başındaki öğeyi bir kopyasını döndürür. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevine izin verir ve listenin değişikliklere karşı korur.  
  
 Listede değilse **const**, `GetHead` listenin başındaki öğeyi bir başvuru döndürür. Bu işlev, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `GetHead`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#41](../../mfc/codesnippet/cpp/clist-class_7.cpp)]  
  
##  <a name="getheadposition"></a>  CList::GetHeadPosition  
 Bu listenin baş öğenin konumunu alır.  
  
```  
POSITION GetHeadPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleme veya nesne işaretçisi alımı için kullanılan konum değeri; Liste boş ise NULL değerini DÖNDÜRÜR.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#42](../../mfc/codesnippet/cpp/clist-class_8.cpp)]  
  
##  <a name="getnext"></a>  CList::GetNext  
 Tarafından tanımlanan liste öğesi alır *rPosition*, ardından ayarlar *rPosition* için listedeki sonraki giriş konum değeri.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
const TYPE& GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede öğelerin türünü belirten bir şablon parametre.  
  
 *rPosition*  
 Bir önceki tarafından döndürülen bir konum değeri başvurusu `GetNext`, [GetHeadPosition](#getheadposition), ya da diğer üye işlev çağrısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste **const**, `GetNext` listedeki bir öğe bir kopyasını döndürür. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevine izin verir ve listenin değişikliklere karşı korur.  
  
 Listede değilse **const**, `GetNext` listedeki bir öğeye bir başvuru döndürür. Bu işlev, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `GetNext` çağrısıyla ilk konumunu kurarsanız ileriye doğru yineleme döngüsünde `GetHeadPosition` veya `Find`.  
  
 KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.  
  
 Alınan öğe listesinde, son öğesinin yeni değeri ise `rPosition` NULL olarak ayarlandı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#43](../../mfc/codesnippet/cpp/clist-class_9.cpp)]  
  
##  <a name="getprev"></a>  CList::GetPrev  
 Tarafından tanımlanan liste öğesi alır `rPosition`, ardından ayarlar `rPosition` konumu değerine listesinde önceki girişi.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
const TYPE& GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede öğelerin türünü belirten bir şablon parametre.  
  
 *rPosition*  
 Bir önceki tarafından döndürülen bir konum değeri başvurusu `GetPrev` veya diğer üye işlev çağrısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste **const**, `GetPrev` listenin başındaki öğeyi bir kopyasını döndürür. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevine izin verir ve listenin değişikliklere karşı korur.  
  
 Listede değilse **const**, `GetPrev` listedeki bir öğeye bir başvuru döndürür. Bu işlev, atama deyiminin her iki tarafında kullanılacak ve bu nedenle değiştirilecek Liste girişlerini olanak sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `GetPrev` çağrısıyla ilk konumunu kurarsanız geriye doğru yineleme döngüsünde `GetTailPosition` veya `Find`.  
  
 KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.  
  
 Alınan öğe listesinde ilk yeni değeri ise *rPosition* NULL olarak ayarlandı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#44](../../mfc/codesnippet/cpp/clist-class_10.cpp)]  
  
##  <a name="getsize"></a>  CList::GetSize  
 Liste öğelerin sayısını döndürür.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listedeki öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Listedeki öğe sayısını almak için bu yöntemi çağırın.  Bu yöntemin çağrılması aynı sonucu üretir [CList::GetCount](#getcount) yöntemi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#45](../../mfc/codesnippet/cpp/clist-class_11.cpp)]  
  
##  <a name="gettail"></a>  CList::GetTail  
 Alır `CObject` Kuyruk öğesi bu listenin temsil eden bir işaretçi.  
  
```  
TYPE& GetTail();  
const TYPE& GetTail() const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listesinde öğelerin türünü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dönüş değeri açıklamasına bakın [GetHead](../../mfc/reference/coblist-class.md#gethead).  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `GetTail`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](../../mfc/reference/coblist-class.md#isempty) liste öğeleri içerdiğini doğrulayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#46](../../mfc/codesnippet/cpp/clist-class_12.cpp)]  
  
##  <a name="gettailposition"></a>  CList::GetTailPosition  
 Bu listenin tail öğenin konumunu alır; Liste boş ise NULL değerini DÖNDÜRÜR.  
  
```  
POSITION GetTailPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleme veya nesne işaretçisi alımı için kullanılan konum değeri; Liste boş ise NULL değerini DÖNDÜRÜR.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#47](../../mfc/codesnippet/cpp/clist-class_13.cpp)]  
  
##  <a name="insertafter"></a>  CList::InsertAfter  
 Belirli bir konumda öğesinden sonra bu listeye bir öğe ekler.  
  
```  
POSITION InsertAfter(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *Konumu*  
 Bir önceki tarafından döndürülen bir konum değeri `GetNext`, `GetPrev`, veya `Find` üye işlev çağrısı.  
  
 *ARG_TYPE*  
 Liste öğesi türünü belirten bir şablon parametre.  
  
 *newElement*  
 Bu listeye eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleme veya liste öğesi almak için kullanılan bir konum değeri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#48](../../mfc/codesnippet/cpp/clist-class_14.cpp)]  
  
##  <a name="insertbefore"></a>  CList::InsertBefore  
 Belirli bir konumda öğesinden önce bu listeye bir öğe ekler.  
  
```  
POSITION InsertBefore(POSITION position, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *Konumu*  
 Bir önceki tarafından döndürülen bir konum değeri `GetNext`, `GetPrev`, veya `Find` üye işlev çağrısı.  
  
 *ARG_TYPE*  
 (Bir başvuru olabilir) liste öğesi türünü belirten bir şablon parametre.  
  
 *newElement*  
 Bu listeye eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yineleme veya liste öğesi almak için kullanılan bir konum değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa *konumu* NULL ise öğe listesinin kafası eklenir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#49](../../mfc/codesnippet/cpp/clist-class_15.cpp)]  
  
##  <a name="isempty"></a>  CList::IsEmpty  
 Bu listeye öğe içerip içermediğini belirtir.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu listenin boş olduğunu olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#50](../../mfc/codesnippet/cpp/clist-class_16.cpp)]  
  
##  <a name="removeall"></a>  CList::RemoveAll  
 Tüm öğeleri bu listeden kaldırır ve ilişkili belleği serbest bırakır.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Liste boş ise, bir hata oluşturulmaz.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#51](../../mfc/codesnippet/cpp/clist-class_17.cpp)]  
  
##  <a name="removeat"></a>  CList::RemoveAt  
 Belirtilen öğeyi listeden kaldırır.  
  
```  
void RemoveAt(POSITION position);
```  
  
### <a name="parameters"></a>Parametreler  
 *Konumu*  
 Listeden kaldırılacak öğenin konumu.  
  
### <a name="remarks"></a>Açıklamalar  
 KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#52](../../mfc/codesnippet/cpp/clist-class_18.cpp)]  
  
##  <a name="removehead"></a>  CList::RemoveHead  
 Öğe listesinin başından kaldırır ve bir işaretçi döndürür.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listesinde öğelerin türünü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe listesinin daha önce sonunda.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `RemoveHead`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#53](../../mfc/codesnippet/cpp/clist-class_19.cpp)]  
  
##  <a name="removetail"></a>  CList::RemoveTail  
 Listenin kuyruğunu öğeyi kaldırır ve bir işaretçi döndürür.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listesinde öğelerin türünü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listenin kuyruğunu öğesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmanız gerekir `RemoveTail`. Liste boşsa, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar. Kullanım [IsEmpty](#isempty) liste öğeleri içerdiğini doğrulayın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#54](../../mfc/codesnippet/cpp/clist-class_20.cpp)]  
  
##  <a name="setat"></a>  CList::SetAt  
 KONUM türünde bir değişken listesi için bir anahtardır.  
  
```  
void SetAt(POSITION pos, ARG_TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *POS*  
 Ayarlanacak öğenin konumu.  
  
 *ARG_TYPE*  
 (Bir başvuru olabilir) liste öğesi türünü belirten bir şablon parametre.  
  
 *newElement*  
 Listeye eklenecek öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu dizin ile aynı değildir ve üzerinde bir konum değeri kendiniz çalışamaz. `SetAt` öğe, listede belirtilen konuma yazar.  
  
 KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmanız gerekir. Geçersiz ise, ardından Microsoft Foundation Class Kitaplığı hata ayıklama sürümünü onaylar.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#55](../../mfc/codesnippet/cpp/clist-class_21.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek Topla](../../visual-cpp-samples.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CMap sınıfı](../../mfc/reference/cmap-class.md)   
 [CArray Sınıfı](../../mfc/reference/carray-class.md)
