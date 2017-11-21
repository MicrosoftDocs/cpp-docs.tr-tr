---
title: "CMapStringToOb sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMapStringToOb
- AFXCOLL/CMapStringToOb
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
dev_langs: C++
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
ms.assetid: 09653980-b885-4f3a-8594-0aeb7f94c601
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7e5ffa1822a983e3792e1484b612ee11288dd547
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cmapstringtoob-class"></a>CMapStringToOb sınıfı
Benzersiz eşleyen bir sözlük koleksiyon sınıfı `CString` nesneleri `CObject` işaretçileri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMapStringToOb : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMapStringToOb::CMapStringToOb](#cmapstringtoob)|Oluşturucu.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMapStringToOb::GetCount](#getcount)|Bu haritada öğe sayısını döndürür.|  
|[CMapStringToOb::GetHashTableSize](#gethashtablesize)|Karma tablodaki öğeler geçerli sayısını belirler.|  
|[CMapStringToOb::GetNextAssoc](#getnextassoc)|Yineleme için sonraki öğeyi alır.|  
|[CMapStringToOb::GetSize](#getsize)|Bu haritada öğe sayısını döndürür.|  
|[CMapStringToOb::GetStartPosition](#getstartposition)|İlk öğe konumunu döndürür.|  
|[CMapStringToOb::HashKey](#hashkey)|Belirtilen anahtar karma değerini hesaplar.|  
|[CMapStringToOb::InitHashTable](#inithashtable)|Karma tablo başlatır.|  
|[CMapStringToOb::IsEmpty](#isempty)|Testleri boş eşleme koşul (öğe yok).|  
|[CMapStringToOb::Lookup](#lookup)|Void işaretçi anahtarına göre void işaretçi arar. İşaretçi değeri değil, işaret varlık anahtar karşılaştırma için kullanılır.|  
|[CMapStringToOb::LookupKey](#lookupkey)|Belirtilen anahtar değeriyle ilişkili anahtar için bir başvuru döndürür.|  
|[CMapStringToOb::RemoveAll](#removeall)|Bu eşlemesinden tüm öğeleri kaldırır.|  
|[CMapStringToOb::RemoveKey](#removekey)|Bir anahtar tarafından belirtilen bir öğeyi kaldırır.|  
|[CMapStringToOb::SetAt](#setat)|Bir öğenin eşlemeye ekler; eşleşen bir anahtarı bulunursa, var olan öğenin yerini alır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMapStringToOb::operator]](#operator_at)|Bir öğenin eşlemeye ekler — işleci değiştirme `SetAt`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ekledikten sonra bir `CString` -  `CObject*` çifti (öğesi) eşlemeye verimli bir şekilde alabileceğiniz veya hatalı bir dize kullanarak çifti silin veya `CString` bir anahtar değeri. Haritanın tüm öğeler üzerinde yineleyebilirsiniz.  
  
 Türünde bir değişken **konumu** tüm harita Çeşitlemeler alternatif giriş erişmek için kullanılır. Kullanabileceğiniz bir **konumu** "bir giriş anımsaması" ve eşlemesi üzerinden yineleme. Bu yineleme anahtar değere göre sıralı olduğunu düşünebilirsiniz; değil. Alınan öğeler belirsiz dizisidir.  
  
 `CMapStringToOb`bir araya getirir `IMPLEMENT_SERIAL` makrosu seri hale getirme ve alt öğeleri dökme desteklemek için. Bir arşiv, aşırı yüklenmiş ekleme ile ya da bir harita depolanıyorsa her öğenin sırayla sıralandığı (  **<<** ) işleci veya ile `Serialize` üye işlevi.  
  
 Haritadaki ayrı ayrı öğeler, bir tanı dökümü ihtiyacınız varsa ( `CString` değeri ve `CObject` içeriği), 1 veya daha büyük döküm bağlam derinliği ayarlamanız gerekir.  
  
 Zaman bir `CMapStringToOb` Nesne silindiğinden veya ne zaman öğeleri kaldırılır, `CString` nesneleri ve `CObject` işaretçileri kaldırılır. Tarafından başvurulan nesneler `CObject` işaretçileri yok yok.  
  
 Eşleme sınıf türetme listesi türetme benzer. Makalesine bakın [koleksiyonları](../../mfc/collections.md) özel amaçlı listesi sınıfının türetme bir çizimi için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMapStringToOb`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
##  <a name="cmapstringtoob"></a>CMapStringToOb::CMapStringToOb  
 Boş bir yapıları `CString`- için - `CObject*` eşleme.  
  
```  
CMapStringToOb(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Parametreler  
 `nBlockSize`  
 Harita genişletmek için bellek ayırma ayrıntı düzeyi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Harita büyüdükçe, bellek, biriminde ayrılır `nBlockSize` girişleri.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir **CMapStringToOb:: CMapStringToOb**.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**CMapPtrToPtr (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**CMapPtrToWord (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**CMapStringToPtr (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CMapStringToString (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CMapWordToOb (INT_PTR** `nBlockSize` **= 10);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**MapWordToPtr (INT_PTR** `nBlockSize` **= 10);**|  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#63](../../mfc/codesnippet/cpp/cmapstringtoob-class_1.cpp)]  
  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
##  <a name="getcount"></a>CMapStringToOb::GetCount  
 Haritada kaç öğeleridir belirler.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu haritada öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CMapStringToOb::GetCount`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetCount () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetCount () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetCount () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetCount () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetCount () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetCount () const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#64](../../mfc/codesnippet/cpp/cmapstringtoob-class_2.cpp)]  
  
##  <a name="gethashtablesize"></a>CMapStringToOb::GetHashTableSize  
 Karma tablodaki öğeler geçerli sayısını belirler.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karma tablosunda öğe sayısını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CMapStringToOb::GetHashTableSize`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT GetHashTableSize () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT GetHashTableSize () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT GetHashTableSize () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT GetHashTableSize () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT GetHashTableSize () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT GetHashTableSize () const;**|  
  
##  <a name="getnextassoc"></a>CMapStringToOb::GetNextAssoc  
 Harita öğesi alır *rNextPosition*, ardından güncelleştirmeleri *rNextPosition* harita sonraki öğe başvurmak için.  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,  
    CString& rKey,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *rNextPosition*  
 Bir başvuru belirtir bir **konumu** önceki tarafından döndürülen değer **GetNextAssoc** veya **GetStartPosition** çağırın.  
  
 *rKey*  
 Alınan öğe (dize) döndürülen anahtarı belirtir.  
  
 *rValue*  
 Alınan öğenin döndürülen değeri belirtir (bir **CObject** işaretçisi). Açıklamalar, bu parametre hakkında daha fazla bilgi için bkz.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev eşlemesi tüm öğeler üzerinden yineleme için kullanışlıdır. Konum sırası mutlaka anahtar değeri dizisi ile aynı olduğunu unutmayın.  
  
 Alınan öğe Haritası son sonra yeni değeri ise *rNextPosition* ayarlanır **NULL**.  
  
 İçin *rValue* parametresi, nesne türüne dönüştürmek mutlaka **CObject\*&**, olduğu ne derleyici gerektirir, aşağıdaki örnekte gösterildiği gibi:  
  
 [!code-cpp[NVC_MFCCollections#65](../../mfc/codesnippet/cpp/cmapstringtoob-class_3.cpp)]  
  
 Bu doğru değildir **GetNextAssoc** şablonlar temelinde eşlemeleri.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir **CMapStringToOb::GetNextAssoc**.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, void\* &**  *rKey* **, void\* &**  *rValue* **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, void\* &**  *rKey* **, WORD &** *rValue* **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, CString &** *rKey* **, void\* &**  *rValue* **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, CString &** *rKey* **, CString &** *rValue* **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, WORD &** *rKey* **, CObject\* &**  *rValue* **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void GetNextAssoc (konum &** *rNextPosition* **, WORD &** *rKey* **, void\* &**  *rValue* **) const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#66](../../mfc/codesnippet/cpp/cmapstringtoob-class_4.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `Lisa : a CAge at $4724 11`  
  
 `Marge : a CAge at $47A8 35`  
  
 `Homer : a CAge at $4766 36`  
  
 `Bart : a CAge at $45D4 13`  
  
##  <a name="getsize"></a>CMapStringToOb::GetSize  
 Harita öğe sayısını döndürür.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Harita öğelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Harita öğelerin sayısını almak için bu yöntemi çağırın.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CMapStringToOb::GetSize`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**INT_PTR GetSize () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**INT_PTR GetSize () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**INT_PTR GetSize () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**INT_PTR GetSize () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**INT_PTR GetSize () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**INT_PTR GetSize () const;**|  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#67](../../mfc/codesnippet/cpp/cmapstringtoob-class_5.cpp)]  
  
##  <a name="getstartposition"></a>CMapStringToOb::GetStartPosition  
 Harita yineleme döndürerek başlatır bir **konumu** için geçirilen değer bir `GetNextAssoc` çağırın.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** ; harita yineleme için bir başlangıç konumunu belirten değer veya **NULL** harita boşsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleme sırası tahmin edilebilir değil; Bu nedenle, "ilk öğenin" eşlemesindeki özel bir önemi yoktur.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CMapStringToOb::GetStartPosition`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**Konum GetStartPosition () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**Konum GetStartPosition () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**Konum GetStartPosition () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**Konum GetStartPosition () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**Konum GetStartPosition () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**Konum GetStartPosition () const;**|  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMapStringToOb::GetNextAssoc](#getnextassoc).  
  
##  <a name="hashkey"></a>CMapStringToOb::HashKey  
 Belirtilen anahtar karma değerini hesaplar.  
  
```  
UINT HashKey(LPCTSTR key) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Karma değeri hesaplanacak olan anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtarın karma değeri  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CMapStringToOb::HashKey`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**UINT HashKey (void\***  `key` **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**UINT HashKey (void\***  `key` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**UINT HashKey (LPCTSTR** `key` **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**UINT HashKey (WORD** `key` **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**UINT HashKey (WORD** `key` **) const;**|  
  
##  <a name="inithashtable"></a>CMapStringToOb::InitHashTable  
 Karma tablo başlatır.  
  
```  
void InitHashTable(
    UINT hashSize,  
    BOOL bAllocNow = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `hashSize`  
 Karma tablosunda giriş sayısı.  
  
 `bAllocNow`  
 Varsa **doğru**, karma tablosu başlatma; bağlı ayırır tablo gerektiğinde aksi ayrılır.  
  
### <a name="remarks"></a>Açıklamalar  
 En iyi performans için karma tablo boyutu asal sayı olmalıdır. Çakışmaları en aza indirmek için boyutu yaklaşık yüzde 20'den büyük beklenen veri kümesi daha büyük olmalıdır.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CMapStringToOb::InitHashTable`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void InitHashTable (UINT** `hashSize` **, BOOL** `bAllocNow` **= TRUE);**|  
  
##  <a name="isempty"></a>CMapStringToOb::IsEmpty  
 Harita boş olup olmadığını belirler.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu haritada öğe içeriyorsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [RemoveAll](#removeall).  
  
### <a name="remarks"></a>Açıklamalar  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir **CMapStringToOb:: IsEmpty**.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL IsEmpty () const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL IsEmpty () const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL IsEmpty () const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL IsEmpty () const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL IsEmpty () const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL IsEmpty () const;**|  
  
##  <a name="lookup"></a>CMapStringToOb::Lookup  
 Döndürür bir `CObject` işaretçi temel alarak bir `CString` değeri.  
  
```  
BOOL Lookup(
    LPCTSTR key,  
    CObject*& rValue) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Bakılacak öğesi tanımlayan dize anahtarını belirtir.  
  
 `rValue`  
 Aranan yukarı öğesinden döndürülen değeri belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesi bulunmazsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `Lookup`map öğesi tam olarak eşleşen bir anahtara hızla bulmak için bir karma algoritması kullanır ( `CString` değeri).  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CMapStringToOb::LookUp`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL arama (void\***  `key` **, void\* &**  `rValue` **) const;**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL arama (void\***  `key` **, WORD &** `rValue` **) const;**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL arama (LPCTSTR** `key` **, void\* &**  `rValue` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL arama (LPCTSTR** `key` **, CString &** `rValue` **) const;**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL arama (WORD** `key` **, CObject\* &**  `rValue` **) const;**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL arama (WORD** `key` **, void\* &**  `rValue` **) const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#68](../../mfc/codesnippet/cpp/cmapstringtoob-class_6.cpp)]  
  
##  <a name="lookupkey"></a>CMapStringToOb::LookupKey  
 Belirtilen anahtar değeriyle ilişkili anahtar için bir başvuru döndürür.  
  
```  
BOOL LookupKey(
    LPCTSTR key,  
    LPCTSTR& rKey) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Bakılacak öğesi tanımlayan dize anahtarını belirtir.  
  
 `rKey`  
 İlişkili anahtar referansı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar bulunduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir anahtar için bir başvuru kullanarak ilişkili öğesi eşlemesinden kaldırıldıktan sonra kullandıysanız veya eşleme yok sonra güvenli değildir.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir **CMapStringToOb:: LookupKey**.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL LookupKey (LPCTSTR** `key` **, LPCTSTR &** `rKey` **) const;**|  
  
##  <a name="operator_at"></a>CMapStringToOb::operator]  
 Uygun bir alternatif için `SetAt` üye işlevi.  
  
```  
CObject*& operator[ ](lpctstr key);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi başvuru bir `CObject` nesne; veya **NULL** harita boşsa veya `key` aralık dışında.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu nedenle yalnızca (bir l-değeri) atama ifadesinin sol tarafta kullanılabilir. Belirtilen anahtarı içeren herhangi bir harita öğe varsa, yeni bir öğe oluşturulur.  
  
 Yoktur yok "sağ tarafında" (r) bu işleci için eşdeğer bir anahtar eşlemesinde bulunamayabilir olasılığı olduğundan. Kullanım `Lookup` öğesi alma için üye işlevi.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir **CMapStringToOb::operator []**.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void\*& [] işleci (void\***  `key`  **\);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**WORD & işleci [] (void\***  `key`  **\);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void\*& [] işleci (lpctstr** `key`  **\);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**CString & işleci [] (lpctstr** `key`  **\);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**CObject\*& [] işleci (word** `key`  **\);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void\*& [] işleci (word** `key`  **\);**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#72](../../mfc/codesnippet/cpp/cmapstringtoob-class_7.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `Operator [] example: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $4A02 11`  
  
 `[Bart] = a CAge at $497E 13`  
  
##  <a name="removeall"></a>CMapStringToOb::RemoveAll  
 Bu eşlemesinden tüm öğeleri kaldırır ve bozar `CString` anahtar nesneleri.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CObject` Her anahtar tarafından başvurulan nesneler değil yok. `RemoveAll` İşlevi başvurulan emin değil, bellek sızıntıları neden olabilecek `CObject` nesneler yok.  
  
 Harita zaten boşsa, işlev düzgün çalışır.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CMapStringToOb::RemoveAll`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void RemoveAll ();**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void RemoveAll ();**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void RemoveAll ();**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void RemoveAll ();**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void RemoveAll ();**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void RemoveAll ();**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#69](../../mfc/codesnippet/cpp/cmapstringtoob-class_8.cpp)]  
  
##  <a name="removekey"></a>CMapStringToOb::RemoveKey  
 Sağlanan anahtarına karşılık gelen eşleme girişi arar; Ardından, anahtar bulunursa, giriş kaldırır.  
  
```  
BOOL RemoveKey(LPCTSTR key);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Harita araması için kullanılan dizeyi belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Giriş bulundu ve başarıyla kaldırıldı, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bellek sızıntıları sunabilir `CObject` nesne başka bir yerde silinmez.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CMapStringToOb::RemoveKey`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**BOOL RemoveKey (void\***  `key` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**BOOL RemoveKey (void\***  `key` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**BOOL RemoveKey (LPCTSTR** `key` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**BOOL RemoveKey (WORD** `key` **);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**BOOL RemoveKey (WORD** `key` **);**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#70](../../mfc/codesnippet/cpp/cmapstringtoob-class_9.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `RemoveKey example: A CMapStringToOb with 3 elements`  
  
 `[Marge] = a CAge at $49A0 35`  
  
 `[Homer] = a CAge at $495E 36`  
  
 `[Bart] = a CAge at $4634 13`  
  
##  <a name="setat"></a>CMapStringToOb::SetAt  
 Birincil bir eşleminde bir öğe eklemek anlamına gelir.  
  
```  
void SetAt(
    LPCTSTR key,  
    CObject* newValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Yeni öğe anahtarı dizeyi belirtir.  
  
 `newValue`  
 Belirtir `CObject` yeni öğe değeri işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk olarak, anahtar aranır. Anahtar bulunursa, karşılık gelen değeri değiştikten sonra; Aksi takdirde, yeni bir anahtar-değer öğesi oluşturulur.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CMapStringToOb::SetAt`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CMapPtrToPtr](../../mfc/reference/cmapptrtoptr-class.md)|**void SetAt (void\***  `key` **, void\***  `newValue` **);**|  
|[CMapPtrToWord](../../mfc/reference/cmapptrtoword-class.md)|**void SetAt (void\***  `key` **, WORD** `newValue` **);**|  
|[CMapStringToPtr](../../mfc/reference/cmapstringtoptr-class.md)|**void SetAt (LPCTSTR** `key` **, void\***  `newValue` **);**|  
|[CMapStringToString](../../mfc/reference/cmapstringtostring-class.md)|**void SetAt (LPCTSTR** `key` **, LPCTSTR** `newValue` **);**|  
|[CMapWordToOb](../../mfc/reference/cmapwordtoob-class.md)|**void SetAt (WORD** `key` **, CObject\***  `newValue` **);**|  
|[CMapWordToPtr](../../mfc/reference/cmapwordtoptr-class.md)|**void SetAt (WORD** `key` **, void\***  `newValue` **);**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#71](../../mfc/codesnippet/cpp/cmapstringtoob-class_10.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `before Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $493C 11`  
  
 `[Bart] = a CAge at $4654 13`  
  
 `after Lisa's birthday: A CMapStringToOb with 2 elements`  
  
 `[Lisa] = a CAge at $49C0 12`  
  
 `[Bart] = a CAge at $4654 13`  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CMapPtrToPtr sınıfı](../../mfc/reference/cmapptrtoptr-class.md)   
 [CMapPtrToWord sınıfı](../../mfc/reference/cmapptrtoword-class.md)   
 [CMapStringToPtr sınıfı](../../mfc/reference/cmapstringtoptr-class.md)   
 [CMapStringToString sınıfı](../../mfc/reference/cmapstringtostring-class.md)   
 [CMapWordToOb sınıfı](../../mfc/reference/cmapwordtoob-class.md)   
 [CMapWordToPtr sınıfı](../../mfc/reference/cmapwordtoptr-class.md)
