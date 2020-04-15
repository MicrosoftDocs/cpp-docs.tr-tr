---
title: CSimpleArray Sınıfı
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
ms.openlocfilehash: e45c9b3fd778aacd3a3e2d5d3696661afa0c6fb0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81330911"
---
# <a name="csimplearray-class"></a>CSimpleArray Sınıfı

Bu sınıf, basit bir dizi yönetmek için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T, class TEqual = CSimpleArrayEqualHelper<T>>
class CSimpleArray
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
Dizide depolayabilmek için veri türü.

*TEqual*<br/>
*T*türündeki öğeler için eşitlik testini tanımlayan bir özellik nesnesi.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleArray::CSimpleArray](#csimplearray)|Basit dizi için yapıcı.|
|[CSimpleArray::~CSimpleArray](#dtor)|Basit diziiçin yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleArray::Ekle](#add)|Diziye yeni bir öğe ekler.|
|[CSimpleArray::Bul](#find)|Dizide bir öğe bulur.|
|[CSimpleArray::Veri Get](#getdata)|Dizide depolanan verilere bir işaretçi döndürür.|
|[CSimpleArray::Getsize](#getsize)|Dizide depolanan öğe sayısını verir.|
|[CSimpleArray::Kaldır](#remove)|Belirli bir öğeyi diziden kaldırır.|
|[CSimpleArray::RemoveAll](#removeall)|Dizideki tüm öğeleri kaldırır.|
|[CSimpleArray::removeat](#removeat)|Belirtilen öğeyi diziden kaldırır.|
|[CSimpleArray::Setatindex](#setatindex)|Dizide belirtilen öğeyi ayarlar.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CSimpleArray::operatör\[\]](#operator_at)|Diziden bir öğe alır.|
|[CSimpleArray::operator =](#operator_eq)|Atama işleci.|

## <a name="remarks"></a>Açıklamalar

`CSimpleArray`belirli bir türde `T`basit bir dizi oluşturmak ve yönetmek için yöntemler sağlar.

Parametre, `TEqual` türiki `T`öğe için bir eşitlik işlevi tanımlama aracı sağlar. [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)benzer bir sınıf oluşturarak, herhangi bir dizi için eşitlik testi davranışını değiştirmek mümkündür. Örneğin, bir işaretçi dizisiyle uğraşırken, eşitliği işaretçilerin başvurulan değerlerine bağlı olarak tanımlamak yararlı olabilir. Varsayılan uygulama **işleci kullanır=()**.

Hem `CSimpleArray` de [CSimpleMap](../../atl/reference/csimplemap-class.md) az sayıda öğe için tasarlanmıştır. Dizi çok sayıda öğe içerdiğinde [CAtlArray](../../atl/reference/catlarray-class.md) ve [CAtlMap](../../atl/reference/catlmap-class.md) kullanılmalıdır.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlsimpcoll.h

## <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#86](../../atl/codesnippet/cpp/csimplearray-class_1.cpp)]

## <a name="csimplearrayadd"></a><a name="add"></a>CSimpleArray::Ekle

Diziye yeni bir öğe ekler.

```
BOOL Add(const T& t);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Diziye eklenecek öğe.

### <a name="return-value"></a>Dönüş Değeri

Öğe diziye başarıyla eklenirse TRUE döndürür, aksi takdirde FALSE.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#87](../../atl/codesnippet/cpp/csimplearray-class_2.cpp)]

## <a name="csimplearraycsimplearray"></a><a name="csimplearray"></a>CSimpleArray::CSimpleArray

Dizi nesnesinin oluşturucusu.

```
CSimpleArray(const CSimpleArray<T, TEqual>& src);
CSimpleArray();
```

### <a name="parameters"></a>Parametreler

*src*<br/>
Varolan bir `CSimpleArray` nesnesi.

### <a name="remarks"></a>Açıklamalar

Yeni boş bir `CSimpleArray` nesne veya varolan `CSimpleArray` bir nesnenin kopyasını oluşturarak veri üyelerini başolarak adlandırır.

## <a name="csimplearraycsimplearray"></a><a name="dtor"></a>CSimpleArray::~CSimpleArray

Yıkıcı.

```
~CSimpleArray();
```

### <a name="remarks"></a>Açıklamalar

Ayrılan tüm kaynakları serbest sağlar.

## <a name="csimplearrayfind"></a><a name="find"></a>CSimpleArray::Bul

Dizide bir öğe bulur.

```
int Find(const T& t) const;
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Aranacak öğe.

### <a name="return-value"></a>Dönüş Değeri

Öğe bulunmazsa, bulunan öğenin dizinini veya -1'i döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#88](../../atl/codesnippet/cpp/csimplearray-class_3.cpp)]

## <a name="csimplearraygetdata"></a><a name="getdata"></a>CSimpleArray::Veri Get

Dizide depolanan verilere bir işaretçi döndürür.

```
T* GetData() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizideki verilere bir işaretçi döndürür.

## <a name="csimplearraygetsize"></a><a name="getsize"></a>CSimpleArray::Getsize

Dizide depolanan öğe sayısını verir.

```
int GetSize() const;
```

### <a name="return-value"></a>Dönüş Değeri

Dizide depolanan öğe sayısını verir.

## <a name="csimplearrayoperator-"></a><a name="operator_at"></a>CSimpleArray::operatör\[\]

Diziden bir öğe alır.

```
T& operator[](int nindex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Öğe dizini.

### <a name="return-value"></a>Dönüş Değeri

*nIndex*tarafından başvurulan dizi öğesini döndürür.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#89](../../atl/codesnippet/cpp/csimplearray-class_4.cpp)]

## <a name="csimplearrayoperator-"></a><a name="operator_eq"></a>CSimpleArray::operator =

Atama işleci.

```
CSimpleArray<T, TEqual>
& operator=(
    const CSimpleArray<T, TEqual>& src);
```

### <a name="parameters"></a>Parametreler

*src*<br/>
Kopyalanması gereken dizi.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneye `CSimpleArray` bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

`CSimpleArray` *Src* tarafından başvurulan nesnedeki tüm öğeleri geçerli dizi nesnesine kopyalayarak varolan tüm verileri değiştirir.

### <a name="example"></a>Örnek

[!code-cpp[NVC_ATL_Utilities#90](../../atl/codesnippet/cpp/csimplearray-class_5.cpp)]

## <a name="csimplearrayremove"></a><a name="remove"></a>CSimpleArray::Kaldır

Belirli bir öğeyi diziden kaldırır.

```
BOOL Remove(const T& t);
```

### <a name="parameters"></a>Parametreler

*T*<br/>
Diziden kaldırılacak öğe.

### <a name="return-value"></a>Dönüş Değeri

Öğe bulunur ve kaldırılırsa TRUE döndürür, aksi takdirde FALSE.

### <a name="remarks"></a>Açıklamalar

Bir öğe kaldırıldığında, dizide kalan öğeler boş alanı doldurmak için yeniden numaralandırılır.

## <a name="csimplearrayremoveall"></a><a name="removeall"></a>CSimpleArray::RemoveAll

Dizideki tüm öğeleri kaldırır.

```
void RemoveAll();
```

### <a name="remarks"></a>Açıklamalar

Dizide şu anda depolanan tüm öğeleri kaldırır.

## <a name="csimplearrayremoveat"></a><a name="removeat"></a>CSimpleArray::removeat

Belirtilen öğeyi diziden kaldırır.

```
BOOL RemoveAtint nIndex);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Kaldırılacak öğeyi gösteren dizin.

### <a name="return-value"></a>Dönüş Değeri

Öğe kaldırıldıysa TRUE döndürür, dizin geçersizse FALSE.

### <a name="remarks"></a>Açıklamalar

Bir öğe kaldırıldığında, dizide kalan öğeler boş alanı doldurmak için yeniden numaralandırılır.

## <a name="csimplearraysetatindex"></a><a name="setatindex"></a>CSimpleArray::Setatindex

Dizide belirtilen öğeyi ayarlayın.

```
BOOL SetAtIndex(
    int nIndex,
    const T& t);
```

### <a name="parameters"></a>Parametreler

*Nındex*<br/>
Değişecek öğenin dizini.

*T*<br/>
Belirtilen öğeye atanacak değer.

### <a name="return-value"></a>Dönüş Değeri

Dizin geçerli değilse doğru döndürür, FALSE.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
