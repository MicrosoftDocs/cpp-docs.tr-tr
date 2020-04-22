---
title: CAtlMap Sınıfı
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
ms.openlocfilehash: 8954eeae28f13fb50643646b41c032588ecc278f
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81748659"
---
# <a name="catlmap-class"></a>CAtlMap Sınıfı

Bu sınıf, bir harita nesnesi oluşturma ve yönetme yöntemleri sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CAtlMap
```

#### <a name="parameters"></a>Parametreler

*Kahraman*<br/>
Anahtar öğe türü.

*V*<br/>
Değer öğesi türü.

*KTraits*<br/>
Anahtar öğeleri kopyalamak veya taşımak için kullanılan kod. Daha fazla bilgi için [CElementTraits Sınıfına](../../atl/reference/celementtraits-class.md) bakın.

*VTraits*<br/>
Değer öğelerini kopyalamak veya taşımak için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefs

|Adı|Açıklama|
|----------|-----------------|
|[CAtlMap::KINARGTYPE](#kinargtype)|Bir anahtar giriş bağımsız değişkeni olarak geçirildiğinde kullanılan tür|
|[CAtlMap::KOUTARGTYPE](#koutargtype)|Bir anahtar çıktı bağımsız değişkeni olarak döndürüldüğünde kullanılan tür.|
|[CAtlMap::VINARGTYPE](#vinargtype)|Bir değer girdi bağımsız değişkeni olarak geçildiğinde kullanılan tür.|
|[CAtlMap::VOUTARGTYPE](#voutargtype)|Bir değer çıktı bağımsız değişkeni olarak geçirildiğinde kullanılan tür.|

### <a name="public-classes"></a>Genel Sınıflar

|Adı|Açıklama|
|----------|-----------------|
|[CAtlMap::CPair Sınıf](#cpair_class)|Anahtar ve değer öğelerini içeren bir sınıf.|

### <a name="cpair-data-members"></a>CPair Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPair::m_key](#m_key)|Anahtar öğeyi depolayan veri üyesi.|
|[CPair::m_value](#m_value)|Değer öğesini depolayan veri üyesi.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlMap::CAtlMap](#catlmap)|Oluşturucu.|
|[CAtlMap::~CAtlMap](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlMap::AssertValid](#assertvalid)|Geçerli `CAtlMap` değilse, bir Assert neden bu yöntemi arayın.|
|[CAtlMap::DisableAutoRehash](#disableautorehash)|Nesnenin `CAtlMap` otomatik rehashing devre dışı kalmak için bu yöntemi arayın.|
|[CAtlMap::EnableAutoRehash](#enableautorehash)|Nesnenin `CAtlMap` otomatik olarak rehashing etkinleştirmek için bu yöntemi arayın.|
|[CAtlMap::GetAt](#getat)|Öğeyi haritada belirli bir konumda döndürmek için bu yöntemi çağırın.|
|[CAtlMap::GetCount](#getcount)|Haritadaki öğe sayısını almak için bu yöntemi arayın.|
|[CAtlMap::GetHashTableSize](#gethashtablesize)|Haritanın karma tablosundaki kutu sayısını belirlemek için bu yöntemi arayın.|
|[CAtlMap::GetKeyAt](#getkeyat)|`CAtlMap` Nesnede verilen konumda depolanan anahtarı almak için bu yöntemi arayın.|
|[CAtlMap::GetNext](#getnext)|Nesnede depolanan sonraki öğe çiftine işaretçi `CAtlMap` almak için bu yöntemi çağırın.|
|[CAtlMap::GetNextAssoc](#getnextassoc)|Yinelenmenin bir sonraki öğesini alır.|
|[CAtlMap::GetNextKey](#getnextkey)|`CAtlMap` Nesneden sonraki anahtarı almak için bu yöntemi arayın.|
|[CAtlMap::GetNextValue](#getnextvalue)|`CAtlMap` Nesneden sonraki değeri almak için bu yöntemi arayın.|
|[CAtlMap::GetStartPosition](#getstartposition)|Bir harita yinelemebaşlatmak için bu yöntemi arayın.|
|[CAtlMap::GetValueAt](#getvalueat)|`CAtlMap` Nesnede belirli bir konumda depolanan değeri almak için bu yöntemi arayın.|
|[CAtlMap::InitHashTable](#inithashtable)|Karma tabloyu başlatmak için bu yöntemi arayın.|
|[CAtlMap::Boş](#isempty)|Boş bir harita nesnesini sınamak için bu yöntemi çağırın.|
|[CAtlMap::Arama](#lookup)|`CAtlMap` Nesnedeki anahtarları veya değerleri aramak için bu yöntemi arayın.|
|[CAtlMap::Rehash](#rehash)|Nesneyi yeniden haşlamak `CAtlMap` için bu yöntemi çağırın.|
|[CAtlMap::RemoveAll](#removeall)|`CAtlMap` Nesneden tüm öğeleri kaldırmak için bu yöntemi arayın.|
|[CAtlMap::RemoveAtPos](#removeatpos)|Nesnede verilen konumdaki öğeyi kaldırmak `CAtlMap` için bu yöntemi çağırın.|
|[CAtlMap::RemoveKey](#removekey)|Anahtar verilen `CAtlMap` bir öğeyi nesneden kaldırmak için bu yöntemi çağırın.|
|[CAtlMap::SetAt](#setat)|Eşmeye bir öğe çifti eklemek için bu yöntemi çağırın.|
|[CAtlMap::SetOptimalLoad](#setoptimalload)|`CAtlMap` Nesnenin en uygun yükünü ayarlamak için bu yöntemi arayın.|
|[CAtlMap::SetValueAt](#setvalueat)|Nesnede belirli bir konumda depolanan değeri değiştirmek `CAtlMap` için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlMap::operatör\[\]](catlmap-class.md#operator_at)|Yerine yeni bir öğe ekler `CAtlMap`veya ekler.|

## <a name="remarks"></a>Açıklamalar

`CAtlMap`sıralanmamış bir anahtar öğe dizisini ve ilişkili değerlerini yöneten, belirli bir türdeki eşleme dizisi için destek sağlar. Öğeler (anahtar ve değerden oluşan) bir karma algoritma kullanılarak depolanır ve büyük miktarda verinin verimli bir şekilde depolanmasına ve alınmasına olanak sağlar.

*KTraits* ve *VTraits* parametreleri öğeleri kopyalamak veya taşımak için gerekli herhangi bir ek kod içeren özellikler sınıflarıdır.

CRBMap `CAtlMap` sınıfı tarafından [CRBMap](../../atl/reference/crbmap-class.md) bir alternatif sunulmaktadır. `CRBMap`anahtar/değer çiftlerini de saklar, ancak farklı performans özellikleri sergiler. Bir öğeyi eklemek, bir anahtarı aramak veya bir `CRBMap` nesneden bir anahtarı silmek için alınan süre, *n* öğe sayısının olduğu sipariş *günlüğü(n)* şeklindedir. Çünkü, `CAtlMap`bu işlemlerin tümü genellikle sabit bir zaman alır, ancak en kötü durum senaryoları *n*. Bu nedenle, tipik `CAtlMap` bir durumda, daha hızlıdır.

Depolanan öğeler `CRBMap` `CAtlMap` arasında diğer fark ve zaman depolanan öğeler arasında belirgin hale gelir. Bir `CRBMap`, öğeleri sıralanmış bir sırada ziyaret edilir. Bir `CAtlMap`, öğeler sıralı değildir ve hiçbir sipariş çıkarılabilir.

Az sayıda öğenin depolanmış olması gerektiğinde, bunun yerine [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfını kullanmayı düşünün.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="catlmapassertvalid"></a><a name="assertvalid"></a>CAtlMap::AssertValid

`CAtlMap` Nesne geçerli değilse, bir Assert neden bu yöntemi arayın.

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarda, `CAtlMap` nesne geçerli değilse, bu yöntem bir Assert neden olur.

### <a name="example"></a>Örnek

[CAtlMap örneğine bakın:CAtlMap](#catlmap).

## <a name="catlmapcatlmap"></a><a name="catlmap"></a>CAtlMap::CAtlMap

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
Depolanan öğelere işaretçiler sağlayan kutu sayısı. Kutularla ilgili bir açıklama için bu konunun ilerleyen yerlerine bakın.

*fOptimalLoad*<br/>
En uygun yük oranı.

*fLoThreshold*<br/>
Yük oranı için alt eşik.

*fHiThreshold*<br/>
Yük oranı için üst eşik.

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

`CAtlMap`anahtar üzerinde karma algoritmakullanarak önce bir dizin oluşturarak depolanan tüm öğeleri başvurur. Bu dizin, depolanan öğelere işaretçi içeren bir "bin" başvurur. Depo gözü zaten kullanılıyorsa, sonraki öğelere erişmek için bağlantılı bir liste oluşturulur. Bir listeyi geçiş yapmak, doğru öğeye doğrudan erişmekten daha yavaştır ve bu nedenle harita yapısının depolama gereksinimlerini performansa göre dengelemesi gerekir. Varsayılan parametreler çoğu durumda iyi sonuçlar vermek için seçilmiştir.

Yük oranı, kutu sayısının harita nesnesinde depolanan öğe sayısına oranıdır. Harita yapısı yeniden hesaplandığında, gerekli sayaç sayısını hesaplamak için *fOptimalLoad* parametre değeri kullanılır. Bu değer [CAtlMap::SetOptimalLoad](#setoptimalload) yöntemi kullanılarak değiştirilebilir.

*fLoThreshold* parametresi, haritanın en uygun boyutunu `CAtlMap` yeniden hesaplamadan önce yük oranının ulaşabileceği daha düşük değerdir.

*fHiThreshold* parametresi, nesne haritanın en uygun `CAtlMap` boyutunu yeniden hesaplamadan önce yük oranının ulaşabileceği üst değerdir.

Bu yeniden hesaplama işlemi (rehashing olarak da bilinir) varsayılan olarak etkinleştirilir. Bu işlemi devre dışı kakmak istiyorsanız, belki de aynı anda çok fazla veri girerken, [CAtlMap::DisableAutoRehash](#disableautorehash) yöntemini arayın. CAtlMap ile yeniden [etkinleştirin::EnableAutoRehash](#enableautorehash) yöntemi.

*nBlockSize* parametresi, yeni bir öğe gerektiğinde ayrılan bellek miktarının ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır.

Herhangi bir veri depolanabilir önce, CAtlMap bir çağrı ile karma tablo başlatılması [gerekir::InitHashTable](#inithashtable).

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]

## <a name="catlmapcatlmap"></a><a name="dtor"></a>CAtlMap::~CAtlMap

Yıkıcı.

```
~CAtlMap() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest sağlar.

