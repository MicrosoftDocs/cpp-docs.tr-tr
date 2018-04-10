---
title: CMap sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CMap
- AFXTEMPL/CMap
- AFXTEMPL/CMap::CPair
- AFXTEMPL/CMap::CMap
- AFXTEMPL/CMap::GetCount
- AFXTEMPL/CMap::GetHashTableSize
- AFXTEMPL/CMap::GetNextAssoc
- AFXTEMPL/CMap::GetSize
- AFXTEMPL/CMap::GetStartPosition
- AFXTEMPL/CMap::InitHashTable
- AFXTEMPL/CMap::IsEmpty
- AFXTEMPL/CMap::Lookup
- AFXTEMPL/CMap::PGetFirstAssoc
- AFXTEMPL/CMap::PGetNextAssoc
- AFXTEMPL/CMap::PLookup
- AFXTEMPL/CMap::RemoveAll
- AFXTEMPL/CMap::RemoveKey
- AFXTEMPL/CMap::SetAt
dev_langs:
- C++
helpviewer_keywords:
- CMap [MFC], CPair
- CMap [MFC], CMap
- CMap [MFC], GetCount
- CMap [MFC], GetHashTableSize
- CMap [MFC], GetNextAssoc
- CMap [MFC], GetSize
- CMap [MFC], GetStartPosition
- CMap [MFC], InitHashTable
- CMap [MFC], IsEmpty
- CMap [MFC], Lookup
- CMap [MFC], PGetFirstAssoc
- CMap [MFC], PGetNextAssoc
- CMap [MFC], PLookup
- CMap [MFC], RemoveAll
- CMap [MFC], RemoveKey
- CMap [MFC], SetAt
ms.assetid: 640a45ab-0993-4def-97ec-42cc78eb10b9
caps.latest.revision: 24
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd7c1b23e3c586bf89a86e17d85ee5b5050fbf37
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmap-class"></a>CMap sınıfı
Benzersiz anahtar değerlerine eşlemeleri sözlüğü collection sınıfı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class KEY, class ARG_KEY, class VALUE, class ARG_VALUE>class CMap : public CObject  
```  
  
#### <a name="parameters"></a>Parametreler  
 `KEY`  
 Eşleme için anahtar olarak kullanılan nesne sınıfı.  
  
 `ARG` *_* `KEY`  
 Veri türü için kullanılan `KEY` bağımsız değişkenleri; genellikle başvuru `KEY`.  
  
 `VALUE`  
 Eşlemesinde depolanan nesne sınıfı.  
  
 `ARG` *_* `VALUE`  
 Veri türü için kullanılan `VALUE` bağımsız değişkenleri; genellikle başvuru `VALUE`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-structures"></a>Genel yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMap::CPair](#cpair)|Bir anahtar değeri ve ilişkili nesnenin değerini içeren bir iç içe geçmiş yapısı.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMap::CMap](#cmap)|Anahtarlarını değerine eşleyen bir koleksiyon oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMap::GetCount](#getcount)|Bu haritada öğe sayısını döndürür.|  
|[CMap::GetHashTableSize](#gethashtablesize)|Karma tablosunda öğe sayısını döndürür.|  
|[CMap::GetNextAssoc](#getnextassoc)|Yineleme için sonraki öğeyi alır.|  
|[CMap::GetSize](#getsize)|Bu haritada öğe sayısını döndürür.|  
|[CMap::GetStartPosition](#getstartposition)|İlk öğe konumunu döndürür.|  
|[CMap::InitHashTable](#inithashtable)|Karma tablo başlatır ve boyutunu belirtir.|  
|[CMap::IsEmpty](#isempty)|Testleri boş eşleme koşul (öğe yok).|  
|[CMap::Lookup](#lookup)|Verilen bir anahtar ile eşlenen değer arar.|  
|[CMap::PGetFirstAssoc](#pgetfirstassoc)|Bir işaretçi ilk öğeye döndürür.|  
|[CMap::PGetNextAssoc](#pgetnextassoc)|Bir işaretçi yineleme için sonraki öğeye alır.|  
|[CMap::PLookup](#plookup)|Bir işaretçi değeri belirtilen değerle eşleşen bir anahtara döndürür.|  
|[CMap::RemoveAll](#removeall)|Bu eşlemesinden tüm öğeleri kaldırır.|  
|[CMap::RemoveKey](#removekey)|Bir anahtar tarafından belirtilen bir öğeyi kaldırır.|  
|[CMap::SetAt](#setat)|Bir öğenin eşlemeye ekler; eşleşen bir anahtarı bulunursa, var olan öğenin yerini alır.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMap::operator]](#operator_at)|Bir öğenin eşlemeye ekler — işleci değiştirme `SetAt`.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir anahtar-değer çifti (öğesi) eşlemeye ekledikten sonra verimli bir şekilde almak veya erişmek için anahtar kullanılarak çifti silin. Haritanın tüm öğeler üzerinde yineleyebilirsiniz.  
  
 Türünde bir değişken **konumu** alternatif erişim girişleri için kullanılır. Kullanabileceğiniz bir **konumu** "bir giriş anımsaması" ve eşlemesi üzerinden yineleme. Bu yineleme anahtar değere göre sıralı olduğunu düşünebilirsiniz; değil. Alınan öğeler belirsiz dizisidir.  
  
 Genel yardımcı işlevleri sınıfı çağrısı belirli üye işlevleri için çoğu kullanımlarını özelleştirilmelidir `CMap` sınıfı. Bkz: [koleksiyon sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) makroları ve genel öğeleri bölümünde `MFC Reference`.  
  
 `CMap`geçersiz kılmaları [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize) seri hale getirme ve alt öğeleri dökme desteklemek için. Bir harita bir arşiv kullanarak depolanıyorsa `Serialize`, her map öğesi sırayla serileştirilir. Varsayılan uygulaması `SerializeElements` yardımcı işlevini Bitsel yazma yapar. İşaretçi koleksiyonu öğelerinin seri hale getirme hakkında bilgi türetildiği için `CObject` veya diğer kullanıcı tanımlı türler bkz [nasıl yapılır: tür kullanımı uyumlu koleksiyon yapma](../../mfc/how-to-make-a-type-safe-collection.md).  
  
 Ayrı ayrı öğeler (anahtarlar ve değerler) eşlemesindeki bir tanılama dökümü gerekiyorsa, 1 veya daha büyük döküm bağlam derinliği ayarlamanız gerekir.  
  
 Zaman bir `CMap` Nesne silindiğinden veya öğeleri kaldırıldığında, anahtarları ve değerleri kaldırılır.  
  
 Eşleme sınıf türetme listesi türetme benzer. Makalesine bakın [koleksiyonları](../../mfc/collections.md) özel amaçlı listesi sınıfının türetme bir çizimi için.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CMap`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxtempl.h  
  
