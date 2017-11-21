---
title: "CMapStringToString sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapStringToString
- AFXCOLL/CMapStringToString
- AFXCOLL/CMapStringToString::CPair
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
- AFXCOLL/CMapStringToString::PGetFirstAssoc
- AFXCOLL/CMapStringToString::PGetNextAssoc
- AFXCOLL/CMapStringToString::PLookup
- AFXCOLL/CMapStringToOb::RemoveAll
- AFXCOLL/CMapStringToOb::RemoveKey
- AFXCOLL/CMapStringToOb::SetAt
dev_langs: C++
helpviewer_keywords:
- CMapStringToString [MFC], CPair
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
- CMapStringToString [MFC], PGetFirstAssoc
- CMapStringToString [MFC], PGetNextAssoc
- CMapStringToString [MFC], PLookup
- CMapStringToOb [MFC], RemoveAll
- CMapStringToOb [MFC], RemoveKey
- CMapStringToOb [MFC], SetAt
ms.assetid: b45794c2-fe6b-4edb-a8ca-faa03b57b4a8
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ea16f46628cd12e0aa4e70f777cede46fd63e703
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmapstringtostring-class"></a>CMapStringToString sınıfı
Haritaları destekleyen `CString` tarafından Anahtarlanan nesneleri `CString` nesneleri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMapStringToString : public CObject  
```  
  
## <a name="members"></a>Üyeler  
 Üye işlevlerini `CMapStringToString` sınıfının üye fonksiyonları benzer [CMapStringToOb](../../mfc/reference/cmapstringtoob-class.md). Bu benzerlik nedeniyle kullandığınız `CMapStringToOb` başvuru belgelerini üye fonksiyonu özellikleri için. Gördüğünüz yerde bir `CObject` işaretçi bir dönüş değeri veya "çıktı" parametresi, işlev gibi alternatif bir işaretçi `char`. Gördüğünüz yerde bir `CObject` işaretçi "Giriş" işlevi parametre olarak değiştirmek için bir işaretçi `char`.  
  
 `BOOL CMapStringToOb::Lookup(const char*<key>, CObject*&<rValue>) const;`  
  
 Örneğin, çevrilir  
  
 `BOOL CMapStringToString::Lookup(LPCTSTR<key>, CString&<rValue>) const;`  
  
### <a name="public-structures"></a>Genel yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMapStringToString::CPair](#cpair)|Bir anahtar değeri ve ilişkili dize nesnenin değerini içeren bir iç içe geçmiş yapısı.|  
  
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
|[CMapStringToString::PGetFirstAssoc](#pgetfirstassoc)|Bir işaretçi ilk alır `CString` eşlemesindeki.|  
|[CMapStringToString::PGetNextAssoc](#pgetnextassoc)|Bir işaretçi sonraki alır `CString` yineleme için.|  
|[CMapStringToString::PLookup](#plookup)|Bir işaretçi döndüren bir `CString` değeri belirtilen değerle eşleşir.|  
|[CMapStringToOb::RemoveAll](../../mfc/reference/cmapstringtoob-class.md#removeall)|Bu eşlemesinden tüm öğeleri kaldırır.|  
|[CMapStringToOb::RemoveKey](../../mfc/reference/cmapstringtoob-class.md#removekey)|Bir anahtar tarafından belirtilen bir öğeyi kaldırır.|  
|[CMapStringToOb::SetAt](../../mfc/reference/cmapstringtoob-class.md#setat)|Bir öğenin eşlemeye ekler; eşleşen bir anahtarı bulunursa, var olan öğenin yerini alır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMapStringToOb::operator]](../../mfc/reference/cmapstringtoob-class.md#operator_at)|Bir öğenin eşlemeye ekler — işleci değiştirme `SetAt`.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CMapStringToString`bir araya getirir `IMPLEMENT_SERIAL` makrosu seri hale getirme ve alt öğeleri dökme desteklemek için. Bir arşiv, aşırı yüklenmiş ekleme ile ya da bir harita depolanıyorsa her öğenin sırayla sıralandığı (  **<<** ) işleci veya ile `Serialize` üye işlevi.  
  
 Tek bir dökümü gerekiyorsa `CString` -  `CString` öğeleri ayarlamalısınız döküm içerik derinliği 1 veya daha büyük.  
  
 Zaman bir `CMapStringToString` Nesne silindiğinden veya ne zaman öğeleri kaldırılır, `CString` nesneleri uygun şekilde kaldırılır.  
  
 Daha fazla bilgi için `CMapStringToString`, makaleye bakın [koleksiyonları](../../mfc/collections.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToString`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
##  <a name="cpair"></a>CMapStringToString::CPair  
 Bir anahtar değeri ve ilişkili dize nesnenin değerini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bir sınıf içinde iç içe geçmiş yapısıdır [CMapStringToString](../../mfc/reference/cmapstringtostring-class.md).  
  
 Yapısı iki alandan oluşur:  
  
- **anahtar** anahtar türü gerçek değeri.  
  
- **değer** ilişkili nesnenin değeri.  
  
 Dönüş değerleri depolamak için kullanılan [CMapStringToString::PLookup](#plookup), [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc), ve [CMapStringToString::PGetNextAssoc](#pgetnextassoc).  
  
### <a name="example"></a>Örnek  
  Örneğin bir kullanım örnek için bkz [CMapStringToString::PLookup](#plookup).  
  
##  <a name="pgetfirstassoc"></a>CMapStringToString::PGetFirstAssoc  
 İlk Giriş eşleme nesnesinin döndürür.  
  
```  
const CPair* PGetFirstAssoc() const;

CPair* PGetFirstAssoc();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Harita ilk giriş için bir işaretçi; bkz: [CMapStringToString::CPair](#cpair). Harita boş değer ise, `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi ilk öğe harita nesnesinde döndürmek için bu işlevini çağırın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#73](../../mfc/codesnippet/cpp/cmapstringtostring-class_1.cpp)]  
  
##  <a name="pgetnextassoc"></a>CMapStringToString::PGetNextAssoc  
 Gösterdiği map öğesi alır `pAssocRec`.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssoc) const;  
  
CPair *PGetNextAssoc(const CPair* pAssoc);
```  
  
### <a name="parameters"></a>Parametreler  
 *pAssoc*  
 Önceki tarafından döndürülen bir eşleme girişi işaret [PGetNextAssoc](#pgetnextassoc) veya [PGetFirstAssoc](#pgetfirstassoc) çağırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Harita sonraki girişi için bir işaretçi; bkz: [CMapStringToString::CPair](#cpair). Öğe harita son değer ise, **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Haritanın tüm öğeler yinelemek için bu yöntemi çağırın. İlk öğe çağrısıyla almak `PGetFirstAssoc` ve ardından eşleme için sonraki çağrılarla yinelemek `PGetNextAssoc`.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CMapStringToString::PGetFirstAssoc](#pgetfirstassoc).  
  
##  <a name="plookup"></a>CMapStringToString::PLookup  
 Verilen bir anahtar ile eşlenen değer arar.  
  
```  
const CPair* PLookup(LPCTSTR key) const;

CPair* PLookup(LPCTSTR key);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranacak öğe için anahtar için bir işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen anahtar için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Verilen anahtar tam olarak eşleşen bir anahtara bir harita öğesi için aramak için bu yöntemi çağırın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#74](../../mfc/codesnippet/cpp/cmapstringtostring-class_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek Topla](../../visual-cpp-samples.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)



