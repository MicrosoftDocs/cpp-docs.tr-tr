---
title: CArray Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CArray
- AFXTEMPL/CArray
- AFXTEMPL/CArray::CArray
- AFXTEMPL/CArray::Add
- AFXTEMPL/CArray::Append
- AFXTEMPL/CArray::Copy
- AFXTEMPL/CArray::ElementAt
- AFXTEMPL/CArray::FreeExtra
- AFXTEMPL/CArray::GetAt
- AFXTEMPL/CArray::GetCount
- AFXTEMPL/CArray::GetData
- AFXTEMPL/CArray::GetSize
- AFXTEMPL/CArray::GetUpperBound
- AFXTEMPL/CArray::InsertAt
- AFXTEMPL/CArray::IsEmpty
- AFXTEMPL/CArray::RemoveAll
- AFXTEMPL/CArray::RemoveAt
- AFXTEMPL/CArray::SetAt
- AFXTEMPL/CArray::SetAtGrow
- AFXTEMPL/CArray::SetSize
helpviewer_keywords:
- CArray [MFC], CArray
- CArray [MFC], Add
- CArray [MFC], Append
- CArray [MFC], Copy
- CArray [MFC], ElementAt
- CArray [MFC], FreeExtra
- CArray [MFC], GetAt
- CArray [MFC], GetCount
- CArray [MFC], GetData
- CArray [MFC], GetSize
- CArray [MFC], GetUpperBound
- CArray [MFC], InsertAt
- CArray [MFC], IsEmpty
- CArray [MFC], RemoveAll
- CArray [MFC], RemoveAt
- CArray [MFC], SetAt
- CArray [MFC], SetAtGrow
- CArray [MFC], SetSize
ms.assetid: fead8b00-4cfd-4625-ad0e-251df62ba92f
ms.openlocfilehash: 3355e72c58365e97f8f3f8ce09754285f671915a
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/22/2020
ms.locfileid: "81753970"
---
# <a name="carray-class"></a>CArray Sınıfı

C dizileri gibi olan, ancak dinamik olarak azaltıp gerektiğinde büyüyebilecek dizileri destekler.

## <a name="syntax"></a>Sözdizimi

```
template <class TYPE, class ARG_TYPE = const TYPE&>
class CArray : public CObject
```

#### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Dizide depolanan nesnelerin türünü belirten şablon parametresi. *TYPE* tarafından döndürülen bir `CArray`parametredir.

