---
title: CUIntArray sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CUIntArray
- AFXCOLL/CUIntArray
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
ms.assetid: d71f3d8f-ef9f-4e48-9b69-7782c0e2ddf7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b2f5f0a72c08aeabcd764cf4c7763c9506769585
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121630"
---
# <a name="cuintarray-class"></a>CUIntArray sınıfı
İmzasız tamsayılar dizileri destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CUIntArray : public CObject  
```  
  
## <a name="members"></a>Üyeler  
 Üye işlevlerini `CUIntArray` sınıfının üye fonksiyonları benzer [CObArray](../../mfc/reference/cobarray-class.md). Bu benzerlik nedeniyle kullandığınız `CObArray` başvuru belgelerini üye fonksiyonu özellikleri için. Gördüğünüz yerde bir `CObject` işaretçisi bir işlev parametresi veya dönüş değeri olarak bir UINT değiştirin.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 Örneğin, çevrilir  
  
 `UINT CUIntArray::GetAt( int <nIndex> ) const;`  
  
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
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizideki öğelere erişim sağlar. NULL olabilir.|  
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
 İşletim ortamı hedef bağlı olarak bir UINT fiziksel boyutunu değiştirebilirsiniz imzasız tamsayı ya da UINT, sözcükleri ve doublewords farklıdır. Bir UINT bir doubleword aynı boyutta olur.  
  
 `CUIntArray` bir araya getirir [ımplement_dynamıc](run-time-object-model-services.md#implement_dynamic) çalışma zamanı tür erişimi ve için dökme desteklemek için makrosu bir [CDumpContext](../../mfc/reference/cdumpcontext-class.md) nesnesi. Tek tek işaretsiz tamsayı öğelerinin bir döküm gerekiyorsa, 1 veya daha büyük döküm bağlam derinliği ayarlamanız gerekir. İşaretsiz tamsayı diziler seri hale getirilemez.  
  
> [!NOTE]
>  Bir dizi kullanmadan önce kullanın `SetSize` boyutuna kurmak ve bunun için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, dizinizi için öğe eklemek görüntülenmesine neden olur sık bırakılan ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara.  
  
 Kullanma hakkında daha fazla bilgi için `CUIntArray`, makaleye bakın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CUIntArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



