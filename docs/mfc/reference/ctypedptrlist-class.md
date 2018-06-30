---
title: CTypedPtrList sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c3f74782241ec69d77ec55b8613c59f87adb40fb
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37122836"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList sınıfı
Tür kullanımı uyumlu "sarmalayıcı" sınıfının nesneleri için sağlar `CPtrList`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class BASE_CLASS, class TYPE>  
class CTypedPtrList : public BASE_CLASS  
```  
  
#### <a name="parameters"></a>Parametreler  
 *BASE_CLASS*  
 Yazılan işaretçi liste sınıfın temel sınıf; bir işaretçi liste sınıf olmalıdır ( `CObList` veya `CPtrList`).  
  
 *TÜRÜ*  
 Taban sınıfı listesinde depolanan öğelerin türü.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CTypedPtrList::AddHead](#addhead)|Bir öğenin (veya başka bir listedeki tüm öğelerin) (yeni head yapmaz) listenin başında ekler.|  
|[CTypedPtrList::AddTail](#addtail)|Bir öğenin (veya başka bir listedeki tüm öğelerin) (yeni bir kuyruk yapmaz) listesi kuyruğu için ekler.|  
|[CTypedPtrList::GetAt](#getat)|Öğe verilen konumunda alır.|  
|[CTypedPtrList::GetHead](#gethead)|(Boş olamaz) listesinin head öğesi döndürür.|  
|[CTypedPtrList::GetNext](#getnext)|Yineleme için sonraki öğeyi alır.|  
|[CTypedPtrList::GetPrev](#getprev)|Yineleme için önceki öğesi alır.|  
|[CTypedPtrList::GetTail](#gettail)|(Boş olamaz) listesinin kuyruk öğesi döndürür.|  
|[CTypedPtrList::RemoveHead](#removehead)|Listenin başından öğeyi kaldırır.|  
|[CTypedPtrList::RemoveTail](#removetail)|Öğeyi listenin tail kaldırır.|  
|[CTypedPtrList::SetAt](#setat)|Öğe verilen konumunda ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Kullandığınızda `CTypedPtrList` yerine `CObList` veya `CPtrList`, C++ tür denetleme olanağı eşleşmeyen işaretçi türlerine göre neden olduğu hata ortadan kaldırmanıza yardımcı olur.  
  
 Ayrıca, `CTypedPtrList` sarmalayıcı kullandıysanız, gerekli olacak atama çoğunu gerçekleştirir `CObList` veya `CPtrList`.  
  
 Çünkü tüm `CTypedPtrList` işlevler satır içi, bu şablonu kullanımını boyutunu veya kodunuzu hızına önemli ölçüde etkilemez.  
  
 Listeleri türetilen `CObList` , ancak bu türetilen seri hale getirilebilir `CPtrList` olamaz.  
  
 Zaman bir `CTypedPtrList` Nesne silindiğinden veya öğeleri kaldırıldığında, yalnızca işaretçileri kaldırılır, yok oldukları varlıklar.  
  
 Kullanma hakkında daha fazla bilgi için `CTypedPtrList`, makalelerine bakın [koleksiyonları](../../mfc/collections.md) ve [şablona dayalı sınıflar](../../mfc/template-based-classes.md).  
  
## <a name="example"></a>Örnek  
 Bu örnek bir örneğini oluşturur `CTypedPtrList`, bir nesne ekler, disk listesine serileştirir ve nesneyi siler:  
  
 [!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]  
  
 [!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `BASE_CLASS`  
  
 `_CTypedPtrList`  
  
 `CTypedPtrList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtempl.h  
  
##  <a name="addhead"></a>  CTypedPtrList::AddHead  
 Bu üye işlevi çağırır `BASE_CLASS` **:: AddHead**.  
  
```  
POSITION AddHead(TYPE newElement);  
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Taban sınıfı listesinde depolanan öğelerin türü.  
  
 *newElement*  
 Bu listeye eklenecek nesne işaretçisi. Bir NULL değerine izin verilir.  
  
 *BASE_CLASS*  
 Yazılan işaretçi liste sınıfın temel sınıf; bir işaretçi liste sınıf olmalıdır ( [CObList](../../mfc/reference/coblist-class.md) veya [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 *pNewList*  
 Başka bir işaretçi [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) nesnesi. Öğeleri *pNewList* bu listeye eklenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürüm konumu yeni eklenen öğenin değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sürüm, listenin başındaki önce yeni bir öğe ekler. İkinci Sürüm öğelerinin head önce başka bir listesine ekler.  
  
##  <a name="addtail"></a>  CTypedPtrList::AddTail  
 Bu üye işlevi çağırır `BASE_CLASS` **:: AddTail**.  
  
```  
POSITION AddTail(TYPE newElement);  
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Taban sınıfı listesinde depolanan öğelerin türü.  
  
 *newElement*  
 Bu listeye eklenecek nesne işaretçisi. Bir NULL değerine izin verilir.  
  
 *BASE_CLASS*  
 Yazılan işaretçi liste sınıfın temel sınıf; bir işaretçi liste sınıf olmalıdır ( [CObList](../../mfc/reference/coblist-class.md) veya [CPtrList](../../mfc/reference/cptrlist-class.md)).  
  
 *pNewList*  
 Başka bir işaretçi [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) nesnesi. Öğeleri *pNewList* bu listeye eklenir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürüm konumu yeni eklenen öğenin değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sürüm listesi tail sonra yeni bir öğe ekler. İkinci sürüm listesi tail sonra başka bir öğe listesi ekler.  
  
