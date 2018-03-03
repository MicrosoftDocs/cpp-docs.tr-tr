---
title: "CSimpleMap sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayElementType
- ATLSIMPCOLL/ATL::CSimpleMap::_ArrayKeyType
- ATLSIMPCOLL/ATL::CSimpleMap::CSimpleMap
- ATLSIMPCOLL/ATL::CSimpleMap::Add
- ATLSIMPCOLL/ATL::CSimpleMap::FindKey
- ATLSIMPCOLL/ATL::CSimpleMap::FindVal
- ATLSIMPCOLL/ATL::CSimpleMap::GetKeyAt
- ATLSIMPCOLL/ATL::CSimpleMap::GetSize
- ATLSIMPCOLL/ATL::CSimpleMap::GetValueAt
- ATLSIMPCOLL/ATL::CSimpleMap::Lookup
- ATLSIMPCOLL/ATL::CSimpleMap::Remove
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleMap::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleMap::ReverseLookup
- ATLSIMPCOLL/ATL::CSimpleMap::SetAt
- ATLSIMPCOLL/ATL::CSimpleMap::SetAtIndex
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMap class
ms.assetid: 61b06eb4-ae73-44b0-a305-0afb5a33e8b1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27e4fdad706ab9e586efe72663880646e6f50f11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="csimplemap-class"></a>CSimpleMap sınıfı
Bu sınıf, bir basit eşleştirme dizisi için destek sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class TKey, class TVal, class TEqual = CSimpleMapEqualHelper<TKey, TVal>>  
class CSimpleMap
```  
  
#### <a name="parameters"></a>Parametreler  
 `TKey`  
 Anahtar öğe türü.  
  
 `TVal`  
 Değer öğe türü.  
  
 `TEqual`  
 Eşitlik test türündeki öğeler için tanımlama bir ayırdedici nitelik nesnesi `T`.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleMap::_ArrayElementType](#_arrayelementtype)|TypeDef değer türü.|  
|[CSimpleMap::_ArrayKeyType](#_arraykeytype)|TypeDef anahtar türü.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleMap::CSimpleMap](#csimplemap)|Oluşturucu.|  
|[CSimpleMap:: ~ CSimpleMap](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSimpleMap::Add](#add)|Bir anahtarı ve ilişkili değeri eşleme dizisine ekler.|  
|[CSimpleMap::FindKey](#findkey)|Belirli bir anahtarın bulur.|  
|[CSimpleMap::FindVal](#findval)|Belirli bir değeri bulur.|  
|[CSimpleMap::GetKeyAt](#getkeyat)|Belirtilen anahtarı alır.|  
|[CSimpleMap::GetSize](#getsize)|Girdi sayısı eşleme dizisinde döndürür.|  
|[CSimpleMap::GetValueAt](#getvalueat)|Belirtilen değer alır.|  
|[CSimpleMap::Lookup](#lookup)|Verilen anahtarla ilişkili değeri döndürür.|  
|[CSimpleMap::Remove](#remove)|Bir anahtar ve eşleşen değeri kaldırır.|  
|[CSimpleMap::RemoveAll](#removeall)|Tüm anahtarları ve değerleri kaldırır.|  
|[CSimpleMap::RemoveAt](#removeat)|Bir özel anahtar ve eşleşen değeri kaldırır.|  
|[CSimpleMap::ReverseLookup](#reverselookup)|Verilen değer ile ilişkili anahtar döndürür.|  
|[CSimpleMap::SetAt](#setat)|Verilen anahtarla ilişkili değeri ayarlar.|  
|[CSimpleMap::SetAtIndex](#setatindex)|Özel anahtarı ve değeri ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CSimpleMap`herhangi bir türde basit eşleştirme dizisi için destek sağlar `T`, sırasız bir dizi temel öğeleri ve ilişkili değerleri yönetme.  
  
 Parametre `TEqual` iki öğe türü için bir eşitlik işlevi tanımlayan bir sağlar `T`. Bir sınıf benzer oluşturarak [CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md), belirli bir dizi eşitlik test davranışını değiştirmek mümkündür. Örneğin, bir dizi işaretçileri ile ilgilenirken, onu olarak eşitlik işaretçileri başvuru değerleri bağlı olarak tanımlamak yararlı olabilir. Varsayılan uygulama yararlanan **operator==()**.  
  
 Her ikisi de `CSimpleMap` ve [CSimpleArray](../../atl/reference/csimplearray-class.md) önceki ATL uyumluluğunu serbest bırakır ve daha eksiksiz ve verimli koleksiyon uygulamaları tarafından sağlanan için sağlanan [CAtlArray](../../atl/reference/catlarray-class.md) ve [ CAtlMap](../../atl/reference/catlmap-class.md).  
  
 Diğer eşleme koleksiyonları ATL ve MFC aksine bu sınıf ile basit bir dizi uygulanır ve arama aramaları doğrusal arama gerektirir. `CAtlMap`Dizi öğeleri çok sayıda içerdiğinde kullanılmalıdır.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsimpcoll.h  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#91](../../atl/codesnippet/cpp/csimplemap-class_1.cpp)]  
  
##  <a name="add"></a>CSimpleMap::Add  
 Bir anahtarı ve ilişkili değeri eşleme dizisine ekler.  
  
