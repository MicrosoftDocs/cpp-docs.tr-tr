---
title: "CMapWordToPtr sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapWordToPtr
- AFXCOLL/CMapWordToPtr
- AFXCOLL/CMapStringToOb::CMapStringToOb
- AFXCOLL/CMapStringToOb::GetCount
- AFXCOLL/CMapStringToOb::GetHashTableSize
- AFXCOLL/CMapStringToOb::GetNextAssoc
- AFXCOLL/CMapStringToOb::GetSize
- AFXCOLL/CMapStringToOb::GetStartPosition
- AFXCOLL/CMapStringToOb::HashKey
- AFXCOLL/CMapStringToOb::InitHashTable
- AFXCOLL/CMapStringToOb::IsEmpty
- AFXCOLL/CMapStringToOb::Lookup
- AFXCOLL/CMapStringToOb::LookupKey
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CMapStringToOb [MFC], CMapStringToOb
- CMapStringToOb [MFC], GetCount
- CMapStringToOb [MFC], GetHashTableSize
- CMapStringToOb [MFC], GetNextAssoc
- CMapStringToOb [MFC], GetSize
- CMapStringToOb [MFC], GetStartPosition
- CMapStringToOb [MFC], HashKey
- CMapStringToOb [MFC], InitHashTable
- CMapStringToOb [MFC], IsEmpty
- CMapStringToOb [MFC], Lookup
- CMapStringToOb [MFC], LookupKey
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: b204d87f-6427-43e1-93e3-a4b1bb41099f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 73d900a941b6612cdb1774302a2897d44d17c3ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmapwordtoptr-class"></a>CMapWordToPtr sınıfı
16 bit sözcükleri anahtarlı void işaretçileri haritaları destekler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMapWordToPtr : public CObject  
```  
  
## <a name="members"></a>Üyeler  
 Üye işlevlerini `CMapWordToPtr` sınıfının üye fonksiyonları benzer [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Bu benzerlik nedeniyle kullandığınız `CMapStringToOb` başvuru belgelerini üye fonksiyonu özellikleri için. Gördüğünüz yerde bir `CObject` işaretçisi bir işlev parametresi veya dönüş değeri olarak değiştirmek için bir işaretçi `void`. Gördüğünüz yerde bir `CString` veya **const** işaretçi `char` işlev parametresi veya dönüş değeri olarak yerine **WORD**.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 Örneğin, çevrilir  
  
 `BOOL CMapWordToPtr::Lookup( WORD <key>, void*& <rValue> ) const;`  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md#cmapstringtoob)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](../../mfc/reference/cmapstringtoob-class.md#getcount)|Bu haritada öğe sayısını döndürür.|  
|[CMapStringToOb::GetHashTableSize](../../mfc/reference/cmapstringtoob-class.md#gethashtablesize)|Karma tablodaki öğeler geçerli sayısını belirler.|  
|[CMapStringToOb::GetNextAssoc](../../mfc/reference/cmapstringtoob-class.md#getnextassoc)|Yineleme için sonraki öğeyi alır.|  
|[CMapStringToOb::GetSize](../../mfc/reference/cmapstringtoob-class.md#getsize)|Bu haritada öğe sayısını döndürür.|  
|[CMapStringToOb::GetStartPosition](../../mfc/reference/cmapstringtoob-class.md#getstartposition)|İlk öğe konumunu döndürür.|  
|[CMapStringToOb::HashKey](../../mfc/reference/cmapstringtoob-class.md#hashkey)|Belirtilen anahtar karma değerini hesaplar.|  
|[CMapStringToOb::InitHashTable](../../mfc/reference/cmapstringtoob-class.md#inithashtable)|Karma tablo başlatır.|  
|[CMapStringToOb::IsEmpty](../../mfc/reference/cmapstringtoob-class.md#isempty)|Testleri boş eşleme koşul (öğe yok).|  
|[CMapStringToOb::Lookup](../../mfc/reference/cmapstringtoob-class.md#lookup)|Void işaretçi anahtarına göre void işaretçi arar. İşaretçi değeri değil, işaret varlık anahtar karşılaştırma için kullanılır.|  
|[CMapStringToOb::LookupKey](../../mfc/reference/cmapstringtoob-class.md#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtar için bir başvuru döndürür.|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Bu eşlemesinden tüm öğeleri kaldırır.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Bir anahtar tarafından belirtilen bir öğeyi kaldırır.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Bir öğenin eşlemeye ekler; eşleşen bir anahtarı bulunursa, var olan öğenin yerini alır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMapStringToOb::operator]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Bir öğenin eşlemeye ekler — işleci değiştirme `SetAt`.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMapWordToPtr`bir araya getirir `IMPLEMENT_DYNAMIC` çalışma zamanı tür erişimi ve için dökme desteklemek için makrosu bir `CDumpContext` nesnesi. Tek tek harita öğelerinin bir döküm gerekiyorsa, 1 veya daha büyük döküm bağlam derinliği ayarlamanız gerekir.  
  
 Word işaretçi eşlemeleri getirilemez.  
  
 Zaman bir `CMapWordToPtr` Nesne silindiğinden veya sözcükler ve işaretçileri öğeleri kaldırıldığında kaldırılır. İşaretçiler tarafından başvurulan varlıklar kaldırılmaz.  
  
 Daha fazla bilgi için `CMapWordToPtr`, makaleye bakın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapWordToPtr`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



