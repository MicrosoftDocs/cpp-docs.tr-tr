---
title: "CMapWordToOb sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapWordToOb
- AFXCOLL/CMapWordToOb
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
ms.assetid: 9c9bcd76-456f-4cf9-b03c-dd28b49d5e4f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b7166fd1b0ce0f8e9152c617979d0ec80bfb2b57
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmapwordtoob-class"></a>CMapWordToOb sınıfı
Haritaları destekleyen `CObject` 16 bit sözcükleri anahtarlı işaretçileri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMapWordToOb : public CObject  
```  
  
## <a name="members"></a>Üyeler  
 Üye işlevlerini `CMapWordToOb` sınıfının üye fonksiyonları benzer [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Bu benzerlik nedeniyle kullandığınız `CMapStringToOb` başvuru belgelerini üye fonksiyonu özellikleri için. Gördüğünüz yerde bir `CString` veya **const** işaretçi `char` işlev parametresi veya dönüş değeri olarak yerine **WORD**.  
  
 `BOOL CMapStringToOb::Lookup( const char* <key>,`  
  
 `CObject*& <rValue> ) const;`  
  
 Örneğin, çevrilir  
  
 `BOOL CMapWordToOb::Lookup( WORD <key>, CObject*& <rValue> ) const;`  
  
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
 `CMapWordToOb`bir araya getirir `IMPLEMENT_SERIAL` makrosu seri hale getirme ve alt öğeleri dökme desteklemek için. Bir arşiv, aşırı yüklenmiş ekleme ile ya da bir harita depolanıyorsa her öğenin sırayla sıralandığı (  **<<** ) işleci veya ile `Serialize` üye işlevi.  
  
 Tek bir dökümü gerekiyorsa **WORD** -  `CObject` öğeleri ayarlamalısınız döküm içerik derinliği 1 veya daha büyük.  
  
 Zaman bir `CMapWordToOb` Nesne silindiğinden veya ne zaman öğeleri kaldırılır, `CObject` işaretçileri kaldırılır. Tarafından başvurulan nesneler `CObject` işaretçileri yok yok.  
  
 Daha fazla bilgi için `CMapWordToOb`, makaleye bakın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapWordToOb`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)



