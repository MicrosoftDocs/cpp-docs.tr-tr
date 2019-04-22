---
title: CAtlMap sınıfı
ms.date: 11/04/2016
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
helpviewer_keywords:
- CAtlMap class
ms.assetid: 5e2fe028-8e6d-4686-93df-1433d2080ec3
ms.openlocfilehash: 1821532a4d5a3078202f180273b02945b8d8e4ba
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58774561"
---
# <a name="catlmap-class"></a>CAtlMap sınıfı

Bu sınıf, oluşturmak ve bir harita nesnesi yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CAtlMap
```

#### <a name="parameters"></a>Parametreler

*K*<br/>
Anahtar öğe türü.

*V*<br/>
Değer öğe türü.

*KTraits*<br/>
Kopyalamak veya taşımak temel öğeleri için kullanılan kod. Bkz: [CElementTraits sınıfı](../../atl/reference/celementtraits-class.md) daha fazla ayrıntı için.

*VTraits*<br/>
Kopyalamak veya taşımak değeri öğeleri için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlMap::KINARGTYPE](#kinargtype)|Bir giriş bağımsız değişkeni bir anahtar geçirildiğinde kullanılan türü|
|[CAtlMap::KOUTARGTYPE](#koutargtype)|Çıkış bağımsız değişken olarak bir anahtar döndürüldüğünde kullanılan türü.|
|[CAtlMap::VINARGTYPE](#vinargtype)|Kullanılması için bir giriş bağımsız değişkeni geçirilen bir değer türü.|
|[CAtlMap::VOUTARGTYPE](#voutargtype)|Çıkış bağımsız değişken olarak geçirilen bir değer olduğunda kullanılan türü.|

### <a name="public-classes"></a>Genel sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[CAtlMap::CPair sınıfı](#cpair_class)|Anahtar ve değer öğeleri içeren bir sınıf.|

### <a name="cpair-data-members"></a>CPair veri üyesi

|Ad|Açıklama|
|----------|-----------------|
|[CPair::m_key](#m_key)|Anahtar öğesi depolama veri üyesi.|
|[CPair::m_value](#m_value)|Değer öğesini depolama veri üyesi.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CAtlMap::CAtlMap](#catlmap)|Oluşturucu.|
|[CAtlMap:: ~ CAtlMap](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlMap::AssertValid](#assertvalid)|ASSERT neden için bu yöntemi çağırın `CAtlMap` geçerli değil.|
|[CAtlMap::DisableAutoRehash](#disableautorehash)|Otomatik rehashing devre dışı bırakmak için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::EnableAutoRehash](#enableautorehash)|Otomatik rehashing etkinleştirmek için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::GetAt](#getat)|Eşlem içindeki belirtilen konumda bir öğeyi döndürmek için bu yöntemi çağırın.|
|[CAtlMap::GetCount](#getcount)|Eşlem içindeki öğelerin sayısını almak için bu yöntemi çağırın.|
|[CAtlMap::GetHashTableSize](#gethashtablesize)|Haritanın karma tablo depo sayısını belirlemek için bu yöntemi çağırın.|
|[CAtlMap::GetKeyAt](#getkeyat)|Belirtilen konumda depolanan anahtarı almak için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::GetNext](#getnext)|Çifti depolanan sonraki öğeye bir işaretçi alma için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::GetNextAssoc](#getnextassoc)|Yineleme için sonraki öğeyi alır.|
|[CAtlMap::GetNextKey](#getnextkey)|Sonraki anahtarını almak için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::GetNextValue](#getnextvalue)|Sonraki değerini almak için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::GetStartPosition](#getstartposition)|Harita yineleme başlangıç için bu yöntemi çağırın.|
|[CAtlMap::GetValueAt](#getvalueat)|Belirli bir konumda depolanan değeri almak için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::InitHashTable](#inithashtable)|Karma tablo başlatmak için bu yöntemi çağırın.|
|[CAtlMap::IsEmpty](#isempty)|Bir boş eşleme nesnesi için test etmek için bu yöntemi çağırın.|
|[CAtlMap::Lookup](#lookup)|Anahtarlar veya değerler aramak için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::Rehash](#rehash)|Rehash için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::RemoveAll](#removeall)|Tüm öğeleri kaldırmak için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::RemoveAtPos](#removeatpos)|Belirtilen konumda bir öğe kaldırmak için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::RemoveKey](#removekey)|Bir öğeyi kaldırmak için bu yöntemi çağırın `CAtlMap` anahtar nesnesi.|
|[CAtlMap::SetAt](#setat)|Haritayı bir öğe çifti eklemek için bu yöntemi çağırın.|
|[CAtlMap::SetOptimalLoad](#setoptimalload)|En iyi yükünü ayarlamak için bu yöntemi çağırın `CAtlMap` nesne.|
|[CAtlMap::SetValueAt](#setvalueat)|Belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın `CAtlMap` nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CAtlMap::operator\[\]](catlmap-class.md#operator_at)|Yeni bir öğe ekler veya değiştirir `CAtlMap`.|

## <a name="remarks"></a>Açıklamalar

`CAtlMap` sırasız bir dizi temel öğeleri ve ilişkili değerleri yönetme, belirli bir türü, eşleme bir dizi için destek sağlar. (Bir anahtar ve değerden oluşan) öğeleri verimli bir şekilde depolanır ve alınan veriler, büyük bir miktarını sağlayan bir karma algoritması kullanılarak depolanır.

*KTraits* ve *VTraits* kopyalama veya öğeleri taşımak için gerekli olan herhangi bir ek kod içeren nitelikleri sınıflar parametrelerdir.

Alternatif `CAtlMap` tarafından sunulan [CRBMap](../../atl/reference/crbmap-class.md) sınıfı. `CRBMap` Ayrıca, anahtar/değer çiftleri depolar ancak farklı performans özellikleri sergiler. Bir öğe eklemek için harcanan süre bir anahtarı aramak veya bir anahtarı silme bir `CRBMap` nesnedir sırasını *log(n)* burada *n* öğe sayısı. İçin `CAtlMap`, iki katına senaryoları sırasını olsa da bu işlemlerin tümü genellikle bir sabit zaman alan *n*. Bu nedenle, normal bir durum içinde `CAtlMap` daha hızlıdır.

Diğer birbirinden `CRBMap` ve `CAtlMap` depolanan öğeler boyunca yineleme görünür olur. İçinde bir `CRBMap`, öğelerin sıralı bir düzende ziyaret edilmedi. İçinde bir `CAtlMap`öğeleri olmayan sıralanır ve hiçbir sırası sonuçlandı.

Küçük bir dizi öğe depolanacak gerektiğinde kullanmayı [CSimpleMap](../../atl/reference/csimplemap-class.md) bunun yerine sınıf.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="assertvalid"></a>  CAtlMap::AssertValid

ASSERT neden için bu yöntemi çağırın `CAtlMap` nesnesi geçerli değil.

```
void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, bu yöntem bir ONAYLAMADIR neden olur `CAtlMap` nesnesi geçerli değil.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlMap::CAtlMap](#catlmap).

##  <a name="catlmap"></a>  CAtlMap::CAtlMap

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

*nBins*<br/>
Bölme depolanan öğelere işaretçileri sağlama sayısı. Depo bir açıklaması için bu konunun ilerleyen bölümlerinde açıklamalara bakın.

*fOptimalLoad*<br/>
En iyi yük oranı.

*fLoThreshold*<br/>
Düşük bir Eşikte yük oranı.

*fHiThreshold*<br/>
Üst eşik yük oranı.

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

`CAtlMap` Tüm saklı öğeleri, bir karma algoritma anahtarı kullanarak dizini oluşturarak başvuruyor. Bu dizin "saklı öğeleri için bir işaretçi içeren depo" başvuruyor. Depo zaten kullanılıyorsa, bağlantılı liste sonraki öğelere erişmek için oluşturulur. Bir liste geçiş doğru öğesi doğrudan erişim daha yavaştır ve bu nedenle depolama gereksinimlerini performans karşı dengelemek eşleme yapısı gerekiyor. Varsayılan parametreleri, çoğu zaman iyi sonuçlar vermek için seçilmiştir.

Yükleme oranı harita nesnesinde saklanan öğe sayısına bölme sayısı oranıdır. Eşleme yapısı hesaplandığında *fOptimalLoad* parametre değeri, gerekli depo sayısını hesaplamak için kullanılır. Bu değer kullanılarak değiştirilebilir. [CAtlMap::SetOptimalLoad](#setoptimalload) yöntemi.

*FLoThreshold* parametredir yük oranı önce ulaşabileceği daha düşük bir değere `CAtlMap` en uygun eşleme boyutunu yeniden hesaplar.

*FHiThreshold* parametredir yük oranı önce ulaşabileceği üst değer `CAtlMap` nesne eşleme en iyi boyutunu yeniden hesaplar.

Bu yeniden hesaplama işleminin (rehashing olarak bilinir), varsayılan olarak etkindir. Bu işlem çok fazla veri tek seferde çağrı girerken belki de devre dışı bırakmak isterseniz [CAtlMap::DisableAutoRehash](#disableautorehash) yöntemi. İle yeniden [CAtlMap::EnableAutoRehash](#enableautorehash) yöntemi.

*NBlockSize* parametre gerektiğinde yeni bir öğe ayrılan bellek miktarını ölçüsüdür. Büyük blok boyutları için bellek ayırma yordamlarını aramalarını azaltır, ancak daha fazla kaynağı kullanır.

Herhangi bir veri depolanabilir önce çağrısı ile karma tablo başlatmak gerekli [CAtlMap::InitHashTable](#inithashtable).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]

##  <a name="dtor"></a>  CAtlMap:: ~ CAtlMap

Yıkıcı.

```
~CAtlMap() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

##  <a name="cpair_class"></a>  CAtlMap::CPair sınıfı

Anahtar ve değer öğeleri içeren bir sınıf.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Açıklamalar

Bu sınıf yöntemleri tarafından kullanılır [CAtlMap::GetNext](#getnext) ve [CAtlMap::Lookup](#lookup) eşleme yapısı içinde depolanan anahtar ve değer öğelere erişmek için.

##  <a name="disableautorehash"></a>  CAtlMap::DisableAutoRehash

Otomatik rehashing devre dışı bırakmak için bu yöntemi çağırın `CAtlMap` nesne.

```
void DisableAutoRehash() throw();
```

### <a name="remarks"></a>Açıklamalar

Otomatik rehashing (Bu varsayılan olarak etkindir) etkin olduğunda, yük değeri (bölme depolanan dizideki öğe sayısına sayısı oranını) en yüksek veya en düşük değeri aşarsa karma tablosundaki bölme sayısı otomatik olarak yeniden hesaplanır Harita oluşturulduğu sırada belirtilen.

`DisableAutoRehash` çok sayıda öğe haritaya tek seferde eklenecek en yararlı olur. Sınırları aşıldığında her zaman rehashing işlemini tetikleme yerine çağırmak için daha etkilidir `DisableAutoRehash`, öğeleri ekleyin ve son olarak çağırmayı [CAtlMap::EnableAutoRehash](#enableautorehash).

##  <a name="enableautorehash"></a>  CAtlMap::EnableAutoRehash

Otomatik rehashing etkinleştirmek için bu yöntemi çağırın `CAtlMap` nesne.

```
void EnableAutoRehash() throw();
```

### <a name="remarks"></a>Açıklamalar

Otomatik rehashing (Bu varsayılan olarak etkindir) etkin olduğunda, yük değeri (bölme depolanan dizideki öğe sayısına sayısı oranını) en yüksek veya en düşük değeri aşarsa karma tablosundaki bölme sayısı otomatik olarak yeniden hesaplanır Harita oluşturulduğunda belirtildi.

`EnableAutoRefresh` çağrısı yapıldıktan sonra en sık kullanılan [CAtlMap::DisableAutoRehash](#disableautorehash).

##  <a name="getat"></a>  CAtlMap::GetAt

Eşlem içindeki belirtilen konumda bir öğeyi döndürmek için bu yöntemi çağırın.

```
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen konum sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

*anahtar*<br/>
Haritanın anahtar türünü belirten bir şablon parametre.

*value*<br/>
Haritanın değerin türünü belirten bir şablon parametre.

### <a name="return-value"></a>Dönüş Değeri

Geçerli bir eşlem içinde depolan anahtar/değer öğe çiftinin bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pos* NULL değerine eşittir.

##  <a name="getcount"></a>  CAtlMap::GetCount

Eşlem içindeki öğelerin sayısını almak için bu yöntemi çağırın.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Harita nesnesinde öğelerin sayısını döndürür. Tek bir öğe, bir anahtar/değer çiftidir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlMap::CAtlMap](#catlmap).

##  <a name="gethashtablesize"></a>  CAtlMap::GetHashTableSize

Haritanın karma tablo depo sayısını belirlemek için bu yöntemi çağırın.

```
UINT GetHashTableSize() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bölme sayısı karma tablosundan döndürür. Bkz: [CAtlMap::CAtlMap](#catlmap) açıklaması.

##  <a name="getkeyat"></a>  CAtlMap::GetKeyAt

Belirtilen konumda depolanan anahtarı almak için bu yöntemi çağırın `CAtlMap` nesne.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen konum sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konumda depolanan anahtar için bir başvuru döndürür `CAtlMap` nesne.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlMap::CAtlMap](#catlmap).

##  <a name="getnext"></a>  CAtlMap::GetNext

Çifti depolanan sonraki öğeye bir işaretçi alma için bu yöntemi çağırın `CAtlMap` nesne.

```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen konum sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Dönüş Değeri

Sonraki bir eşlem içinde depolan anahtar/değer öğe çiftinin bir işaretçi döndürür. *Pos* konumu sayaç her çağrıdan sonra güncelleştirilir. Eşlem içindeki son alınan öğe ise *pos* NULL olarak ayarlandı.

##  <a name="getnextassoc"></a>  CAtlMap::GetNextAssoc

Yineleme için sonraki öğeyi alır.

```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen konum sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

*anahtar*<br/>
Haritanın anahtar türünü belirten bir şablon parametre.

*value*<br/>
Haritanın değerin türünü belirten bir şablon parametre.

### <a name="remarks"></a>Açıklamalar

*Pos* konumu sayaç her çağrıdan sonra güncelleştirilir. Eşlem içindeki son alınan öğe ise *pos* NULL olarak ayarlandı.

##  <a name="getnextkey"></a>  CAtlMap::GetNextKey

Sonraki anahtarını almak için bu yöntemi çağırın `CAtlMap` nesne.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen konum sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Dönüş Değeri

Haritada sonraki anahtarı için bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli konumu sayacı güncelleştiren *pos*. Haritada daha fazla girdi yoksa konumu sayaç değeri NULL olarak ayarlanır.

##  <a name="getnextvalue"></a>  CAtlMap::GetNextValue

Sonraki değerini almak için bu yöntemi çağırın `CAtlMap` nesne.

```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen konum sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Dönüş Değeri

Haritada sonraki değerine bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli konumu sayacı güncelleştiren *pos*. Haritada daha fazla girdi yoksa konumu sayaç değeri NULL olarak ayarlanır.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlMap::CAtlMap](#catlmap).

##  <a name="getstartposition"></a>  CAtlMap::GetStartPosition

Harita yineleme başlangıç için bu yöntemi çağırın.

```
POSITION GetStartPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başlangıç konumu veya NULL bir eşlem boşsa, döndürülen döndürür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem bir konuma döndürerek bir harita yineleme başlangıç değeri çağrı geçilebilir `GetNextAssoc` yöntemi.

> [!NOTE]
>  Yineleme sırası, tahmin edilebilir değil.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlMap::CAtlMap](#catlmap).

##  <a name="getvalueat"></a>  CAtlMap::GetValueAt

Belirli bir konumda depolanan değeri almak için bu yöntemi çağırın `CAtlMap` nesne.

```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen konum sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konumda depolanan değeri bir başvuru döndürür `CAtlMap` nesne.

##  <a name="inithashtable"></a>  CAtlMap::InitHashTable

Karma tablo başlatmak için bu yöntemi çağırın.

```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```

### <a name="parameters"></a>Parametreler

*nBins*<br/>
Karma tablosu tarafından kullanılan depo sayısı. Bkz: [CAtlMap::CAtlMap](#catlmap) açıklaması.

*bAllocNow*<br/>
Bellek ayrılmış bir bayrak göstergesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı başlatmayı, doğru döndürür başarısız olduğunda FALSE.

### <a name="remarks"></a>Açıklamalar

`InitHashTable` herhangi bir öğe karma tablosundan depolanmadan önce çağrılmalıdır.  Bu yöntemi açıkça çağrılmaz, otomatik olarak bir öğe tarafından belirtilen bölme sayısı kullanarak eklenen ilk kez çağrılacağı `CAtlMap` Oluşturucusu.  Aksi halde, eşleme tarafından belirtilen yeni bölme sayısı kullanılarak başlatılacak *nBins* parametresi.

Varsa *bAllocNow* parametre değeri false ise ilk gerekli olana kadar karma tablosu tarafından gerekli bellek tahsis olmaz. Bu harita kullanılacaksa belirsiz ise yararlı olabilir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlMap::CAtlMap](#catlmap).

##  <a name="isempty"></a>  CAtlMap::IsEmpty

Bir boş eşleme nesnesi için test etmek için bu yöntemi çağırın.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Harita değilse FALSE değerini boş, TRUE döndürür.

##  <a name="kinargtype"></a>  CAtlMap::KINARGTYPE

Bir giriş bağımsız değişkeni bir anahtar geçirildiğinde kullanılan türü.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

##  <a name="koutargtype"></a>  CAtlMap::KOUTARGTYPE

Çıkış bağımsız değişken olarak bir anahtar döndürüldüğünde kullanılan türü.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

##  <a name="lookup"></a>  CAtlMap::Lookup

Anahtarlar veya değerler aramak için bu yöntemi çağırın `CAtlMap` nesne.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Bakılacak öğeyi tanımlayan anahtar belirtir.

*value*<br/>
Değişken, aranan yukarı değerini alır.

### <a name="return-value"></a>Dönüş Değeri

İlk yöntem biçiminin anahtar, aksi takdirde false bulunursa true değerini döndürür. İkinci ve üçüncü formları için bir işaretçi döndürür bir [CPair](#cpair_class) kullanılabilir olarak bir konumu aramak için [CAtlMap::GetNext](#getnext) ve benzeri.

### <a name="remarks"></a>Açıklamalar

`Lookup` Belirtilen anahtar parametresi tam olarak eşleşen bir anahtara içeren harita öğesi hızla bulmak için bir karma algoritma kullanır.

##  <a name="operator_at"></a>  CAtlMap::operator \[\]

Yeni bir öğe ekler veya değiştirir `CAtlMap`.

```
V& operator[](kinargtype key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Eklenecek veya değiştirilecek öğenin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Verilen anahtarla ilişkili değeri bir başvuru döndürür.

### <a name="example"></a>Örnek

Anahtar zaten varsa, öğe değiştirilir. Anahtar mevcut değilse yeni bir öğe eklendi. Örneğin bakın [CAtlMap::CAtlMap](#catlmap).

##  <a name="rehash"></a>  CAtlMap::Rehash

Rehash için bu yöntemi çağırın `CAtlMap` nesne.

```
void Rehash(UINT nBins = 0);
```

### <a name="parameters"></a>Parametreler

*nBins*<br/>
Yeni Karma tablosunda kullanmak için depo sayısı. Bkz: [CAtlMap::CAtlMap](#catlmap) açıklaması.

### <a name="remarks"></a>Açıklamalar

Varsa *nBins* 0 ' dır `CAtlMap` Haritası ve en iyi yük ayarı içindeki öğelerin sayısını temel makul sayıda hesaplar. Normalde rehashing otomatik, işlemidir ancak [CAtlMap::DisableAutoRehash](#disableautorehash) kaldırıldı olarak adlandırılan, bu yöntem gerekli boyutlandırma gerçekleştirir.

##  <a name="removeall"></a>  CAtlMap::RemoveAll

Tüm öğeleri kaldırmak için bu yöntemi çağırın `CAtlMap` nesne.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Temizler `CAtlMap` öğeleri depolamak için kullanılan bellek boşaltma nesnesi.

##  <a name="removeatpos"></a>  CAtlMap::RemoveAtPos

Belirtilen konumda bir öğe kaldırmak için bu yöntemi çağırın `CAtlMap` nesne.

```
void RemoveAtPos(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen konum sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="remarks"></a>Açıklamalar

Belirtilen konumda depolanan anahtar/değer çifti kaldırır. Öğe depolamak için kullanılan bellek serbest bırakılır. KONUMU tarafından başvurulan *pos* geçersiz hale gelir ve aynı sırada herhangi bir öğe konumu haritada yaptıkları mutlaka geçerli kalırken korur.

##  <a name="removekey"></a>  CAtlMap::RemoveKey

Bir öğeyi kaldırmak için bu yöntemi çağırın `CAtlMap` anahtar nesnesi.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kaldırmak istediğiniz anahtar karşılık gelen bir öğe çifti.

### <a name="return-value"></a>Dönüş Değeri

TRUE anahtar değilse bulunan ve kaldırılmış, başarısız olduğunda FALSE döndürür.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlMap::CAtlMap](#catlmap).

##  <a name="setat"></a>  CAtlMap::SetAt

Haritayı bir öğe çifti eklemek için bu yöntemi çağırın.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Eklenecek anahtar değeri `CAtlMap` nesne.

*value*<br/>
Eklenecek değer `CAtlMap` nesne.

### <a name="return-value"></a>Dönüş Değeri

Anahtar/değer öğe çiftinin konumunu döndürür `CAtlMap` nesne.

### <a name="remarks"></a>Açıklamalar

`SetAt` eşleşen bir anahtar bulunursa, var olan öğenin yerini alır. Anahtar bulunamazsa yeni bir anahtar/değer çifti oluşturulur.

##  <a name="setoptimalload"></a>  CAtlMap::SetOptimalLoad

En iyi yükünü ayarlamak için bu yöntemi çağırın `CAtlMap` nesne.

```
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```

### <a name="parameters"></a>Parametreler

*fOptimalLoad*<br/>
En iyi yük oranı.

*fLoThreshold*<br/>
Düşük bir Eşikte yük oranı.

*fHiThreshold*<br/>
Üst eşik yük oranı.

*bRehashNow*<br/>
Karma tabloyu yeniden hesaplanması gerektiği olmadığını belirten bayrak.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, en iyi yük değeri'ı yeniden tanımladığı `CAtlMap` nesne. Bkz: [CAtlMap::CAtlMap](#catlmap) çeşitli parametreleri hakkında ayrıntılı bilgi için. Varsa *bRehashNow* true ise ve öğelerinin sayısını dışında minimum ve maksimum değerler, karma tabloyu yeniden hesaplanır.

##  <a name="setvalueat"></a>  CAtlMap::SetValueAt

Belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın `CAtlMap` nesne.

```
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Önceki bir çağrı tarafından döndürülen konum sayaç [CAtlMap::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

*value*<br/>
Eklenecek değer `CAtlMap` nesne.

### <a name="remarks"></a>Açıklamalar

Belirtilen konumda depolanan değer öğesini değiştirir `CAtlMap` nesne.

##  <a name="vinargtype"></a>  CAtlMap::VINARGTYPE

Kullanılması için bir giriş bağımsız değişkeni geçirilen bir değer türü.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

##  <a name="voutargtype"></a>  CAtlMap::VOUTARGTYPE

Çıkış bağımsız değişken olarak geçirilen bir değer olduğunda kullanılan türü.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

##  <a name="m_key"></a>  CAtlMap::CPair::m_key

Anahtar öğesi depolama veri üyesi.

```
const K m_key;
```

### <a name="parameters"></a>Parametreler

*K*<br/>
Anahtar öğe türü.

##  <a name="m_value"></a>  CAtlMap::CPair::m_value

Değer öğesini depolama veri üyesi.

```
V  m_value;
```

### <a name="parameters"></a>Parametreler

*V*<br/>
Değer öğe türü.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan örnek](../../overview/visual-cpp-samples.md)<br/>
[Oluşturma](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
