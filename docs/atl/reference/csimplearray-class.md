---
description: 'Daha fazla bilgi edinin: CSimpleArray sınıfı'
title: CSimpleArray sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::CSimpleArray
- ATLSIMPCOLL/ATL::CSimpleArray::Add
- ATLSIMPCOLL/ATL::CSimpleArray::Find
- ATLSIMPCOLL/ATL::CSimpleArray::GetData
- ATLSIMPCOLL/ATL::CSimpleArray::GetSize
- ATLSIMPCOLL/ATL::CSimpleArray::Remove
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAll
- ATLSIMPCOLL/ATL::CSimpleArray::RemoveAt
- ATLSIMPCOLL/ATL::CSimpleArray::SetAtIndex
helpviewer_keywords:
- CSimpleArray class
ms.assetid: ee0c9f39-b61c-4c18-bc43-4eada21dca3a
ms.openlocfilehash: 95750662587c7ab47500a338c3ecd7e74a92eb34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97140796"
---
# <a name="csimplearray-class"></a>CSimpleArray sınıfı

Bu sınıf basit bir diziyi yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>
class CSimpleArray
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Dizide depolanacak veri türü.

*TEqual*<br/>
*T* türü öğeler için eşitlik testini tanımlayarak bir nitelik nesnesi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleArray:: CSimpleArray](#csimplearray)|Basit dizi için Oluşturucu.|
|[CSimpleArray:: ~ CSimpleArray](#dtor)|Basit dizi için yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleArray:: Add](#add)|Diziye yeni bir öğe ekler.|
|[CSimpleArray:: Find](#find)|Dizide bir öğe bulur.|
|[CSimpleArray:: GetData](#getdata)|Dizide depolanan verilere yönelik bir işaretçi döndürür.|
|[CSimpleArray:: GetSize](#getsize)|Dizide depolanan öğe sayısını döndürür.|
|[CSimpleArray:: Remove](#remove)|Belirli bir öğeyi diziden kaldırır.|
|[CSimpleArray:: RemoveAll](#removeall)|Tüm öğeleri diziden kaldırır.|
|[CSimpleArray:: RemoveAt](#removeat)|Belirtilen öğeyi diziden kaldırır.|
|[CSimpleArray:: SetAtIndex](#setatindex)|Dizide belirtilen öğeyi ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CSimpleArray:: işleci\[\]](#operator_at)|Diziden bir öğe alır.|
|[CSimpleArray:: operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

`CSimpleArray` verilen herhangi bir türde basit bir dizi oluşturmak ve yönetmek için yöntemler sağlar `T` .

Parametresi, `TEqual` türü iki öğe için eşitlik işlevi tanımlamayı sağlar `T` . [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)öğesine benzer bir sınıf oluşturarak, belirli bir dizi için eşitlik testinin davranışını değiştirmek mümkündür. Örneğin, bir işaretçiler dizisiyle ilgilenirken, işaretçiler başvurusunun değerlerine bağlı olarak eşitlik tanımlanması yararlı olabilir. Varsayılan uygulama **operator = ()** kullanır.

Hem hem de `CSimpleArray` [CSimpleMap](../../atl/reference/csimplemap-class.md) , az sayıda öğe için tasarlanmıştır. Dizi çok sayıda öğe içerdiğinde [CAtlArray](../../atl/reference/catlarray-class.md) ve [CAtlMap](../../atl/reference/catlmap-class.md) kullanılmalıdır.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlsimpcoll. h

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]

## <a name="csimplearrayadd"></a><a name="add"></a> CSimpleArray:: Add

Diziye yeni bir öğe ekler.

```
BOOL Add(const T& t);
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
Diziye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Öğe diziye başarıyla eklendiyse TRUE, aksi takdirde FALSE döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]

## <a name="csimplearraycsimplearray"></a><a name="csimplearray"></a> CSimpleArray:: CSimpleArray

Dizi nesnesi için Oluşturucu.

```
CSimpleArray(const CSimpleArray<T, TEqual>& src);
CSimpleArray();
```

### <a name="parameters"></a>Parametreler

*src*<br/>
Varolan bir `CSimpleArray` nesnesi.

### <a name="remarks"></a>Açıklamalar

Veri üyelerini başlatır, yeni boş bir `CSimpleArray` nesne veya var olan bir nesnenin bir kopyasını oluşturur `CSimpleArray` .

## <a name="csimplearraycsimplearray"></a><a name="dtor"></a> CSimpleArray:: ~ CSimpleArray

Yok edicisi.

```
~CSimpleArray();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest bırakır.

## <a name="csimplearrayfind"></a><a name="find"></a> CSimpleArray:: Find

Dizide bir öğe bulur.

```
int Find(const T& t) const;
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
Aranacak öğe.

### <a name="return-value"></a>Dönüş Değeri

Bulunan öğenin dizinini veya öğe bulunmazsa-1 ' i döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]

## <a name="csimplearraygetdata"></a><a name="getdata"></a> CSimpleArray:: GetData

Dizide depolanan verilere yönelik bir işaretçi döndürür.

```
T* GetData() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki verilere yönelik bir işaretçi döndürür.

## <a name="csimplearraygetsize"></a><a name="getsize"></a> CSimpleArray:: GetSize

Dizide depolanan öğe sayısını döndürür.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizide depolanan öğe sayısını döndürür.

## <a name="csimplearrayoperator-"></a><a name="operator_at"></a> CSimpleArray:: işleci \[\]

Diziden bir öğe alır.

```
T& operator[](int nindex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Öğe dizini.

### <a name="return-value"></a>Dönüş Değeri

*Nindex* tarafından başvurulan dizinin öğesini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]

## <a name="csimplearrayoperator-"></a><a name="operator_eq"></a> CSimpleArray:: operator =

Atama işleci.

```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
Kopyalanacak dizi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneye bir işaretçi döndürür `CSimpleArray` .

### <a name="remarks"></a>Açıklamalar

Tüm `CSimpleArray` mevcut verileri değiştirerek *src* tarafından başvurulan nesneden tüm öğeleri geçerli dizi nesnesine kopyalar.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]

## <a name="csimplearrayremove"></a><a name="remove"></a> CSimpleArray:: Remove

Belirli bir öğeyi diziden kaldırır.

```
BOOL Remove(const T& t);
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
Diziden kaldırılacak öğe.

### <a name="return-value"></a>Dönüş Değeri

Öğe bulunursa ve kaldırılırsa TRUE, değilse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bir öğe kaldırıldığında dizideki kalan öğeler boş alanı dolduracak şekilde yeniden numaralandırılır.

## <a name="csimplearrayremoveall"></a><a name="removeall"></a> CSimpleArray:: RemoveAll

Tüm öğeleri diziden kaldırır.

```cpp
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Dizide depolanmış olan tüm öğeleri kaldırır.

## <a name="csimplearrayremoveat"></a><a name="removeat"></a> CSimpleArray:: RemoveAt

Belirtilen öğeyi diziden kaldırır.

```
BOOL RemoveAtint nIndex);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Kaldırılacak öğeyi işaret eden dizin.

### <a name="return-value"></a>Dönüş Değeri

Öğe kaldırılmışsa TRUE, Dizin geçersizse FALSE döndürür.

### <a name="remarks"></a>Açıklamalar

Bir öğe kaldırıldığında dizideki kalan öğeler boş alanı dolduracak şekilde yeniden numaralandırılır.

## <a name="csimplearraysetatindex"></a><a name="setatindex"></a> CSimpleArray:: SetAtIndex

Dizide belirtilen öğeyi ayarlayın.

```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```

### <a name="parameters"></a>Parametreler

*nDizin*<br/>
Değiştirilecek öğenin dizini.

*şı*<br/>
Belirtilen öğeye atanacak değer.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa TRUE, dizin geçerli değilse FALSE döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../atl/atl-class-overview.md)
