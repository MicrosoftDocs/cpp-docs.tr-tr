---
title: CAtlArray Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CAtlArray
- ATLCOLL/ATL::CAtlArray
- ATLCOLL/ATL::Add
- ATLCOLL/ATL::Append
- ATLCOLL/ATL::AssertValid
- ATLCOLL/ATL::Copy
- ATLCOLL/ATL::FreeExtra
- ATLCOLL/ATL::GetAt
- ATLCOLL/ATL::GetCount
- ATLCOLL/ATL::GetData
- ATLCOLL/ATL::InsertArrayAt
- ATLCOLL/ATL::InsertAt
- ATLCOLL/ATL::IsEmpty
- ATLCOLL/ATL::RemoveAll
- ATLCOLL/ATL::RemoveAt
- ATLCOLL/ATL::SetAt
- ATLCOLL/ATL::SetAtGrow
- ATLCOLL/ATL::SetCount
- ATLCOLL/ATL::INARGTYPE
- ATLCOLL/ATL::OUTARGTYPE
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
ms.openlocfilehash: 85168af654d3d63e06559486b464938b7fd90ad3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81321568"
---
# <a name="catlarray-class"></a>CAtlArray Sınıfı

Bu sınıf bir dizi nesnesi uygular.

## <a name="syntax"></a>Sözdizimi

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```

#### <a name="parameters"></a>Parametreler

*E*<br/>
Dizide depolanacak veri türü.

*EÖzellikler*<br/>
Öğeleri kopyalamak veya taşımak için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Ekle](#add)|Dizi nesnesine bir öğe eklemek için bu yöntemi çağırın.|
|[Ekle](#append)|Bir dizinin içeriğini diğerinin sonuna eklemek için bu yöntemi arayın.|
|[AssertValid](#assertvalid)|Dizi nesnesinin geçerli olduğunu doğrulamak için bu yöntemi arayın.|
|[Catlarray](#catlarray)|Oluşturucu.|
|[~CAtlArray](#dtor)|Yıkıcı.|
|[Kopyala](#copy)|Bir dizinin öğelerini diğerine kopyalamak için bu yöntemi arayın.|
|[Ücretsiz Ekstra](#freeextra)|Dizideki boş öğeleri kaldırmak için bu yöntemi arayın.|
|[Getat](#getat)|Dizi nesnesinden tek bir öğe almak için bu yöntemi çağırın.|
|[GetCount](#getcount)|Dizide depolanan öğe sayısını döndürmek için bu yöntemi arayın.|
|[GetData](#getdata)|Dizideki ilk öğeye bir işaretçi döndürmek için bu yöntemi çağırın.|
|[InsertArrayAt](#insertarrayat)|Bir diziyi diğerine eklemek için bu yöntemi arayın.|
|[ınsertat](#insertat)|Dizi nesnesine yeni bir öğe (veya bir öğenin birden çok kopyası) eklemek için bu yöntemi çağırın.|
|[ısempty](#isempty)|Dizi boş olup olmadığını sınamak için bu yöntemi arayın.|
|[RemoveAll](#removeall)|Tüm öğeleri dizi nesnesinden kaldırmak için bu yöntemi çağırın.|
|[RemoveAt](#removeat)|Diziden bir veya daha fazla öğeyi kaldırmak için bu yöntemi çağırın.|
|[Setat](#setat)|Dizi nesnesindeki bir öğenin değerini ayarlamak için bu yöntemi çağırın.|
|[SetatGrow](#setatgrow)|Dizi nesnesindeki bir öğenin değerini ayarlamak ve diziyi gerektiği gibi genişletmek için bu yöntemi çağırın.|
|[SetCount](#setcount)|Dizi nesnesinin boyutunu ayarlamak için bu yöntemi çağırın.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operatör &#91;&#93;](#operator_at)|Dizideki bir öğeye bir başvuru döndürmek için bu işleci çağırın.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[INARGTYPE](#inargtype)|Diziye öğe eklemek için kullanılacak veri türü.|
|[OUTARGTYPE](#outargtype)|Diziden öğeleri almak için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

`CAtlArray`kullanıcı tanımlı türdeki bir dizi öğe oluşturmak ve yönetmek için yöntemler sağlar. Standart C dizilerine benzer `CAtlArray` olsa da, nesne dinamik olarak küçülebilir ve gerektiği gibi büyüyebilir. Dizi dizini her zaman 0 konumunda başlar ve üst sınır düzeltilebilir veya yeni öğeler eklendikçe genişlemesine izin verilir.

Az sayıda öğeye sahip diziler için ATL sınıfı [CSimpleArray](../../atl/reference/csimplearray-class.md) kullanılabilir.

`CAtlArray`MFC'nin `CArray` sınıfıyla yakından ilişkilidir ve serileştirme desteği olmasa da bir MFC projesinde çalışacaktır.

Daha fazla bilgi için [ATL Koleksiyon Sınıfları'na](../../atl/atl-collection-classes.md)bakın.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll.h

## <a name="catlarrayadd"></a><a name="add"></a>CAtlArray::Ekle

Dizi nesnesine bir öğe eklemek için bu yöntemi çağırın.

```
size_t Add(INARGTYPE element);
size_t Add();
```

### <a name="parameters"></a>Parametreler

*Öğe*<br/>
Diziye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin dizinini döndürür.

### <a name="remarks"></a>Açıklamalar

Yeni öğe dizinin sonuna eklenir. Öğe sağlanmazsa, boş bir öğe eklenir; diğer bir deyişle, dizi gerçek bir öğe eklenmiştir gibi boyutu artar. İşlem başarısız olursa, [AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow) E_OUTOFMEMORY bağımsız değişkeni ile çağrılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]

## <a name="catlarrayappend"></a><a name="append"></a>CAtlArray::Ek

Bir dizinin içeriğini diğerinin sonuna eklemek için bu yöntemi arayın.

```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Parametreler