## <a name="catlmapcpair-class"></a><a name="cpair_class"></a>CAtlMap::CPair Sınıf

Anahtar ve değer öğelerini içeren bir sınıf.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Açıklamalar

Bu sınıf [CAtlMap::GetNext](#getnext) ve [CAtlMap::Haritalama](#lookup) yapısında depolanan anahtar ve değer öğelerine erişmek için arama yöntemleri yle kullanılır.

## <a name="catlmapdisableautorehash"></a><a name="disableautorehash"></a>CAtlMap::DisableAutoRehash

Nesnenin `CAtlMap` otomatik rehashing devre dışı kalmak için bu yöntemi arayın.

```cpp
void DisableAutoRehash() throw();
```

### <a name="remarks"></a>Açıklamalar

Otomatik yeniden hashing etkinleştirildiğinde (varsayılan olarak olduğu gibi), yük değeri (depo kutusu sayısının dizideki depolanan eleman sayısına oranı) haritanın oluşturulduğu anda belirtilen maksimum veya minimum değerleri aşarsa, karma tablodaki depo kutusu sayısı otomatik olarak yeniden hesaplanır.

`DisableAutoRehash`eşmeye aynı anda çok sayıda öğe eklence en kullanışlıdır. Sınırlar her aşıldığında yeniden elemanlandırma işlemini tetiklemek yerine, çağırmak, `DisableAutoRehash`öğeleri eklemek ve son olarak [CAtlMap'i aramak daha verimlidir::EnableAutoRehash](#enableautorehash).

## <a name="catlmapenableautorehash"></a><a name="enableautorehash"></a>CAtlMap::EnableAutoRehash

Nesnenin `CAtlMap` otomatik olarak rehashing etkinleştirmek için bu yöntemi arayın.

```cpp
void EnableAutoRehash() throw();
```

### <a name="remarks"></a>Açıklamalar

Otomatik yeniden hashing etkinleştirildiğinde (varsayılan olarak olduğu gibi), yük değeri (depo kutusu sayısının dizideki depolanan eleman sayısına oranı) haritanın oluşturulduğu anda belirtilen maksimum veya minimum değerleri aşarsa, karma tablodaki depo kutusu sayısı otomatik olarak yeniden hesaplanır.

`EnableAutoRefresh`en sık CAtlMap bir çağrı dan sonra [kullanılır::DisableAutoRehash](#disableautorehash).

## <a name="catlmapgetat"></a><a name="getat"></a>CAtlMap::GetAt

Öğeyi haritada belirli bir konumda döndürmek için bu yöntemi çağırın.

```cpp
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Pozisyon sayacı, CAtlMap önceki bir çağrı ile [döndürülen::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

*anahtar*<br/>
Haritanın anahtarının türünü belirten şablon parametresi.

*value*<br/>
Eşin değerinin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Eşönünde depolanan geçerli anahtar/değer öğeleri çiftine bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, *pos* NULL'a eşitse bir tasnif hatası oluşur.

## <a name="catlmapgetcount"></a><a name="getcount"></a>CAtlMap::GetCount

Haritadaki öğe sayısını almak için bu yöntemi arayın.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Harita nesnesindeki öğe sayısını döndürür. Tek bir öğe anahtar/değer çiftidir.

### <a name="example"></a>Örnek

[CAtlMap örneğine bakın:CAtlMap](#catlmap).

## <a name="catlmapgethashtablesize"></a><a name="gethashtablesize"></a>CAtlMap::GetHashTableSize

Haritanın karma tablosundaki kutu sayısını belirlemek için bu yöntemi arayın.

```
UINT GetHashTableSize() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Karma tablodaki kutu sayısını verir. Bkz. [CAtlMap::CAtlMap](#catlmap) bir açıklama için.

## <a name="catlmapgetkeyat"></a><a name="getkeyat"></a>CAtlMap::GetKeyAt

`CAtlMap` Nesnede verilen konumda depolanan anahtarı almak için bu yöntemi arayın.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Pozisyon sayacı, CAtlMap önceki bir çağrı ile [döndürülen::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Dönüş Değeri

Nesnede verilen konumda depolanan anahtara `CAtlMap` bir başvuru verir.

### <a name="example"></a>Örnek

[CAtlMap örneğine bakın:CAtlMap](#catlmap).

## <a name="catlmapgetnext"></a><a name="getnext"></a>CAtlMap::GetNext

Nesnede depolanan sonraki öğe çiftine işaretçi `CAtlMap` almak için bu yöntemi çağırın.

```
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Pozisyon sayacı, CAtlMap önceki bir çağrı ile [döndürülen::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Dönüş Değeri

Eşönünde depolanan bir sonraki anahtar/değer öğeleri çiftine bir işaretçi döndürür. *Pos* konum sayacı her çağrıdan sonra güncelleştirilir. Alınan öğe haritadaki son öğeyse, *pos* NULL olarak ayarlanır.

## <a name="catlmapgetnextassoc"></a><a name="getnextassoc"></a>CAtlMap::GetNextAssoc

Yinelenmenin bir sonraki öğesini alır.

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Pozisyon sayacı, CAtlMap önceki bir çağrı ile [döndürülen::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

*anahtar*<br/>
Haritanın anahtarının türünü belirten şablon parametresi.

*value*<br/>
Eşin değerinin türünü belirten şablon parametresi.

### <a name="remarks"></a>Açıklamalar

*Pos* konum sayacı her çağrıdan sonra güncelleştirilir. Alınan öğe haritadaki son öğeyse, *pos* NULL olarak ayarlanır.

## <a name="catlmapgetnextkey"></a><a name="getnextkey"></a>CAtlMap::GetNextKey

`CAtlMap` Nesneden sonraki anahtarı almak için bu yöntemi arayın.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Pozisyon sayacı, CAtlMap önceki bir çağrı ile [döndürülen::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Dönüş Değeri

Haritadaki bir sonraki anahtara bir başvuru verir.

### <a name="remarks"></a>Açıklamalar

Güncel konum sayacını, *pos'u*güncelleştirir. Haritada başka giriş yoksa, konum sayacı NULL olarak ayarlanır.

## <a name="catlmapgetnextvalue"></a><a name="getnextvalue"></a>CAtlMap::GetNextValue

`CAtlMap` Nesneden sonraki değeri almak için bu yöntemi arayın.

```
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Pozisyon sayacı, CAtlMap önceki bir çağrı ile [döndürülen::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Dönüş Değeri

Haritadaki bir sonraki değere başvuru verir.

### <a name="remarks"></a>Açıklamalar

Güncel konum sayacını, *pos'u*güncelleştirir. Haritada başka giriş yoksa, konum sayacı NULL olarak ayarlanır.

### <a name="example"></a>Örnek

[CAtlMap örneğine bakın:CAtlMap](#catlmap).

## <a name="catlmapgetstartposition"></a><a name="getstartposition"></a>CAtlMap::GetStartPosition

Bir harita yinelemebaşlatmak için bu yöntemi arayın.

```
POSITION GetStartPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başlangıç konumunu döndürür veya harita boşsa NULL döndürülür.

### <a name="remarks"></a>Açıklamalar

`GetNextAssoc` Yönteme geçirilebilen bir KONUM değeri döndürerek bir harita yinelemebaşlatmak için bu yöntemi arayın.

> [!NOTE]
> Yineleme sırası öngörülebilir değildir

### <a name="example"></a>Örnek

[CAtlMap örneğine bakın:CAtlMap](#catlmap).

## <a name="catlmapgetvalueat"></a><a name="getvalueat"></a>CAtlMap::GetValueAt

`CAtlMap` Nesnede belirli bir konumda depolanan değeri almak için bu yöntemi arayın.

```
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Pozisyon sayacı, CAtlMap önceki bir çağrı ile [döndürülen::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="return-value"></a>Dönüş Değeri

`CAtlMap` Nesnede verilen konumda depolanan değere bir başvuru verir.

## <a name="catlmapinithashtable"></a><a name="inithashtable"></a>CAtlMap::InitHashTable

Karma tabloyu başlatmak için bu yöntemi arayın.

```
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```

### <a name="parameters"></a>Parametreler

*nBins*<br/>
Karma tablo tarafından kullanılan kutu sayısı. Bkz. [CAtlMap::CAtlMap](#catlmap) bir açıklama için.

*bAllocNow*<br/>
Belleğin ayrılması gereken bayrak göstergesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı başlatmada TRUE'yı döndürür, hatada FALSE.

### <a name="remarks"></a>Açıklamalar

`InitHashTable`herhangi bir öğe karma tabloda depolanan önce çağrılmalıdır.  Bu yöntem açıkça çağrılmazsa, `CAtlMap` oluşturucu tarafından belirtilen depo sayısı kullanılarak ilk kez bir öğe eklenmede otomatik olarak çağrılacaktır.  Aksi takdirde, harita *nBins* parametresi tarafından belirtilen yeni depo kutusu sayısı kullanılarak başharfe çevrilir.

*bAllocNow* parametresi yanlışsa, karma tablonun gerektirdiği bellek ilk gerekli olana kadar ayrılmaz. Bu, haritanın kullanılıp kullanılacılacılamışolmasının belirsiz olduğuna gÜ

### <a name="example"></a>Örnek

[CAtlMap örneğine bakın:CAtlMap](#catlmap).

## <a name="catlmapisempty"></a><a name="isempty"></a>CAtlMap::Boş

Boş bir harita nesnesini sınamak için bu yöntemi çağırın.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Harita boşsa TRUE döndürür, aksi takdirde FALSE.

## <a name="catlmapkinargtype"></a><a name="kinargtype"></a>CAtlMap::KINARGTYPE

Bir anahtar giriş bağımsız değişkeni olarak geçirildiğinde kullanılan tür.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="catlmapkoutargtype"></a><a name="koutargtype"></a>CAtlMap::KOUTARGTYPE

Bir anahtar çıktı bağımsız değişkeni olarak döndürüldüğünde kullanılan tür.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="catlmaplookup"></a><a name="lookup"></a>CAtlMap::Arama

`CAtlMap` Nesnedeki anahtarları veya değerleri aramak için bu yöntemi arayın.

```
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğeyi tanımlayan anahtarı belirtir.

*value*<br/>
Aradeğerini alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Yöntemin ilk biçimi anahtar bulunursa doğru döndürür, aksi takdirde yanlış. İkinci ve üçüncü formlar CAtlMap için aramalar için bir konum olarak kullanılabilecek bir [CPair](#cpair_class) için bir işaretçi döndürür::GetNext ve benzeri. [CAtlMap::GetNext](#getnext)

### <a name="remarks"></a>Açıklamalar

`Lookup`verilen anahtar parametresi ile tam olarak eşleşen bir anahtar içeren eş öğeyi hızla bulmak için karma algoritması kullanır.

## <a name="catlmapoperator-"></a><a name="operator_at"></a>CAtlMap::operatör\[\]

Yerine yeni bir öğe ekler `CAtlMap`veya ekler.

```
V& operator[](kinargtype key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Öğenin eklemek veya değiştirmek için anahtar.

### <a name="return-value"></a>Dönüş Değeri

Verilen anahtarla ilişkili değere bir başvuru verir.

### <a name="example"></a>Örnek

Anahtar zaten varsa, öğe değiştirilir. Anahtar yoksa, yeni bir öğe eklenir. [CAtlMap örneğine bakın:CAtlMap](#catlmap).

## <a name="catlmaprehash"></a><a name="rehash"></a>CAtlMap::Rehash

Nesneyi yeniden haşlamak `CAtlMap` için bu yöntemi çağırın.

```cpp
void Rehash(UINT nBins = 0);
```

### <a name="parameters"></a>Parametreler

*nBins*<br/>
Karma tabloda kullanılacak yeni kutu sayısı. Bkz. [CAtlMap::CAtlMap](#catlmap) bir açıklama için.

### <a name="remarks"></a>Açıklamalar

*nBins* 0 ise, `CAtlMap` haritadaki eleman sayısını ve en uygun yük ayarını temel alan makul bir sayı hesaplar. Normalde rehashing işlemi otomatiktir, ancak [CAtlMap::DisableAutoRehash](#disableautorehash) çağrıldıysa, bu yöntem gerekli yeniden boyutlandırma gerçekleştirecektir.

## <a name="catlmapremoveall"></a><a name="removeall"></a>CAtlMap::RemoveAll

`CAtlMap` Nesneden tüm öğeleri kaldırmak için bu yöntemi arayın.

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Öğeleri depolamak `CAtlMap` için kullanılan belleği serbest, nesneyi temizler.

## <a name="catlmapremoveatpos"></a><a name="removeatpos"></a>CAtlMap::RemoveAtPos

Nesnede verilen konumdaki öğeyi kaldırmak `CAtlMap` için bu yöntemi çağırın.

```cpp
void RemoveAtPos(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Pozisyon sayacı, CAtlMap önceki bir çağrı ile [döndürülen::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

### <a name="remarks"></a>Açıklamalar

Belirtilen konumda depolanan anahtar/değer çiftini kaldırır. Öğeyi depolamak için kullanılan bellek serbest bırakılır. *POS* tarafından başvurulan KONUM geçersiz hale gelir ve haritadaki diğer öğelerin KONUMU geçerli kalırken, aynı sırayı korumak zorunda kalmazlar.

## <a name="catlmapremovekey"></a><a name="removekey"></a>CAtlMap::RemoveKey

Anahtar verilen `CAtlMap` bir öğeyi nesneden kaldırmak için bu yöntemi çağırın.

```
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kaldırmak istediğiniz öğe çiftine karşılık gelen anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunur ve kaldırılırsa TRUE döndürür, hata false üzerinde FALSE.

### <a name="example"></a>Örnek

[CAtlMap örneğine bakın:CAtlMap](#catlmap).

## <a name="catlmapsetat"></a><a name="setat"></a>CAtlMap::SetAt

Eşmeye bir öğe çifti eklemek için bu yöntemi çağırın.

```
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
`CAtlMap` Nesneye eklenecek anahtar değer.

*value*<br/>
`CAtlMap` Nesneye eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

Nesnedeki anahtar/değer öğesi çiftinin `CAtlMap` konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

`SetAt`eşleşen bir anahtar bulunursa varolan bir öğenin yerini alır. Anahtar bulunamazsa, yeni bir anahtar/değer çifti oluşturulur.

## <a name="catlmapsetoptimalload"></a><a name="setoptimalload"></a>CAtlMap::SetOptimalLoad

`CAtlMap` Nesnenin en uygun yükünü ayarlamak için bu yöntemi arayın.

```cpp
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```

### <a name="parameters"></a>Parametreler

*fOptimalLoad*<br/>
En uygun yük oranı.

*fLoThreshold*<br/>
Yük oranı için alt eşik.

*fHiThreshold*<br/>
Yük oranı için üst eşik.

*bRehashNow*<br/>
Karma tablonun yeniden hesaplanıp hesaplanmaması gerektiğini belirten bayrak.

### <a name="remarks"></a>Açıklamalar

Bu `CAtlMap` yöntem, nesne için en uygun yük değerini yeniden tanımlar. Çeşitli parametrelerin tartışılması için [CAtlMap::CAtlMap'e](#catlmap) bakın. *bRehashNow* doğruysa ve eleman sayısı minimum ve maksimum değerlerin dışındaysa, karma tablo yeniden hesaplanır.

## <a name="catlmapsetvalueat"></a><a name="setvalueat"></a>CAtlMap::SetValueAt

Nesnede belirli bir konumda depolanan değeri değiştirmek `CAtlMap` için bu yöntemi çağırın.

```cpp
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Pozisyon sayacı, CAtlMap önceki bir çağrı ile [döndürülen::GetNextAssoc](#getnextassoc) veya [CAtlMap::GetStartPosition](#getstartposition).

*value*<br/>
`CAtlMap` Nesneye eklenecek değer.

### <a name="remarks"></a>Açıklamalar

Nesnede verilen konumda depolanan değer `CAtlMap` öğesini değiştirir.

## <a name="catlmapvinargtype"></a><a name="vinargtype"></a>CAtlMap::VINARGTYPE

Bir değer girdi bağımsız değişkeni olarak geçildiğinde kullanılan tür.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="catlmapvoutargtype"></a><a name="voutargtype"></a>CAtlMap::VOUTARGTYPE

Bir değer çıktı bağımsız değişkeni olarak geçirildiğinde kullanılan tür.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="catlmapcpairm_key"></a><a name="m_key"></a>CAtlMap::CPair::m_key

Anahtar öğeyi depolayan veri üyesi.

```
const K m_key;
```

### <a name="parameters"></a>Parametreler

*Kahraman*<br/>
Anahtar öğe türü.

## <a name="catlmapcpairm_value"></a><a name="m_value"></a>CAtlMap::CPair::m_value

Değer öğesini depolayan veri üyesi.

```
V  m_value;
```

### <a name="parameters"></a>Parametreler

*V*<br/>
Değer öğesi türü.

## <a name="see-also"></a>Ayrıca bkz.

[Marquee Örnek](../../overview/visual-cpp-samples.md)<br/>
[GüncellemePV Örneği](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