##  <a name="cmap"></a>CMap::CMap  
 Boş bir harita oluşturur.  
  
```  
CMap(INT_PTR nBlockSize = 10);
```  
  
### <a name="parameters"></a>Parametreler  
 `nBlockSize`  
 Harita genişletmek için bellek ayırma ayrıntı düzeyi belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Harita büyüdükçe, bellek, biriminde ayrılır `nBlockSize` girişleri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#56](../../mfc/codesnippet/cpp/cmap-class_1.cpp)]  
  
##  <a name="cpair"></a>CMap::CPair  
 Bir anahtar değeri ve ilişkili nesnenin değerini içerir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu bir sınıf içinde iç içe geçmiş yapısıdır [CMap](../../mfc/reference/cmap-class.md).  
  
 Yapısı iki alandan oluşur:  
  
- **anahtar** anahtar türü gerçek değeri.  
  
- **değer** ilişkili nesnenin değeri.  
  
 Dönüş değerleri depolamak için kullanılan [CMap::PLookup](#plookup), [CMap::PGetFirstAssoc](#pgetfirstassoc), ve [CMap::PGetNextAssoc](#pgetnextassoc).  
  
### <a name="example"></a>Örnek  
 Örneğin bir kullanım örnek için bkz [CMap::PLookup](#plookup).  
  
##  <a name="getcount"></a>CMap::GetCount  
 Haritadaki öğe sayısını alır.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğe sayısı.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMap::Lookup](#lookup).  
  
##  <a name="gethashtablesize"></a>CMap::GetHashTableSize  
 Harita karma tablodaki öğeler sayısını belirler.  
  
```  
UINT GetHashTableSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karma tablosundaki öğelerin sayısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#57](../../mfc/codesnippet/cpp/cmap-class_2.cpp)]  
  
##  <a name="getnextassoc"></a>CMap::GetNextAssoc  
 Harita öğesi alır `rNextPosition`, ardından güncelleştirmeleri `rNextPosition` harita sonraki öğe başvurmak için.  
  
```  
void GetNextAssoc(
    POSITION& rNextPosition,
    KEY& rKey,
    VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `rNextPosition`  
 Bir başvuru belirtir bir **konumu** önceki tarafından döndürülen değer `GetNextAssoc` veya `GetStartPosition` çağırın.  
  
 *KEY*  
 Haritanın anahtarın türünü belirten bir şablon parametre.  
  
 `rKey`  
 Alınan öğenin döndürülen anahtarı belirtir.  
  
 *DEĞER*  
 Haritanın değerin türünü belirten bir şablon parametre.  
  
 `rValue`  
 Alınan öğenin döndürülen değerini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev eşlemesi tüm öğeler üzerinden yineleme için kullanışlıdır. Konum sırası mutlaka anahtar değeri dizisi ile aynı olduğunu unutmayın.  
  
 Alınan öğe Haritası son sonra yeni değeri ise `rNextPosition` ayarlanır **NULL**.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMap::SetAt](#setat).  
  
##  <a name="getsize"></a>CMap::GetSize  
 Harita öğe sayısını döndürür.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Harita öğelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Harita öğelerin sayısını almak için bu yöntemi çağırın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="getstartposition"></a>CMap::GetStartPosition  
 Harita yineleme döndürerek başlatır bir **konumu** için geçirilen değer bir `GetNextAssoc` çağırın.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 A **konumu** ; harita yineleme için bir başlangıç konumunu belirten değer veya **NULL** harita boşsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Yineleme sırası tahmin edilebilir değil; Bu nedenle, "ilk öğenin" eşlemesindeki özel bir önemi yoktur.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMap::SetAt](#setat).  
  
##  <a name="inithashtable"></a>CMap::InitHashTable  
 Karma tablo başlatır.  
  
```  
void InitHashTable(UINT hashSize, BOOL  bAllocNow = TRUE);  
```  
  
### <a name="parameters"></a>Parametreler  
 `hashSize`  
 Karma tablosunda giriş sayısı.  
  
 `bAllocNow`  
 Varsa **doğru**, karma tablosu başlatma; bağlı ayırır tablo gerektiğinde aksi ayrılır.  
  
### <a name="remarks"></a>Açıklamalar  
 En iyi performans için karma tablo boyutu asal sayı olmalıdır. Çakışmaları en aza indirmek için boyutu yaklaşık yüzde 20'den büyük beklenen veri kümesi daha büyük olmalıdır.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMap::Lookup](#lookup).  
  
##  <a name="isempty"></a>CMap::IsEmpty  
 Harita boş olup olmadığını belirler.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu haritada öğe içeriyorsa, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMap::RemoveAll](#removeall).  
  
##  <a name="lookup"></a>CMap::Lookup  
 Verilen bir anahtar ile eşlenen değer arar.  
  
```  
BOOL Lookup(ARG_KEY key, VALUE& rValue) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `ARG_KEY`  
 Şablon parametresi türünü belirleyen `key` değeri.  
  
 `key`  
 Bakılacak öğesi tanımlayan anahtarını belirtir.  
  
 *DEĞER*  
 Bakılacak değerin türünü belirtir.  
  
 `rValue`  
 Aranan yukarı değerini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Öğesi bulunmazsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `Lookup`map öğesi verilen anahtar ile tam olarak bir anahtarla hızla bulmak için bir karma algoritması kullanır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#58](../../mfc/codesnippet/cpp/cmap-class_3.cpp)]  
  
##  <a name="operator_at"></a>CMap::operator]  
 Uygun bir alternatif için `SetAt` üye işlevi.  
  
```  
VALUE& operator[](arg_key key);
```  
  
### <a name="parameters"></a>Parametreler  
 *DEĞER*  
 Harita değerin türünü belirten bir şablon parametre.  
  
 `ARG_KEY`  
 Anahtar değeri türünü belirten bir şablon parametre.  
  
 `key`  
 Haritadaki değerini almak için kullanılan anahtar.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu nedenle yalnızca (bir l-değeri) atama ifadesinin sol tarafta kullanılabilir. Belirtilen anahtarı içeren herhangi bir harita öğe varsa, yeni bir öğe oluşturulur.  
  
 Yoktur yok "sağ tarafında" (r) bu işleci için eşdeğer bir anahtar eşlemesinde bulunamayabilir olasılığı olduğundan. Kullanım `Lookup` öğesi alma için üye işlevi.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMap::Lookup](#lookup).  
  
##  <a name="pgetfirstassoc"></a>CMap::PGetFirstAssoc  
 İlk Giriş eşleme nesnesinin döndürür.  
  
```  
const CPair* PGetFirstAssoc() const; 
CPair* PGetFirstAssoc();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Harita ilk giriş için bir işaretçi; bkz: [CMap::CPair](#cpair). Harita hiçbir giriş içeriyorsa, değerdir **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir işaretçi ilk öğe harita nesnesinde döndürmek için bu işlevini çağırın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#59](../../mfc/codesnippet/cpp/cmap-class_4.cpp)]  
  
##  <a name="pgetnextassoc"></a>CMap::PGetNextAssoc  
 Gösterdiği map öğesi alır `pAssocRec`.  
  
```  
const CPair *PGetNextAssoc(const CPair* pAssocRet) const;  
  
CPair *PGetNextAssoc(const CPair* pAssocRet);
```  
  
### <a name="parameters"></a>Parametreler  
 *pAssocRet*  
 Önceki tarafından döndürülen bir eşleme girişi işaret [PGetNextAssoc](#pgetnextassoc) veya [CMap::PGetFirstAssoc](#pgetfirstassoc) çağırın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Harita sonraki girişi için bir işaretçi; bkz: [CMap::CPair](#cpair). Öğe harita son değer ise, **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Haritanın tüm öğeler yinelemek için bu yöntemi çağırın. İlk öğe çağrısıyla almak `PGetFirstAssoc` ve ardından eşleme için sonraki çağrılarla yinelemek `PGetNextAssoc`.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMap::PGetFirstAssoc](#pgetfirstassoc).  
  
##  <a name="plookup"></a>CMap::PLookup  
 Verilen bir anahtar ile eşlenen değeri bulur.  
  
```  
const CPair* PLookup(ARG_KEY key) const;
CPair* PLookup(ARG_KEY key);  
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranacak öğe anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir anahtar yapısına yönelik işaretçinin; bkz: [CMap::CPair](#cpair). Eşleşme bulunamazsa, `CMap::PLookup` döndürür `NULL`.  
  
### <a name="remarks"></a>Açıklamalar  
 Verilen anahtar tam olarak eşleşen bir anahtara bir harita öğesi için aramak için bu yöntemi çağırın.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#60](../../mfc/codesnippet/cpp/cmap-class_5.cpp)]  
  
##  <a name="removeall"></a>CMap::RemoveAll  
 Genel yardımcı işlevini çağırarak tüm değerleri bu eşlemesinden kaldırır **DestructElements**.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Harita zaten boşsa, işlev düzgün çalışır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#61](../../mfc/codesnippet/cpp/cmap-class_6.cpp)]  
  
##  <a name="removekey"></a>CMap::RemoveKey  
 Sağlanan anahtarına karşılık gelen eşleme girişi arar; Ardından, anahtar bulunursa, giriş kaldırır.  
  
```  
BOOL RemoveKey(ARG_KEY key);
```  
  
### <a name="parameters"></a>Parametreler  
 `ARG_KEY`  
 Anahtar türü belirten bir şablon parametre.  
  
 `key`  
 Kaldırılacak öğenin anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Giriş bulundu ve başarıyla kaldırıldı, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 **DestructElements** yardımcı işlevi, giriş kaldırmak için kullanılır.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CMap::SetAt](#setat).  
  
##  <a name="setat"></a>CMap::SetAt  
 Birincil bir eşleminde bir öğe eklemek anlamına gelir.  
  
```  
void SetAt(ARG_KEY key, ARG_VALUE newValue);
```  
  
### <a name="parameters"></a>Parametreler  
 `ARG_KEY`  
 Şablon parametresi türünü belirleyen `key` parametresi.  
  
 `key`  
 Yeni öğe anahtarı belirtir.  
  
 `ARG_VALUE`  
 Şablon parametresi türünü belirleyen `newValue` parametresi.  
  
 `newValue`  
 Yeni öğe değerini belirtir.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk olarak, anahtar aranır. Anahtar bulunursa, karşılık gelen değeri değiştikten sonra; Aksi takdirde, yeni bir anahtar-değer çifti oluşturulur.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#62](../../mfc/codesnippet/cpp/cmap-class_7.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek Topla](../../visual-cpp-samples.md)   
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)  
