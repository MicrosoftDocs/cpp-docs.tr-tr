---
title: "CAtlMap sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlMap
- ATLCOLL/ATL::CAtlMap
- ATLCOLL/ATL::CAtlMap::KINARGTYPE
- ATLCOLL/ATL::CAtlMap::KOUTARGTYPE
- ATLCOLL/ATL::CAtlMap::VINARGTYPE
- ATLCOLL/ATL::CAtlMap::VOUTARGTYPE
- ATLCOLL/ATL::CPair::m_key
- ATLCOLL/ATL::CPair::m_value
- ATLCOLL/ATL::CAtlMap::CAtlMap
- ATLCOLL/ATL::CAtlMap::AssertValid
- ATLCOLL/ATL::CAtlMap::DisableAutoRehash
- ATLCOLL/ATL::CAtlMap::EnableAutoRehash
- ATLCOLL/ATL::CAtlMap::GetAt
- ATLCOLL/ATL::CAtlMap::GetCount
- ATLCOLL/ATL::CAtlMap::GetHashTableSize
- ATLCOLL/ATL::CAtlMap::GetKeyAt
- ATLCOLL/ATL::CAtlMap::GetNext
- ATLCOLL/ATL::CAtlMap::GetNextAssoc
- ATLCOLL/ATL::CAtlMap::GetNextKey
- ATLCOLL/ATL::CAtlMap::GetNextValue
- ATLCOLL/ATL::CAtlMap::GetStartPosition
- ATLCOLL/ATL::CAtlMap::GetValueAt
- ATLCOLL/ATL::CAtlMap::InitHashTable
- ATLCOLL/ATL::CAtlMap::IsEmpty
- ATLCOLL/ATL::CAtlMap::Lookup
- ATLCOLL/ATL::CAtlMap::Rehash
- ATLCOLL/ATL::CAtlMap::RemoveAll
- ATLCOLL/ATL::CAtlMap::RemoveAtPos
- ATLCOLL/ATL::CAtlMap::RemoveKey
- ATLCOLL/ATL::CAtlMap::SetAt
- ATLCOLL/ATL::CAtlMap::SetOptimalLoad
- ATLCOLL/ATL::CAtlMap::SetValueAt
dev_langs:
- C++
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9166e8f7804a3138d3e891fbe15b54cb0e270811
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="catlmap-class"></a>CAtlMap sınıfı
Bu sınıf oluşturmak ve bir harita nesnesi yönetmek için yöntemler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <typename K,
          typename V, 
          class KTraits = CElementTraits<K>, 
          class VTraits = CElementTraits<V>>