*ARG_TYPE*<br/>
Dizide depolanan nesnelere erişmek için kullanılan bağımsız değişken türünü belirten şablon parametresi. Genellikle *TYPE*için bir başvuru . *ARG_TYPE'* ye `CArray`geçirilen bir parametredir.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CArray::CArray](#carray)|Boş bir dizi oluşturuyor.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CArray::Ekle](#add)|Dizinin sonuna bir öğe ekler; gerekirse diziyi büyütür.|
|[CArray::Ek](#append)|Diziye başka bir dizi ekler; gerekirse dizi yi büyütür|
|[CArray::Kopyala](#copy)|Başka bir diziyi diziye kopyalar; gerekirse diziyi büyütür.|
|[CArray::elementat](#elementat)|Dizi içindeki öğe işaretçisine geçici bir başvuru verir.|
|[CArray::FreeExtra](#freeextra)|Tüm kullanılmayan belleği geçerli üst sınır üzerinde serbest eder.|
|[CArray::Getat](#getat)|Belirli bir dizindeki değeri döndürür.|
|[CArray::GetCount](#getcount)|Bu dizideki öğelerin sayısını alır.|
|[CArray::Veri Alma](#getdata)|Dizideki öğelere erişim sağlar. NULL olabilir.|
|[CArray::Getsize](#getsize)|Bu dizideki öğelerin sayısını alır.|
|[CArray::GetUpperBound](#getupperbound)|En büyük geçerli dizini döndürür.|
|[CArray::InsertAt](#insertat)|Belirli bir dizide bir öğe (veya başka bir dizideki tüm öğeler) ekler.|
|[CArray::Boş](#isempty)|Dizinin boş olup olmadığını belirler.|
|[CArray::RemoveAll](#removeall)|Bu dizideki tüm öğeleri kaldırır.|
|[CArray::Removeat](#removeat)|Belirli bir dizindeki bir öğeyi kaldırır.|
|[CArray::Setat](#setat)|Belirli bir dizinin değerini ayarlar; dizi büyümeye izin verilmez.|
|[CArray::Setatgrow](#setatgrow)|Belirli bir dizinin değerini ayarlar; gerekirse diziyi büyütür.|
|[CArray::SetSize](#setsize)|Bu dizide yer alan öğe sayısını ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[operatör&#91;&#93;](#operator_at)|Belirtilen dizilişte öğeyi ayarlar veya alır.|

## <a name="remarks"></a>Açıklamalar

Dizi dizinleri her zaman 0 konumundan başlar. Geçerli sınırı aştığınızda üst sınırı düzeltmeye veya dizinin genişlemesini mi etkinleştirmeye karar verebilirsiniz. Bellek, bazı öğeler null olsa bile, üst sınıra bitişik olarak ayrılır.

> [!NOTE]
> Bir `CArray` nesneyi yeniden boyutlandıran veya ona öğe ekleyen yöntemlerin çoğu, öğeleri taşımak için [memcpy_s](../../c-runtime-library/reference/memcpy-s-wmemcpy-s.md) kullanır. Bu bir sorundur, çünkü `memcpy_s` oluşturucunun çağrılmasını gerektiren nesnelerle uyumlu değildir. Öğeler `CArray` ile `memcpy_s`uyumlu değilse, uygun boyutta yeni `CArray` bir oluşturmanız gerekir. Daha sonra [CArray kullanmanız gerekir::Kopyala](#copy) ve [CArray::SetAt](#setat) yerine bir atama `memcpy_s`işleci kullanmak, çünkü bu yöntemler in yeni dizi doldurmak için .

C dizisinde olduğu gibi, `CArray` dizilimöğesinin erişim süresi sabittir ve dizi boyutundan bağımsızdır.

> [!TIP]
> Bir dizi kullanmadan önce, boyutunu oluşturmak ve bellek ayırmak için [SetSize'ı](#setsize) kullanın. `SetSize`Kullanmazsanız, dizinize öğe eklemek, dizinin sık sık yeniden tahsis edilmesine ve kopyalanmasını sağlar. Sık yeniden tahsis ve kopyalama verimsizdir ve belleği parçalayabilir.

Bir dizideki tek tek öğelerin dökümüne ihtiyacınız varsa, [CDumpContext](../../mfc/reference/cdumpcontext-class.md) nesnesinin derinliğini 1 veya daha büyük olarak ayarlamanız gerekir.

Bu sınıfın belirli üye işlevleri, `CArray` sınıfın çoğu kullanımı için özelleştirilmiş olması gereken genel yardımcı işlevleri çağırır. MFC Makrolar ve Geneller bölümündeki [Toplama Sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md) konusuna bakın.

Dizi sınıfı türetme liste türetme gibidir.

Nasıl kullanılacağı `CArray`hakkında daha fazla bilgi [için,](../../mfc/collections.md)makale Koleksiyonları'na bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

`CArray`

## <a name="requirements"></a>Gereksinimler

**Başlık:** afxtempl.h

## <a name="carrayadd"></a><a name="add"></a>CArray::Ekle

Dizinin sonuna yeni bir öğe ekleyerek diziyi 1 büyütür.

```
INT_PTR Add(ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*ARG_TYPE*<br/>
Bu dizideki öğelere başvuran bağımsız değişkenlerin türünü belirten şablon parametresi.

*newElement*<br/>
Bu diziye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin dizin.

### <a name="remarks"></a>Açıklamalar

[SetSize](#setsize) 1'den büyük `nGrowBy` bir değerle kullanılmışsa, fazladan bellek ayrılabilir. Ancak, üst sınır sadece 1 artacaktır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#22](../../mfc/codesnippet/cpp/carray-class_1.cpp)]

## <a name="carrayappend"></a><a name="append"></a>CArray::Ek

Bir dizinin içeriğini diğerinin sonuna eklemek için bu üye işlevi arayın.

```
INT_PTR Append(const CArray& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
Bir diziye eklenecek öğelerin kaynağı.

### <a name="return-value"></a>Dönüş Değeri

İlk eklenen öğenin dizini.

### <a name="remarks"></a>Açıklamalar

Diziler aynı türde olmalıdır.

Gerekirse, `Append` diziye eklenen öğeleri yerleştirmek için ek bellek ayırabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#23](../../mfc/codesnippet/cpp/carray-class_2.cpp)]

## <a name="carraycarray"></a><a name="carray"></a>CArray::CArray

Boş bir dizi oluşturuyor.

```
CArray();
```

### <a name="remarks"></a>Açıklamalar

Dizi, aynı anda bir öğe büyür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#24](../../mfc/codesnippet/cpp/carray-class_3.cpp)]

## <a name="carraycopy"></a><a name="copy"></a>CArray::Kopyala

Bir dizinin öğelerini diğerine kopyalamak için bu üye işlevi kullanın.

```cpp
void Copy(const CArray& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
Bir diziye kopyalanacak öğelerin kaynağı.

### <a name="remarks"></a>Açıklamalar

Bir dizinin öğelerini başka bir dizinin öğeleriyle birlikte yazmak için bu üye işlevi arayın.

`Copy`bellek serbest değildir; ancak, gerekirse, `Copy` diziye kopyalanan öğeleri yerleştirmek için ek bellek ayırabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#25](../../mfc/codesnippet/cpp/carray-class_4.cpp)]

## <a name="carrayelementat"></a><a name="elementat"></a>CArray::elementat

Dizi içinde belirtilen öğeye geçici bir başvuru verir.

```
TYPE& ElementAt(INT_PTR nIndex);
const TYPE& ElementAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[GetUpperBound](#getupperbound)tarafından döndürülen değerden daha büyük veya 0'a eşit ve daha az veya eşit olan bir sonsayı dizini.

### <a name="return-value"></a>Dönüş Değeri

Bir dizi öğesine başvuru.

### <a name="remarks"></a>Açıklamalar

Diziler için sol taraftaki atama işlecinin uygulanması için kullanılır.

### <a name="example"></a>Örnek

  [GetSize](#getsize)için örneğe bakın.

## <a name="carrayfreeextra"></a><a name="freeextra"></a>CArray::FreeExtra

Dizi büyütülme sırasında ayrılan tüm ekstra belleği serbest eder.

```cpp
void FreeExtra();
```

### <a name="remarks"></a>Açıklamalar

Bu işlev, dizinin boyutu veya üst sınırı üzerinde hiçbir etkisi yoktur.

### <a name="example"></a>Örnek

  [GetData](#getdata)örneğine bakın.

## <a name="carraygetat"></a><a name="getat"></a>CArray::Getat

Belirtilen dizideki dizi öğesini döndürür.

```
TYPE& GetAt(INT_PTR nIndex);
const TYPE& GetAt(INT_PTR nIndex) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Dizi elemanlarının türünü belirten şablon parametresi.

*Nındex*<br/>
[GetUpperBound](#getupperbound)tarafından döndürülen değerden daha büyük veya 0'a eşit ve daha az veya eşit olan bir sonsayı dizini.

### <a name="return-value"></a>Dönüş Değeri

Dizi öğesi şu anda bu dizide.

### <a name="remarks"></a>Açıklamalar

Negatif bir değer ingeçirilmesi veya döndürülen `GetUpperBound` değerden büyük bir değerin geçirilmesi başarısız bir iddiayla sonuçlanır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#26](../../mfc/codesnippet/cpp/carray-class_5.cpp)]

## <a name="carraygetcount"></a><a name="getcount"></a>CArray::GetCount

Dizi öğelerinin sayısını verir.

```
INT_PTR GetCount() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki öğelerin sayısı.

### <a name="remarks"></a>Açıklamalar

Dizideki öğe sayısını almak için bu yöntemi çağırın. Dizinler sıfır tabanlı olduğundan, boyutu 1 en büyük dizin daha büyüktür. Bu yöntemi çağırmak CArray ile aynı sonucu [oluşturur::GetSize](#getsize) yöntemi.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#27](../../mfc/codesnippet/cpp/carray-class_6.cpp)]

## <a name="carraygetdata"></a><a name="getdata"></a>CArray::Veri Alma

Bir dizideki öğelere doğrudan erişim sağlamak için bu üye işlevi kullanın.

```
const TYPE* GetData() const;
TYPE* GetData();
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Dizi elemanlarının türünü belirten şablon parametresi.

### <a name="return-value"></a>Dönüş Değeri

Bir dizi öğesi için bir işaretçi.

### <a name="remarks"></a>Açıklamalar

Kullanılabilir öğe yoksa, `GetData` null değeri döndürür.

Bir dizinin öğelerine doğrudan erişim daha hızlı çalışmanıza yardımcı olsa `GetData`da, ararken dikkatli olun; yaptığınız hatalar doğrudan dizinizin öğelerini etkiler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#28](../../mfc/codesnippet/cpp/carray-class_7.cpp)]

## <a name="carraygetsize"></a><a name="getsize"></a>CArray::Getsize

Dizinin boyutunu döndürür.

```
INT_PTR GetSize() const;
```

### <a name="remarks"></a>Açıklamalar

Dizinler sıfır tabanlı olduğundan, boyutu 1 en büyük dizin daha büyüktür. Bu yöntemi çağırmak [CArray::GetCount](#getcount) yöntemiyle aynı sonucu oluşturur.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#29](../../mfc/codesnippet/cpp/carray-class_8.cpp)]

## <a name="carraygetupperbound"></a><a name="getupperbound"></a>CArray::GetUpperBound

Bu dizinin geçerli üst sınırını döndürür.

```
INT_PTR GetUpperBound() const;
```

### <a name="remarks"></a>Açıklamalar

Dizi dizinleri sıfır tabanlı olduğundan, bu işlev `GetSize`değeri 1'den daha az döndürür.

Durum `GetUpperBound( )` = -1 dizi hiçbir öğe içerdiğini gösterir.

### <a name="example"></a>Örnek

  CArray örneğine [bakın:GetAt](#getat).

## <a name="carrayinsertat"></a><a name="insertat"></a>CArray::InsertAt

Bir dizideki `InsertAt` belirli bir diziye bir öğe (veya bir öğenin birden çok kopyası) ekler ilk sürümü.

```cpp
void InsertAt(
    INT_PTR nIndex,
    ARG_TYPE newElement,
    INT_PTR nCount = 1);

void InsertAt(
    INT_PTR nStartIndex,
    CArray* pNewArray);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Tarafından döndürülen değerden büyük olabilecek bir `GetUpperBound`karşılayon dizini.

*ARG_TYPE*<br/>
Bu dizideki öğelerin türünü belirten şablon parametresi.

*newElement*<br/>
Bu diziye yerleştirilecek öğe.

*nSayısı*<br/>
Bu öğenin kaç kez eklenmesi gerekir (varsayılan olarak 1).

*nBaşlangıç Endeksi*<br/>
[GetUpperBound](#getupperbound)tarafından döndürülen değerden büyük olabilecek bir sonsayı dizini.

*pNewArray*<br/>
Bu diziye eklenecek öğeleri içeren başka bir dizi.

### <a name="remarks"></a>Açıklamalar

İşlemsırasında, bu dizindeki varolan öğeyi (dizini yükselterek) yukarı kaydırıyor ve üzerindeki tüm öğeleri yukarı kaydırıyor.

İkinci sürüm, *nStartIndex* konumundan `CArray` başlayarak başka bir koleksiyondaki tüm öğeleri ekler.

İşlev, `SetAt` aksine, belirtilen bir dizi öğesi nin yerini alır ve herhangi bir öğeyi kaydırmaz.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#30](../../mfc/codesnippet/cpp/carray-class_9.cpp)]

## <a name="carrayisempty"></a><a name="isempty"></a>CArray::Boş

Dizinin boş olup olmadığını belirler.

```
BOOL IsEmpty() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizi öğe içermisse sıfır olmayan; aksi takdirde 0.

## <a name="carrayoperator-"></a><a name="operator_at"></a>CArray::operatör\[\]

Bu alt komut işleçleri [SetAt](#setat) ve [GetAt](#getat) işlevleri için uygun bir yedek vardır.

```
TYPE& operator[](int_ptr nindex);
const TYPE& operator[](int_ptr nindex) const;
```

### <a name="parameters"></a>Parametreler

*TÜR*<br/>
Bu dizideki öğelerin türünü belirten şablon parametresi.

*Nındex*<br/>
Erişilecek öğenin dizin.

### <a name="remarks"></a>Açıklamalar

**Const**olmayan diziler için çağrılan ilk işleç, atama deyiminin sağında (r değeri) veya sol (l-değeri) kullanılabilir. Const diziler **const** için çağrılan ikinci, yalnızca sağda kullanılabilir.

Kitaplığın Hata Ayıklama sürümü, alt yazının (atama deyiminin solunda veya sağ tarafında) sınırların dışında olduğunu ileri sürer.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#34](../../mfc/codesnippet/cpp/carray-class_10.cpp)]

## <a name="carrayrelocateelements"></a><a name="relocateelements"></a>CArray::RelocateElements

Dizi büyüyüp küçüldüğünde verileri yeni bir arabelleğe yerdeğiştirir.

```
template<class TYPE, class ARG_TYPE>
AFX_INLINE void CArray<TYPE, ARG_TYPE>::RelocateElements(
    TYPE* pNewData,
    const TYPE* pData,
    INT_PTR nCount);
```

### <a name="parameters"></a>Parametreler

*pNewData*<br/>
Öğeler dizisi için yeni bir arabellek.

*Pdata*<br/>
Eski öğeler dizisi.

*nSayısı*<br/>
Eski dizideki öğe sayısı.

### <a name="remarks"></a>Açıklamalar

*pNewData* her zaman tüm *pData* öğelerini tutacak kadar büyüktür.

[CArray](../../mfc/reference/carray-class.md) uygulaması, dizi büyüyüp küçülmesi gerektiğinde [(SetSize](#setsize) veya [FreeExtra](#freeextra) çağrıldığında) eski verileri yeni bir arabelleğe kopyalamak için bu yöntemi kullanır. Varsayılan uygulama yalnızca verileri kopyalar.

Bir öğenin kendi üyelerinden birine işaretçi içerdiği veya başka bir yapının dizi öğelerinden birine işaretçi içerdiği diziler için işaretçiler düz kopyada güncelleştiredilmez. Bu durumda, ilgili türleri `RelocateElements` ile bir uzmanlık uygulayarak işaretçileri düzeltebilirsiniz. Ayrıca veri kopyalama dan da sorumlusunuz.

## <a name="carrayremoveall"></a><a name="removeall"></a>CArray::RemoveAll

Bu dizideki tüm öğeleri kaldırır.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Dizi zaten boşsa, işlev yine de çalışır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#31](../../mfc/codesnippet/cpp/carray-class_11.cpp)]

## <a name="carrayremoveat"></a><a name="removeat"></a>CArray::Removeat

Bir dizide belirli bir diziden başlayan bir veya daha fazla öğeyi kaldırır.

```cpp
void RemoveAt(
    INT_PTR nIndex,
    INT_PTR nCount = 1);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[GetUpperBound](#getupperbound)tarafından döndürülen değerden daha büyük veya 0'a eşit ve daha az veya eşit olan bir sonsayı dizini.

*nSayısı*<br/>
Kaldırılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

İşlemde, kaldırılan öğenin (ler) üzerindeki tüm öğeleri aşağı kaydırıyor. Dizinin üst sınırını uzatır, ancak belleği boş almaz.

Kaldırma noktasının üzerindeki dizide bulunandan daha fazla öğeyi kaldırmaya çalışırsanız, kitaplığın Hata Ayıklama sürümü ileri sürüler.

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#32](../../mfc/codesnippet/cpp/carray-class_12.cpp)]

## <a name="carraysetat"></a><a name="setat"></a>CArray::Setat

Dizi öğesini belirtilen dizide ayarlar.

```cpp
void SetAt(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
[GetUpperBound](#getupperbound)tarafından döndürülen değerden daha büyük veya 0'a eşit ve daha az veya eşit olan bir sonsayı dizini.

*ARG_TYPE*<br/>
Dizi öğelerine başvurmak için kullanılan bağımsız değişken türünü belirten şablon parametresi.

*newElement*<br/>
Belirtilen konumda depolanacak yeni öğe değeri.

### <a name="remarks"></a>Açıklamalar

`SetAt`dizinin büyümesine neden olmaz. Dizinin otomatik olarak büyümesini istiyorsanız [SetAtGrow'u](#setatgrow) kullanın.

Dizin değerinizin dizide geçerli bir konumu temsil ettiğinden emin olmalısınız. Sınırların dışındaysa, kitaplığın Hata Ayıklama sürümü ileri sürüler.

### <a name="example"></a>Örnek

  [GetAt](#getat)için örneğe bakın.

## <a name="carraysetatgrow"></a><a name="setatgrow"></a>CArray::Setatgrow

Dizi öğesini belirtilen dizide ayarlar.

```cpp
void SetAtGrow(INT_PTR nIndex, ARG_TYPE newElement);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
0'dan büyük veya eşit bir sonsayı dizini.

*ARG_TYPE*<br/>
Dizideki öğelerin türünü belirten şablon parametresi.

*newElement*<br/>
Bu diziye eklenecek öğe. NULL değerine izin verilir.

### <a name="remarks"></a>Açıklamalar

Gerekirse dizi otomatik olarak büyür (diğer bir şekilde üst sınır yeni öğeyi barındıracak şekilde ayarlanır).

### <a name="example"></a>Örnek

[!code-cpp[NVC_MFCCollections#33](../../mfc/codesnippet/cpp/carray-class_13.cpp)]

## <a name="carraysetsize"></a><a name="setsize"></a>CArray::SetSize

Boş veya varolan bir dizinin boyutunu kurar; gerekirse bellek ayırır.

```cpp
void SetSize(
    INT_PTR nNewSize,
    INT_PTR nGrowBy = -1);
```

### <a name="parameters"></a>Parametreler

*nNewSize*<br/>
Yeni dizi boyutu (öğe sayısı). 0 değerinden büyük veya 0 değerine eşit olmalıdır.

*nGrowBy*<br/>
Boyut artışı gerekiyorsa ayrılacak en az öğe yuvası sayısı.

### <a name="remarks"></a>Açıklamalar

Yeni boyut eski boyuttan küçükse, dizi kesilir ve kullanılmayan tüm bellek serbest bırakılır.

Diziyi kullanmaya başlamadan önce dizinizin boyutunu ayarlamak için bu işlevi kullanın. `SetSize`Kullanmazsanız, dizinize öğe eklemek, dizinin sık sık yeniden tahsis edilmesine ve kopyalanmasını sağlar. Sık yeniden tahsis ve kopyalama verimsizdir ve belleği parçalayabilir.

*nGrowBy* parametresi dizi büyürken dahili bellek ayırmaetkiler. Kullanımı [GetSize](#getsize) ve [GetUpperBound](#getupperbound)tarafından bildirilen dizi boyutunu asla etkilemez. Varsayılan değer kullanılırsa, MFC bellek parçalanmasını önlemek ve çoğu servis talebi için verimliliği en iyi duruma getirmek için hesaplanan bir şekilde belleği ayırır.

### <a name="example"></a>Örnek

  [GetData](#getdata)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Örnek TOPLAMA](../../overview/visual-cpp-samples.md)<br/>
[CObject Sınıfı](../../mfc/reference/cobject-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CObArray Sınıfı](../../mfc/reference/cobarray-class.md)<br/>
[Koleksiyon Sınıfı Yardımcıları](../../mfc/reference/collection-class-helpers.md)