*aSrc*<br/>
Eklemek için dizi.

### <a name="return-value"></a>Dönüş Değeri

İlk eklenen öğenin dizinini döndürür.

### <a name="remarks"></a>Açıklamalar

Sağlanan dizideki öğeler varolan dizinin sonuna eklenir. Gerekirse, bellek yeni öğeleri karşılamak için tahsis edilecektir.

Diziler aynı türde olmalıdır ve bir diziyi kendisine iliştirmek mümkün değildir.

Hata ayıklama yapılarında, `CAtlArray` bağımsız değişken geçerli bir dizi değilse veya *aSrc* aynı nesneye başvuruyorsa bir ATLASSERT yükseltilir. Sürüm oluşturur, geçersiz bağımsız değişkenler öngörülemeyen davranışlara yol açabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]

## <a name="catlarrayassertvalid"></a><a name="assertvalid"></a>CAtlArray::AssertValid

Dizi nesnesinin geçerli olduğunu doğrulamak için bu yöntemi arayın.

```
void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

Dizi nesnesi geçerli değilse, ATLASSERT bir iddia atar. Bu yöntem yalnızca _DEBUG tanımlanırsa kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]

## <a name="catlarraycatlarray"></a><a name="catlarray"></a>CAtlArray::CAtlArray

Oluşturucu.

```
CAtlArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Dizi nesnesini başharfe alır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]

## <a name="catlarraycatlarray"></a><a name="dtor"></a>CAtlArray::~CAtlArray

Yıkıcı.

```
~CAtlArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Dizi nesnesi tarafından kullanılan tüm kaynakları boşaltıyor.

## <a name="catlarraycopy"></a><a name="copy"></a>CAtlArray::Kopyala

Bir dizinin öğelerini diğerine kopyalamak için bu yöntemi arayın.

```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Parametreler