class CAtlMap
```  
  
#### <a name="parameters"></a>Parametreler  
 `K`  
 Anahtar öğe türü.  
  
 V  
 Değer öğe türü.  
  
 `KTraits`  
 Kopyalama veya anahtar öğeleri taşıma için kullanılan kod. Bkz: [CElementTraits sınıfı](../../atl/reference/celementtraits-class.md) daha fazla ayrıntı için.  
  
 `VTraits`  
 Kopyalama veya değer öğeleri taşıma için kullanılan kod.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlMap::KINARGTYPE](#kinargtype)|Bir giriş bağımsız değişkeni bir anahtar geçirildiğinde kullanılan türü|  
|[CAtlMap::KOUTARGTYPE](#koutargtype)|Bir anahtar çıkış bağımsız değişken olarak döndürüldüğünde kullanılan türü.|  
|[CAtlMap::VINARGTYPE](#vinargtype)|Bir giriş bağımsız değişkeni bir değer geçirildiğinde kullanılan türü.|  
|[CAtlMap::VOUTARGTYPE](#voutargtype)|Çıkış bağımsız değişken olarak bir değer geçirildiğinde kullanılan türü.|  
  
### <a name="public-classes"></a>Genel sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlMap::CPair sınıfı](#cpair_class)|Anahtar ve değer öğeleri içeren bir sınıf.|  

  
### <a name="cpair-data-members"></a>CPair veri üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPair::m_key](#m_key)|Anahtar öğesi depolama veri üyesi.|  
|[CPair::m_value](#m_value)|Değer öğesini depolama veri üyesi.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlMap::CAtlMap](#catlmap)|Oluşturucu.|  
|[CAtlMap:: ~ CAtlMap](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlMap::AssertValid](#assertvalid)|ASSERT neden için bu yöntemi çağırın `CAtlMap` geçerli değil.|  
|[CAtlMap::DisableAutoRehash](#disableautorehash)|Otomatik rehashing devre dışı bırakmak için bu yöntemi çağırabilmeniz `CAtlMap` nesnesi.|  
|[CAtlMap::EnableAutoRehash](#enableautorehash)|Otomatik rehashing etkinleştirmek için bu yöntemi çağırın `CAtlMap` nesnesi.|  
|[CAtlMap::GetAt](#getat)|Belirtilen konumda harita öğesi döndürmek için bu yöntemi çağırın.|  
|[CAtlMap::GetCount](#getcount)|Harita öğelerin sayısını almak için bu yöntemi çağırın.|  
|[CAtlMap::GetHashTableSize](#gethashtablesize)|Haritanın karma tablosu depo sayısını belirlemek için bu yöntemi çağırın.|  
|[CAtlMap::GetKeyAt](#getkeyat)|Verilen konumunda depolanan anahtarı almak için bu yöntemi çağırın `CAtlMap` nesnesi.|  
|[CAtlMap::GetNext](#getnext)|Bir işaretçi çifti depolanır sonraki öğeye elde etmek için bu yöntemi çağırın `CAtlMap` nesnesi.|  
|[CAtlMap::GetNextAssoc](#getnextassoc)|Yineleme için sonraki öğeyi alır.|  
|[CAtlMap::GetNextKey](#getnextkey)|Sonraki anahtarından almak için bu yöntemi çağırın `CAtlMap` nesnesi.|  
|[CAtlMap::GetNextValue](#getnextvalue)|Sonraki değer almak için bu yöntemi çağırın `CAtlMap` nesnesi.|  
|[CAtlMap::GetStartPosition](#getstartposition)|Harita yineleme başlatmak için bu yöntemi çağırın.|  
|[CAtlMap::GetValueAt](#getvalueat)|Belirli bir konumda depolanan değerini almak için bu yöntemi çağırın `CAtlMap` nesnesi.|  
|[CAtlMap::InitHashTable](#inithashtable)|Karma tablo başlatmak için bu yöntemi çağırın.|  
|[CAtlMap::IsEmpty](#isempty)|Boş eşleme nesnesi için test etmek için bu yöntemi çağırın.|  
|[CAtlMap::Lookup](#lookup)|Anahtarlar veya değerler aramak için bu yöntemi çağırın `CAtlMap` nesnesi.|  
|[CAtlMap::Rehash](#rehash)|Rehash için bu yöntemi çağırın `CAtlMap` nesnesi.|  
|[CAtlMap::RemoveAll](#removeall)|Tüm öğeleri kaldırmak için bu yöntemi çağırın `CAtlMap` nesnesi.|  
|[CAtlMap::RemoveAtPos](#removeatpos)|Belirtilen konumda öğesini kaldırmak için bu yöntemi çağırın `CAtlMap` nesnesi.|  
|[CAtlMap::RemoveKey](#removekey)|Bir öğeyi kaldırmak için bu yöntemi çağırın `CAtlMap` anahtarı verilen nesnesi.|  
|[CAtlMap::SetAt](#setat)|Bir öğe çifti eşlemeye eklemek için bu yöntemi çağırın.|  
|[CAtlMap::SetOptimalLoad](#setoptimalload)|En iyi yükünü ayarlamak için bu yöntemi çağırın `CAtlMap` nesnesi.|  
|[CAtlMap::SetValueAt](#setvalueat)|Belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın `CAtlMap` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|Yeni bir öğe ekler veya değiştirir `CAtlMap`.|  

  
## <a name="remarks"></a>Açıklamalar  
 `CAtlMap`Destek için temel öğeleri ve ilişkili değerleri sırasız bir dizi yönetme, belirli bir türde, eşleme bir dizi sağlar. (Bir anahtarı ve değeri oluşan) öğeleri büyük miktarda verimli bir şekilde depolanır ve alınan veri sağlayan bir karma algoritması kullanılarak depolanır.  
  
 `KTraits` Ve `VTraits` parametreleridir kopyalamak veya öğeleri taşımak için gereken ek kod içeren özellikler sınıfları.  
  
 Alternatif `CAtlMap` tarafından sunulan [CRBMap](../../atl/reference/crbmap-class.md) sınıfı. `CRBMap`aynı zamanda anahtar/değer çiftlerinin depolar, ancak farklı performans özellikleri sergiler. Bir öğe eklemek için geçen süre bir anahtarı aramak veya bir anahtarı silme bir `CRBMap` nesnesidir sırasını *log(n)*, burada  *n*  öğe sayısı. İçin `CAtlMap`, en kötü durum senaryoları sırasını olabilir, ancak bu işlemlerin tümü genellikle sabit bir saat sürer  *n* . Bu nedenle, normal bir durum içinde `CAtlMap` daha hızlıdır.  
  
 Diğer birbirinden `CRBMap` ve `CAtlMap` aracılığıyla depolanan öğelerin dolaşırken belirgin hale gelir. İçinde bir `CRBMap`, öğeleri sıralı bir düzende ziyaret edilen. İçinde bir `CAtlMap`öğeleri değil sıralanır ve hiçbir sipariş çıkarsanabileceği.  
  
 Az sayıda öğesi depolanması gerektiğinde kullanmayı [CSimpleMap](../../atl/reference/csimplemap-class.md) yerine sınıfı.  
  
 Daha fazla bilgi için bkz: [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcoll.h  
  
##  <a name="assertvalid"></a>CAtlMap::AssertValid  
 ASSERT neden için bu yöntemi çağırın `CAtlMap` nesnesi geçerli değil.  
  
```
void AssertValid() const;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bu yöntem ASSERT neden olur `CAtlMap` nesnesi geçerli değil.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="catlmap"></a>CAtlMap::CAtlMap  
 Oluşturucu.  
  
