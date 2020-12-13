---
description: 'Daha fazla bilgi edinin: CRBTree sınıfı'
title: CRBTree sınıfı
ms.date: 11/04/2016
f1_keywords:
- CRBTree
- ATLCOLL/ATL::CRBTree
- ATLCOLL/ATL::CRBTree::KINARGTYPE
- ATLCOLL/ATL::CRBTree::KOUTARGTYPE
- ATLCOLL/ATL::CRBTree::VINARGTYPE
- ATLCOLL/ATL::CRBTree::VOUTARGTYPE
- ATLCOLL/ATL::CRBTree::FindFirstKeyAfter
- ATLCOLL/ATL::CRBTree::GetAt
- ATLCOLL/ATL::CRBTree::GetCount
- ATLCOLL/ATL::CRBTree::GetHeadPosition
- ATLCOLL/ATL::CRBTree::GetKeyAt
- ATLCOLL/ATL::CRBTree::GetNext
- ATLCOLL/ATL::CRBTree::GetNextAssoc
- ATLCOLL/ATL::CRBTree::GetNextKey
- ATLCOLL/ATL::CRBTree::GetNextValue
- ATLCOLL/ATL::CRBTree::GetPrev
- ATLCOLL/ATL::CRBTree::GetTailPosition
- ATLCOLL/ATL::CRBTree::GetValueAt
- ATLCOLL/ATL::CRBTree::IsEmpty
- ATLCOLL/ATL::CRBTree::RemoveAll
- ATLCOLL/ATL::CRBTree::RemoveAt
- ATLCOLL/ATL::CRBTree::SetValueAt
helpviewer_keywords:
- CRBTree class
ms.assetid: a1b1cb63-38e4-4fc2-bb28-f774d1721760
ms.openlocfilehash: 3c45c8b05429ba75905912d76f87605a07ff49e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140978"
---
# <a name="crbtree-class"></a>CRBTree sınıfı