*aSrc*<br/>
Bir diziye kopyalanması gereken öğelerin kaynağı.

### <a name="remarks"></a>Açıklamalar

Bir dizinin öğelerini başka bir dizinin öğeleriyle birlikte yazmak için bu yöntemi çağırın. Gerekirse, bellek yeni öğeleri karşılamak için tahsis edilecektir. Bir dizinin öğelerini kendisine kopyalamak mümkün değildir.

Dizinin varolan içeriği korunacaksa, [CAtlArray kullanın::Bunun](#append) yerine Ekedin.

Hata ayıklama yapılarında, varolan `CAtlArray` nesne geçerli değilse veya *aSrc* aynı nesneye başvuruyorsa bir ATLASSERT yükseltilir. Sürüm oluşturur, geçersiz bağımsız değişkenler öngörülemeyen davranışlara yol açabilir.

> [!NOTE]
> `CAtlArray::Copy`[CAutoPtr](../../atl/reference/cautoptr-class.md) sınıfı yla oluşturulan öğelerden oluşan dizileri desteklemez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]

## <a name="catlarrayfreeextra"></a><a name="freeextra"></a>CAtlArray::FreeExtra

Dizideki boş öğeleri kaldırmak için bu yöntemi arayın.

```
void FreeExtra() throw();
```

### <a name="remarks"></a>Açıklamalar

Boş öğeler kaldırılır, ancak dizinin boyutu ve üst sınırı değişmeden kalır.

Hata ayıklama yapılarında, CAtlArray nesnesi geçerli değilse veya dizi en büyük boyutunu aşarsa bir ATLASSERT yükseltilir.

## <a name="catlarraygetat"></a><a name="getat"></a>CAtlArray::GetAt

Dizi nesnesinden tek bir öğe almak için bu yöntemi çağırın.

```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```

### <a name="parameters"></a>Parametreler

*ıelement*<br/>
Döndürülecek dizi öğesinin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

Gerekli dizi öğesine bir başvuru verir.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, *iElement* dizideki öğe sayısını aşarsa bir ATLASSERT yükseltilir. Sürüm oluşturur, geçersiz bir argüman öngörülemeyen davranışa neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]

## <a name="catlarraygetcount"></a><a name="getcount"></a>CAtlArray::GetCount

Dizide depolanan öğe sayısını döndürmek için bu yöntemi arayın.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizide depolanan öğe sayısını verir.

### <a name="remarks"></a>Açıklamalar

Dizideki ilk öğe 0 konumunda olduğundan, döndürülen `GetCount` değer her zaman en büyük dizinden 1 daha büyüktür.

### <a name="example"></a>Örnek

