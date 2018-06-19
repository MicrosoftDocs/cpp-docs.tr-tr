---
title: CStringList sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringList
- AFXCOLL/CStringList
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
ms.assetid: 310a7edb-263c-4bd2-ac43-0bfbfddc5a33
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 91a88fc73b27323327bce477fa2cdaca747ed21c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33375154"
---
# <a name="cstringlist-class"></a>CStringList sınıfı
Listelerini destekler `CString` nesneleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CStringList : public CObject  
```  
  
## <a name="members"></a>Üyeler  
 Üye işlevlerini `CStringList` sınıfının üye fonksiyonları benzer [CObList](../../mfc/reference/coblist-class.md). Bu benzerlik nedeniyle kullandığınız `CObList` başvuru belgelerini üye fonksiyonu özellikleri için. Yerde gördüğünüz bir `CObject` işaretçi dönüş değeri olarak, alternatif bir `CString` (değil bir `CString` işaretçisi). Gördüğünüz yerde bir `CObject` işaretçi işlevi parametre olarak, alternatif bir `LPCTSTR`.  
  
 `CObject*& CObList::GetHead() const;`  
  
 Örneğin, çevrilir  
  
 `CString& CStringList::GetHead() const;`  
  
 and  
  
 `POSITION AddHead( CObject* <newElement> );`  
  
 çevrilir  
  
 `POSITION AddHead( LPCTSTR <newElement> );`  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObList::CObList](../../mfc/reference/coblist-class.md#coblist)|Boş bir liste oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObList::AddHead](../../mfc/reference/coblist-class.md#addhead)|Bir öğenin (veya başka bir listedeki tüm öğelerin) (yeni head yapmaz) listenin başında ekler.|  
|[CObList::AddTail](../../mfc/reference/coblist-class.md#addtail)|Bir öğenin (veya başka bir listedeki tüm öğelerin) (yeni bir kuyruk yapmaz) listesi kuyruğu için ekler.|  
|[CObList::Find](../../mfc/reference/coblist-class.md#find)|İşaretçi değeri tarafından belirtilen bir öğenin konumunu alır.|  
|[CObList::FindIndex](../../mfc/reference/coblist-class.md#findindex)|Bir öğenin sıfır tabanlı dizini tarafından belirtilen konumunu alır.|  
|[CObList::GetAt](../../mfc/reference/coblist-class.md#getat)|Öğe verilen konumunda alır.|  
|[CObList::GetCount](../../mfc/reference/coblist-class.md#getcount)|Bu listedeki öğe sayısını döndürür.|  
|[CObList::GetHead](../../mfc/reference/coblist-class.md#gethead)|(Boş olamaz) listesinin head öğesi döndürür.|  
|[CObList::GetHeadPosition](../../mfc/reference/coblist-class.md#getheadposition)|Head öğesi listesinin konumunu döndürür.|  
|[CObList::GetNext](../../mfc/reference/coblist-class.md#getnext)|Yineleme için sonraki öğeyi alır.|  
|[CObList::GetPrev](../../mfc/reference/coblist-class.md#getprev)|Yineleme için önceki öğesi alır.|  
|[CObList::GetSize](../../mfc/reference/coblist-class.md#getsize)|Bu listedeki öğe sayısını döndürür.|  
|[CObList::GetTail](../../mfc/reference/coblist-class.md#gettail)|(Boş olamaz) listesinin kuyruk öğesi döndürür.|  
|[CObList::GetTailPosition](../../mfc/reference/coblist-class.md#gettailposition)|Tail öğenin listesinin konumunu döndürür.|  
|[CObList::InsertAfter](../../mfc/reference/coblist-class.md#insertafter)|Verilen bir konuma sonra yeni bir öğe ekler.|  
|[CObList::InsertBefore](../../mfc/reference/coblist-class.md#insertbefore)|Verilen bir konuma önce yeni bir öğe ekler.|  
|[CObList::IsEmpty](../../mfc/reference/coblist-class.md#isempty)|Testler için boş liste koşul (öğe yok).|  
|[CObList::RemoveAll](../../mfc/reference/coblist-class.md#removeall)|Tüm öğeleri bu listeden kaldırır.|  
|[CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat)|Bu listeden konumu tarafından belirtilen bir öğeyi kaldırır.|  
|[CObList::RemoveHead](../../mfc/reference/coblist-class.md#removehead)|Listenin başından öğeyi kaldırır.|  
|[CObList::RemoveTail](../../mfc/reference/coblist-class.md#removetail)|Öğeyi listenin tail kaldırır.|  
|[CObList::SetAt](../../mfc/reference/coblist-class.md#setat)|Öğe verilen konumunda ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Tüm karşılaştırmaları dizedeki karakter dizeleri adresler yerine karşılaştırılır anlamı değeriyle yapılır.  
  
 `CStringList` bir araya getirir `IMPLEMENT_SERIAL` makrosu seri hale getirme ve alt öğeleri dökme desteklemek için. Bir listesi, `CString` nesneleri aşırı yüklenmiş ekleme işleciyle veya ile bir arşivde saklanır `Serialize` her üye işlev `CString` öğenin sırayla sıralandığı.  
  
 Tek bir dökümü gerekiyorsa `CString` öğeleri ayarlamalısınız döküm içerik derinliği 1 veya daha büyük.  
  
 Kullanma hakkında daha fazla bilgi için `CStringList`, makaleye bakın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CStringList`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek Topla](../../visual-cpp-samples.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