Bu sınıf Red-Black ağacı oluşturmak ve kullanmak için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBTree
```

#### <a name="parameters"></a>Parametreler

*K*<br/>
Anahtar öğe türü.

*V*<br/>
Değer öğesi türü.

*Knitelikler*<br/>
Anahtar öğelerini kopyalamak veya taşımak için kullanılan kod. Daha fazla ayrıntı için bkz. [Celementnitelikler sınıfı](../../atl/reference/celementtraits-class.md) .

*Sanal nitelikler*<br/>
Değer öğelerini kopyalamak veya taşımak için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Ortak tür tanımları

|Ad|Açıklama|
|----------|-----------------|
|[CRBTree:: KINARGTYPE](#kinargtype)|Giriş bağımsız değişkeni olarak bir anahtar geçirildiğinde kullanılan tür.|
|[CRBTree:: KOUTARGTYPE](#koutargtype)|Bir anahtar, çıkış bağımsız değişkeni olarak döndürüldüğünde kullanılan tür.|
|[CRBTree:: VINARGTYPE](#vinargtype)|Giriş bağımsız değişkeni olarak bir değer geçirildiğinde kullanılan tür.|
|[CRBTree:: VOUTARGTYPE](#voutargtype)|Bir değer çıkış bağımsız değişkeni olarak geçirildiğinde kullanılan tür.|

### <a name="public-classes"></a>Ortak sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[CRBTree:: CPair sınıfı](#cpair_class)|Anahtar ve değer öğelerini içeren bir sınıf.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRBTree:: ~ CRBTree](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRBTree:: FindFirstKeyAfter](#findfirstkeyafter)|Bir sonraki kullanılabilir anahtarı kullanan öğenin konumunu bulmak için bu yöntemi çağırın.|
|[CRBTree:: GetAt](#getat)|Öğeyi ağaçta belirli bir konumda almak için bu yöntemi çağırın.|
|[CRBTree:: GetCount](#getcount)|Ağaçtaki öğelerin sayısını almak için bu yöntemi çağırın.|
|[CRBTree:: GetHeadPosition](#getheadposition)|Ağacın baş tarafındaki öğe için konum değerini almak üzere bu yöntemi çağırın.|
|[CRBTree:: GetKeyAt](#getkeyat)|Ağaçtaki belirli bir konumdan anahtarı almak için bu yöntemi çağırın.|
|[CRBTree:: GetNext](#getnext)|Nesnede depolanan bir öğeye yönelik bir işaretçi almak için bu yöntemi çağırın `CRBTree` ve konumu sonraki öğeye ilerletin.|
|[CRBTree:: GetNextAssoc](#getnextassoc)|Haritada depolanan bir öğenin anahtar ve değerini almak için bu yöntemi çağırın ve konumu sonraki öğeye ilerletin.|
|[CRBTree:: GetNextKey](#getnextkey)|Ağaçta depolanan bir öğenin anahtarını almak için bu yöntemi çağırın ve konumu sonraki öğeye ilerletin.|
|[CRBTree:: GetNextValue](#getnextvalue)|Ağaçta depolanan bir öğenin değerini almak için bu yöntemi çağırın ve konumu sonraki öğeye ilerletin.|
|[CRBTree:: Getöncekini](#getprev)|Nesnede depolanan bir öğeye yönelik bir işaretçi almak için bu yöntemi çağırın `CRBTree` ve sonra konumu önceki öğeye güncelleştirin.|
|[CRBTree:: Getbir Position](#gettailposition)|Ağacın sırasındaki öğesinin konum değerini almak için bu yöntemi çağırın.|
|[CRBTree:: Getvaluyemek](#getvalueat)|Nesnede belirli bir konumda depolanan değeri almak için bu yöntemi çağırın `CRBTree` .|
|[CRBTree:: IsEmpty](#isempty)|Boş bir ağaç nesnesini test etmek için bu yöntemi çağırın.|
|[CRBTree:: RemoveAll](#removeall)|Nesnesinden tüm öğeleri kaldırmak için bu yöntemi çağırın `CRBTree` .|
|[CRBTree:: RemoveAt](#removeat)|Nesnede verilen konumdaki öğeyi kaldırmak için bu yöntemi çağırın `CRBTree` .|
|[CRBTree:: Setvaluyemek](#setvalueat)|Nesnedeki belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın `CRBTree` .|

## <a name="remarks"></a>Açıklamalar

Red-Black ağacı, düğüm başına fazladan bir bilgi kullanan bir ikili arama ağacıdır; Yani, ağaç yüksekliği orantısız bir şekilde büyümez ve performansı etkiler.

Bu şablon sınıfı, [CRBMap](../../atl/reference/crbmap-class.md) ve [CRBMultiMap](../../atl/reference/crbmultimap-class.md)tarafından kullanılmak üzere tasarlanmıştır. Bu türetilmiş sınıfları oluşturan yöntemlerin toplu yöntemi tarafından sağlanır `CRBTree` .

Çeşitli koleksiyon sınıflarının ve bunların özelliklerinin ve performans özelliklerinin daha kapsamlı bir tartışması için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

## <a name="crbtreecpair-class"></a><a name="cpair_class"></a> CRBTree:: CPair sınıfı

Anahtar ve değer öğelerini içeren bir sınıf.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Açıklamalar

Bu sınıf, ağaç yapısında depolanan anahtar ve değer öğelerine erişmek için [CRBTree:: GetAt](#getat), [CRBTree:: GetNext](#getnext)ve [CRBTree:: getönceki](#getprev) yöntemleri tarafından kullanılır.

Üyeler aşağıdaki gibidir:

|Veri üyesi|Açıklama|
|-|-|
|`m_key`|Anahtar öğesini depolayan veri üyesi.|
|`m_value`|Değer öğesini depolayan veri üyesi.|

## <a name="crbtreecrbtree"></a><a name="dtor"></a> CRBTree:: ~ CRBTree

Yok edicisi.

```
~CRBTree() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest bırakır. Tüm öğeleri silmek için [CRBTree:: RemoveAll](#removeall) öğesini çağırır.

## <a name="crbtreefindfirstkeyafter"></a><a name="findfirstkeyafter"></a> CRBTree:: FindFirstKeyAfter

Bir sonraki kullanılabilir anahtarı kullanan öğenin konumunu bulmak için bu yöntemi çağırın.

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Bir sonraki kullanılabilir anahtarı kullanan öğenin konum değerini döndürür. Daha fazla öğe yoksa, NULL döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, konum değerlerini önceden hesaplamak zorunda kalmadan ağacın çapraz geçişini kolaylaştırır.

## <a name="crbtreegetat"></a><a name="getat"></a> CRBTree:: GetAt

Öğeyi ağaçta belirli bir konumda almak için bu yöntemi çağırın.

```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum değeri.

*anahtar*<br/>
Anahtarı alan değişken.

*değer*<br/>
Değeri alan değişken.

### <a name="return-value"></a>Dönüş Değeri

İlk iki form, [CPair](#cpair_class)için bir işaretçi döndürür. Üçüncü form, belirtilen konum için bir anahtar ve bir değer alır.

### <a name="remarks"></a>Açıklamalar

Konum değeri, daha önce [CRBTree:: GetHeadPosition](#getheadposition) veya [CRBTree:: getsavposition](#gettailposition)gibi bir yönteme yapılan çağrıyla belirlenebilir.

Hata ayıklama yapılarında, *POS* null değerine eşitse bir onaylama hatası oluşur.

## <a name="crbtreegetcount"></a><a name="getcount"></a> CRBTree:: GetCount

Ağaçtaki öğelerin sayısını almak için bu yöntemi çağırın.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ağaçta depolanan öğelerin (her anahtar/değer çifti bir öğe) sayısını döndürür.

## <a name="crbtreegetheadposition"></a><a name="getheadposition"></a> CRBTree:: GetHeadPosition

Ağacın baş tarafındaki öğe için konum değerini almak üzere bu yöntemi çağırın.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ağacın baş tarafındaki öğe için konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer, `GetHeadPosition` ağaç üzerinde geçiş yapmak ve değerleri almak Için [CRBTree:: GetKeyAt](#getkeyat) veya [CRBTree:: GetNext](#getnext) gibi yöntemlerle kullanılabilir.

## <a name="crbtreegetkeyat"></a><a name="getkeyat"></a> CRBTree:: GetKeyAt

Ağaçtaki belirli bir konumdan anahtarı almak için bu yöntemi çağırın.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
Konum değeri.

### <a name="return-value"></a>Dönüş Değeri

Ağaçta *POS* konumunda depolanan anahtarı döndürür.

### <a name="remarks"></a>Açıklamalar

*POS* geçerli bir konum değeri değilse, sonuçlar tahmin edilemez. Hata ayıklama yapılarında, *POS* null değerine eşitse bir onaylama hatası oluşur.

## <a name="crbtreegetnext"></a><a name="getnext"></a> CRBTree:: GetNext

Nesnede depolanan bir öğeye yönelik bir işaretçi almak için bu yöntemi çağırın `CRBTree` ve konumu sonraki öğeye ilerletin.

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
[CRBTree:: GetHeadPosition](#getheadposition) veya [CRBTree:: FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere yapılan bir çağrı tarafından döndürülen konum sayacı.

### <a name="return-value"></a>Dönüş Değeri

Ağaçtaki sonraki [CPair](#cpair_class) değerine bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

*POS* konum sayacı her çağrıdan sonra güncelleştirilir. Alınan öğe ağaçta son ise, *POS* null olarak ayarlanır.

## <a name="crbtreegetnextassoc"></a><a name="getnextassoc"></a> CRBTree:: GetNextAssoc

Haritada depolanan bir öğenin anahtar ve değerini almak için bu yöntemi çağırın ve konumu sonraki öğeye ilerletin.

```cpp
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
[CRBTree:: GetHeadPosition](#getheadposition) veya [CRBTree:: FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere yapılan bir çağrı tarafından döndürülen konum sayacı.

*anahtar*<br/>
Ağaç anahtarının türünü belirten şablon parametresi.

*değer*<br/>
Ağaç değerinin türünü belirten şablon parametresi.

### <a name="remarks"></a>Açıklamalar

*POS* konum sayacı her çağrıdan sonra güncelleştirilir. Alınan öğe ağaçta son ise, *POS* null olarak ayarlanır.

## <a name="crbtreegetnextkey"></a><a name="getnextkey"></a> CRBTree:: GetNextKey

Ağaçta depolanan bir öğenin anahtarını almak için bu yöntemi çağırın ve konumu sonraki öğeye ilerletin.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
[CRBTree:: GetHeadPosition](#getheadposition) veya [CRBTree:: FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere yapılan bir çağrı tarafından döndürülen konum sayacı.

### <a name="return-value"></a>Dönüş Değeri

Ağaçtaki bir sonraki anahtara bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli pozisyon sayacını güncelleştirir, *POS*. Ağaçta daha fazla giriş yoksa, konum sayacı NULL olarak ayarlanır.

## <a name="crbtreegetnextvalue"></a><a name="getnextvalue"></a> CRBTree:: GetNextValue

Ağaçta depolanan bir öğenin değerini almak için bu yöntemi çağırın ve konumu sonraki öğeye ilerletin.

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
[CRBTree:: GetHeadPosition](#getheadposition) veya [CRBTree:: FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere yapılan bir çağrı tarafından döndürülen konum sayacı.

### <a name="return-value"></a>Dönüş Değeri

Ağaçtaki bir sonraki değere bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli pozisyon sayacını güncelleştirir, *POS*. Ağaçta daha fazla giriş yoksa, konum sayacı NULL olarak ayarlanır.

## <a name="crbtreegetprev"></a><a name="getprev"></a> CRBTree:: Getöncekini

Nesnede depolanan bir öğeye yönelik bir işaretçi almak için bu yöntemi çağırın `CRBTree` ve sonra konumu önceki öğeye güncelleştirin.

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
[CRBTree:: GetHeadPosition](#getheadposition) veya [CRBTree:: FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere yapılan bir çağrı tarafından döndürülen konum sayacı.

### <a name="return-value"></a>Dönüş Değeri

Ağaçta depolanan önceki [CPair](#cpair_class) değerine yönelik bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli pozisyon sayacını güncelleştirir, *POS*. Ağaçta daha fazla giriş yoksa, konum sayacı NULL olarak ayarlanır.

## <a name="crbtreegettailposition"></a><a name="gettailposition"></a> CRBTree:: Getbir Position

Ağacın sırasındaki öğesinin konum değerini almak için bu yöntemi çağırın.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ağacın sırasındaki öğe için konum değerini döndürür.

### <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer, `GetTailPosition` ağacı çapraz geçiş yapmak ve değerleri almak Için [CRBTree:: GetKeyAt](#getkeyat) veya [CRBTree:: getöncekini](#getprev) gibi yöntemlerle kullanılabilir.

## <a name="crbtreegetvalueat"></a><a name="getvalueat"></a> CRBTree:: Getvaluyemek

Nesnede belirli bir konumda depolanan değeri almak için bu yöntemi çağırın `CRBTree` .

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
[CRBTree:: GetHeadPosition](#getheadposition) veya [CRBTree:: FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere yapılan bir çağrı tarafından döndürülen konum sayacı.

### <a name="return-value"></a>Dönüş Değeri

Nesnede verilen konumda depolanan değere bir başvuru döndürür `CRBTree` .

## <a name="crbtreeisempty"></a><a name="isempty"></a> CRBTree:: IsEmpty

Boş bir ağaç nesnesini test etmek için bu yöntemi çağırın.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ağaç boşsa TRUE, değilse FALSE döndürür.

## <a name="crbtreekinargtype"></a><a name="kinargtype"></a> CRBTree:: KINARGTYPE

Giriş bağımsız değişkeni olarak bir anahtar geçirildiğinde kullanılan tür.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="crbtreekoutargtype"></a><a name="koutargtype"></a> CRBTree:: KOUTARGTYPE

Bir anahtar, çıkış bağımsız değişkeni olarak döndürüldüğünde kullanılan tür.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="crbtreeremoveall"></a><a name="removeall"></a> CRBTree:: RemoveAll

Nesnesinden tüm öğeleri kaldırmak için bu yöntemi çağırın `CRBTree` .

```cpp
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

`CRBTree`Nesneleri depolamak için kullanılan belleği serbest bırakarak nesneyi temizler.

## <a name="crbtreeremoveat"></a><a name="removeat"></a> CRBTree:: RemoveAt

Nesnede verilen konumdaki öğeyi kaldırmak için bu yöntemi çağırın `CRBTree` .

```cpp
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
[CRBTree:: GetHeadPosition](#getheadposition) veya [CRBTree:: FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere yapılan bir çağrı tarafından döndürülen konum sayacı.

### <a name="remarks"></a>Açıklamalar

Belirtilen konumda depolanan anahtar/değer çiftini kaldırır. Öğeyi depolamak için kullanılan bellek serbest bırakıldı. *POS* tarafından başvurulan konum geçersiz hale gelir ve ağaçtaki DIĞER öğelerin konumu geçerli kalır, ancak aynı sırada tutulması gerekmez.

## <a name="crbtreesetvalueat"></a><a name="setvalueat"></a> CRBTree:: Setvaluyemek

Nesnedeki belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın `CRBTree` .

```cpp
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>Parametreler

*'un*<br/>
[CRBTree:: GetHeadPosition](#getheadposition) veya [CRBTree:: FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere yapılan bir çağrı tarafından döndürülen konum sayacı.

*değer*<br/>
Nesneye eklenecek değer `CRBTree` .

### <a name="remarks"></a>Açıklamalar

Nesnede verilen konumda depolanan değer öğesini değiştirir `CRBTree` .

## <a name="crbtreevinargtype"></a><a name="vinargtype"></a> CRBTree:: VINARGTYPE

Giriş bağımsız değişkeni olarak bir değer geçirildiğinde kullanılan tür.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="crbtreevoutargtype"></a><a name="voutargtype"></a> CRBTree:: VOUTARGTYPE

Bir değer çıkış bağımsız değişkeni olarak geçirildiğinde kullanılan tür.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
