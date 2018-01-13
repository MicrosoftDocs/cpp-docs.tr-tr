---
title: "CAtlList sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlList
- ATLCOLL/ATL::CAtlList
- ATLCOLL/ATL::CAtlList::INARGTYPE
- ATLCOLL/ATL::CAtlList::CAtlList
- ATLCOLL/ATL::CAtlList::AddHead
- ATLCOLL/ATL::CAtlList::AddHeadList
- ATLCOLL/ATL::CAtlList::AddTail
- ATLCOLL/ATL::CAtlList::AddTailList
- ATLCOLL/ATL::CAtlList::AssertValid
- ATLCOLL/ATL::CAtlList::Find
- ATLCOLL/ATL::CAtlList::FindIndex
- ATLCOLL/ATL::CAtlList::GetAt
- ATLCOLL/ATL::CAtlList::GetCount
- ATLCOLL/ATL::CAtlList::GetHead
- ATLCOLL/ATL::CAtlList::GetHeadPosition
- ATLCOLL/ATL::CAtlList::GetNext
- ATLCOLL/ATL::CAtlList::GetPrev
- ATLCOLL/ATL::CAtlList::GetTail
- ATLCOLL/ATL::CAtlList::GetTailPosition
- ATLCOLL/ATL::CAtlList::InsertAfter
- ATLCOLL/ATL::CAtlList::InsertBefore
- ATLCOLL/ATL::CAtlList::IsEmpty
- ATLCOLL/ATL::CAtlList::MoveToHead
- ATLCOLL/ATL::CAtlList::MoveToTail
- ATLCOLL/ATL::CAtlList::RemoveAll
- ATLCOLL/ATL::CAtlList::RemoveAt
- ATLCOLL/ATL::CAtlList::RemoveHead
- ATLCOLL/ATL::CAtlList::RemoveHeadNoReturn
- ATLCOLL/ATL::CAtlList::RemoveTail
- ATLCOLL/ATL::CAtlList::RemoveTailNoReturn
- ATLCOLL/ATL::CAtlList::SetAt
- ATLCOLL/ATL::CAtlList::SwapElements
dev_langs: C++
helpviewer_keywords: CAtlList class
ms.assetid: 09e98053-64b2-4efa-99ab-d0542caaf981
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13d26ba7107e21e64ad65ec53264b4f3740fd13a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catllist-class"></a>CAtlList sınıfı
Bu sınıf oluşturmak ve bir liste nesnesi yönetmek için yöntemler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename E, class ETraits = CElementTraits<E>>  
class CAtlList
```  
  
#### <a name="parameters"></a>Parametreler  
 `E`  
 Öğe türü.  
  
 `ETraits`  
 Kopyalama veya öğeleri taşıma için kullanılan kod. Bkz: [CElementTraits sınıfı](../../atl/reference/celementtraits-class.md) daha fazla ayrıntı için.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlList::INARGTYPE](#inargtype)||  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlList::CAtlList](#catllist)|Oluşturucu.|  
|[CAtlList:: ~ CAtlList](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlList::AddHead](#addhead)|Listenin başında bir öğe eklemek için bu yöntemi çağırın.|  
|[CAtlList::AddHeadList](#addheadlist)|Varolan bir listesini listenin başında eklemek için bu yöntemi çağırın.|  
|[CAtlList::AddTail](#addtail)|Bu liste kuyruk için bir öğe eklemek için bu yöntemi çağırın.|  
|[CAtlList::AddTailList](#addtaillist)|Bu liste kuyruk için varolan bir listesini eklemek için bu yöntemi çağırın.|  
|[CAtlList::AssertValid](#assertvalid)|Listeden geçerli olduğunu doğrulamak için bu yöntemi çağırın.|  
|[CAtlList::Find](#find)|Belirtilen öğe listesi aramak için bu yöntemi çağırın.|  
|[CAtlList::FindIndex](#findindex)|Bir dizin değeri verilen bir öğenin konumunu almak için bu yöntemi çağırın.|  
|[CAtlList::GetAt](#getat)|Listede belirtilen bir konuma öğede döndürmek için bu yöntemi çağırın.|  
|[CAtlList::GetCount](#getcount)|Listede nesne sayısını döndürmek için bu yöntemi çağırın.|  
|[CAtlList::GetHead](#gethead)|Listenin başındaki öğesi döndürmek için bu yöntemi çağırın.|  
|[CAtlList::GetHeadPosition](#getheadposition)|Listenin başındaki konumunu almak için bu yöntemi çağırın.|  
|[CAtlList::GetNext](#getnext)|Sonraki öğeye listeden döndürmek için bu yöntemi çağırın.|  
|[CAtlList::GetPrev](#getprev)|Önceki öğeyi listeden döndürmek için bu yöntemi çağırın.|  
|[CAtlList::GetTail](#gettail)|Listenin kuyruğu öğede döndürmek için bu yöntemi çağırın.|  
|[CAtlList::GetTailPosition](#gettailposition)|Tail listesinin konumunu almak için bu yöntemi çağırın.|  
|[CAtlList::InsertAfter](#insertafter)|Yeni bir öğe belirtilen konuma sonra listeye eklemek için bu yöntemi çağırın.|  
|[CAtlList::InsertBefore](#insertbefore)|Yeni bir öğe belirtilen konuma önce listeye eklemek için bu yöntemi çağırın.|  
|[CAtlList::IsEmpty](#isempty)|Liste boş olup olmadığını belirlemek için bu yöntemi çağırın.|  
|[CAtlList::MoveToHead](#movetohead)|Listenin başında belirtilen öğe taşımak için bu yöntemi çağırın.|  
|[CAtlList::MoveToTail](#movetotail)|Listenin kuyruk için belirtilen öğe taşımak için bu yöntemi çağırın.|  
|[CAtlList::RemoveAll](#removeall)|Tüm öğeleri listeden kaldırmak için bu yöntemi çağırın.|  
|[CAtlList::RemoveAt](#removeat)|Tek bir öğe listesinden kaldırmak için bu yöntemi çağırın.|  
|[CAtlList::RemoveHead](#removehead)|Listenin başındaki öğesini kaldırmak için bu yöntemi çağırın.|  
|[CAtlList::RemoveHeadNoReturn](#removeheadnoreturn)|Değer döndürme olmadan listenin başındaki öğesini kaldırmak için bu yöntemi çağırın.|  
|[CAtlList::RemoveTail](#removetail)|Listenin kuyruğu öğede kaldırmak için bu yöntemi çağırın.|  
|[CAtlList::RemoveTailNoReturn](#removetailnoreturn)|Değer döndürme olmadan listesi kuyruğu öğede kaldırmak için bu yöntemi çağırın.|  
|[CAtlList::SetAt](#setat)|Listesinde verilen konumda öğenin değerini ayarlamak için bu yöntemi çağırın.|  
|[CAtlList::SwapElements](#swapelements)|Listesindeki öğeleri değiştirmek için bu yöntemi çağırın.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CAtlList` Sınıfı sırayla veya değere göre sıralı listeler erişilebilir verildiğinden nesnelerin destekler. `CAtlList`listeleri karakteriyle bağlantılı listeleri gibi davranır. Her liste head ve bir kuyruk sahip ve yeni öğeler (veya bazı durumlarda listeleri) ya da listenin sonuna eklenebilir, veya önce veya sonra belirli öğeleri eklenir.  
  
 Çoğu `CAtlList` yöntemleri olun konum değeri kullanın. Bu değer, burada öğeleri depolanan ve hesaplanan veya doğrudan tahmin gerçek bellek konumuna başvurmak için yöntemler tarafından kullanılır. Erişim için gerekli değilse  *n* th öğesi listesinde, yöntem [CAtlList::FindIndex](#findindex) belirli bir dizine karşılık gelen konum değeri döndürür. Yöntemleri [CAtlList::GetNext](#getnext) ve [CAtlList::GetPrev](#getprev) nesneleri listesinde yinelemek için kullanılabilecek.  
  
 ATL ile kullanılabilen koleksiyon sınıfları hakkında daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="addhead"></a>CAtlList::AddHead  
 Listenin başında bir öğe eklemek için bu yöntemi çağırın.  
  
```
POSITION AddHead();
POSITION AddHead(INARGTYPE element);
```  
  
### <a name="parameters"></a>Parametreler  
 `element`  
 Yeni öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni eklenen öğenin konumunu döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sürüm kullanılırsa, boş bir öğe kopya kurucusu yerine kendi varsayılan oluşturucu kullanılarak oluşturulur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#13](../../atl/codesnippet/cpp/catllist-class_1.cpp)]  
  
##  <a name="addheadlist"></a>CAtlList::AddHeadList  
 Varolan bir listesini listenin başında eklemek için bu yöntemi çağırın.  
  
```
void AddHeadList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>Parametreler  
 `plNew`  
 Eklenecek listesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından için listenin işaret `plNew` varolan listenin başlangıcında eklenir. Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `plNew` NULL değerine eşittir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#14](../../atl/codesnippet/cpp/catllist-class_2.cpp)]  
  
##  <a name="addtail"></a>CAtlList::AddTail  
 Bu liste kuyruk için bir öğe eklemek için bu yöntemi çağırın.  
  
```
POSITION AddTail();
POSITION AddTail(INARGTYPE element);
```  
  
### <a name="parameters"></a>Parametreler  
 `element`  
 Eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni eklenen öğenin KONUMUNU döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sürüm kullanılırsa, boş bir öğe kopya kurucusu yerine kendi varsayılan oluşturucu kullanılarak oluşturulur. Öğe listesinin sonuna eklenir ve bu nedenle kuyruğunu şimdi olur. Bu yöntem boş bir liste ile kullanılabilir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#15](../../atl/codesnippet/cpp/catllist-class_3.cpp)]  
  
##  <a name="addtaillist"></a>CAtlList::AddTailList  
 Bu liste kuyruk için varolan bir listesini eklemek için bu yöntemi çağırın.  
  
```
void AddTailList(const CAtlList<E, ETraits>* plNew);
```  
  
### <a name="parameters"></a>Parametreler  
 `plNew`  
 Eklenecek listesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından için listenin işaret `plNew` son öğeden sonra liste nesnesinde (varsa) eklenir. Son öğesi `plNew` listesi, bu nedenle kuyruğunu olur. Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır *plNew* NULL değerine eşittir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#16](../../atl/codesnippet/cpp/catllist-class_4.cpp)]  
  
##  <a name="assertvalid"></a>CAtlList::AssertValid  
 Listeden geçerli olduğunu doğrulamak için bu yöntemi çağırın.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bir onaylama hatası ortaya liste nesnesi geçerli değil. Geçerli olması için boş bir liste head ve NULL olarak işaret eden tail olması gerekir ve boş olmayan bir listesi head ve geçerli bir adresi işaret eden tail sahip olmalıdır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#17](../../atl/codesnippet/cpp/catllist-class_5.cpp)]  
  
##  <a name="catllist"></a>CAtlList::CAtlList  
 Oluşturucu.  
  
```
CAtlList(UINT nBlockSize = 10) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBlockSize`  
 Blok boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucusu `CAtlList` nesnesi. Blok boyutu, yeni bir öğesi gerekli olduğunda ayrılmış bellek miktarı ölçüsüdür. Daha büyük öbek boyutları bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynağı kullanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#18](../../atl/codesnippet/cpp/catllist-class_6.cpp)]  
  
##  <a name="dtor"></a>CAtlList:: ~ CAtlList  
 Yok Edicisi.  
  
```
~CAtlList() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Çağrı dahil olmak üzere, ayrılan tüm kaynakları serbest bırakır [CAtlList::RemoveAll](#removeall) tüm öğeler listeden kaldırılacak.  
  
 Listenin hala çağrısından sonra bazı öğeler içeriyorsa, hata ayıklama derlemelerinde, bir onaylama hatası meydana gelir `RemoveAll`.  
  
##  <a name="find"></a>CAtlList::Find  
 Belirtilen öğe listesi aramak için bu yöntemi çağırın.  
  
```
POSITION Find(INARGTYPE element, POSITION posStartAfter = NULL) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `element`  
 Listede bulunacak öğe.  
  
 `posStartAfter`  
 Arama için başlangıç konumu. Herhangi bir değer belirtilirse, arama head öğesi ile başlar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğenin konumu değerini döndürür bulundu, aksi takdirde NULL değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, liste nesnesi geçerli değilse veya bir onaylama hatası meydana gelir `posStartAfter` değer aralık dışında.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#19](../../atl/codesnippet/cpp/catllist-class_7.cpp)]  
  
##  <a name="findindex"></a>CAtlList::FindIndex  
 Bir dizin değeri verilen bir öğenin konumunu almak için bu yöntemi çağırın.  
  
```
POSITION FindIndex(size_t iElement) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `iElement`  
 Gerekli liste öğesinin sıfır tabanlı dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karşılık gelen konum değeri ya da NULL ise döndürür `iElement` aralık dışında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem erişimine izin verilen dizine değerine karşılık gelen KONUMUNU döndürür  *n* listesinde th öğesi.  
  
 Hata ayıklama derlemelerinde, bir onaylama hatası ortaya liste nesnesi geçerli değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#20](../../atl/codesnippet/cpp/catllist-class_8.cpp)]  
  
##  <a name="getat"></a>CAtlList::GetAt  
 Listede belirtilen bir konuma öğede döndürmek için bu yöntemi çağırın.  
  
```
E& GetAt(POSITION pos) throw();
const E& GetAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Belirli bir öğeyle belirten konum değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru veya kopyasını, öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste ise **const**, `GetAt` öğenin bir kopyasını döndürür. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak bir yöntem sağlar ve liste değiştirilmeye karşı korur.  
  
 Listede değilse **const**, `GetAt` öğesine bir başvuru döndürür. Bu atama ifadesinin iki tarafında kullanılacak bir yöntem sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
 Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `pos` NULL değerine eşittir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlList::FindIndex](#findindex).  
  
##  <a name="getcount"></a>CAtlList::GetCount  
 Listede nesne sayısını döndürmek için bu yöntemi çağırın.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listedeki öğe sayısını döndürür.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlList::Find](#find).  
  
##  <a name="gethead"></a>CAtlList::GetHead  
 Listenin başındaki öğesi döndürmek için bu yöntemi çağırın.  
  
```
E& GetHead() throw();
const E& GetHead() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru ya da bir kopyasını, listenin başındaki öğesi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste ise **const**, `GetHead` listenin başındaki öğenin bir kopyasını döndürür. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak bir yöntem sağlar ve liste değiştirilmeye karşı korur.  
  
 Listede değilse **const**, `GetHead` listenin başındaki öğeye bir başvuru döndürür. Bu atama ifadesinin iki tarafında kullanılacak bir yöntem sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
 Hata ayıklama derlemelerinde, listenin başındaki NULL olarak gösteriyorsa onaylama hatası meydana gelir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlList::AddHead](#addhead).  
  
##  <a name="getheadposition"></a>CAtlList::GetHeadPosition  
 Listenin başındaki konumunu almak için bu yöntemi çağırın.  
  
```
POSITION GetHeadPosition() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listenin başındaki öğesine karşılık gelen konum değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste boşsa, döndürülen değer NULL olur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#21](../../atl/codesnippet/cpp/catllist-class_9.cpp)]  
  
##  <a name="getnext"></a>CAtlList::GetNext  
 Sonraki öğeye listeden döndürmek için bu yöntemi çağırın.  
  
```
E& GetNext(POSITION& pos) throw();
const E& GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Önceki bir çağrı tarafından döndürülen bir konum değeri `GetNext`, [CAtlList::GetHeadPosition](#getheadposition), veya diğer `CAtlList` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste ise **const**, `GetNext` listesinin sonraki öğenin bir kopyasını döndürür. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak bir yöntem sağlar ve liste değiştirilmeye karşı korur.  
  
 Listede değilse **const**, `GetNext` listesinin sonraki öğeye bir başvuru döndürür. Bu atama ifadesinin iki tarafında kullanılacak bir yöntem sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Konum sayaç `pos`, listedeki sonraki öğeye noktası ya da daha fazla öğe varsa NULL için güncelleştirilmiştir. Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `pos` NULL değerine eşittir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlList::GetHeadPosition](#getheadposition).  
  
##  <a name="getprev"></a>CAtlList::GetPrev  
 Önceki öğeyi listeden döndürmek için bu yöntemi çağırın.  
  
```
E& GetPrev(POSITION& pos) throw();
const E& GetPrev(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Önceki bir çağrı tarafından döndürülen bir konum değeri `GetPrev`, [CAtlList::GetTailPosition](#gettailposition), veya diğer `CAtlList` yöntemi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste ise **const**, `GetPrev` listedeki bir öğeye kopyasını döndürür. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak bir yöntem sağlar ve liste değiştirilmeye karşı korur.  
  
 Listede değilse **const**, `GetPrev` liste öğesi için bir başvuru döndürür. Bu atama ifadesinin iki tarafında kullanılacak bir yöntem sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Konum sayaç `pos`, listesinde önceki öğesine işaret ya da daha fazla öğe varsa NULL için güncelleştirilmiştir. Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `pos` NULL değerine eşittir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlList::GetTailPosition](#gettailposition).  
  
##  <a name="gettail"></a>CAtlList::GetTail  
 Listenin kuyruğu öğede döndürmek için bu yöntemi çağırın.  
  
```
E& GetTail() throw();
const E& GetTail() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru ya da bir kopyasını, listenin kuyruğu öğede döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste ise **const**, `GetTail` listenin başındaki öğenin bir kopyasını döndürür. Bu, yalnızca sağ tarafta Atama ifadesinin kullanılacak bir yöntem sağlar ve liste değiştirilmeye karşı korur.  
  
 Listede değilse **const**, `GetTail` listenin başındaki öğeye bir başvuru döndürür. Bu atama ifadesinin iki tarafında kullanılacak bir yöntem sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
 Listenin kuyruğu NULL olarak gösteriyorsa hata ayıklama derlemelerinde, bir onaylama hatası meydana gelir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlList::AddTail](#addtail).  
  
##  <a name="gettailposition"></a>CAtlList::GetTailPosition  
 Tail listesinin konumunu almak için bu yöntemi çağırın.  
  
```
POSITION GetTailPosition() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listenin kuyruğu öğede karşılık gelen konum değeri döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Liste boşsa, döndürülen değer NULL olur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#22](../../atl/codesnippet/cpp/catllist-class_10.cpp)]  
  
##  <a name="inargtype"></a>CAtlList::INARGTYPE  
 Bir giriş bağımsız değişkeni bir öğe geçirildiğinde kullanılan türü.  
  
```
typedef ETraits::INARGTYPE INARGTYPE;
```  
  
##  <a name="insertafter"></a>CAtlList::InsertAfter  
 Yeni bir öğe belirtilen konuma sonra listeye eklemek için bu yöntemi çağırın.  
  
```
POSITION InsertAfter(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Konum değerini daha sonra yeni öğe eklenir.  
  
 `element`  
 Eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni öğe konumu değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bir onaylama hatası ortaya ekleme başarısız olursa ya da sonra Kuyruk öğesi eklemek için bir girişimde listesi geçerli değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#23](../../atl/codesnippet/cpp/catllist-class_11.cpp)]  
  
##  <a name="insertbefore"></a>CAtlList::InsertBefore  
 Yeni bir öğe belirtilen konuma önce listeye eklemek için bu yöntemi çağırın.  
  
```
POSITION InsertBefore(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Yeni öğe, bu konum değeri önce listeye eklenir.  
  
 `element`  
 Eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni öğe konumu değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bir onaylama hatası ortaya ekleme başarısız olursa ya da önce head öğesi eklemek için bir girişimde listesi geçerli değil.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#24](../../atl/codesnippet/cpp/catllist-class_12.cpp)]  
  
##  <a name="isempty"></a>CAtlList::IsEmpty  
 Liste boş olup olmadığını belirlemek için bu yöntemi çağırın.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listede hiçbir nesne, aksi takdirde false varsa true değerini döndürür.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#25](../../atl/codesnippet/cpp/catllist-class_13.cpp)]  
  
##  <a name="movetohead"></a>CAtlList::MoveToHead  
 Listenin başında belirtilen öğe taşımak için bu yöntemi çağırın.  
  
```
void MoveToHead(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Taşımak için öğesinin konum değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen öğe, listenin başındaki geçerli konumundan taşınır. Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `pos` NULL değerine eşittir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#26](../../atl/codesnippet/cpp/catllist-class_14.cpp)]  
  
##  <a name="movetotail"></a>CAtlList::MoveToTail  
 Listenin kuyruk için belirtilen öğe taşımak için bu yöntemi çağırın.  
  
```
void MoveToTail(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Taşımak için öğesinin konum değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen öğe listesi kuyruğu için geçerli konumundan taşınır. Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `pos` NULL değerine eşittir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlList::MoveToHead](#movetohead).  
  
##  <a name="removeall"></a>CAtlList::RemoveAll  
 Tüm öğeleri listeden kaldırmak için bu yöntemi çağırın.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem, tüm öğeleri listeden kaldırır ve ayrılmış bellek boşaltır. Tüm öğeler silinmez veya liste yapısını bozulmuşsa hatalarını düzeltir derlemelerde bir ATLASSERT gerçekleştirilecektir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlList::IsEmpty](#isempty).  
  
##  <a name="removeat"></a>CAtlList::RemoveAt  
 Tek bir öğe listesinden kaldırmak için bu yöntemi çağırın.  
  
```
void RemoveAt(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Kaldırılacak öğenin konum değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından başvuruda bulunulan öğe `pos` kaldırılır ve bellek serbest. Kullanmak için kabul edilebilir `RemoveAt` kafası veya kuyruğu listesinin kaldırmak için.  
  
 Hata ayıklama derlemelerinde, listenin geçerli değilse veya liste yapısını parçası olmayan erişim belleği listesine öğe kaldırıldığında neden olursa bir onaylama hatası meydana gelir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#27](../../atl/codesnippet/cpp/catllist-class_15.cpp)]  
  
##  <a name="removehead"></a>CAtlList::RemoveHead  
 Listenin başındaki öğesini kaldırmak için bu yöntemi çağırın.  
  
```
E RemoveHead();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listenin başındaki öğeyi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Head öğesi listesinden silinir ve bellek serbest bırakılır. Öğenin bir kopyasını döndürülür. Hata ayıklama derlemelerinde, liste boşsa bir onaylama hatası meydana gelir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#28](../../atl/codesnippet/cpp/catllist-class_16.cpp)]  
  
##  <a name="removeheadnoreturn"></a>CAtlList::RemoveHeadNoReturn  
 Değer döndürme olmadan listenin başındaki öğesini kaldırmak için bu yöntemi çağırın.  
  
```
void RemoveHeadNoReturn() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Head öğesi listesinden silinir ve bellek serbest bırakılır. Hata ayıklama derlemelerinde, liste boşsa bir onaylama hatası meydana gelir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlList::IsEmpty](#isempty).  
  
##  <a name="removetail"></a>CAtlList::RemoveTail  
 Listenin kuyruğu öğede kaldırmak için bu yöntemi çağırın.  
  
```
E RemoveTail();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Listenin kuyruğu öğede döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Kuyruk öğesi listesinden silinir ve bellek serbest bırakılır. Öğenin bir kopyasını döndürülür. Hata ayıklama derlemelerinde, liste boşsa bir onaylama hatası meydana gelir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#29](../../atl/codesnippet/cpp/catllist-class_17.cpp)]  
  
##  <a name="removetailnoreturn"></a>CAtlList::RemoveTailNoReturn  
 Değer döndürme olmadan listesi kuyruğu öğede kaldırmak için bu yöntemi çağırın.  
  
```
void RemoveTailNoReturn() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Kuyruk öğesi listesinden silinir ve bellek serbest bırakılır. Hata ayıklama derlemelerinde, liste boşsa bir onaylama hatası meydana gelir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlList::IsEmpty](#isempty).  
  
##  <a name="setat"></a>CAtlList::SetAt  
 Listesinde verilen konumda öğenin değerini ayarlamak için bu yöntemi çağırın.  
  
```
void SetAt(POSITION pos, INARGTYPE element);
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 KONUMU değiştirmek için öğeye karşılık gelen değer.  
  
 `element`  
 Yeni öğe değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Varolan değeri ile değiştirir `element`. Hata ayıklama derlemelerinde, bir onaylama işlemi hatasına oluşacaktır `pos` NULL değerine eşittir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#30](../../atl/codesnippet/cpp/catllist-class_18.cpp)]  
  
##  <a name="swapelements"></a>CAtlList::SwapElements  
 Listesindeki öğeleri değiştirmek için bu yöntemi çağırın.  
  
```
void SwapElements(POSITION pos1, POSITION pos2) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *pos1*  
 İlk konum değeri.  
  
 *pos2*  
 İkinci konum değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen iki konumlarda öğeleri değiştirir. Hata ayıklama derlemelerinde, iki konum değeri NULL değerine eşitse onaylama hatası meydana gelir.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#31](../../atl/codesnippet/cpp/catllist-class_19.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CList sınıfı](../../mfc/reference/clist-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