```
BOOL Add(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Anahtar.  
  
 *VAL*  
 İlişkili değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar ve değer Aksi halde başarıyla eklendi, FALSE ise TRUE döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Her anahtar ve değer çifti eşleme dizi belleği serbest ve bırakılan için her biri için her zaman bitişik veriler sağlamak için neden eklendi. Diğer bir deyişle, ikinci anahtar öğe her zaman doğrudan bellek ilk anahtar öğe vb. izler.  
  
##  <a name="_arrayelementtype"></a>CSimpleMap::_ArrayElementType  
 Typedef anahtar türü.  
  
```
typedef TVal _ArrayElementType;
```  
  
##  <a name="_arraykeytype"></a>CSimpleMap::_ArrayKeyType  
 Typedef değer türü.  
  
```
typedef TKey _ArrayKeyType;
```  
  
##  <a name="csimplemap"></a>CSimpleMap::CSimpleMap  
 Oluşturucu.  
  
```
CSimpleMap();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Veri üyeleri başlatır.  
  
##  <a name="dtor"></a>CSimpleMap:: ~ CSimpleMap  
 Yok Edicisi.  
  
```
~CSimpleMap();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="findkey"></a>CSimpleMap::FindKey  
 Belirli bir anahtarın bulur.  
  
```
int FindKey(const TKey& key) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Aranacak anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar IF dizini bulunamadı, döndürür, aksi takdirde -1 döndürür.  
  
##  <a name="findval"></a>CSimpleMap::FindVal  
 Belirli bir değeri bulur.  
  
```
int FindVal(const TVal& val) const;
```  
  
### <a name="parameters"></a>Parametreler  
 *VAL*  
 Aranacak değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bulunursa, değer dizin yoksa -1 döndürür.  
  
##  <a name="getkeyat"></a>CSimpleMap::GetKeyAt  
 Belirtilen dizindeki anahtarı alır.  
  
```
TKey& GetKeyAt(int nIndex) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Döndürülecek anahtar dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından başvurulan anahtarını döner `nIndex`.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçirilen dizin `nIndex` dönüş değeri anlamlı olacak şekilde geçerli olmalıdır.  
  
##  <a name="getsize"></a>CSimpleMap::GetSize  
 Girdi sayısı eşleme dizisinde döndürür.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 (Bir anahtarı ve değeri olan bir giriş) girdi sayısı eşleme dizisinde döndürür.  
  
##  <a name="getvalueat"></a>CSimpleMap::GetValueAt  
 Belirli dizindeki değeri alır.  
  
```
TVal& GetValueAt(int nIndex) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Döndürülecek değeri dizini.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tarafından başvurulan değer verir `nIndex`.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçirilen dizin `nIndex` dönüş değeri anlamlı olacak şekilde geçerli olmalıdır.  
  
##  <a name="lookup"></a>CSimpleMap::Lookup  
 Verilen anahtarla ilişkili değeri döndürür.  
  
```
TVal Lookup(const TKey& key) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlişkilendirilen değeri döndürür. Eşleşen anahtarı bulunan, NULL döndürülür.  
  
##  <a name="remove"></a>CSimpleMap::Remove  
 Bir anahtar ve eşleşen değeri kaldırır.  
  
```
BOOL Remove(const TKey& key);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Anahtar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar ve eşleşen değeri, aksi halde başarıyla kaldırıldı, FALSE ise TRUE döndürür.  
  
##  <a name="removeall"></a>CSimpleMap::RemoveAll  
 Tüm anahtarları ve değerleri kaldırır.  
  
```
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm anahtarları ve değerleri eşleme dizi nesnesinden kaldırır.  
  
##  <a name="removeat"></a>CSimpleMap::RemoveAt  
 Bir anahtarı ve ilişkili değeri belirtilen dizinde kaldırır.  
  
```
BOOL RemoveAt(int nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Dizin anahtarı ve kaldırmak için ilişkili değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dizin geçersiz bir dizin ise TRUE başarı, FALSE değerini döndürür.  
  
##  <a name="reverselookup"></a>CSimpleMap::ReverseLookup  
 Verilen değer ile ilişkili anahtar döndürür.  
  
```
TKey ReverseLookup(const TVal& val) const;
```  
  
### <a name="parameters"></a>Parametreler  
 *VAL*  
 Değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlişkili anahtar döndürür. Eşleşen anahtarı bulunan, NULL döndürülür.  
  
##  <a name="setat"></a>CSimpleMap::SetAt  
 Verilen anahtarla ilişkili değeri ayarlar.  
  
```
BOOL SetAt(const TKey& key, const TVal& val);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Anahtar.  
  
 *VAL*  
 Atamak için yeni değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE anahtar bulundu ve değeri, aksi halde başarıyla değiştirildi, FALSE değerini döndürür.  
  
##  <a name="setatindex"></a>CSimpleMap::SetAtIndex  
 Belirtilen bir dizinde anahtarı ve değeri ayarlar.  
  
```
BOOL SetAtIndex(  
    int nIndex,
    const TKey& key,
    const TVal& val);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Anahtar ve değer değiştirmek için eşleştirme başvuran dizini.  
  
 `key`  
 Yeni anahtar.  
  
 *VAL*  
 Yeni değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 TRUE başarılı olduğunda, yanlış dizini geçerli değil, döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Anahtar ve değer gösterdiği güncelleştirmeleri `nIndex`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
