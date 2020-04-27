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
ms.openlocfilehash: b79e6cbd796569e6ba11c96158099de6c30b310a
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168065"
---
# <a name="catlmap-class"></a>CAtlMap Sınıfı

Bu sınıf bir harita nesnesi oluşturmak ve yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CAtlMap
```

### <a name="parameters"></a>Parametreler

*Ek*<br/>
Anahtar öğe türü.

*Yönetim*<br/>
Değer öğesi türü.

*Knitelikler*<br/>
Anahtar öğelerini kopyalamak veya taşımak için kullanılan kod. Daha fazla ayrıntı için bkz. [Celementnitelikler sınıfı](../../atl/reference/celementtraits-class.md) .

*Sanal nitelikler*<br/>
Değer öğelerini kopyalamak veya taşımak için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Adı|Açıklama|
|----------|-----------------|
|[CAtlMap:: KINARGTYPE](#kinargtype)|Giriş bağımsız değişkeni olarak bir anahtar geçirildiğinde kullanılan tür|
|[CAtlMap:: KOUTARGTYPE](#koutargtype)|Bir anahtar, çıkış bağımsız değişkeni olarak döndürüldüğünde kullanılan tür.|
|[CAtlMap:: VINARGTYPE](#vinargtype)|Giriş bağımsız değişkeni olarak bir değer geçirildiğinde kullanılan tür.|
|[CAtlMap:: VOUTARGTYPE](#voutargtype)|Bir değer çıkış bağımsız değişkeni olarak geçirildiğinde kullanılan tür.|

### <a name="public-classes"></a>Ortak sınıflar

|Adı|Açıklama|
|----------|-----------------|
|[CAtlMap:: CPair sınıfı](#cpair_class)|Anahtar ve değer öğelerini içeren bir sınıf.|

### <a name="cpair-data-members"></a>CPair veri üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CPair:: m_key](#m_key)|Anahtar öğesini depolayan veri üyesi.|
|[CPair:: m_value](#m_value)|Değer öğesini depolayan veri üyesi.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CAtlMap:: CAtlMap](#catlmap)|Oluşturucu.|
|[CAtlMap:: ~ CAtlMap](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlMap:: AssertValid](#assertvalid)|Geçerli değilse, `CAtlMap` bir onay sağlamak için bu yöntemi çağırın.|
|[CAtlMap::D Isableoto rehash](#disableautorehash)|`CAtlMap` Nesnenin otomatik yeniden karmasını devre dışı bırakmak için bu yöntemi çağırın.|
|[CAtlMap:: Enableoto rehash](#enableautorehash)|`CAtlMap` Nesnenin otomatik yeniden karma özelliğini etkinleştirmek için bu yöntemi çağırın.|
|[CAtlMap:: GetAt](#getat)|Öğeyi haritada belirtilen bir konumda döndürmek için bu yöntemi çağırın.|
|[CAtlMap:: GetCount](#getcount)|Eşlemedeki öğelerin sayısını almak için bu yöntemi çağırın.|
|[CAtlMap:: GetHashTableSize](#gethashtablesize)|Haritanın karma tablosundaki sepetler sayısını öğrenmek için bu yöntemi çağırın.|
|[CAtlMap:: GetKeyAt](#getkeyat)|`CAtlMap` Nesnede verilen konumda depolanan anahtarı almak için bu yöntemi çağırın.|
|[CAtlMap:: GetNext](#getnext)|`CAtlMap` Nesnede depolanan bir sonraki öğe çiftiyle bir işaretçi almak için bu yöntemi çağırın.|
|[CAtlMap:: GetNextAssoc](#getnextassoc)|Yineleme için bir sonraki öğeyi alır.|
|[CAtlMap:: GetNextKey](#getnextkey)|`CAtlMap` Nesnesinden sonraki anahtarı almak için bu yöntemi çağırın.|
|[CAtlMap:: GetNextValue](#getnextvalue)|`CAtlMap` Nesnesinden bir sonraki değeri almak için bu yöntemi çağırın.|
|[CAtlMap:: GetStartPosition](#getstartposition)|Harita yinelemesi başlatmak için bu yöntemi çağırın.|
|[CAtlMap:: Getvaluyemek](#getvalueat)|`CAtlMap` Nesnede belirli bir konumda depolanan değeri almak için bu yöntemi çağırın.|
|[CAtlMap:: InitHashTable](#inithashtable)|Karma tabloyu başlatmak için bu yöntemi çağırın.|
|[CAtlMap:: IsEmpty](#isempty)|Boş bir harita nesnesi için test etmek üzere bu yöntemi çağırın.|
|[CAtlMap:: Lookup](#lookup)|`CAtlMap` Nesne içindeki anahtarları veya değerleri aramak için bu yöntemi çağırın.|
|[CAtlMap:: rehash](#rehash)|`CAtlMap` Nesneyi yeniden sağlaması için bu yöntemi çağırın.|
|[CAtlMap:: RemoveAll](#removeall)|`CAtlMap` Nesnesinden tüm öğeleri kaldırmak için bu yöntemi çağırın.|
|[CAtlMap:: RemoveAtPos](#removeatpos)|`CAtlMap` Nesnede verilen konumdaki öğeyi kaldırmak için bu yöntemi çağırın.|
|[CAtlMap:: RemoveKey](#removekey)|Bu yöntemi, anahtar verildiğinde `CAtlMap` nesnesinden bir öğeyi kaldırmak için çağırın.|
|[CAtlMap:: SetAt](#setat)|Haritaya bir öğe çifti eklemek için bu yöntemi çağırın.|
|[CAtlMap:: SetOptimalLoad](#setoptimalload)|`CAtlMap` Nesnenin en iyi yükünü ayarlamak için bu yöntemi çağırın.|
|[CAtlMap:: Setvaluyemek](#setvalueat)|`CAtlMap` Nesnedeki belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CAtlMap:: işleci\[\]](catlmap-class.md#operator_at)|Öğesine yeni bir öğesi koyar veya öğesine ekler `CAtlMap`.|

## <a name="remarks"></a>Açıklamalar

`CAtlMap`verilen herhangi bir türde bir eşleme dizisi için destek sağlar ve sıralanmamış bir anahtar öğesi dizisi ve bunlarla ilişkili değerleri yönetebilir. Öğeler (bir anahtar ve bir değerden oluşan), karma algoritma kullanılarak depolanır, bu da büyük miktarda verinin etkin bir şekilde saklanmasını ve alınmasını sağlar.

*Knitelikler* ve *vnitelikler* parametreleri, öğeleri kopyalamak veya taşımak için gereken ek kodu içeren nitelikler sınıflarıdır.

Bir alternatifi `CAtlMap` [CRBMap](../../atl/reference/crbmap-class.md) sınıfı tarafından sunulur. `CRBMap`Ayrıca anahtar/değer çiftlerini depolar, ancak farklı performans özellikleri sergiler. Bir öğeyi eklemek, anahtar aramak veya bir `CRBMap` nesneden bir anahtarı silmek için geçen süre *(n)*, burada *n* öğe sayısıdır. İçin `CAtlMap`, bu işlemlerin hepsi genellikle sabit bir zaman alır, ancak en kötü durum senaryoları *n*sırası olabilir. Bu nedenle, tipik bir durumda `CAtlMap` daha hızlıdır.

Ve `CRBMap` `CAtlMap` arasındaki diğer fark, saklı öğeler arasında yineleme yaparken görünür hale gelir. Bir `CRBMap`içinde, öğeleri sıralanmış bir sırada ziyaret edilir. Bir `CAtlMap`içinde, öğeler sıralı değildir ve hiçbir sıra çıkarılamayabilir.

Az sayıda öğe depolanması gerektiğinde, bunun yerine [CSimpleMap](../../atl/reference/csimplemap-class.md) sınıfını kullanmayı göz önünde bulundurun.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="catlmapassertvalid"></a><a name="assertvalid"></a>CAtlMap:: AssertValid

`CAtlMap` Nesne geçerli değilse bir onay sağlamak için bu yöntemi çağırın.

```cpp
void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, `CAtlMap` nesne geçerli değilse bu yöntem bir onaylama yapılmasına neden olur.

