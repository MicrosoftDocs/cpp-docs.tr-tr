---
title: CAtlArray sınıfı
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
ms.openlocfilehash: 6a0b83f722d1b616e9c10713646d337f9cb090a4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78864898"
---
# <a name="catlarray-class"></a>CAtlArray sınıfı

Bu sınıf bir dizi nesnesi uygular.

## <a name="syntax"></a>Sözdizimi

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```

#### <a name="parameters"></a>Parametreler

*A*<br/>
Dizide depolanacak veri türü.

*Oy*<br/>
Öğeleri kopyalamak veya taşımak için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Add](#add)|Dizi nesnesine bir öğesi eklemek için bu yöntemi çağırın.|
|[Ýna](#append)|Bir dizinin içeriğini diğerinin sonuna eklemek için bu yöntemi çağırın.|
|[AssertValid](#assertvalid)|Dizi nesnesinin geçerli olduğunu doğrulamak için bu yöntemi çağırın.|
|[CAtlArray](#catlarray)|Oluşturucu.|
|[~ CAtlArray](#dtor)|Yok edicisi.|
|[Kopyala](#copy)|Bir dizinin öğelerini diğerine kopyalamak için bu yöntemi çağırın.|
|[FreeExtra](#freeextra)|Dizideki boş öğeleri kaldırmak için bu yöntemi çağırın.|
|[GetAt](#getat)|Dizi nesnesinden tek bir öğe almak için bu yöntemi çağırın.|
|[GetCount](#getcount)|Dizide depolanan öğelerin sayısını döndürmek için bu yöntemi çağırın.|
|[GetData](#getdata)|Dizideki ilk öğeye bir işaretçi döndürmek için bu yöntemi çağırın.|
|[Insertarrayat](#insertarrayat)|Bir diziyi diğerine eklemek için bu yöntemi çağırın.|
|[InsertAt](#insertat)|Dizi nesnesine yeni bir öğe (veya bir öğenin birden çok kopyasını) eklemek için bu yöntemi çağırın.|
|[IsEmpty](#isempty)|Dizinin boş olup olmadığını test etmek için bu yöntemi çağırın.|
|[RemoveAll](#removeall)|Dizi nesnesinden tüm öğeleri kaldırmak için bu yöntemi çağırın.|
|[RemoveAt](#removeat)|Diziden bir veya daha fazla öğeyi kaldırmak için bu yöntemi çağırın.|
|[SetAt](#setat)|Dizi nesnesindeki bir öğenin değerini ayarlamak için bu yöntemi çağırın.|
|[SetAtGrow](#setatgrow)|Dizi nesnesindeki bir öğenin değerini ayarlamak için bu yöntemi çağırın, diziyi gereken şekilde genişleterek.|
|[SetCount](#setcount)|Dizi nesnesinin boyutunu ayarlamak için bu yöntemi çağırın.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işlecinde&#91;&#93;](#operator_at)|Dizideki bir öğeye başvuru döndürmek için bu işleci çağırın.|

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[INARGTYPE](#inargtype)|Diziye öğe eklemek için kullanılacak veri türü.|
|[OUTARGTYPE](#outargtype)|Diziden öğeleri almak için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

`CAtlArray`, Kullanıcı tanımlı bir türdeki öğelerin dizisini oluşturmak ve yönetmek için yöntemler sağlar. Standart C dizilerine benzer olsa da, `CAtlArray` nesnesi, gerektiğinde dinamik olarak küçültülebilir ve büyüyebilir. Dizi dizini her zaman 0 konumunda başlar ve üst sınır düzeltilebilir veya yeni öğe eklendikçe genişlemesine izin verilebilir.

Az sayıda öğe içeren diziler için, [CSimpleArray](../../atl/reference/csimplearray-class.md) ATL sınıfı kullanılabilir.

`CAtlArray` MFC 'nin `CArray` sınıfı ile yakından ilgilidir ve bir MFC projesinde çalışarak serileştirme desteği yoktur.

Daha fazla bilgi için bkz. [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcoll. h

##  <a name="add"></a>CAtlArray:: Add

Dizi nesnesine bir öğesi eklemek için bu yöntemi çağırın.

```
size_t Add(INARGTYPE element);
size_t Add();
```

### <a name="parameters"></a>Parametreler

*dosyalarında*<br/>
Diziye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin dizinini döndürür.

### <a name="remarks"></a>Açıklamalar

Yeni öğe dizinin sonuna eklenir. Hiçbir öğe sağlanmazsa, boş bir öğe eklenir; diğer bir deyişle, dizi gerçek bir öğe eklenmiş olsa da boyutu artar. İşlem başarısız olursa, [AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow) e_outofmemory bağımsız değişkeniyle çağırılır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]

##  <a name="append"></a>CAtlArray:: Append

Bir dizinin içeriğini diğerinin sonuna eklemek için bu yöntemi çağırın.

```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Parametreler

