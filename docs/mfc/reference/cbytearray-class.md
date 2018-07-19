---
title: CByteArray sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CByteArray
- AFXCOLL/CByteArray
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
ms.assetid: 53d4a512-657c-4187-9609-e3f5339a78e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 22e138b586070a0e47ffa399d2c76d086fd4b951
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335860"
---
# <a name="cbytearray-class"></a>CByteArray sınıfı
Dinamik bayt dizilerini destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CByteArray : public CObject  
```  
  
## <a name="members"></a>Üyeler  
 Üye işlevlerinin `CByteArray` sınıfın üye işlevleri için benzer [CObArray](../../mfc/reference/cobarray-class.md). Bu benzerlik nedeniyle kullanabileceğiniz `CObArray` başvuru belgeleri üye işlev özellikleri için. Gördüğünüz yerde bir `CObject` işaretçi bir işlev parametre veya dönüş değeri olarak bir bayt değiştirin.  
  
 `CObject* CObArray::GetAt( int <nIndex> ) const;`  
  
 Örneğin, için çevirir  
  
 `BYTE CByteArray::GetAt( int <nIndex> ) const;`  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::CObArray](../../mfc/reference/cobarray-class.md#cobarray)|Boş bir dizi oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::Add](../../mfc/reference/cobarray-class.md#add)|Dizinin sonuna bir öğe ekler; dizi gerekirse büyür.|  
|[CObArray::Append](../../mfc/reference/cobarray-class.md#append)|Diziyi başka diziye ekler; dizi gerekirse büyür.|  
|[CObArray::Copy](../../mfc/reference/cobarray-class.md#copy)|Diziyi başka diziye kopyalar; dizi gerekirse büyür.|  
|[CObArray::ElementAt](../../mfc/reference/cobarray-class.md#elementat)|Dizi içinde bayta geçici bir başvuru döndürür.|  
|[CObArray::FreeExtra](../../mfc/reference/cobarray-class.md#freeextra)|Geçerli üst sınır yukarıdaki tüm kullanılmayan belleği serbest bırakır.|  
|[CObArray::GetAt](../../mfc/reference/cobarray-class.md#getat)|Belirtilen dizindeki değeri döndürür.|  
|[CObArray::GetCount](../../mfc/reference/cobarray-class.md#getcount)|Bu dizinin içinde öğe sayısını alır.|  
|[CObArray::GetData](../../mfc/reference/cobarray-class.md#getdata)|Dizide öğelere erişim sağlar. NULL olabilir.|  
|[CObArray::GetSize](../../mfc/reference/cobarray-class.md#getsize)|Bu dizinin içinde öğe sayısını alır.|  
|[CObArray::GetUpperBound](../../mfc/reference/cobarray-class.md#getupperbound)|En büyük geçerli dizinini döndürür.|  
|[CObArray::InsertAt](../../mfc/reference/cobarray-class.md#insertat)|Belirtilen dizindeki öğenin (veya başka bir dizideki tüm öğeler) ekler.|  
|[CObArray::IsEmpty](../../mfc/reference/cobarray-class.md#isempty)|Dizi boş olup olmadığını belirler.|  
|[CObArray::RemoveAll](../../mfc/reference/cobarray-class.md#removeall)|Bu dizisinden tüm öğeleri kaldırır.|  
|[CObArray::RemoveAt](../../mfc/reference/cobarray-class.md#removeat)|Belirli bir dizindeki öğeyi kaldırır.|  
|[CObArray::SetAt](../../mfc/reference/cobarray-class.md#setat)|Belirtilen dizin için değeri ayarlar; dizi büyümesine izin verilmiyor.|  
|[CObArray::SetAtGrow](../../mfc/reference/cobarray-class.md#setatgrow)|Belirtilen dizin için değeri ayarlar; dizi gerekirse büyür.|  
|[CObArray::SetSize](../../mfc/reference/cobarray-class.md#setsize)|Bu dizinin içinde yer alması için öğe sayısını ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::operator]](../../mfc/reference/cobarray-class.md#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CByteArray` Serileştirme ve alt öğeleri dökme desteklemek için ımplement_serıal makrosu içerir. Bayt dizisine bir arşiv, aşırı yüklenmiş ekleme ile depolanıyorsa ( **<<**) işleci veya `Serialize` üye işlevi, her öğe olan, sırayla, serileştirilmiş.  
  
> [!NOTE]
>  Bir dizi kullanmadan önce kullanmayı `SetSize` boyutuna kurmak ve kendisi için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, diziniz için öğeleri ekleme, oluyor, sık sık yeniden ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçası.  
  
 Hata ayıklama çıkışı dizi içindeki tek tek öğelerinden varsa, derinliğini ayarlamalısınız `CDumpContext` 1 veya daha büyük bir nesneye.  
  
 Kullanma hakkında daha fazla bilgi için `CByteArray`, makaleye göz atın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CByteArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CObArray Sınıfı](../../mfc/reference/cobarray-class.md)
