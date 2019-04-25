---
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
ms.openlocfilehash: 59416000eecf4be25746d9dedd86ea2af116087a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62278078"
---
# <a name="crbtree-class"></a>CRBTree sınıfı

Bu sınıf, oluşturma ve Red-siyah ağaç kullanan yöntemleri sağlar.

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
Değer öğe türü.

*KTraits*<br/>
Kopyalamak veya taşımak temel öğeleri için kullanılan kod. Bkz: [CElementTraits sınıfı](../../atl/reference/celementtraits-class.md) daha fazla ayrıntı için.

*VTraits*<br/>
Kopyalamak veya taşımak değeri öğeleri için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="public-typedefs"></a>Genel Typedefler

|Ad|Açıklama|
|----------|-----------------|
|[CRBTree::KINARGTYPE](#kinargtype)|Bir giriş bağımsız değişkeni bir anahtar geçirildiğinde kullanılan türü.|
|[CRBTree::KOUTARGTYPE](#koutargtype)|Çıkış bağımsız değişken olarak bir anahtar döndürüldüğünde kullanılan türü.|
|[CRBTree::VINARGTYPE](#vinargtype)|Kullanılması için bir giriş bağımsız değişkeni geçirilen bir değer türü.|
|[CRBTree::VOUTARGTYPE](#voutargtype)|Çıkış bağımsız değişken olarak geçirilen bir değer olduğunda kullanılan türü.|

### <a name="public-classes"></a>Genel sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[CRBTree::CPair sınıfı](#cpair_class)|Anahtar ve değer öğeleri içeren bir sınıf.|

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CRBTree:: ~ CRBTree](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CRBTree::FindFirstKeyAfter](#findfirstkeyafter)|Sonraki kullanılabilir anahtarı kullanan bir öğenin konumunu bulmak için bu yöntemi çağırın.|
|[CRBTree::GetAt](#getat)|Verilen konumda ağacındaki öğe almak için bu yöntemi çağırın.|
|[CRBTree::GetCount](#getcount)|Ağaçta öğelerin sayısını almak için bu yöntemi çağırın.|
|[CRBTree::GetHeadPosition](#getheadposition)|Öğe ağacı başındaki konum değerini almak için bu yöntemi çağırın.|
|[CRBTree::GetKeyAt](#getkeyat)|Ağaçta belirli bir konumdan anahtarı almak için bu yöntemi çağırın.|
|[CRBTree::GetNext](#getnext)|İçinde depolan bir öğeye bir işaretçi alma için bu yöntemi çağırın `CRBTree` nesne ve sonraki öğeye konumuna ilerleyin.|
|[CRBTree::GetNextAssoc](#getnextassoc)|Eşlem içinde depolan bir öğenin değerini ve anahtarı almak için bu yöntemi çağırın ve sonraki öğeye konumuna ilerleyin.|
|[CRBTree::GetNextKey](#getnextkey)|Depolanan ağaçta bir öğenin anahtarı almak için bu yöntemi çağırın ve sonraki öğeye konumuna ilerleyin.|
|[CRBTree::GetNextValue](#getnextvalue)|Ağacı içinde depolan bir öğeye değerini almak için bu yöntemi çağırın ve sonraki öğeye konumuna ilerleyin.|
|[CRBTree::GetPrev](#getprev)|İçinde depolan bir öğeye bir işaretçi alma için bu yöntemi çağırın `CRBTree` nesnesi ve ardından önceki öğenin konumunu güncelleştirin.|
|[CRBTree::GetTailPosition](#gettailposition)|Öğe ağacı kuyruğunu konum değerini almak için bu yöntemi çağırın.|
|[CRBTree::GetValueAt](#getvalueat)|Belirli bir konumda depolanan değeri almak için bu yöntemi çağırın `CRBTree` nesne.|
|[CRBTree::IsEmpty](#isempty)|Boş bir ağaç nesne için test etmek için bu yöntemi çağırın.|
|[CRBTree::RemoveAll](#removeall)|Tüm öğeleri kaldırmak için bu yöntemi çağırın `CRBTree` nesne.|
|[CRBTree::RemoveAt](#removeat)|Belirtilen konumda bir öğe kaldırmak için bu yöntemi çağırın `CRBTree` nesne.|
|[CRBTree::SetValueAt](#setvalueat)|Belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın `CRBTree` nesne.|

## <a name="remarks"></a>Açıklamalar

Ek kullanan ikili arama ağacını Red-siyah ağacıdır bilgilerin, kalmasını sağlamak için düğüm başına bit "Dengeli," olan, ağaç yüksekliği orantısız büyük büyütme ve performans üzerindeki etkisi yoktur.

Bu şablon sınıfının tarafından kullanılmak üzere tasarlanmıştır [CRBMap](../../atl/reference/crbmap-class.md) ve [CRBMultiMap](../../atl/reference/crbmultimap-class.md). Bu türetilmiş sınıfları yöntemlerin toplu tarafından sağlanan `CRBTree`.

Çeşitli koleksiyon sınıflarını ve özelliklerini ve performans özelliklerini daha eksiksiz bir açıklaması için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="cpair_class"></a>  CRBTree::CPair sınıfı

Anahtar ve değer öğeleri içeren bir sınıf.

```
class CPair : public __POSITION
```

### <a name="remarks"></a>Açıklamalar

Bu sınıf yöntemleri tarafından kullanılır [CRBTree::GetAt](#getat), [CRBTree::GetNext](#getnext), ve [CRBTree::GetPrev](#getprev) ağaç yapısı içinde depolanan anahtar ve değer öğelere erişmek için.

Üyeleri aşağıdaki gibidir:

|||
|-|-|
|`m_key`|Anahtar öğesi depolama veri üyesi.|
|`m_value`|Değer öğesini depolama veri üyesi.|

##  <a name="dtor"></a>  CRBTree:: ~ CRBTree

Yıkıcı.

```
~CRBTree() throw();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır. Çağrıları [CRBTree::RemoveAll](#removeall) tüm öğeleri silinemedi.

##  <a name="findfirstkeyafter"></a>  CRBTree::FindFirstKeyAfter

Sonraki kullanılabilir anahtarı kullanan bir öğenin konumunu bulmak için bu yöntemi çağırın.

```
POSITION FindFirstKeyAfter(KINARGTYPE key) const throw();
```

### <a name="parameters"></a>Parametreler

*anahtar*<br/>
Bir anahtar değeri.

### <a name="return-value"></a>Dönüş Değeri

Sonraki kullanılabilir anahtarı kullanan öğenin konumunu değerini döndürür. Daha fazla öğe yoksa NULL döndürülür.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, önceden konum değerleri hesaplama yapmak zorunda kalmadan ağacı gezme kolaylaştırır.

##  <a name="getat"></a>  CRBTree::GetAt

Verilen konumda ağacındaki öğe almak için bu yöntemi çağırın.

```
CPair* GetAt(POSITION pos) throw();
const CPair* GetAt(POSITION pos) const throw();
void GetAt(POSITION pos, KOUTARGTYPE key, VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Konum değeri.

*anahtar*<br/>
Değişken anahtarı alır.

*value*<br/>
Değişken değerini alır.

### <a name="return-value"></a>Dönüş Değeri

İlk iki form bir işaretçi döndürür bir [CPair](#cpair_class). Üçüncü formu bir anahtarı ve belirtilen konum için bir değer alır.

### <a name="remarks"></a>Açıklamalar

Konum değerini daha önce bir yönteme bir çağrı ile gibi belirlenebilir [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::GetTailPosition](#gettailposition).

Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pos* NULL değerine eşittir.

##  <a name="getcount"></a>  CRBTree::GetCount

Ağaçta öğelerin sayısını almak için bu yöntemi çağırın.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ağaçta depolanan (her anahtar/değer çifti bir öğedir) öğelerin sayısını döndürür.

##  <a name="getheadposition"></a>  CRBTree::GetHeadPosition

Öğe ağacı başındaki konum değerini almak için bu yöntemi çağırın.

```
POSITION GetHeadPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Öğe ağacı başındaki konum değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `GetHeadPosition` yöntemleriyle gibi kullanılabilir [CRBTree::GetKeyAt](#getkeyat) veya [CRBTree::GetNext](#getnext) ağacı gezme ve değerleri almak için.

##  <a name="getkeyat"></a>  CRBTree::GetKeyAt

Ağaçta belirli bir konumdan anahtarı almak için bu yöntemi çağırın.

```
const K& GetKeyAt(POSITION pos) const throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Konum değeri.

### <a name="return-value"></a>Dönüş Değeri

Konumunda depolanan anahtar döndürür *pos* ağacında.

### <a name="remarks"></a>Açıklamalar

Varsa *pos* bir geçerli konumu değeri değil sonuçların tahmin edilemeyeceğine. Hata ayıklama yapılarında, onaylama işlemi hatası meydana gelir *pos* NULL değerine eşittir.

##  <a name="getnext"></a>  CRBTree::GetNext

İçinde depolan bir öğeye bir işaretçi alma için bu yöntemi çağırın `CRBTree` nesne ve sonraki öğeye konumuna ilerleyin.

```
const CPair* GetNext(POSITION& pos) const throw();
CPair* GetNext(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konum sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Dönüş Değeri

Sonraki bir işaretçi döndürür [CPair](#cpair_class) ağacında değeri.

### <a name="remarks"></a>Açıklamalar

*Pos* konumu sayaç her çağrıdan sonra güncelleştirilir. Alınan öğe ağacında, son ise *pos* NULL olarak ayarlandı.

##  <a name="getnextassoc"></a>  CRBTree::GetNextAssoc

Eşlem içinde depolan bir öğenin değerini ve anahtarı almak için bu yöntemi çağırın ve sonraki öğeye konumuna ilerleyin.

```
void GetNextAssoc(
    POSITION& pos,
    KOUTARGTYPE key,
    VOUTARGTYPE value) const;
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konum sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

*anahtar*<br/>
Ağacının anahtar türünü belirten bir şablon parametre.

*value*<br/>
Ağacının değerin türünü belirten bir şablon parametre.

### <a name="remarks"></a>Açıklamalar

*Pos* konumu sayaç her çağrıdan sonra güncelleştirilir. Alınan öğe ağacında, son ise *pos* NULL olarak ayarlandı.

##  <a name="getnextkey"></a>  CRBTree::GetNextKey

Depolanan ağaçta bir öğenin anahtarı almak için bu yöntemi çağırın ve sonraki öğeye konumuna ilerleyin.

```
const K& GetNextKey(POSITION& pos) const throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konum sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Dönüş Değeri

Sonraki anahtarı için bir başvuru ağacında döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli konumu sayacı güncelleştiren *pos*. Ağacında daha fazla girdi yoksa konumu sayaç değeri NULL olarak ayarlanır.

##  <a name="getnextvalue"></a>  CRBTree::GetNextValue

Ağacı içinde depolan bir öğeye değerini almak için bu yöntemi çağırın ve sonraki öğeye konumuna ilerleyin.

```
const V& GetNextValue(POSITION& pos) const throw();
V& GetNextValue(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konum sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Dönüş Değeri

Ağaçta sonraki değerine bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Geçerli konumu sayacı güncelleştiren *pos*. Ağacında daha fazla girdi yoksa konumu sayaç değeri NULL olarak ayarlanır.

##  <a name="getprev"></a>  CRBTree::GetPrev

İçinde depolan bir öğeye bir işaretçi alma için bu yöntemi çağırın `CRBTree` nesnesi ve ardından önceki öğenin konumunu güncelleştirin.

```
const CPair* GetPrev(POSITION& pos) const throw();
CPair* GetPrev(POSITION& pos) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konum sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Dönüş Değeri

Önceki bir işaretçi döndürür [CPair](#cpair_class) ağacında depolanan değer.

### <a name="remarks"></a>Açıklamalar

Geçerli konumu sayacı güncelleştiren *pos*. Ağacında daha fazla girdi yoksa konumu sayaç değeri NULL olarak ayarlanır.

##  <a name="gettailposition"></a>  CRBTree::GetTailPosition

Öğe ağacı kuyruğunu konum değerini almak için bu yöntemi çağırın.

```
POSITION GetTailPosition() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Öğe ağacı sonu için konum değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Tarafından döndürülen değer `GetTailPosition` yöntemleriyle gibi kullanılabilir [CRBTree::GetKeyAt](#getkeyat) veya [CRBTree::GetPrev](#getprev) ağacı gezme ve değerleri almak için.

##  <a name="getvalueat"></a>  CRBTree::GetValueAt

Belirli bir konumda depolanan değeri almak için bu yöntemi çağırın `CRBTree` nesne.

```
const V& GetValueAt(POSITION pos) const throw();
V& GetValueAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konum sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="return-value"></a>Dönüş Değeri

Belirtilen konumda depolanan değeri bir başvuru döndürür `CRBTree` nesne.

##  <a name="isempty"></a>  CRBTree::IsEmpty

Boş bir ağaç nesne için test etmek için bu yöntemi çağırın.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Ağaç değilse FALSE değerini boş, TRUE döndürür.

##  <a name="kinargtype"></a>  CRBTree::KINARGTYPE

Bir giriş bağımsız değişkeni bir anahtar geçirildiğinde kullanılan türü.

```
typedef KTraits::INARGTYPE KINARGTYPE;
```

##  <a name="koutargtype"></a>  CRBTree::KOUTARGTYPE

Çıkış bağımsız değişken olarak bir anahtar döndürüldüğünde kullanılan türü.

```
typedef KTraits::OUTARGTYPE KOUTARGTYPE;
```

##  <a name="removeall"></a>  CRBTree::RemoveAll

Tüm öğeleri kaldırmak için bu yöntemi çağırın `CRBTree` nesne.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Temizler `CRBTree` öğeleri depolamak için kullanılan bellek boşaltma nesnesi.

##  <a name="removeat"></a>  CRBTree::RemoveAt

Belirtilen konumda bir öğe kaldırmak için bu yöntemi çağırın `CRBTree` nesne.

```
void RemoveAt(POSITION pos) throw();
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konum sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

### <a name="remarks"></a>Açıklamalar

Belirtilen konumda depolanan anahtar/değer çifti kaldırır. Öğe depolamak için kullanılan bellek serbest bırakılır. KONUMU tarafından başvurulan *pos* geçersiz hale gelir ve aynı sırada herhangi bir öğe konumu ağacında yaptıkları mutlaka geçerli kalırken korur.

##  <a name="setvalueat"></a>  CRBTree::SetValueAt

Belirli bir konumda depolanan değeri değiştirmek için bu yöntemi çağırın `CRBTree` nesne.

```
void SetValueAt(POSITION pos, VINARGTYPE value);
```

### <a name="parameters"></a>Parametreler

*POS*<br/>
Gibi yöntemleri için önceki bir çağrı tarafından döndürülen konum sayaç [CRBTree::GetHeadPosition](#getheadposition) veya [CRBTree::FindFirstKeyAfter](#findfirstkeyafter).

*value*<br/>
Eklenecek değer `CRBTree` nesne.

### <a name="remarks"></a>Açıklamalar

Belirtilen konumda depolanan değer öğesini değiştirir `CRBTree` nesne.

##  <a name="vinargtype"></a>  CRBTree::VINARGTYPE

Kullanılması için bir giriş bağımsız değişkeni geçirilen bir değer türü.

```
typedef VTraits::INARGTYPE VINARGTYPE;
```

##  <a name="voutargtype"></a>  CRBTree::VOUTARGTYPE

Çıkış bağımsız değişken olarak geçirilen bir değer olduğunda kullanılan türü.

```
typedef VTraits::OUTARGTYPE VOUTARGTYPE;
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfına genel bakış](../../atl/atl-class-overview.md)