```
CAtlMap(
    UINT nBins = 17,
    float fOptimalLoad = 0.75f,
    float fLoThreshold = 0.25f,
    float fHiThreshold = 2.25f,
    UINT nBlockSize = 10) throw ();
```  
  
### <a name="parameters"></a>Parametreler  
 `nBins`  
 Depolanan öğeler işaretçiler sağlayan depo sayısı. Depo bir açıklaması için bu konunun ilerleyen bölümlerinde açıklamalar bakın.  
  
 `fOptimalLoad`  
 En iyi yükü oranı.  
  
 `fLoThreshold`  
 Alt eşik yük oranı.  
  
 `fHiThreshold`  
 Üst eşik yük oranı.  
  
 `nBlockSize`  
 Blok boyutu.  
  
### <a name="remarks"></a>Açıklamalar  
 `CAtlMap`tüm depolanmış öğeleri, bir karma algoritması anahtarı kullanarak dizini oluşturarak başvurur. Bu dizin "depolanan öğeler için bir işaretçi içeren bir depo" başvurur. Depo kullanımda olduğundan, bağlantılı listesi sonraki öğeleri erişmek için oluşturulur. Bir liste çapraz geçiş yapan doğru öğesi doğrudan erişimini daha yavaştır ve bu nedenle depolama gereksinimlerine göre performans dengelemek eşleme yapısı gerekiyor. Çoğu durumda iyi sonuçlar vermek için varsayılan parametreleri seçildi.  
  
 Harita nesnesindeki öğe sayısı için depo sayısı oranını yük orandır. Eşleme yapısı hesaplandığında *fOptimalLoad* parametre değeri, gerekli depo sayısını hesaplamak için kullanılacak. Bu değer kullanılarak değiştirilebilir [CAtlMap::SetOptimalLoad](#setoptimalload) yöntemi.  
  
 `fLoThreshold` Parametredir yük oranına önce ulaşabilir daha düşük değer `CAtlMap` harita en iyi boyutunu yeniden hesaplar.  
  
 `fHiThreshold` Parametredir yük oranına önce ulaşabilir üst değer `CAtlMap` nesne eşleme en iyi boyutunu yeniden hesaplar.  
  
 Bu yeniden hesaplama işlem (rehashing olarak bilinir), varsayılan olarak etkindir. Bu işlem, belki de çok miktarda veri aynı anda çağrı girerken devre dışı bırakmak istiyorsanız [CAtlMap::DisableAutoRehash](#disableautorehash) yöntemi. İle yeniden [CAtlMap::EnableAutoRehash](#enableautorehash) yöntemi.  
  
 `nBlockSize` Parametresi yeni bir öğesi gerekli olduğunda ayrılmış bellek miktarı ölçüsüdür. Daha büyük öbek boyutları bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynağı kullanır.  
  
 Herhangi bir veri depolanabilir önce çağrısıyla karma tablosu başlatmak gerekli olan [CAtlMap::InitHashTable](#inithashtable).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]  
  
##  <a name="dtor"></a>CAtlMap:: ~ CAtlMap  
 Yok Edicisi.  
  
```
~CAtlMap() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılan tüm kaynakları serbest bırakır.  
  
##  <a name="cpair_class"></a>CAtlMap::CPair sınıfı  
 Anahtar ve değer öğeleri içeren bir sınıf.  
  
```
class CPair : public __POSITION
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu sınıf yöntemler tarafından kullanılan [CAtlMap::GetNext](#getnext) ve [CAtlMap::Lookup](#lookup) eşleme yapısında depolanmış anahtar ve değer öğeleri erişmek için.  
  
##  <a name="disableautorehash"></a>CAtlMap::DisableAutoRehash  
 Otomatik rehashing devre dışı bırakmak için bu yöntemi çağırabilmeniz `CAtlMap` nesnesi.  
  
```
void DisableAutoRehash() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik rehashing (varsayılan olarak etkindir) etkin olduğu zaman, en düşük veya en yüksek değerleri (dizisinde depolanan öğe sayısı için depo sayısının oranını) yük değerini aşarsa, karma tablosundaki depo sayısı otomatik olarak hesaplanır Harita oluşturulduğu sırada belirtilen.  
  
 `DisableAutoRehash`çok sayıda öğelerinin eşlemeye aynı anda eklenecek özellikle yararlıdır. Sınırlarını aştı her zaman rehashing işlemini tetikler yerine, çağırmak için daha etkilidir `DisableAutoRehash`, öğe ekleyin ve son olarak çağrısı [CAtlMap::EnableAutoRehash](#enableautorehash).  
  
##  <a name="enableautorehash"></a>CAtlMap::EnableAutoRehash  
 Otomatik rehashing etkinleştirmek için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
void EnableAutoRehash() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik rehashing (varsayılan olarak etkindir) etkin olduğu zaman, en düşük veya en yüksek değerleri (dizisinde depolanan öğe sayısı için depo sayısının oranını) yük değerini aşarsa, karma tablosundaki depo sayısı otomatik olarak hesaplanır Harita oluşturulduğunda belirtilmiş.  
  
 **EnableAutoRefresh** yapılan bir çağrı sonra en sık kullanılan [CAtlMap::DisableAutoRehash](#disableautorehash).  
  
##  <a name="getat"></a>CAtlMap::GetAt  
 Belirtilen konumda harita öğesi döndürmek için bu yöntemi çağırın.  
  
```
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Önceki bir çağrı tarafından döndürülen konumu sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).  
  
 `key`  
 Haritanın anahtarın türünü belirten bir şablon parametre.  
  
 *value*  
 Haritanın değerin türünü belirten bir şablon parametre.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli çiftlerini eşlemesinde depolanan anahtar/değer için bir işaretçi döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata ayıklama derlemelerinde, bir onaylama hata oluşacaktır `pos` NULL değerine eşittir.  
  
##  <a name="getcount"></a>CAtlMap::GetCount  
 Harita öğelerin sayısını almak için bu yöntemi çağırın.  
  
```
size_t GetCount() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Harita nesnesinde öğe sayısını döndürür. Bir anahtar/değer çifti tek bir öğedir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="gethashtablesize"></a>CAtlMap::GetHashTableSize  
 Haritanın karma tablosu depo sayısını belirlemek için bu yöntemi çağırın.  
  
```
UINT GetHashTableSize() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Karma tablosunda depo sayısını döndürür. Bkz: [CAtlMap::CAtlMap](#catlmap) için bir açıklama.  
  
##  <a name="getkeyat"></a>CAtlMap::GetKeyAt  
 Verilen konumunda depolanan anahtarı almak için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
const K& GetKeyAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Önceki bir çağrı tarafından döndürülen konumu sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen konumunda depolanan anahtar için bir başvuru döndürür `CAtlMap` nesnesi.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="getnext"></a>CAtlMap::GetNext  
 Bir işaretçi çifti depolanır sonraki öğeye elde etmek için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Önceki bir çağrı tarafından döndürülen konumu sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonraki çiftlerini eşlemesinde depolanan anahtar/değer için bir işaretçi döndürür. `pos` Konumu sayaç, her çağrısından sonra güncelleştirilir. Alınan öğe Haritası son ise `pos` NULL olarak ayarlandı.  
  
##  <a name="getnextassoc"></a>CAtlMap::GetNextAssoc  
 Yineleme için sonraki öğeyi alır.  
  
```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Önceki bir çağrı tarafından döndürülen konumu sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).  
  
 `key`  
 Haritanın anahtarın türünü belirten bir şablon parametre.  
  
 *value*  
 Haritanın değerin türünü belirten bir şablon parametre.  
  
### <a name="remarks"></a>Açıklamalar  
 `pos` Konumu sayaç, her çağrısından sonra güncelleştirilir. Alınan öğe Haritası son ise `pos` NULL olarak ayarlandı.  
  
##  <a name="getnextkey"></a>CAtlMap::GetNextKey  
 Sonraki anahtarından almak için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
const K& GetNextKey(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Önceki bir çağrı tarafından döndürülen konumu sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonraki anahtarı başvuru eşlemesinde döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli konumu sayaç güncelleştirmeleri `pos`. Eşleme içinde daha fazla girdi yoksa konumu sayacı NULL olarak ayarlanır.  
  
##  <a name="getnextvalue"></a>CAtlMap::GetNextValue  
 Sonraki değer almak için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Önceki bir çağrı tarafından döndürülen konumu sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Sonraki değeri başvuru eşlemesinde döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli konumu sayaç güncelleştirmeleri `pos`. Eşleme içinde daha fazla girdi yoksa konumu sayacı NULL olarak ayarlanır.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="getstartposition"></a>CAtlMap::GetStartPosition  
 Harita yineleme başlatmak için bu yöntemi çağırın.  
  
```
POSITION GetStartPosition() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlangıç konumu ya da NULL harita boşsa, döndürülen döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Harita yineleme döndürerek başlatmak için bu yöntemi çağırabilmeniz bir **konumu** için geçirilen değer `GetNextAssoc` yöntemi.  
  
> [!NOTE]
>  Yineleme sırası tahmin edilebilir değil  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="getvalueat"></a>CAtlMap::GetValueAt  
 Belirli bir konumda depolanan değerini almak için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Önceki bir çağrı tarafından döndürülen konumu sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen konumunda depolanan değeri bir başvuru döndürür `CAtlMap` nesnesi.  
  
##  <a name="inithashtable"></a>CAtlMap::InitHashTable  
 Karma tablo başlatmak için bu yöntemi çağırın.  
  
```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```  
  
### <a name="parameters"></a>Parametreler  
 `nBins`  
 Karma tablosu tarafından kullanılan depo sayısı. Bkz: [CAtlMap::CAtlMap](#catlmap) için bir açıklama.  
  
 `bAllocNow`  
 Bellek ayrılması gereken zaman bayrağı gösterimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** başarılı başlatma üzerinde **false** hatasında.  
  
### <a name="remarks"></a>Açıklamalar  
 `InitHashTable`herhangi bir öğe karma tablosunda depolanır önce çağrılmalıdır.  Bu yöntem açıkça çağrılmazsa otomatik olarak bir öğe tarafından belirtilen depo sayısı kullanılarak eklendiğinden ilk kez çağrılacağı **CAtlMap** Oluşturucusu.  Aksi takdirde eşlemesi tarafından belirtilen yeni depo sayısı kullanılarak başlatılacak `nBins` parametresi.  
  
 Varsa `bAllocNow` parametre false ise, önce gerekli olana kadar karma tablosu tarafından gerekli bellek tahsis olmaz. Bu harita kullandıysanız belirsiz varsa yararlı olabilir.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="isempty"></a>CAtlMap::IsEmpty  
 Boş eşleme nesnesi için test etmek için bu yöntemi çağırın.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** harita boşsa, **false** Aksi takdirde.  
  
##  <a name="kinargtype"></a>CAtlMap::KINARGTYPE  
 Bir giriş bağımsız değişkeni bir anahtar geçirildiğinde kullanılan türü.  
  
```
typedef KTraits::INARGTYPE KINARGTYPE;
```  
  
##  <a name="koutargtype"></a>CAtlMap::KOUTARGTYPE  
 Bir anahtar çıkış bağımsız değişken olarak döndürüldüğünde kullanılan türü.  
  
```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```  
  
##  <a name="lookup"></a>CAtlMap::Lookup  
 Anahtarlar veya değerler aramak için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Bakılacak öğesi tanımlayan anahtarını belirtir.  
  
 *value*  
 Değişken, aranan yukarı değerini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yönteminin ilk form anahtar, aksi takdirde false bulunursa true değerini döndürür. İkinci ve üçüncü forms bir işaretçi döndürmek bir [CPair](#cpair_class) kullanılabileceği bir konum çağrılar için [CAtlMap::GetNext](#getnext) ve benzeri.  
  
### <a name="remarks"></a>Açıklamalar  
 `Lookup`Belirtilen anahtar parametresi tam olarak eşleşen bir anahtar içeren map öğesi hızla bulmak için bir karma algoritması kullanır.  
  
##  <a name="operator_at"></a>CAtlMap::operator\[\]  
 Yeni bir öğe ekler veya değiştirir `CAtlMap`.  
  
```
V& operator[](kinargtype key) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Eklenecek veya değiştirilecek öğenin anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Verilen anahtarla ilişkili değeri bir başvuru döndürür.  
  
### <a name="example"></a>Örnek  
 Anahtar zaten varsa öğe değiştirilir. Anahtar mevcut değilse yeni bir öğesi eklenir. Örneğin bkz [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="rehash"></a>CAtlMap::Rehash  
 Rehash için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
void Rehash(UINT nBins = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `nBins`  
 Karma tablosunda kullanmak için depo yeni sayısı. Bkz: [CAtlMap::CAtlMap](#catlmap) için bir açıklama.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `nBins` 0 ' dır `CAtlMap` harita ve en iyi yük ayarı öğe sayısına dayalı makul bir sayıyı hesaplar. Normalde rehashing işlemi, otomatiktir ancak [CAtlMap::DisableAutoRehash](#disableautorehash) bırakıldı olarak adlandırılan, bu yöntem gerekli yeniden boyutlandırma gerçekleştirir.  
  
##  <a name="removeall"></a>CAtlMap::RemoveAll  
 Tüm öğeleri kaldırmak için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
void RemoveAll() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Temizler `CAtlMap` öğeleri depolamak için kullanılan bellek boşaltma nesnesi.  
  
##  <a name="removeatpos"></a>CAtlMap::RemoveAtPos  
 Belirtilen konumda öğesini kaldırmak için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
void RemoveAtPos(POSITION pos) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Önceki bir çağrı tarafından döndürülen konumu sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).  
  
### <a name="remarks"></a>Açıklamalar  
 Belirtilen konumda saklanan anahtar/değer çifti kaldırır. Öğe depolamak için kullanılan bellek serbest bırakılır. KONUM tarafından başvurulan `pos` geçersiz hale gelir ve diğer öğeleri KONUMUNU eşlemesindeki yapmaları gerekmez, geçerli kalırken aynı sırada korur.  
  
##  <a name="removekey"></a>CAtlMap::RemoveKey  
 Bir öğeyi kaldırmak için bu yöntemi çağırın `CAtlMap` anahtarı verilen nesnesi.  
  
```
bool RemoveKey(KINARGTYPE key) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Kaldırmak istediğiniz öğe çiftine karşılık gelen anahtarı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** anahtarı bulundu ve kaldırıldı, **false** hatasında.  
  
### <a name="example"></a>Örnek  
 Örneğin bkz [CAtlMap::CAtlMap](#catlmap).  
  
##  <a name="setat"></a>CAtlMap::SetAt  
 Bir öğe çifti eşlemeye eklemek için bu yöntemi çağırın.  
  
```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>Parametreler  
 `key`  
 Anahtar değeri eklemek için `CAtlMap` nesnesi.  
  
 *value*  
 Eklenecek değer `CAtlMap` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Anahtar/değer öğesi çifti konumunu döndürür `CAtlMap` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `SetAt`eşleşen bir anahtarı bulunursa, var olan öğenin yerini alır. Anahtar bulunamazsa yeni bir anahtar/değer çifti oluşturulur.  
  
##  <a name="setoptimalload"></a>CAtlMap::SetOptimalLoad  
 En iyi yükünü ayarlamak için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```  
  
### <a name="parameters"></a>Parametreler  
 `fOptimalLoad`  
 En iyi yükü oranı.  
  
 `fLoThreshold`  
 Alt eşik yük oranı.  
  
 `fHiThreshold`  
 Üst eşik yük oranı.  
  
 `bRehashNow`  
 Karma tablo yeniden hesaplanması tanımlanmadığını belirten bayrak.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem için en iyi yükü değer yeniden tanımlamaktadır `CAtlMap` nesnesi. Bkz: [CAtlMap::CAtlMap](#catlmap) çeşitli parametrelerin bir tartışma için. Varsa `bRehashNow` true olur ve öğelerin sayısı minimum ve maksimum değerleri dışında karma tablosu yeniden hesaplanır.  
  
##  <a name="setvalueat"></a>CAtlMap::SetValueAt  
 Belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın `CAtlMap` nesnesi.  
  
```
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```  
  
### <a name="parameters"></a>Parametreler  
 `pos`  
 Önceki bir çağrı tarafından döndürülen konumu sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).  
  
 *value*  
 Eklenecek değer `CAtlMap` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Verilen konumunda depolanan değer öğesini değiştirir `CAtlMap` nesnesi.  
  
##  <a name="vinargtype"></a>CAtlMap::VINARGTYPE  
 Bir giriş bağımsız değişkeni bir değer geçirildiğinde kullanılan türü.  
  
```
typedef VTraits::INARGTYPE VINARGTYPE;
```  
  
##  <a name="voutargtype"></a>CAtlMap::VOUTARGTYPE  
 Çıkış bağımsız değişken olarak bir değer geçirildiğinde kullanılan türü.  
  
```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```  
  
##  <a name="m_key"></a>CAtlMap::CPair::m_key  
 Anahtar öğesi depolama veri üyesi.  
  
```
const K m_key;
```    
  
### <a name="parameters"></a>Parametreler  
 `K`  
 Anahtar öğe türü.  
  
##  <a name="m_value"></a>CAtlMap::CPair::m_value  
 Değer öğesini depolama veri üyesi.  
  
```
V  m_value;
```    
  
### <a name="parameters"></a>Parametreler  
 *V*  
 Değer öğe türü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kayan örnek](../../visual-cpp-samples.md)   
 [Oluşturma](../../visual-cpp-samples.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
