---
title: "CPtrArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPtrArray
- AFXCOLL/CPtrArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: c23b87a3-bf84-49d6-a66b-61e999d0938a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 90f04b55a06ef5f24fe4c0b9906d8364a22051dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cptrarray-class"></a>CPtrArray sınıfı
Void işaretçileri dizileri destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPtrArray : public CObject  
```  
  
## <a name="members"></a>Üyeler  
 Üye işlevlerini `CPtrArray` sınıfının üye fonksiyonları benzer [CObArray](../../mfc/reference/cobarray-class.md). Bu benzerlik nedeniyle kullandığınız `CObArray` başvuru belgelerini üye fonksiyonu özellikleri için. Gördüğünüz yerde bir `CObject` işaretçisi bir işlev parametresi veya dönüş değeri olarak değiştirmek için bir işaretçi `void`.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 Örneğin, çevrilir  
  
 `void* CPtrArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Bir öğeyi dizinin sonuna ekler; dizi gerekirse artar.|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Başka bir dizi diziye ekler; dizi gerekirse artar.|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Başka bir dizi diziye kopyalar; dizi gerekirse artar.|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi öğesi işaretçinin geçici bir başvuru döndürür.|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli bir üst sınır yukarıdaki tüm kullanılmayan belleği serbest bırakır.|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Belirtilen dizindeki değeri döndürür.|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizide öğe sayısını alır.|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişim sağlar. Olabilir `NULL`.|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizide öğe sayısını alır.|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizinini döndürür.|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Bir öğenin (veya başka bir dizinin tüm öğeleri) belirtilen bir dizinde ekler.|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Dizi boş olup olmadığını belirler.|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizisinden tüm öğeleri kaldırır.|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizinindeki bir öğeyi kaldırır.|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirli bir dizine için değeri ayarlar; dizi büyümeye izin verilmiyor.|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirli bir dizine için değeri ayarlar; dizi gerekirse artar.|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizide dahil edilmek üzere öğe sayısını ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::operator]](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CPtrArray`bir araya getirir `IMPLEMENT_DYNAMIC` çalışma zamanı tür erişimi ve için dökme desteklemek için makrosu bir `CDumpContext` nesnesi. Tek tek işaretçi dizi öğelerinin bir döküm gerekiyorsa, 1 veya daha büyük döküm bağlam derinliği ayarlamanız gerekir.  
  
> [!NOTE]
>  Bir dizi kullanmadan önce kullanın `SetSize` boyutuna kurmak ve bunun için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, dizinizi için öğe eklemek görüntülenmesine neden olur sık bırakılan ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara.  
  
 İşaretçi diziler seri hale getirilemez.  
  
 Bir işaretçi dizi silindiğinde veya öğeleri kaldırıldığında, yalnızca işaretçileri kaldırılır, yok oldukları varlıklar.  
  
 Kullanma hakkında daha fazla bilgi için `CPtrArray`, makaleye bakın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CPtrArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CObArray Sınıfı](../../mfc/reference/cobarray-class.md)
