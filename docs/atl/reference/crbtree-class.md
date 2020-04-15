---
title: CRBTree Sınıfı
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
ms.openlocfilehash: 56c9db9d1a7bcd7fe2a2647d8b1339d223c4b66b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331249"
---
# <a name="crbtree-class"></a>CRBTree Sınıfı

Bu sınıf, kırmızı-siyah ağaç oluşturmak ve kullanmak için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <typename K,
          typename V,
          class KTraits = CElementTraits<K>,
          class VTraits = CElementTraits<V>>
class CRBTree
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
|[CRBTree::KINARGTYPE](#kinargtype)|Bir anahtar giriş bağımsız değişkeni olarak geçirildiğinde kullanılan tür.|
|[CRBTree::KOUTARGTYPE](#koutargtype)|Bir anahtar çıktı bağımsız değişkeni olarak döndürüldüğünde kullanılan tür.|
|[CRBTree::VINARGTYPE](#vinargtype)|Bir değer girdi bağımsız değişkeni olarak geçildiğinde kullanılan tür.|
|[CRBTree::VOUTARGTYPE](#voutargtype)|Bir değer çıktı bağımsız değişkeni olarak geçirildiğinde kullanılan tür.|

### <a name="public-classes"></a>Genel Sınıflar

|Adı|Açıklama|
|----------|-----------------|
|[CRBTree::CPair Sınıfı](#cpair_class)|Anahtar ve değer öğelerini içeren bir sınıf.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CRBTree::~CRBTree](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CRBTree::FindfirstkeyAfter](#findfirstkeyafter)|Bir sonraki kullanılabilir anahtarı kullanan öğenin konumunu bulmak için bu yöntemi arayın.|
|[CRBTree:Getat](#getat)|Öğeyi ağaçta belirli bir konumda almak için bu yöntemi arayın.|
|[CRBTree::GetCount](#getcount)|Ağaçtaki öğe sayısını almak için bu yöntemi arayın.|
|[CRBTree::GetHeadPosition](#getheadposition)|Ağacın başındaki öğenin konum değerini almak için bu yöntemi arayın.|
|[CRBTree:Getkeyat](#getkeyat)|Anahtarı ağaçtaki belirli bir konumdan almak için bu yöntemi arayın.|
|[CRBTree::GetNext](#getnext)|`CRBTree` Nesnede depolanan bir öğeiçin işaretçi almak ve konumu bir sonraki öğeye ilerletmek için bu yöntemi çağırın.|
|[CRBTree:GetNextAssoc](#getnextassoc)|Haritada depolanan bir öğenin anahtarını ve değerini almak ve konumu bir sonraki öğeye ilerletmek için bu yöntemi arayın.|
|[CRBTree::GetNextKey](#getnextkey)|Ağaçta depolanan bir öğenin anahtarını almak ve konumu bir sonraki öğeye ilerletmek için bu yöntemi arayın.|
|[CRBTree::GetNextValue](#getnextvalue)|Ağaçta depolanan bir öğenin değerini almak ve konumu bir sonraki öğeye ilerletmek için bu yöntemi arayın.|
|[CRBTree:GetPrev](#getprev)|`CRBTree` Nesnede depolanan bir öğeiçin işaretçi almak için bu yöntemi çağırın ve sonra önceki öğeye konumunu güncelleştirin.|
|[CRBTree::GetTailPosition](#gettailposition)|Ağacın kuyruğundaki öğenin konum değerini almak için bu yöntemi arayın.|
|[CRBTree::GetValueat](#getvalueat)|`CRBTree` Nesnede belirli bir konumda depolanan değeri almak için bu yöntemi arayın.|
|[CRBTree::Boş](#isempty)|Boş bir ağaç nesnesi için test etmek için bu yöntemi arayın.|
|[CRBTree::RemoveAll](#removeall)|`CRBTree` Nesneden tüm öğeleri kaldırmak için bu yöntemi arayın.|
|[CRBTree::Removeat](#removeat)|Nesnede verilen konumdaki öğeyi kaldırmak `CRBTree` için bu yöntemi çağırın.|
|[CRBTree:SetValueat](#setvalueat)|Nesnede belirli bir konumda depolanan değeri değiştirmek `CRBTree` için bu yöntemi çağırın.|

## <a name="remarks"></a>Açıklamalar

Kırmızı-Siyah ağaç, "dengeli" kalmasını sağlamak için düğüm başına fazladan bilgi biti kullanan ikili bir arama ağacıdır, yani ağaç yüksekliği orantısız bir şekilde büyüyemez ve performansı etkiler.

Bu şablon sınıfı [CRBMap](../../atl/reference/crbmap-class.md) ve [CRBMultiMap](../../atl/reference/crbmultimap-class.md)tarafından kullanılmak üzere tasarlanmıştır. Bu türemiş sınıfları oluşturan yöntemlerin `CRBTree`toplu tarafından sağlanır.

Çeşitli toplama sınıfları ve özellikleri ve performans özellikleri hakkında daha eksiksiz bir tartışma için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="crbtreecpair-class"></a><a name="cpair_class"></a>CRBTree::CPair Sınıfı

Anahtar ve değer öğelerini içeren bir sınıf.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Açıklamalar

Bu sınıf [CRBTree::GetAt,](#getat) [CRBTree::GetNext](#getnext)ve [CRBTree::GetPrev](#getprev) ağaç yapısında depolanan anahtar ve değer öğelerine erişmek için kullanılır.

Üyeler aşağıdaki gibidir:

|||
|-|-|
|`m_key`|Anahtar öğeyi depolayan veri üyesi.|
|`m_value`|Değer öğesini depolayan veri üyesi.|

## <a name="crbtreecrbtree"></a><a name="dtor"></a>CRBTree::~CRBTree

Yıkıcı.

```
~CRBTree() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan kaynakları serbest sağlar. [CRBTree'yi çağırır::RemoveAll](#removeall) tüm öğeleri silmek için kullanılır.

## <a name="crbtreefindfirstkeyafter"></a><a name="findfirstkeyafter"></a>CRBTree::FindfirstkeyAfter

Bir sonraki kullanılabilir anahtarı kullanan öğenin konumunu bulmak için bu yöntemi arayın.

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Önemli bir değer.

### <a name="return-value"></a>Dönüş Değeri

Kullanılabilir sonraki anahtarı kullanan öğenin konum değerini verir. Başka öğe yoksa, NULL döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, konum değerlerini önceden hesaplamak zorunda kalmadan ağaçta gezinmeyi kolaylaştırır.

## <a name="crbtreegetat"></a><a name="getat"></a>CRBTree:Getat

Öğeyi ağaçta belirli bir konumda almak için bu yöntemi arayın.

```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Konum değeri.

*anahtar*<br/>
Anahtarı alan değişken.

*Değer*<br/>
Değeri alan değişken.

### <a name="return-value"></a>Dönüş Değeri

İlk iki form bir işaretçiyi [CPair'e](#cpair_class)döndürür. Üçüncü form, verilen pozisyon için bir anahtar ve bir değer elde eder.

### <a name="remarks"></a>Açıklamalar

Konum değeri daha önce [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::GetTailPosition](#gettailposition)gibi bir yönteme yapılan bir çağrıyla belirlenebilir.

Hata ayıklama oluştururda, *pos* NULL'a eşitse bir tasnif hatası oluşur.

## <a name="crbtreegetcount"></a><a name="getcount"></a>CRBTree::GetCount

Ağaçtaki öğe sayısını almak için bu yöntemi arayın.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ağaçta depolanan öğe sayısını (her anahtar/değer çifti bir öğedir) verir.

## <a name="crbtreegetheadposition"></a><a name="getheadposition"></a>CRBTree::GetHeadPosition

Ağacın başındaki öğenin konum değerini almak için bu yöntemi arayın.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ağacın başındaki öğenin konum değerini verir.

### <a name="remarks"></a>Açıklamalar

Döndürülen `GetHeadPosition` değer [CRBTree::GetKeyAt](#getkeyat) veya [CRBTree::GetNext](#getnext) ağaç çapraz ve değerleri almak gibi yöntemlerle kullanılabilir.

## <a name="crbtreegetkeyat"></a><a name="getkeyat"></a>CRBTree:Getkeyat

Anahtarı ağaçtaki belirli bir konumdan almak için bu yöntemi arayın.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
Konum değeri.

### <a name="return-value"></a>Dönüş Değeri

Ağaçtaki pozisyon *pos'unda* depolanan anahtarı döndürür.

### <a name="remarks"></a>Açıklamalar

*Pos* geçerli bir konum değeri değilse, sonuçlar öngörülemez. Hata ayıklama oluştururda, *pos* NULL'a eşitse bir tasnif hatası oluşur.

## <a name="crbtreegetnext"></a><a name="getnext"></a>CRBTree::GetNext

`CRBTree` Nesnede depolanan bir öğeiçin işaretçi almak ve konumu bir sonraki öğeye ilerletmek için bu yöntemi çağırın.

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
[CrBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere önceki bir çağrı ile döndürülen konum sayacı.

### <a name="return-value"></a>Dönüş Değeri

Bir işaretçiyi ağaçtaki bir sonraki [CPair](#cpair_class) değerine döndürür.

### <a name="remarks"></a>Açıklamalar

*Pos* konum sayacı her çağrıdan sonra güncelleştirilir. Alınan öğe ağaçtaki son öğeyse, *pos* NULL olarak ayarlanır.

## <a name="crbtreegetnextassoc"></a><a name="getnextassoc"></a>CRBTree:GetNextAssoc

Haritada depolanan bir öğenin anahtarını ve değerini almak ve konumu bir sonraki öğeye ilerletmek için bu yöntemi arayın.

```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
[CrBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere önceki bir çağrı ile döndürülen konum sayacı.

*anahtar*<br/>
Ağacın anahtarının türünü belirten şablon parametresi.

*Değer*<br/>
Ağacın değerini belirten şablon parametresi.

### <a name="remarks"></a>Açıklamalar

*Pos* konum sayacı her çağrıdan sonra güncelleştirilir. Alınan öğe ağaçtaki son öğeyse, *pos* NULL olarak ayarlanır.

## <a name="crbtreegetnextkey"></a><a name="getnextkey"></a>CRBTree::GetNextKey

Ağaçta depolanan bir öğenin anahtarını almak ve konumu bir sonraki öğeye ilerletmek için bu yöntemi arayın.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
[CrBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere önceki bir çağrı ile döndürülen konum sayacı.

### <a name="return-value"></a>Dönüş Değeri

Ağaçtaki bir sonraki anahtara bir başvuru verir.

### <a name="remarks"></a>Açıklamalar

Güncel konum sayacını, *pos'u*güncelleştirir. Ağaçta başka giriş yoksa, konum sayacı NULL olarak ayarlanır.

## <a name="crbtreegetnextvalue"></a><a name="getnextvalue"></a>CRBTree::GetNextValue

Ağaçta depolanan bir öğenin değerini almak ve konumu bir sonraki öğeye ilerletmek için bu yöntemi arayın.

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
[CrBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere önceki bir çağrı ile döndürülen konum sayacı.

### <a name="return-value"></a>Dönüş Değeri

Ağaçtaki bir sonraki değere başvuru verir.

### <a name="remarks"></a>Açıklamalar

Güncel konum sayacını, *pos'u*güncelleştirir. Ağaçta başka giriş yoksa, konum sayacı NULL olarak ayarlanır.

## <a name="crbtreegetprev"></a><a name="getprev"></a>CRBTree:GetPrev

`CRBTree` Nesnede depolanan bir öğeiçin işaretçi almak için bu yöntemi çağırın ve sonra önceki öğeye konumunu güncelleştirin.

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
[CrBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere önceki bir çağrı ile döndürülen konum sayacı.

### <a name="return-value"></a>Dönüş Değeri

Ağaçta depolanan önceki [CPair](#cpair_class) değerine bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Güncel konum sayacını, *pos'u*güncelleştirir. Ağaçta başka giriş yoksa, konum sayacı NULL olarak ayarlanır.

## <a name="crbtreegettailposition"></a><a name="gettailposition"></a>CRBTree::GetTailPosition

Ağacın kuyruğundaki öğenin konum değerini almak için bu yöntemi arayın.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ağacın kuyruğundaki öğenin konum değerini verir.

### <a name="remarks"></a>Açıklamalar

Döndürülen `GetTailPosition` değer [CRBTree::GetKeyAt](#getkeyat) veya [CRBTree::GetPrev](#getprev) gibi yöntemlerle ağaç çapraz ve değerleri almak için kullanılabilir.

## <a name="crbtreegetvalueat"></a><a name="getvalueat"></a>CRBTree::GetValueat

`CRBTree` Nesnede belirli bir konumda depolanan değeri almak için bu yöntemi arayın.

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
[CrBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere önceki bir çağrı ile döndürülen konum sayacı.

### <a name="return-value"></a>Dönüş Değeri

`CRBTree` Nesnede verilen konumda depolanan değere bir başvuru verir.

## <a name="crbtreeisempty"></a><a name="isempty"></a>CRBTree::Boş

Boş bir ağaç nesnesi için test etmek için bu yöntemi arayın.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ağaç boşsa DOĞRU döndürür, aksi takdirde YANLIŞ.

## <a name="crbtreekinargtype"></a><a name="kinargtype"></a>CRBTree::KINARGTYPE

Bir anahtar giriş bağımsız değişkeni olarak geçirildiğinde kullanılan tür.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

## <a name="crbtreekoutargtype"></a><a name="koutargtype"></a>CRBTree::KOUTARGTYPE

Bir anahtar çıktı bağımsız değişkeni olarak döndürüldüğünde kullanılan tür.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

## <a name="crbtreeremoveall"></a><a name="removeall"></a>CRBTree::RemoveAll

`CRBTree` Nesneden tüm öğeleri kaldırmak için bu yöntemi arayın.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Öğeleri depolamak `CRBTree` için kullanılan belleği serbest, nesneyi temizler.

## <a name="crbtreeremoveat"></a><a name="removeat"></a>CRBTree::Removeat

Nesnede verilen konumdaki öğeyi kaldırmak `CRBTree` için bu yöntemi çağırın.

```
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
[CrBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere önceki bir çağrı ile döndürülen konum sayacı.

### <a name="remarks"></a>Açıklamalar

Belirtilen konumda depolanan anahtar/değer çiftini kaldırır. Öğeyi depolamak için kullanılan bellek serbest bırakılır. *Pos* tarafından başvurulan KONUM geçersiz olur ve ağaçtaki diğer öğelerin KONUMU geçerli kalırken, aynı sırayı korumak zorunda kalmazlar.

## <a name="crbtreesetvalueat"></a><a name="setvalueat"></a>CRBTree:SetValueat

Nesnede belirli bir konumda depolanan değeri değiştirmek `CRBTree` için bu yöntemi çağırın.

```
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>Parametreler

*Pos*<br/>
[CrBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter)gibi yöntemlere önceki bir çağrı ile döndürülen konum sayacı.

*Değer*<br/>
`CRBTree` Nesneye eklenecek değer.

### <a name="remarks"></a>Açıklamalar

Nesnede verilen konumda depolanan değer `CRBTree` öğesini değiştirir.

## <a name="crbtreevinargtype"></a><a name="vinargtype"></a>CRBTree::VINARGTYPE

Bir değer girdi bağımsız değişkeni olarak geçildiğinde kullanılan tür.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

## <a name="crbtreevoutargtype"></a><a name="voutargtype"></a>CRBTree::VOUTARGTYPE

Bir değer çıktı bağımsız değişkeni olarak geçirildiğinde kullanılan tür.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