[CAtlArray örneğine bakın:GetAt](#getat).

## <a name="catlarraygetdata"></a><a name="getdata"></a>CAtlArray::Veri Alın

Dizideki ilk öğeye bir işaretçi döndürmek için bu yöntemi çağırın.

```
E* GetData() throw();
const E* GetData() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki ilk öğeyi depolayan bellek konumuna bir işaretçi döndürür. Kullanılabilir öğe yoksa, NULL döndürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]

## <a name="catlarrayinargtype"></a><a name="inargtype"></a>CAtlArray::INARGTYPE

Diziye öğe eklemek için kullanılacak veri türü.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

## <a name="catlarrayinsertarrayat"></a><a name="insertarrayat"></a>CAtlArray::InsertArrayAt

Bir diziyi diğerine eklemek için bu yöntemi arayın.

```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```

### <a name="parameters"></a>Parametreler

*iBaşlat*<br/>
Dizinin eklendiği dizin.

*paYeni*<br/>
Eklenecek dizi.

### <a name="remarks"></a>Açıklamalar

*paNew* dizisindeki öğeler *iStart*öğesinden başlayarak dizi nesnesine kopyalanır. Varolan dizi öğeleri, üzerine yazılmayı önlemek için taşınır.

Hata ayıklama oluştururda, `CAtlArray` nesne geçerli değilse veya *paNew* işaretçisi NULL veya geçersizse bir ATLASSERT yükseltilir.

> [!NOTE]
> `CAtlArray::InsertArrayAt`[CAutoPtr](../../atl/reference/cautoptr-class.md) sınıfı yla oluşturulan öğelerden oluşan dizileri desteklemez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]

## <a name="catlarrayinsertat"></a><a name="insertat"></a>CAtlArray::InsertAt

Dizi nesnesine yeni bir öğe (veya bir öğenin birden çok kopyası) eklemek için bu yöntemi çağırın.

```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```

### <a name="parameters"></a>Parametreler

*ıelement*<br/>
Öğe nin veya öğelerin eklenecek olduğu dizin.

*Öğe*<br/>
Eklenecek öğe veya öğelerin değeri.

*nSayısı*<br/>
Eklenecek öğe sayısı.

### <a name="remarks"></a>Açıklamalar

*dizii iElement'ten*başlayarak diziye bir veya daha fazla öğe ekler. Varolan öğeler, üzerine yazılmaktan kaçınmak için taşınır.

Hata ayıklama yapılarda, `CAtlArray` nesne geçersizse, eklenecek öğe sayısı sıfırsa veya birleştirilmiş öğe sayısı dizinin içeremeyecek kadar büyükse, bir ATLASSERT yükseltilir. Perakende yapılarda, geçersiz parametrelerin geçirilmesi öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]

## <a name="catlarrayisempty"></a><a name="isempty"></a>CAtlArray::IsEmpty

Dizi boş olup olmadığını sınamak için bu yöntemi arayın.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizi boşsa, aksi takdirde yanlış ise doğru döndürür.

### <a name="remarks"></a>Açıklamalar

Öğe içermisse diziboş olduğu söylenir. Bu nedenle, dizi boş öğeler içerse bile, boş değildir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]

## <a name="catlarrayoperator-"></a><a name="operator_at"></a>CAtlArray::operatör []

Dizideki bir öğeye bir başvuru döndürmek için bu işleci çağırın.

```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```

### <a name="parameters"></a>Parametreler

*ıelement*<br/>
Döndürülecek dizi öğesinin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

Gerekli dizi öğesine bir başvuru verir.

### <a name="remarks"></a>Açıklamalar

CAtlArray benzer bir işlev icra [eder::GetAt](#getat). MFC sınıfı [CArray](../../mfc/reference/carray-class.md)aksine, bu işleç [CAtlArray yerine kullanılamaz::SetAt](#setat).

Hata ayıklama yapılarında, *iElement* dizideki toplam öğe sayısını aşarsa bir ATLASSERT yükseltilir. Perakende yapılarda, geçersiz bir parametre öngörülemeyen sonuçlara neden olabilir.

## <a name="catlarrayoutargtype"></a><a name="outargtype"></a>CAtlArray::OUTARGTYPE

Diziden öğeleri almak için kullanılacak veri türü.

```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```

## <a name="catlarrayremoveall"></a><a name="removeall"></a>CAtlArray::RemoveAll

Tüm öğeleri dizi nesnesinden kaldırmak için bu yöntemi çağırın.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm öğeleri dizi nesnesinden kaldırır.

Bu yöntem, diziyi yeniden boyutlandırmak için [CAtlArray::SetCount](#setcount) çağırır ve daha sonra ayrılan tüm belleği serbest bırakalır.

### <a name="example"></a>Örnek

[CAtlArray örneğine bakın::Boş.](#isempty)

## <a name="catlarrayremoveat"></a><a name="removeat"></a>CAtlArray::RemoveAt

Diziden bir veya daha fazla öğeyi kaldırmak için bu yöntemi çağırın.

```
void RemoveAt(size_t iElement, size_t nCount = 1);
```

### <a name="parameters"></a>Parametreler

*ıelement*<br/>
Kaldırılacak ilk öğenin dizini.

*nSayısı*<br/>
Kaldırılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Diziden bir veya daha fazla öğe kaldırır. Kalan öğeler aşağı kaydırılır. Üst sınır karara bağlanır, ancak CAtlArray'e yapılan bir çağrı yapılana kadar bellek serbest [bırakılmaz::FreeExtra](#freeextra) yapılır.

Hata ayıklama yapılarda, `CAtlArray` nesne geçerli değilse veya *iElement* ve *nCount'nin* toplam toplamı dizideki toplam öğe sayısını aşıyorsa bir ATLASSERT yükseltilir. Perakende yapılarda, geçersiz parametreler öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]

## <a name="catlarraysetat"></a><a name="setat"></a>CAtlArray::SetAt

Dizi nesnesindeki bir öğenin değerini ayarlamak için bu yöntemi çağırın.

```
void SetAt(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*ıelement*<br/>
Ayarlanan dizi öğesini gösteren dizin.

*Öğe*<br/>
Belirtilen öğenin yeni değeri.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, *iElement* dizideki öğe sayısını aşarsa bir ATLASSERT yükseltilir. Perakende yapılarda, geçersiz bir parametre öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

[CAtlArray örneğine bakın:GetAt](#getat).

## <a name="catlarraysetcount"></a><a name="setcount"></a>CAtlArray::SetCount

Dizi nesnesinin boyutunu ayarlamak için bu yöntemi çağırın.

```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```

### <a name="parameters"></a>Parametreler

*nNewSize*<br/>
Dizinin gerekli boyutu.

*nGrowBy*<br/>
Arabellek yapmak için ne kadar büyük belirlemek için kullanılan bir değer. -1 değeri, dahili olarak hesaplanan bir değerin kullanılmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Dizi başarıyla yeniden boyutlandırılırsa doğru döndürür, aksi takdirde yanlış.

### <a name="remarks"></a>Açıklamalar

Dizi boyutu artırılabilir veya azaltılabilir. Artırılırsa, diziye fazladan boş öğeler eklenir. Azaltılırsa, en büyük endekslere sahip öğeler silinir ve bellek serbest bırakılır.

Kullanmadan önce dizinin boyutunu ayarlamak için bu yöntemi kullanın. `SetCount` Kullanılmazsa, öğeleri ekleme işlemi -ve sonraki bellek ayırma sı gerçekleştirilir- performansı ve parça belleği azaltır.

### <a name="example"></a>Örnek

[CAtlArray örneğine bakın:GetData](#getdata).

## <a name="catlarraysetatgrow"></a><a name="setatgrow"></a>CAtlArray::SetAtGrow

Dizi nesnesindeki bir öğenin değerini ayarlamak ve diziyi gerektiği gibi genişletmek için bu yöntemi çağırın.

```
void SetAtGrow(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*ıelement*<br/>
Ayarlanan dizi öğesini gösteren dizin.

*Öğe*<br/>
Belirtilen öğenin yeni değeri.

### <a name="remarks"></a>Açıklamalar

Dizin tarafından işaret edilen öğenin değerini değiştirir. *iElement* dizinin geçerli boyutundan büyükse, [catlArray::SetCount'a](#setcount)yapılan bir çağrı kullanılarak dizi otomatik olarak artırılır. Hata ayıklama yapılarında, `CAtlArray` nesne geçerli değilse bir ATLASSERT yükseltilir. Perakende yapılarda, geçersiz parametreler öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MMXSwarm Numunesi](../../overview/visual-cpp-samples.md)<br/>
[DinamikTüketici Örneği](../../overview/visual-cpp-samples.md)<br/>
[GüncellemePV Örneği](../../overview/visual-cpp-samples.md)<br/>
[Marquee Örnek](../../overview/visual-cpp-samples.md)<br/>
[CArray Sınıfı](../../mfc/reference/carray-class.md)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