*aSrc*<br/>
Eklenecek dizi.

### <a name="return-value"></a>Dönüş Değeri

İlk eklenen öğenin dizinini döndürür.

### <a name="remarks"></a>Açıklamalar

Sağlanan dizideki öğeler var olan dizinin sonuna eklenir. Gerekirse, bellek yeni öğeleri kapsayacak şekilde ayrılacaktır.

Diziler aynı türde olmalıdır ve bir diziyi kendisine eklemek mümkün değildir.

Hata ayıklama yapılarında, `CAtlArray` bağımsız değişkeni geçerli bir dizi değilse veya *aSrc* aynı nesneye başvuruyorsa bir ATLASSERT oluşur. Yayın yapılarında geçersiz bağımsız değişkenler öngörülemeyen davranışlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]

##  <a name="assertvalid"></a>CAtlArray:: AssertValid

Dizi nesnesinin geçerli olduğunu doğrulamak için bu yöntemi çağırın.

```
void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

Dizi nesnesi geçerli değilse ATLASSERT bir onaylama işlemi oluşturur. Bu yöntem yalnızca _DEBUG tanımlanmışsa kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]

##  <a name="catlarray"></a>CAtlArray::CAtlArray

Oluşturucu.

```
CAtlArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Dizi nesnesini başlatır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]

##  <a name="dtor"></a>CAtlArray:: ~ CAtlArray

Yok edicisi.

```
~CAtlArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Dizi nesnesi tarafından kullanılan kaynakları boşaltır.

##  <a name="copy"></a>CAtlArray:: Copy

Bir dizinin öğelerini diğerine kopyalamak için bu yöntemi çağırın.

```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Parametreler

*aSrc*<br/>
Bir diziye kopyalanacak öğelerin kaynağı.

### <a name="remarks"></a>Açıklamalar

Başka bir dizinin öğeleriyle bir dizinin öğelerinin üzerine yazmak için bu yöntemi çağırın. Gerekirse, bellek yeni öğeleri kapsayacak şekilde ayrılacaktır. Bir dizinin öğelerinin kendisine kopyalanması mümkün değildir.

Dizinin varolan içeriği korunmak ise bunun yerine [CAtlArray:: Append](#append) kullanın.

Hata ayıklama yapılarında, mevcut `CAtlArray` nesnesi geçerli değilse veya *aSrc* aynı nesneye başvuruyorsa bir ATLASSERT oluşur. Yayın yapılarında geçersiz bağımsız değişkenler öngörülemeyen davranışlara neden olabilir.

> [!NOTE]
> `CAtlArray::Copy`, [CAutoPtr](../../atl/reference/cautoptr-class.md) sınıfıyla oluşturulan öğelerden oluşan dizileri desteklemez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]

##  <a name="freeextra"></a>CAtlArray:: FreeExtra

Dizideki boş öğeleri kaldırmak için bu yöntemi çağırın.

```
void FreeExtra() throw();
```

### <a name="remarks"></a>Açıklamalar

Boş öğeler kaldırılır, ancak dizinin boyutu ve üst sınırı değişmeden kalır.

Hata ayıklama yapılarında, CAtlArray nesnesi geçerli değilse veya dizi en büyük boyutunu aşacaksa bir ATLASSERT tetiklenir.

##  <a name="getat"></a>CAtlArray:: GetAt

Dizi nesnesinden tek bir öğeyi almak için bu yöntemi çağırın.