### <a name="example"></a>Örnek

[CAtlMap:: CAtlMap](#catlmap)örneğine bakın.

## <a name="catlmapcatlmap"></a><a name="catlmap"></a>CAtlMap:: CAtlMap

Oluşturucu.

```cpp
CAtlMap(
    UINT nBins = 17,
    float fOptimalLoad = 0.75f,
    float fLoThreshold = 0.25f,
    float fHiThreshold = 2.25f,
    UINT nBlockSize = 10) throw ();
```

### <a name="parameters"></a>Parametreler

*Nbıns*<br/>
Saklı öğelere işaretçiler sağlayan bölme sayısı. Sepetler hakkında açıklama için bu konunun devamındaki açıklamaları bölümüne bakın.

*Foptimize Malload*<br/>
En iyi yükleme oranı.

*fLoThreshold*<br/>
Yük oranının alt eşiği.

*fHiThreshold*<br/>
Yük oranının üst eşiği.

*nBlockSize*<br/>
Blok boyutu.

### <a name="remarks"></a>Açıklamalar

`CAtlMap`önce anahtar üzerinde bir karma algoritması kullanarak bir dizin oluşturarak, depolanan tüm öğelerine başvurur. Bu dizin, saklı öğelerin işaretçisini içeren bir "bin" öğesine başvurur. Bin zaten kullanımda ise, sonraki öğelere erişmek için bağlantılı liste oluşturulur. Bir listenin geçiş işlemi, doğru öğeye doğrudan erişmekten daha yavaştır ve bu nedenle eşleme yapısının, depolama gereksinimlerini performansa karşı dengelenmesi gerekir. Çoğu durumda iyi sonuçlar vermek için varsayılan parametreler seçilmiştir.

Yük oranı, harita nesnesinde depolanan öğe sayısına bölme sayısının oranıdır. Eşleme yapısı yeniden hesaplandığında, gerekli olan sepetler sayısını hesaplamak için *Foptimize Malload* parametre değeri kullanılacaktır. Bu değer, [CAtlMap:: SetOptimalLoad](#setoptimalload) yöntemi kullanılarak değiştirilebilir.

*FLoThreshold* parametresi, eşlemenin en uygun boyutunu yeniden hesaplamadan önce `CAtlMap` yük oranının ulaşabilmesi için düşük değerdir.

*FHiThreshold* parametresi, `CAtlMap` nesne haritanın en iyi boyutunu yeniden hesaplamadan önce yük oranının ulaşabileceği üst değerdir.

Bu yeniden hesaplama işlemi (yeniden karma olarak bilinir) varsayılan olarak etkindir. Tek seferde çok fazla veri girerken bu işlemi devre dışı bırakmak istiyorsanız, [CAtlMap::D Isableoto rehash](#disableautorehash) metodunu çağırın. [CAtlMap:: Enableoto rehash](#enableautorehash) yöntemiyle yeniden etkinleştirin.

*NBlockSize* parametresi, yeni bir öğe gerektiğinde ayrılan bellek miktarının bir ölçüsüdür. Daha büyük blok boyutları, bellek ayırma yordamlarına yapılan çağrıları azaltır, ancak daha fazla kaynak kullanır.

Herhangi bir veri depolanmadan önce, bir [CAtlMap:: InitHashTable](#inithashtable)çağrısıyla karma tablo başlatması gerekir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#72](../../atl/codesnippet/cpp/catlmap-class_1.cpp)]

## <a name="catlmapcatlmap"></a><a name="dtor"></a>CAtlMap:: ~ CAtlMap

Yok edicisi.

```cpp
~CAtlMap() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest bırakır.

## <a name="catlmapcpair-class"></a><a name="cpair_class"></a>CAtlMap:: CPair sınıfı

Anahtar ve değer öğelerini içeren bir sınıf.

```cpp
class CPair : public __POSITION
```

### <a name="remarks"></a>Açıklamalar

Bu sınıf, eşleme yapısında depolanan anahtar ve değer öğelerine erişmek için [CAtlMap:: GetNext](#getnext) ve [CAtlMap:: Lookup](#lookup) yöntemleri tarafından kullanılır.

## <a name="catlmapdisableautorehash"></a><a name="disableautorehash"></a>CAtlMap::D Isableoto rehash

`CAtlMap` Nesnenin otomatik yeniden karmasını devre dışı bırakmak için bu yöntemi çağırın.

```cpp
void DisableAutoRehash() throw();
```

### <a name="remarks"></a>Açıklamalar

Otomatik yeniden karma etkinleştirildiğinde (varsayılan olarak), yük değeri (dizide depolanan öğe sayısı için depo sayısı oranı), eşlemenin oluşturulduğu sırada belirtilen en büyük veya en küçük değerleri aşarsa karma tablodaki depo gözü sayısı otomatik olarak yeniden hesaplanır.

`DisableAutoRehash`tek seferde haritaya çok sayıda öğe eklendiğinde çok yararlı olur. Sınırlar her aşıldığında yeniden karma işlemi tetiklemenin yerine, çağrı `DisableAutoRehash`yapmak, öğeleri eklemek ve son olarak [CAtlMap:: Enableoto yeniden karmasını](#enableautorehash)çağırmak daha etkilidir.

## <a name="catlmapenableautorehash"></a><a name="enableautorehash"></a>CAtlMap:: Enableoto rehash

`CAtlMap` Nesnenin otomatik yeniden karma özelliğini etkinleştirmek için bu yöntemi çağırın.

```cpp
void EnableAutoRehash() throw();
```

### <a name="remarks"></a>Açıklamalar

Otomatik yeniden karma etkinleştirildiğinde (varsayılan olarak), yük değeri (dizide depolanan öğe sayısı için depo sayısı oranı), eşleme oluşturulduğu sırada belirtilen en büyük veya en küçük değerleri aşarsa, karma tablodaki bölme sayısı otomatik olarak yeniden hesaplanır.

`EnableAutoRefresh`en yaygın olarak, bir [CAtlMap::D Isableoto rehash](#disableautorehash)çağrısından sonra kullanılır.

## <a name="catlmapgetat"></a><a name="getat"></a>CAtlMap:: GetAt

Öğeyi haritada belirtilen bir konumda döndürmek için bu yöntemi çağırın.

```cpp
void GetAt(
    POSITION pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;

CPair* GetAt(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum sayacı, bir önceki [CAtlMap:: GetNextAssoc](#getnextassoc) veya [CAtlMap:: GetStartPosition](#getstartposition)çağrısı tarafından döndürüldü.

*anahtar*<br/>
Harita anahtarının türünü belirten şablon parametresi.

*value*<br/>
Harita değerinin türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Haritada depolanan anahtar/değer öğelerinin geçerli çiftine yönelik bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, *POS* null değerine eşitse bir onaylama hatası meydana gelir.

## <a name="catlmapgetcount"></a><a name="getcount"></a>CAtlMap:: GetCount

Eşlemedeki öğelerin sayısını almak için bu yöntemi çağırın.

```cpp
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Map nesnesindeki öğe sayısını döndürür. Tek bir öğe, anahtar/değer çiftidir.

### <a name="example"></a>Örnek

[CAtlMap:: CAtlMap](#catlmap)örneğine bakın.

## <a name="catlmapgethashtablesize"></a><a name="gethashtablesize"></a>CAtlMap:: GetHashTableSize

Haritanın karma tablosundaki sepetler sayısını öğrenmek için bu yöntemi çağırın.

```cpp
UINT GetHashTableSize() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Karma tablodaki bölme sayısını döndürür. Bir açıklama için bkz. [CAtlMap:: CAtlMap](#catlmap) .

## <a name="catlmapgetkeyat"></a><a name="getkeyat"></a>CAtlMap:: GetKeyAt

`CAtlMap` Nesnede verilen konumda depolanan anahtarı almak için bu yöntemi çağırın.

```cpp
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum sayacı, bir önceki [CAtlMap:: GetNextAssoc](#getnextassoc) veya [CAtlMap:: GetStartPosition](#getstartposition)çağrısı tarafından döndürüldü.

### <a name="return-value"></a>Dönüş Değeri

`CAtlMap` Nesnede verilen konumda depolanan anahtara bir başvuru döndürür.

### <a name="example"></a>Örnek

[CAtlMap:: CAtlMap](#catlmap)örneğine bakın.

## <a name="catlmapgetnext"></a><a name="getnext"></a>CAtlMap:: GetNext

`CAtlMap` Nesnede depolanan bir sonraki öğe çiftiyle bir işaretçi almak için bu yöntemi çağırın.

```cpp
CPair* GetNext(POSITION& pos) throw();
const CPair* GetNext(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum sayacı, bir önceki [CAtlMap:: GetNextAssoc](#getnextassoc) veya [CAtlMap:: GetStartPosition](#getstartposition)çağrısı tarafından döndürüldü.

### <a name="return-value"></a>Dönüş Değeri

Haritada depolanan anahtar/değer öğelerinin bir sonraki çiftine yönelik bir işaretçi döndürür. *POS* konum sayacı her çağrıdan sonra güncelleştirilir. Alınan öğe haritada son ise, *POS* null olarak ayarlanır.

## <a name="catlmapgetnextassoc"></a><a name="getnextassoc"></a>CAtlMap:: GetNextAssoc

Yineleme için bir sonraki öğeyi alır.

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum sayacı, bir önceki [CAtlMap:: GetNextAssoc](#getnextassoc) veya [CAtlMap:: GetStartPosition](#getstartposition)çağrısı tarafından döndürüldü.

*anahtar*<br/>
Harita anahtarının türünü belirten şablon parametresi.

*value*<br/>
Harita değerinin türünü belirten şablon parametresi.

### <a name="remarks"></a>Açıklamalar

*POS* konum sayacı her çağrıdan sonra güncelleştirilir. Alınan öğe haritada son ise, *POS* null olarak ayarlanır.

## <a name="catlmapgetnextkey"></a><a name="getnextkey"></a>CAtlMap:: GetNextKey

`CAtlMap` Nesnesinden sonraki anahtarı almak için bu yöntemi çağırın.

```cpp
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum sayacı, bir önceki [CAtlMap:: GetNextAssoc](#getnextassoc) veya [CAtlMap:: GetStartPosition](#getstartposition)çağrısı tarafından döndürüldü.

### <a name="return-value"></a>Dönüş Değeri

Eşlemedeki bir sonraki anahtara bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli pozisyon sayacını güncelleştirir, *POS*. Haritada daha fazla giriş yoksa, konum sayacı NULL olarak ayarlanır.

## <a name="catlmapgetnextvalue"></a><a name="getnextvalue"></a>CAtlMap:: GetNextValue

`CAtlMap` Nesnesinden bir sonraki değeri almak için bu yöntemi çağırın.

```cpp
V& GetNextValue(POSITION& pos) throw();
const V& GetNextValue(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum sayacı, bir önceki [CAtlMap:: GetNextAssoc](#getnextassoc) veya [CAtlMap:: GetStartPosition](#getstartposition)çağrısı tarafından döndürüldü.

### <a name="return-value"></a>Dönüş Değeri

Eşlemedeki bir sonraki değere bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli pozisyon sayacını güncelleştirir, *POS*. Haritada daha fazla giriş yoksa, konum sayacı NULL olarak ayarlanır.

### <a name="example"></a>Örnek

[CAtlMap:: CAtlMap](#catlmap)örneğine bakın.

## <a name="catlmapgetstartposition"></a><a name="getstartposition"></a>CAtlMap:: GetStartPosition

Harita yinelemesi başlatmak için bu yöntemi çağırın.

```cpp
POSITION GetStartPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başlangıç konumunu döndürür veya eşleme boşsa NULL değeri döndürülür.

### <a name="remarks"></a>Açıklamalar

`GetNextAssoc` Yönteme GEÇIRILEBILECEK bir konum değeri döndürerek eşleme yinelemesi başlatmak için bu yöntemi çağırın.

> [!NOTE]
> Yineleme sırası öngörülebilir değil

### <a name="example"></a>Örnek

[CAtlMap:: CAtlMap](#catlmap)örneğine bakın.

## <a name="catlmapgetvalueat"></a><a name="getvalueat"></a>CAtlMap:: Getvaluyemek

`CAtlMap` Nesnede belirli bir konumda depolanan değeri almak için bu yöntemi çağırın.

```cpp
V& GetValueAt(POSITION pos) throw();
const V& GetValueAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum sayacı, bir önceki [CAtlMap:: GetNextAssoc](#getnextassoc) veya [CAtlMap:: GetStartPosition](#getstartposition)çağrısı tarafından döndürüldü.

### <a name="return-value"></a>Dönüş Değeri

`CAtlMap` Nesnede verilen konumda depolanan değere bir başvuru döndürür.

## <a name="catlmapinithashtable"></a><a name="inithashtable"></a>CAtlMap:: InitHashTable

Karma tabloyu başlatmak için bu yöntemi çağırın.

```cpp
bool InitHashTable(
    UINT nBins,
    bool bAllocNow = true);
```

### <a name="parameters"></a>Parametreler

*Nbıns*<br/>
Karma tablo tarafından kullanılan bölme sayısı. Bir açıklama için bkz. [CAtlMap:: CAtlMap](#catlmap) .

*bAllocNow*<br/>
Bellek ayrıldığınızda bayrak göstergesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı başlatma sırasında TRUE, hatada FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

`InitHashTable`Karma tabloda herhangi bir öğe depolanmadan önce çağrılmalıdır.  Bu yöntem açıkça çağrılmaması halinde, `CAtlMap` Oluşturucu tarafından belirtilen bin sayısı kullanılarak bir öğe ilk kez eklendiğinde otomatik olarak çağrılır.  Aksi takdirde, eşleme, *nBins* parametresi tarafından belirtilen yeni bin sayısı kullanılarak başlatılır.

*BAllocNow* parametresi false ise, karma tablo için gereken bellek, ilk gerekene kadar ayrılmaz. Bu, eşlemenin kullanılacaksa emin olursa yararlı olabilir.

### <a name="example"></a>Örnek

[CAtlMap:: CAtlMap](#catlmap)örneğine bakın.

## <a name="catlmapisempty"></a><a name="isempty"></a>CAtlMap:: IsEmpty

Boş bir harita nesnesi için test etmek üzere bu yöntemi çağırın.

```cpp
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Eşleme boşsa TRUE, değilse FALSE döndürür.

## <a name="catlmapkinargtype"></a><a name="kinargtype"></a>CAtlMap:: KINARGTYPE

Giriş bağımsız değişkeni olarak bir anahtar geçirildiğinde kullanılan tür.

```cpp
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="catlmapkoutargtype"></a><a name="koutargtype"></a>CAtlMap:: KOUTARGTYPE

Bir anahtar, çıkış bağımsız değişkeni olarak döndürüldüğünde kullanılan tür.

```cpp
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="catlmaplookup"></a><a name="lookup"></a>CAtlMap:: Lookup

`CAtlMap` Nesne içindeki anahtarları veya değerleri aramak için bu yöntemi çağırın.

```cpp
bool Lookup(KINARGTYPE key, VOUTARGTYPE value) const;
const CPair* Lookup(KINARGTYPE key) const throw();
CPair* Lookup(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Aranacak öğeyi tanımlayan anahtarı belirtir.

*value*<br/>
Aranan değeri alan değişken.

### <a name="return-value"></a>Dönüş Değeri

Metodun ilk formu, anahtar bulunursa true, değilse false döndürür. İkinci ve üçüncü formlar, bir [CPair](#cpair_class) Için, [CAtlMap:: GetNext](#getnext) öğesine yapılan çağrılar için bir konum olarak kullanılabilecek bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

`Lookup`verilen anahtar parametresiyle tam olarak eşleşen bir anahtar içeren Map öğesini hızlı bir şekilde bulmak için bir karma algoritması kullanır.

## <a name="catlmapoperator-"></a><a name="operator_at"></a>CAtlMap:: işleci\[\]

Öğesine yeni bir öğesi koyar veya öğesine ekler `CAtlMap`.

```cpp
V& operator[](kinargtype key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Eklenecek veya değiştirilecek öğenin anahtarı.

### <a name="return-value"></a>Dönüş Değeri

Verilen anahtarla ilişkili değere bir başvuru döndürür.

### <a name="example"></a>Örnek

Anahtar zaten varsa, öğe değiştirilmiştir. Anahtar yoksa, yeni bir öğe eklenir. [CAtlMap:: CAtlMap](#catlmap)örneğine bakın.

## <a name="catlmaprehash"></a><a name="rehash"></a>CAtlMap:: rehash

`CAtlMap` Nesneyi yeniden sağlaması için bu yöntemi çağırın.

```cpp
void Rehash(UINT nBins = 0);
```

### <a name="parameters"></a>Parametreler

*Nbıns*<br/>
Karma tablosunda kullanılacak yeni depo gözü sayısı. Bir açıklama için bkz. [CAtlMap:: CAtlMap](#catlmap) .

### <a name="remarks"></a>Açıklamalar

*Nbıns* 0 ise, `CAtlMap` eşlemedeki öğelerin sayısına ve en iyi yükleme ayarına göre makul bir sayı hesaplar. Normal olarak yeniden karma işlemi otomatiktir, ancak [CAtlMap::D Isableotomatik rehash](#disableautorehash) çağrılırsa, bu yöntem gerekli yeniden boyutlandırmayı gerçekleştirir.

## <a name="catlmapremoveall"></a><a name="removeall"></a>CAtlMap:: RemoveAll

`CAtlMap` Nesnesinden tüm öğeleri kaldırmak için bu yöntemi çağırın.

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

`CAtlMap` Nesneleri depolamak için kullanılan belleği serbest bırakarak nesneyi temizler.

## <a name="catlmapremoveatpos"></a><a name="removeatpos"></a>CAtlMap:: RemoveAtPos

`CAtlMap` Nesnede verilen konumdaki öğeyi kaldırmak için bu yöntemi çağırın.

```cpp
void RemoveAtPos(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum sayacı, bir önceki [CAtlMap:: GetNextAssoc](#getnextassoc) veya [CAtlMap:: GetStartPosition](#getstartposition)çağrısı tarafından döndürüldü.

### <a name="remarks"></a>Açıklamalar

Belirtilen konumda depolanan anahtar/değer çiftini kaldırır. Öğeyi depolamak için kullanılan bellek serbest bırakıldı. *POS* tarafından başvurulan konum geçersiz hale gelir ve haritadaki DIĞER öğelerin konumu geçerli kalır, ancak aynı sırada tutulması gerekmez.

## <a name="catlmapremovekey"></a><a name="removekey"></a>CAtlMap:: RemoveKey

Bu yöntemi, anahtar verildiğinde `CAtlMap` nesnesinden bir öğeyi kaldırmak için çağırın.

```cpp
bool RemoveKey(KINARGTYPE key) throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Kaldırmak istediğiniz öğe çiftine karşılık gelen anahtar.

### <a name="return-value"></a>Dönüş Değeri

Anahtar bulunursa ve kaldırılırsa TRUE, hata durumunda FALSE döndürür.

### <a name="example"></a>Örnek

[CAtlMap:: CAtlMap](#catlmap)örneğine bakın.

## <a name="catlmapsetat"></a><a name="setat"></a>CAtlMap:: SetAt

Haritaya bir öğe çifti eklemek için bu yöntemi çağırın.

```cpp
POSITION SetAt(
    KINARGTYPE key,
    VINARGTYPE value);
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
`CAtlMap` Nesneye eklenecek anahtar değeri.

*value*<br/>
`CAtlMap` Nesneye eklenecek değer.

### <a name="return-value"></a>Dönüş Değeri

`CAtlMap` Nesnedeki anahtar/değer öğesi çiftinin konumunu döndürür.

### <a name="remarks"></a>Açıklamalar

`SetAt`eşleşen bir anahtar bulunursa varolan bir öğeyi değiştirir. Anahtar bulunamazsa yeni bir anahtar/değer çifti oluşturulur.

## <a name="catlmapsetoptimalload"></a><a name="setoptimalload"></a>CAtlMap:: SetOptimalLoad

`CAtlMap` Nesnenin en iyi yükünü ayarlamak için bu yöntemi çağırın.

```cpp
void SetOptimalLoad(
    float fOptimalLoad,
    float fLoThreshold,
    float fHiThreshold,
    bool bRehashNow = false);
```

### <a name="parameters"></a>Parametreler

*Foptimize Malload*<br/>
En iyi yükleme oranı.

*fLoThreshold*<br/>
Yük oranının alt eşiği.

*fHiThreshold*<br/>
Yük oranının üst eşiği.

*bRehashNow*<br/>
Karma tablosunun yeniden hesaplanması gerekip gerekmediğini belirten bayrak.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `CAtlMap` nesne için en iyi yükleme değerini tekrar tanımlar. Çeşitli parametrelerin tartışılması için bkz. [CAtlMap:: CAtlMap](#catlmap) . *BRehashNow* değeri true ise ve öğe sayısı minimum ve maksimum değerlerin dışındaysa, karma tablo yeniden hesaplanır.

## <a name="catlmapsetvalueat"></a><a name="setvalueat"></a>CAtlMap:: Setvaluyemek

`CAtlMap` Nesnedeki belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın.

```cpp
void SetValueAt(
    POSITION pos,
    VINARGTYPE value);
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum sayacı, bir önceki [CAtlMap:: GetNextAssoc](#getnextassoc) veya [CAtlMap:: GetStartPosition](#getstartposition)çağrısı tarafından döndürüldü.

*value*<br/>
`CAtlMap` Nesneye eklenecek değer.

### <a name="remarks"></a>Açıklamalar

`CAtlMap` Nesnede verilen konumda depolanan değer öğesini değiştirir.

## <a name="catlmapvinargtype"></a><a name="vinargtype"></a>CAtlMap:: VINARGTYPE

Giriş bağımsız değişkeni olarak bir değer geçirildiğinde kullanılan tür.

```cpp
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="catlmapvoutargtype"></a><a name="voutargtype"></a>CAtlMap:: VOUTARGTYPE

Bir değer çıkış bağımsız değişkeni olarak geçirildiğinde kullanılan tür.

```cpp
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="catlmapcpairm_key"></a><a name="m_key"></a>CAtlMap:: CPair:: m_key

Anahtar öğesini depolayan veri üyesi.

```cpp
const K m_key;
```

### <a name="parameters"></a>Parametreler

*Ek*<br/>
Anahtar öğe türü.

## <a name="catlmapcpairm_value"></a><a name="m_value"></a>CAtlMap:: CPair:: m_value

Değer öğesini depolayan veri üyesi.

```cpp
V  m_value;
```

### <a name="parameters"></a>Parametreler

*Yönetim*<br/>
Değer öğesi türü.

## <a name="see-also"></a>Ayrıca bkz.

[Kayan yazı örneği](../../overview/visual-cpp-samples.md)<br/>
[UpdatePV örneği](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