##  <a name="getat"></a>  CTypedPtrList::GetAt  
 KONUM türünde bir değişken listesi için bir anahtardır.  
  
```  
TYPE& GetAt(POSITION position);  
TYPE GetAt(POSITION position) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede depolanan öğelerin türünü belirten bir şablon parametre.  
  
 *Konumu*  
 Önceki tarafından döndürülen bir konum değeri `GetHeadPosition` veya `Find` üye işlev çağrısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste için bir işaretçi üzerinden erişilen varsa bir `const CTypedPtrList`, ardından `GetAt` şablon parametresi tarafından belirtilen türde bir işaretçi döndürür *türü*. Bu yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece listenin değiştirilmeye karşı korur.  
  
 Listenin doğrudan veya bir işaretçi üzerinden erişiliyorsa bir `CTypedPtrList`, ardından `GetAt` şablon parametresi tarafından belirtilen türde bir işaretçi bir başvuru döndürür *türü*. Bu atama ifadesinin iki tarafında kullanılacak işlevi sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu dizin ile aynı değildir ve bir konum değeri kendiniz çalışamaz. `GetAt` alır `CObject` verilen bir konumu ile ilişkili işaretçi.  
  
 KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmalısınız. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Bu satır içi işlev çağrılarını `BASE_CLASS` **:: GetAt**.  
  
##  <a name="gethead"></a>  CTypedPtrList::GetHead  
 Head öğesi, bu listenin temsil eden imleci alır.  
  
```  
TYPE& GetHead();  
TYPE GetHead() const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede depolanan öğelerin türünü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste için bir işaretçi üzerinden erişilen varsa bir `const CTypedPtrList`, ardından `GetHead` şablon parametresi tarafından belirtilen türde bir işaretçi döndürür *türü*. Bu yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece listenin değiştirilmeye karşı korur.  
  
 Listenin doğrudan veya bir işaretçi üzerinden erişiliyorsa bir `CTypedPtrList`, ardından `GetHead` şablon parametresi tarafından belirtilen türde bir işaretçi bir başvuru döndürür *türü*. Bu atama ifadesinin iki tarafında kullanılacak işlevi sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `GetHead`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](../../mfc/reference/coblist-class.md#isempty) liste öğeleri içerdiğini doğrulayın.  
  
##  <a name="getnext"></a>  CTypedPtrList::GetNext  
 Tarafından tanımlanan liste öğesi alır *rPosition*, ardından ayarlar *rPosition* listesindeki sonraki girdi konumu değerine.  
  
```  
TYPE& GetNext(POSITION& rPosition);  
TYPE GetNext(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Bu listede yer alan öğelerin türünü belirten bir şablon parametre.  
  
 *rPosition*  
 Önceki tarafından döndürülen bir konum değeri başvuru `GetNext`, `GetHeadPosition`, ya da diğer üye işlev çağrısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste için bir işaretçi üzerinden erişilen varsa bir `const CTypedPtrList`, ardından `GetNext` şablon parametresi tarafından belirtilen türde bir işaretçi döndürür *türü*. Bu yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece listenin değiştirilmeye karşı korur.  
  
 Listenin doğrudan veya bir işaretçi üzerinden erişiliyorsa bir `CTypedPtrList`, ardından `GetNext` şablon parametresi tarafından belirtilen türde bir işaretçi bir başvuru döndürür *türü*. Bu atama ifadesinin iki tarafında kullanılacak işlevi sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `GetNext` çağrısıyla ilk konum kurarsanız ileriye doğru yineleme döngü `GetHeadPosition` veya [CPtrList::Find](../../mfc/reference/coblist-class.md#find).  
  
 KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmalısınız. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Alınan öğe listesinde, son sonra yeni değeri ise *rPosition* NULL olarak ayarlandı.  
  
 Yineleme sırasında bir öğeyi kaldırın mümkündür. Örneğin bkz [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat).  
  
##  <a name="getprev"></a>  CTypedPtrList::GetPrev  
 Tarafından tanımlanan liste öğesi alır *rPosition*, ardından ayarlar *rPosition* için listede bir önceki girişi konum değerini.  
  
```  
TYPE& GetPrev(POSITION& rPosition);  
TYPE GetPrev(POSITION& rPosition) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Bu listede yer alan öğelerin türünü belirten bir şablon parametre.  
  
 *rPosition*  
 Önceki tarafından döndürülen bir konum değeri başvuru `GetPrev` veya diğer üye işlev çağrısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste için bir işaretçi üzerinden erişilen varsa bir `const CTypedPtrList`, ardından `GetPrev` şablon parametresi tarafından belirtilen türde bir işaretçi döndürür *türü*. Bu yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece listenin değiştirilmeye karşı korur.  
  
 Listenin doğrudan veya bir işaretçi üzerinden erişiliyorsa bir `CTypedPtrList`, ardından `GetPrev` şablon parametresi tarafından belirtilen türde bir işaretçi bir başvuru döndürür *türü*. Bu atama ifadesinin iki tarafında kullanılacak işlevi sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanabileceğiniz `GetPrev` çağrısıyla ilk konum kurarsanız geriye doğru yineleme döngü `GetTailPosition` veya `Find`.  
  
 KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmalısınız. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Alınan öğe listede ilk sonra yeni değeri ise *rPosition* NULL olarak ayarlandı.  
  
##  <a name="gettail"></a>  CTypedPtrList::GetTail  
 Head öğesi, bu listenin temsil eden imleci alır.  
  
```  
TYPE& GetTail();  
TYPE GetTail() const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede depolanan öğelerin türünü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Liste için bir işaretçi üzerinden erişilen varsa bir `const CTypedPtrList`, ardından `GetTail` şablon parametresi tarafından belirtilen türde bir işaretçi döndürür *türü*. Bu yalnızca sağ tarafta Atama ifadesinin kullanılacak işlevi sağlar ve böylece listenin değiştirilmeye karşı korur.  
  
 Listenin doğrudan veya bir işaretçi üzerinden erişiliyorsa bir `CTypedPtrList`, ardından `GetTail` şablon parametresi tarafından belirtilen türde bir işaretçi bir başvuru döndürür *türü*. Bu atama ifadesinin iki tarafında kullanılacak işlevi sağlar ve böylece değiştirilecek Liste girişlerini sağlar.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `GetTail`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](../../mfc/reference/coblist-class.md#isempty) liste öğeleri içerdiğini doğrulayın.  
  
##  <a name="removehead"></a>  CTypedPtrList::RemoveHead  
 Listenin başından öğeyi kaldırır ve döndürür.  
  
```  
TYPE RemoveHead();
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede depolanan öğelerin türünü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce listenin başındaki işaretçi. Bu şablon parametresi tarafından belirtilen türde işaretçidir *türü*.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `RemoveHead`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](../../mfc/reference/coblist-class.md#isempty) liste öğeleri içerdiğini doğrulayın.  
  
##  <a name="removetail"></a>  CTypedPtrList::RemoveTail  
 Öğeyi listenin tail kaldırır ve döndürür.  
  
```  
TYPE RemoveTail();
```  
  
### <a name="parameters"></a>Parametreler  
 *TÜRÜ*  
 Listede depolanan öğelerin türünü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Daha önce tail listesinin en işaretçi. Bu şablon parametresi tarafından belirtilen türde işaretçidir *türü*.  
  
### <a name="remarks"></a>Açıklamalar  
 Listenin çağırmadan önce boş olmadığından emin olmalısınız `RemoveTail`. Liste boşsa, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar. Kullanım [IsEmpty](../../mfc/reference/coblist-class.md#isempty) liste öğeleri içerdiğini doğrulayın.  
  
##  <a name="setat"></a>  CTypedPtrList::SetAt  
 Bu üye işlevi çağırır `BASE_CLASS` **:: SetAt**.  
  
```  
void SetAt(POSITION pos, TYPE newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *POS*  
 Ayarlanacak öğenin konumu.  
  
 *TÜRÜ*  
 Taban sınıfı listesinde depolanan öğelerin türü.  
  
 *newElement*  
 Listeye yazılacak nesne işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 KONUM türünde bir değişken listesi için bir anahtardır. Bu dizin ile aynı değildir ve bir konum değeri kendiniz çalışamaz. `SetAt` nesne işaretçisi listede belirtilen konuma yazar.  
  
 KONUM değeri geçerli bir konum listesinde temsil ettiğini emin olmalısınız. Geçersiz ise, Microsoft Foundation Class Kitaplığı hata ayıklama sürümü onaylar.  
  
 Daha ayrıntılı açıklamalar için bkz: [CObList::SetAt](../../mfc/reference/coblist-class.md#setat).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek Topla](../../visual-cpp-samples.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CPtrList sınıfı](../../mfc/reference/cptrlist-class.md)   
 [CObList Sınıfı](../../mfc/reference/coblist-class.md)