```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Döndürülecek dizi öğesinin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

Gerekli dizi öğesine bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, *IElement* dizideki öğe sayısını AŞARSA BIR ATLASSERT tetiklenir. Yayın yapıları içinde geçersiz bir bağımsız değişken öngörülemeyen davranışlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]

##  <a name="getcount"></a>CAtlArray:: GetCount

Dizide depolanan öğelerin sayısını döndürmek için bu yöntemi çağırın.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizide depolanan öğe sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Dizideki ilk öğe 0 konumunda olduğunda, `GetCount` tarafından döndürülen değer her zaman en büyük dizinden 1 büyüktür.

### <a name="example"></a>Örnek

[CAtlArray:: GetAt](#getat)için örneğe bakın.

##  <a name="getdata"></a>CAtlArray:: GetData

Dizideki ilk öğeye bir işaretçi döndürmek için bu yöntemi çağırın.

```
E* GetData() throw();
const E* GetData() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki ilk öğeyi depolayan bellek konumuna bir işaretçi döndürür. Hiçbir öğe yoksa, NULL döndürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]

##  <a name="inargtype"></a>CAtlArray:: ıNARGTYPE

Diziye öğe eklemek için kullanılacak veri türü.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

##  <a name="insertarrayat"></a>CAtlArray:: ınsertarrayat

Bir diziyi diğerine eklemek için bu yöntemi çağırın.

```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```

### <a name="parameters"></a>Parametreler

*Isdan Başlat*<br/>
Dizinin ekleneceği dizin.

*Paneni*<br/>
Eklenecek dizi.

### <a name="remarks"></a>Açıklamalar

Dizideki öğeler, öğe *ıBaşlat*öğesinden *başlayarak dizi nesnesine* kopyalanır. Geçersiz kılınmamak için mevcut dizi öğeleri taşınır.

Hata ayıklama yapılarında, `CAtlArray` nesne geçerli değilse veya *Paneni* işaretçisi null ya da geçersiz Ise BIR ATLASSERT tetiklenir.

> [!NOTE]
> `CAtlArray::InsertArrayAt`, [CAutoPtr](../../atl/reference/cautoptr-class.md) sınıfıyla oluşturulan öğelerden oluşan dizileri desteklemez.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]

##  <a name="insertat"></a>CAtlArray:: InsertAt

Dizi nesnesine yeni bir öğe (veya bir öğenin birden çok kopyasını) eklemek için bu yöntemi çağırın.

```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Öğe veya öğelerin ekleneceği dizin.

*dosyalarında*<br/>
Eklenecek öğe veya öğelerin değeri.

*nCount*<br/>
Eklenecek öğe sayısı.

### <a name="remarks"></a>Açıklamalar

*IElement*dizininde başlayan diziye bir veya daha fazla öğe ekler. Varolan öğeler, üzerine yazılmaması için taşınır.

Hata ayıklama yapılarında, `CAtlArray` nesnesi geçersizse, eklenecek öğe sayısı sıfır veya dizi öğe sayısı dizinin içermesi için çok büyük olduğunda bir ATLASSERT oluşur. Perakende derlemelerde, geçersiz parametrelerin geçirilmesi öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]

##  <a name="isempty"></a>CAtlArray:: IsEmpty

Dizinin boş olup olmadığını test etmek için bu yöntemi çağırın.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizi boşsa true, değilse false döndürür.

### <a name="remarks"></a>Açıklamalar

Dizi hiçbir öğe içermiyorsa, dizi boş olarak kabul edilir. Bu nedenle, dizi boş öğeler içeriyorsa bile boş değildir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]

##  <a name="operator_at"></a>CAtlArray:: operator []

Dizideki bir öğeye başvuru döndürmek için bu işleci çağırın.

```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Döndürülecek dizi öğesinin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

Gerekli dizi öğesine bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

