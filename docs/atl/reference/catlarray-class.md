---
title: CAtlArray sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CAtlArray class
ms.assetid: 0b503aa8-2357-40af-a326-6654bf1da098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c08387d5c1a2a9b9b757bab7a8112783a3810065
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097802"
---
# <a name="catlarray-class"></a>CAtlArray sınıfı

Bu sınıf, bir dizi nesnesi uygular.

## <a name="syntax"></a>Sözdizimi

```
template<typename E, class ETraits = CElementTraits<E>>
class CAtlArray
```

#### <a name="parameters"></a>Parametreler

*E*<br/>
Dizide depolanan verinin türü.

*ETraits*<br/>
Kopyalama veya öğeleri taşıma için kullanılan kod.

## <a name="members"></a>Üyeler

### <a name="methods"></a>Yöntemler

|||
|-|-|
|[Add](#add)|Dizi nesnesi için bir öğe eklemek için bu yöntemi çağırın.|
|[Ekleme](#append)|Bir dizinin içeriğini başka bir sonuna eklemek için bu yöntemi çağırın.|
|[AssertValid](#assertvalid)|Dizi nesnesi geçerli olduğundan emin olmak için bu yöntemi çağırın.|
|[CAtlArray](#catlarray)|Oluşturucu.|
|[~ CAtlArray](#dtor)|Yıkıcı.|
|[kopyalama](#copy)|Bir dizinin öğeleri diğerine kopyalamak için bu yöntemi çağırın.|
|[FreeExtra](#freeextra)|Herhangi bir boş öğe diziden kaldırmak için bu yöntemi çağırın.|
|[GetAt](#getat)|Tek bir öğe dizisi nesneyi almak için bu yöntemi çağırın.|
|[GetCount](#getcount)|Dizide depolanan öğelerin sayısını döndürmek için bu yöntemi çağırın.|
|[GetData](#getdata)|Dizideki ilk öğe için bir işaretçiyi döndürmek için bu yöntemi çağırın.|
|[InsertArrayAt](#insertarrayat)|Bir dizi diğerine eklemek için bu yöntemi çağırın.|
|[InsertAt](#insertat)|Dizi nesnesi yeni bir öğe (veya birden çok kopyasını bir öğe) eklemek için bu yöntemi çağırın.|
|[IsEmpty](#isempty)|Dizi boş olup olmadığını test etmek için bu yöntemi çağırın.|
|[RemoveAll](#removeall)|Dizi nesneden tüm öğeleri kaldırmak için bu yöntemi çağırın.|
|[RemoveAt](#removeat)|Bir veya daha fazla öğe diziden kaldırmak için bu yöntemi çağırın.|
|[SetAt](#setat)|Dizi nesnesinde bir öğenin değerini ayarlamak için bu yöntemi çağırın.|
|[SetAtGrow](#setatgrow)|Gerektiği gibi bir dizi genişletme dizi nesnesinde, bir öğenin değerini ayarlamak için bu yöntemi çağırın.|
|[SetCount](#setcount)|Dizi nesnesi boyutunu ayarlamak için bu yöntemi çağırın.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işleci&#91;&#93;](#operator_at)|Dizide bir öğeye başvuru döndürmek için bu işleci çağırın.|  

### <a name="typedefs"></a>Tür tanımları

|||
|-|-|
|[INARGTYPE](#inargtype)|Diziye öğeleri eklemek için kullanılacak veri türü.|
|[OUTARGTYPE](#outargtype)|Diziden öğeleri almak için kullanılacak veri türü.|

## <a name="remarks"></a>Açıklamalar

`CAtlArray` oluşturma ve kullanıcı tanımlı bir tür öğelerinin bir dizisini yönetme için yöntemleri sağlar. Standart C dizilerine benzer ancak `CAtlArray` nesne, dinamik olarak daraltmak ve gerektikçe büyütün. Dizi dizini her zaman 0 konumunda başlar ve üst sınırı sabit veya yeni öğeleri eklendikçe genişletmek için izin verilen.

Küçük bir dizi öğe, ATL sınıfı içeren diziler için [CSimpleArray](../../atl/reference/csimplearray-class.md) kullanılabilir.

`CAtlArray` MFC'nin için yakından ilgili `CArray` sınıfı ve bir MFC projesinde paralelleştirmeye serileştirme desteği olmadan çalışır.

Daha fazla bilgi için [ATL koleksiyon sınıfları](../../atl/atl-collection-classes.md).

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcoll.h

##  <a name="add"></a>  CAtlArray::Add

Dizi nesnesi için bir öğe eklemek için bu yöntemi çağırın.

```
size_t Add(INARGTYPE element);
size_t Add();
```

### <a name="parameters"></a>Parametreler

*Öğesi*<br/>
Diziye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Eklenen öğenin dizinini döndürür.

### <a name="remarks"></a>Açıklamalar

Yeni öğe, dizinin sonuna eklenir. Boş bir öğe eklendiğinde sağlanan herhangi bir öğe ise; diğer bir deyişle, gerçek bir öğe eklendi ancak dizi boyutu artar. İşlem başarısız olursa [çeşitlemeleri](debugging-and-error-reporting-global-functions.md#atlthrow) E_OUTOFMEMORY bağımsız değişkenle çağrıldığında.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#1](../../atl/codesnippet/cpp/catlarray-class_1.cpp)]

##  <a name="append"></a>  CAtlArray::Append

Bir dizinin içeriğini başka bir sonuna eklemek için bu yöntemi çağırın.

```
size_t Append(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Parametreler

*aSrc*<br/>
Ekleneceği dizi.

### <a name="return-value"></a>Dönüş Değeri

Eklenen ilk öğenin indisini döndürür.

### <a name="remarks"></a>Açıklamalar

Sağlanan dizideki öğelerin mevcut dizinin sonuna eklenir. Gerekirse, yeni öğeleri yerleştirmek için bellek tahsis edilir.

Diziler aynı türde olmalıdır ve bir dizi kendisine eklemek mümkün değildir.

Hata ayıklama yapılarında, bir ATLASSERT gerçekleştirilecektir `CAtlArray` bağımsız değişkeni geçerli bir dizi değil veya *aSrc* aynı nesneye başvurur. Sürüm yapılandırmasında geçersiz bağımsız değişkenler için öngörülemeyen davranışlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#2](../../atl/codesnippet/cpp/catlarray-class_2.cpp)]

##  <a name="assertvalid"></a>  CAtlArray::AssertValid

Dizi nesnesi geçerli olduğundan emin olmak için bu yöntemi çağırın.

```
void AssertValid() const;
```

### <a name="remarks"></a>Açıklamalar

Dizi nesnesi geçerli değilse ATLASSERT onaylama durum oluşturur. Bu yöntem, yalnızca _DEBUG tanımlıysa kullanılabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#3](../../atl/codesnippet/cpp/catlarray-class_3.cpp)]

##  <a name="catlarray"></a>  CAtlArray::CAtlArray

Oluşturucu.

```
CAtlArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Dizi nesnesi başlatır.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#4](../../atl/codesnippet/cpp/catlarray-class_4.cpp)]

##  <a name="dtor"></a>  CAtlArray:: ~ CAtlArray

Yıkıcı.

```
~CAtlArray() throw();
```

### <a name="remarks"></a>Açıklamalar

Dizi nesnesi tarafından kullanılan tüm kaynakları serbest bırakır.

##  <a name="copy"></a>  CAtlArray::Copy

Bir dizinin öğeleri diğerine kopyalamak için bu yöntemi çağırın.

```
void Copy(const CAtlArray<E, ETraits>& aSrc);
```

### <a name="parameters"></a>Parametreler

*aSrc*<br/>
Bir diziye kopyalanacak öğe kaynağı.

### <a name="remarks"></a>Açıklamalar

Bir dizinin öğeleri başka bir dizinin öğeleri ile üzerine yazmak için bu yöntemi çağırın. Gerekirse, yeni öğeleri yerleştirmek için bellek tahsis edilir. Bir dizinin öğeleri kendisine kopyalamak mümkün değildir.

Varolan bir dizinin içeriğini tutulacak kullanırsanız [CAtlArray::Append](#append) yerine.

Hata ayıklama yapılarında, bir ATLASSERT gerçekleştirilecektir varolan `CAtlArray` nesnesi geçerli değil veya *aSrc* aynı nesneye başvurur. Sürüm yapılandırmasında geçersiz bağımsız değişkenler için öngörülemeyen davranışlara neden olabilir.

> [!NOTE]
> `CAtlArray::Copy` ile oluşturulan öğeleri oluşan dizi desteklemiyor [CAutoPtr](../../atl/reference/cautoptr-class.md) sınıfı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#5](../../atl/codesnippet/cpp/catlarray-class_5.cpp)]

##  <a name="freeextra"></a>  CAtlArray::FreeExtra

Herhangi bir boş öğe diziden kaldırmak için bu yöntemi çağırın.

```
void FreeExtra() throw();
```

### <a name="remarks"></a>Açıklamalar

Boş öğeleri kaldırılır, ancak boyutu ve dizi çokluğun değişmeden kalır.

Hata ayıklama derlemelerinde, CAtlArray nesnesi geçerli değil veya dizinin en büyük boyutunu aşacak bir ATLASSERT gerçekleştirilecektir.

##  <a name="getat"></a>  CAtlArray::GetAt

Çağrı bu yöntem için tek bir öğe dizisi nesneden alır.

```
const E& GetAt(size_t iElement) const throw();
E& GetAt(size_t iElement) throw();
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Döndürülecek dizi öğesinin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

Gerekli bir dizi öğesine bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, bir ATLASSERT gerçekleştirilecektir *IElement* dizideki öğelerin sayısını aşıyor. Sürüm yapılandırmasında geçersiz bir bağımsız değişken beklenmeyen davranışa neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#6](../../atl/codesnippet/cpp/catlarray-class_6.cpp)]

##  <a name="getcount"></a>  CAtlArray::GetCount

Dizide depolanan öğelerin sayısını döndürmek için bu yöntemi çağırın.

```
size_t GetCount() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizide depolanan öğelerin sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Dizideki ilk öğe 0 konumunda olduğundan, değer tarafından döndürülen `GetCount` her zaman 1 en büyük dizinden daha büyüktür.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlArray::GetAt](#getat).

##  <a name="getdata"></a>  CAtlArray::GetData

Dizideki ilk öğe için bir işaretçiyi döndürmek için bu yöntemi çağırın.

```
E* GetData() throw();
const E* GetData() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki ilk öğe depolama bellek konumuna bir işaretçi döndürür. Hiçbir öğe yoksa NULL döndürülür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#7](../../atl/codesnippet/cpp/catlarray-class_7.cpp)]

##  <a name="inargtype"></a>  CAtlArray::INARGTYPE

Diziye öğeleri eklemek için kullanılacak veri türü.

```
typedef ETraits::INARGTYPE INARGTYPE;
```

##  <a name="insertarrayat"></a>  CAtlArray::InsertArrayAt

Bir dizi diğerine eklemek için bu yöntemi çağırın.

```
void InsertArrayAt(size_t iStart, const CAtlArray<E, ETraits>* paNew);
```

### <a name="parameters"></a>Parametreler

*iStart*<br/>
Diziye eklenecek olan dizini.

*paNew*<br/>
Ekleneceği dizi.

### <a name="remarks"></a>Açıklamalar

Dizi öğeleri *paNew* öğesinde başlayarak, bir dizi nesnesi içine kopyalanır *iStart*. Var olan bir dizi öğeleri, üzerine yazılmasını engellemek için taşınır.

Hata ayıklama yapılarında, bir ATLASSERT gerçekleştirilecektir `CAtlArray` nesnesi geçerli değil veya *paNew* işaretçisidir NULL veya geçersiz.

> [!NOTE]
> `CAtlArray::InsertArrayAt` ile oluşturulan öğeleri oluşan dizi desteklemiyor [CAutoPtr](../../atl/reference/cautoptr-class.md) sınıfı.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#8](../../atl/codesnippet/cpp/catlarray-class_8.cpp)]

##  <a name="insertat"></a>  CAtlArray::InsertAt

Dizi nesnesi yeni bir öğe (veya birden çok kopyasını bir öğe) eklemek için bu yöntemi çağırın.

```
void InsertAt(size_t iElement, INARGTYPE element, size_t nCount = 1);
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Eklenecek öğe veya öğeleri nerede olduğunuza dizini.

*Öğesi*<br/>
Veya birden çok eklenecek öğe değeri.

*nCount*<br/>
Eklenecek öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Dizinden başlayarak bir diziye bir veya daha fazla öğe ekler *IElement*. Var olan öğelerin üzerine yazılmasını engellemek için taşınır.

Hata ayıklama yapılarında, bir ATLASSERT gerçekleştirilecektir `CAtlArray` Nesne geçersiz, eklenecek öğe sayısı sıfıra eşit veya öğelerin toplam sayısını içerecek şekilde dizi için çok büyük. Perakende sürümlerde geçersiz parametreler geçirme öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#9](../../atl/codesnippet/cpp/catlarray-class_9.cpp)]

##  <a name="isempty"></a>  CAtlArray::IsEmpty

Dizi boş olup olmadığını test etmek için bu yöntemi çağırın.

```
bool IsEmpty() const throw();
```

### <a name="return-value"></a>Dönüş Değeri

Dizi yanlış Aksi takdirde boş ise, true döndürür.

### <a name="remarks"></a>Açıklamalar

Dizi hiç öğe içeriyorsa, boş olarak kabul edilir. Dizi boş öğeleri içeriyorsa bile, bu nedenle, bunu boş değil.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#10](../../atl/codesnippet/cpp/catlarray-class_10.cpp)]

##  <a name="operator_at"></a>  CAtlArray::operator]

Dizide bir öğeye başvuru döndürmek için bu işleci çağırın.

```
E& operator[](size_t ielement) throw();
const E& operator[](size_t ielement) const throw();
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Döndürülecek dizi öğesinin dizin değeri.

### <a name="return-value"></a>Dönüş Değeri

Gerekli bir dizi öğesine bir başvuru döndürür.

### <a name="remarks"></a>Açıklamalar

Benzer bir işlevi gerçekleştiren [CAtlArray::GetAt](#getat). MFC sınıfı aksine [CArray](../../mfc/reference/carray-class.md), yerine bu işleci kullanılamaz [CAtlArray::SetAt](#setat).

Hata ayıklama yapılarında, bir ATLASSERT gerçekleştirilecektir *IElement* dizideki öğelerin toplam sayısını aşıyor. Perakende sürümlerde geçersiz bir parametre öngörülemeyen sonuçlara neden olabilir.

##  <a name="outargtype"></a>  CAtlArray::OUTARGTYPE

Diziden öğeleri almak için kullanılacak veri türü.

```
typedef ETraits::OUTARGTYPE OUTARGTYPE;
```

##  <a name="removeall"></a>  CAtlArray::RemoveAll

Dizi nesneden tüm öğeleri kaldırmak için bu yöntemi çağırın.

```
void RemoveAll() throw();
```

### <a name="remarks"></a>Açıklamalar

Tüm öğeleri dizi nesnesinden kaldırır.

Bu yöntemin çağırdığı [CAtlArray::SetCount](#setcount) dizinin yeniden boyutlandırmak için ve daha sonra ayrılan belleği serbest bırakır.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlArray::IsEmpty](#isempty).

##  <a name="removeat"></a>  CAtlArray::RemoveAt

Bir veya daha fazla öğe diziden kaldırmak için bu yöntemi çağırın.

```
void RemoveAt(size_t iElement, size_t nCount = 1);
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Kaldırılacak ilk öğenin dizini.

*nCount*<br/>
Kaldırılacak öğe sayısı.

### <a name="remarks"></a>Açıklamalar

Bir veya daha fazla öğe diziden kaldırır. Kalan öğeler kaydırılan. Üst sınır azaltılır, ancak bellek çağrısı kadar serbest değil [CAtlArray::FreeExtra](#freeextra) yapılır.

Hata ayıklama yapılarında, bir ATLASSERT gerçekleştirilecektir `CAtlArray` nesnesi geçerli değil veya toplam *IElement* ve *nCount* dizideki öğelerin toplam sayısını aşıyor. Perakende sürümlerde geçersiz parametreler öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#11](../../atl/codesnippet/cpp/catlarray-class_11.cpp)]

##  <a name="setat"></a>  CAtlArray::SetAt

Dizi nesnesinde bir öğenin değerini ayarlamak için bu yöntemi çağırın.

```
void SetAt(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Ayarlanacak dizi öğesine işaret eden dizini.

*Öğesi*<br/>
Belirtilen öğenin yeni değeri.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, bir ATLASSERT gerçekleştirilecektir *IElement* dizideki öğelerin sayısını aşıyor. Perakende sürümlerde geçersiz bir parametre içinde öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlArray::GetAt](#getat).

##  <a name="setcount"></a>  CAtlArray::SetCount

Dizi nesnesi boyutunu ayarlamak için bu yöntemi çağırın.

```
bool SetCount(size_t nNewSize, int nGrowBy = - 1);
```

### <a name="parameters"></a>Parametreler

*nNewSize*<br/>
Dizinin gerekli boyutu.

*nGrowBy*<br/>
Bir değer belirlemek için kullanılan arabellek hale getirmek için ne kadar büyük. -1 değeri, kullanılacak dahili olarak hesaplanmış bir değeri neden olur.

### <a name="return-value"></a>Dönüş Değeri

Dizi başarılı bir şekilde yeniden boyutlandırılan, yanlış Aksi halde ise true döndürür.

### <a name="remarks"></a>Açıklamalar

Dizi artırabilir veya boyutu azaltılabilir. Artırılmış ek boş öğeleri diziye eklenir. Azaltılabilir, en büyük dizinler ile öğeler silinecek ve bellek serbest.

Kullanmadan önce dizinin boyutunu ayarlamak için bu yöntemi kullanın. Varsa `SetCount` kullanılmıyorsa, öğeleri ekleme işlemini — ve sonraki bellek ayırma işlemi yapılmadan — performansı azaltabileceği ve parçalara bellek.

### <a name="example"></a>Örnek

Örneğin bakın [CAtlArray::GetData](#getdata).

##  <a name="setatgrow"></a>  CAtlArray::SetAtGrow

Gerektiği gibi bir dizi genişletme dizi nesnesinde, bir öğenin değerini ayarlamak için bu yöntemi çağırın.

```
void SetAtGrow(size_t iElement, INARGTYPE element);
```

### <a name="parameters"></a>Parametreler

*IElement*<br/>
Ayarlanacak dizi öğesine işaret eden dizini.

*Öğesi*<br/>
Belirtilen öğenin yeni değeri.

### <a name="remarks"></a>Açıklamalar

İşaret dizine göre öğe değerini değiştirir. Varsa *IElement* geçerli boyuttan daha büyük bir dizi dizi otomatik olarak yapılan bir çağrı kullanılarak artırılır [CAtlArray::SetCount](#setcount). Hata ayıklama yapılarında, bir ATLASSERT gerçekleştirilecektir `CAtlArray` nesnesi geçerli değil. Perakende sürümlerde geçersiz parametreler öngörülemeyen sonuçlara neden olabilir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#12](../../atl/codesnippet/cpp/catlarray-class_12.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[MMXSwarm örnek](../../visual-cpp-samples.md)<br/>
[DynamicConsumer örnek](../../visual-cpp-samples.md)<br/>
[Oluşturma](../../visual-cpp-samples.md)<br/>
[Kayan örnek](../../visual-cpp-samples.md)<br/>
[CArray Sınıfı](../../mfc/reference/carray-class.md)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