[CAtlArray:: GetAt](#getat)için benzer bir işlev gerçekleştirir. MFC sınıfından [CArray](../../mfc/reference/carray-class.md)'in aksine, bu işleç [CAtlArray:: SetAt](#setat)için bir alternatif olarak kullanılamaz.

Hata ayıklama yapılarında, *IElement* dizideki toplam öğe sayısını AŞARSA BIR ATLASSERT tetiklenir. Perakende derlemelerde, geçersiz bir parametre öngörülemeyen sonuçlara neden olabilir.

##  <a name="outargtype"></a>CAtlArray:: OUTARGTYPE

Diziden öğeleri almak için kullanılacak veri türü.

```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```

##  <a name="removeall"></a>CAtlArray:: RemoveAll

Dizi nesnesinden tüm öğeleri kaldırmak için bu yöntemi çağırın.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm öğeleri dizi nesnesinden kaldırır.

Bu yöntem, diziyi yeniden boyutlandırmak için [CAtlArray:: SetCount](#setcount) çağırır ve ardından ayrılan tüm belleği serbest bırakır.

### <a name="example"></a>Örnek

[CAtlArray:: IsEmpty](#isempty)için örneğe bakın.

##  <a name="removeat"></a>CAtlArray:: RemoveAt

Diziden bir veya daha fazla öğeyi kaldırmak için bu yöntemi çağırın.

```
void RemoveAt(size_t iElement, size_t nCount = 1);
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Kaldırılacak ilk öğenin dizini.

*nCount*<br/>
Kaldırılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Diziden bir veya daha fazla öğeyi kaldırır. Kalan tüm öğeler aşağı kaydıralınır. Üst sınır azaltılır, ancak [CAtlArray:: FreeExtra](#freeextra) çağrısı yapılıncaya kadar bellek serbest bırakılmaz.

Hata ayıklama yapılarında, `CAtlArray` nesnesi geçerli değilse veya birleştirilmiş toplam *IElement* ve *nCount* öğeleri dizideki toplam öğe SAYıSıNı AŞARSA bir atlassert tetiklenir. Perakende derlemelerde, geçersiz parametreler öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]

##  <a name="setat"></a>CAtlArray:: SetAt

Dizi nesnesindeki bir öğenin değerini ayarlamak için bu yöntemi çağırın.

```
void SetAt(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Ayarlanacak dizi öğesine işaret eden dizin.

*dosyalarında*<br/>
Belirtilen öğenin yeni değeri.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, *IElement* dizideki öğe sayısını AŞARSA BIR ATLASSERT tetiklenir. Perakende derlemelerde, geçersiz bir parametre öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

[CAtlArray:: GetAt](#getat)için örneğe bakın.

##  <a name="setcount"></a>CAtlArray:: SetCount

Dizi nesnesinin boyutunu ayarlamak için bu yöntemi çağırın.

```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```

### <a name="parameters"></a>Parametreler

*nNewSize*<br/>
Dizinin gerekli boyutu.

*nGrowBy*<br/>
Arabelleği ne kadar büyük hale getirmek için kullanılan bir değer. -1 değeri, dahili olarak hesaplanan değerin kullanılmasına neden olur.

### <a name="return-value"></a>Dönüş Değeri

Dizi başarıyla yeniden boyutlandırılırsa true, aksi takdirde false döndürür.

### <a name="remarks"></a>Açıklamalar

Dizi, boyutta artırılabilir veya azaltılabilir. Daha fazla, daha fazla boş öğe diziye eklenir. Azaldıysanız, en büyük indisi olan öğeler silinir ve bellekten serbest bırakılır.

Kullanmadan önce dizinin boyutunu ayarlamak için bu yöntemi kullanın. `SetCount` kullanılmazsa, öğe ekleme işlemi ve gerçekleştirilen sonraki bellek ayırma, performansı ve parça belleğini azaltır.

### <a name="example"></a>Örnek

[CAtlArray:: GetData](#getdata)örneğine bakın.

##  <a name="setatgrow"></a>CAtlArray:: SetAtGrow

Dizi nesnesindeki bir öğenin değerini ayarlamak için bu yöntemi çağırın, diziyi gereken şekilde genişleterek.

```
void SetAtGrow(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Ayarlanacak dizi öğesine işaret eden dizin.

*dosyalarında*<br/>
Belirtilen öğenin yeni değeri.

### <a name="remarks"></a>Açıklamalar

Dizin tarafından işaret edilen öğenin değerini değiştirir. *IElement* dizinin geçerli boyutundan büyükse dizi [CAtlArray:: SetCount](#setcount)çağrısı kullanılarak otomatik olarak artırılır. Hata ayıklama yapılarında, `CAtlArray` nesnesi geçerli değilse bir ATLASSERT oluşur. Perakende derlemelerde, geçersiz parametreler öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[Mmxsısınma örneği](../../overview/visual-cpp-samples.md)<br/>
[DynamicConsumer örneği](../../overview/visual-cpp-samples.md)<br/>
[UpdatePV örneği](../../overview/visual-cpp-samples.md)<br/>
[Kayan yazı örneği](../../overview/visual-cpp-samples.md)<br/>
[CArray Sınıfı](../../mfc/reference/carray-class.md)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
