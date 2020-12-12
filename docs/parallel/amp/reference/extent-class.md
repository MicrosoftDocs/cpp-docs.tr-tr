---
description: 'Daha fazla bilgi edinin: kapsam sınıfı (C++ AMP)'
title: extent Sınıfı (C++ AMP)
ms.date: 03/27/2019
f1_keywords:
- extent
- AMP/extent
- AMP/Concurrency::extent::extent
- AMP/Concurrency::extent::contains
- AMP/Concurrency::extent::size
- AMP/Concurrency::extent::tile
- AMP/Concurrency::extent::rank Constant
helpviewer_keywords:
- extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
ms.openlocfilehash: fb355d0ab0676256df42a880722ebaac33eb3cb5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325869"
---
# <a name="extent-class-c-amp"></a>extent Sınıfı (C++ AMP)

0 ' ın kaynağına sahip *n* boyutlu bir alanın sınırlarını belirten *n* tamsayı değerlerinin bir vektörünü temsil eder. Vektördeki değerler en önemli değerden en az önemli olarak sıralanır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <int _Rank>
class extent;
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
`extent`Nesnenin sıralaması.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

**Ad alanı:** Zamanlı

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Uzantı Oluşturucusu](#ctor)|`extent` sınıfının yeni bir örneğini başlatır.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[vardır](#contains)|Belirtilen `extent` nesnenin belirtilen dereceye sahip olduğunu doğrular.|
|[boyutla](#size)|Kapsamın toplam doğrusal boyutunu döndürür (öğe birimleri cinsinden).|
|[Kaldır](#tile)|`tiled_extent`Belirtilen boyutlar tarafından verilen kutucuk uzantılarına sahip bir nesne oluşturur.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işlecinde](#operator_min)|`extent` `index` Karşılık gelen öğelerden öğeleri çıkararak oluşturulan yeni bir nesnesi döndürür `extent` .|
|[işleç--](#operator_min_min)|Nesnenin her öğesini azaltır `extent` .|
|[işleç% =](#operator_mod_eq)|`extent`Bu öğe bir sayıyla bölündüğünde nesnedeki her öğenin mod (geri kalanı) sayısını hesaplar.|
|[işleç * =](#operator_star_eq)|Nesne öğelerinin her birini `extent` bir sayı ile çarpar.|
|[işleç/=](#operator_min_eq)|Nesnenin her öğesini `extent` bir sayıya böler.|
|[kapsam:: işleç\[\]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|
|[işleç +](#operator_add)|`extent`Karşılık gelen ve öğeleri eklenerek oluşturulan yeni bir nesne döndürür `index` `extent` .|
|[işleç + +](#operator_add_add)|Nesnenin her öğesini arttırır `extent` .|
|[işleç + =](#operator_add_eq)|Nesnenin her öğesine belirtilen sayıyı ekler `extent` .|
|[işleç =](#operator_eq)|Başka bir `extent` nesnenin içeriğini buna kopyalar.|
|[işleç-=](#operator_min_eq)|Nesnenin her öğesinden belirtilen sayıyı çıkartır `extent` .|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıralama sabiti](#rank_constant)|Nesnenin derecesini alır `extent` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`extent`

## <a name="contains"></a><a name="contains"></a> vardır

Belirtilen [Dizin](index-class.md) değerinin ' uzantı ' nesnesi içinde içerilip içerilmeyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool contains(const index<rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
`index`Sınanacak değer.

### <a name="return-value"></a>Dönüş Değeri

**`true`** Belirtilen *Dizin* değeri nesnede içerilse `extent` , aksi durumda, **`false`** .

## <a name="extent"></a><a name="ctor"></a> genişliğini

' Uzantı ' sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```cpp
extent() restrict(amp,cpu);
extent(const extent<_Rank>& _Other) restrict(amp,cpu);
explicit extent(int _I) restrict(amp,cpu);
extent(int _I0,  int _I1) restrict(amp,cpu);
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);
explicit extent(const int _Array[_Rank])restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Array*<br/>
`_Rank`Yeni nesneyi oluşturmak için kullanılan tamsayılar dizisi `extent` .

*_I*<br/>
Kapsamın uzunluğu.

*_I0*<br/>
En önemli boyutun uzunluğu.

*_I1*<br/>
Bir sonraki en-önemli boyutun uzunluğu.

*_I2*<br/>
En az önemli boyutun uzunluğu.

*_Other*<br/>
`extent`Yeni `extent` nesnenin temel aldığı nesne.

## <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu, `extent` üç dereceye sahip bir nesnesi başlatır.

Bir nesne oluşturmak için bir dizi kullanılıyorsa `extent` , dizinin uzunluğu nesnenin sırasıyla eşleşmelidir `extent` .

## <a name="operator"></a><a name="operator_mod_eq"></a> işleç% =

Bu öğe bir sayıyla bölündüğünde, ' uzantı ' içindeki her öğenin mod (geri kalanı) sayısını hesaplar.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Mod ' un bulunacağı sayı.

### <a name="return-value"></a>Dönüş Değeri

`extent` nesnesi.

## <a name="operator"></a><a name="operator_star_eq"></a> işleç * =

' Uzantı ' nesnesindeki her öğeyi belirtilen sayı ile çarpar.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Çarpılacak sayı.

### <a name="return-value"></a>Dönüş Değeri

`extent` nesnesi.

## <a name="operator"></a><a name="operator_add"></a> işleç +

`extent`Karşılık gelen ve öğeleri eklenerek oluşturulan yeni bir nesne `index` döndürür `extent` .

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
`index`Eklenecek öğeleri içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Yeni `extent` nesnesi.

## <a name="operator"></a><a name="operator_add_add"></a> işleç + +

' Uzantı ' nesnesinin her bir öğesini arttırır.

### <a name="syntax"></a>Syntax

```cpp
extent<_Rank>& operator++() restrict(amp,cpu);
extent<_Rank> operator++(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Önek işleci için, `extent` nesnesi ( **`*this`** ). Son ek işleci için yeni bir `extent` nesne.

## <a name="operator"></a><a name="operator_add_eq"></a> işleç + =

' Uzantı ' nesnesinin her öğesine belirtilen sayıyı ekler.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Eklenecek sayı, dizin veya kapsam.

### <a name="return-value"></a>Dönüş Değeri

Elde edilen `extent` nesne.

## <a name="operator-"></a><a name="operator_min"></a> işlecinde

`extent`Belirtilen nesne içindeki her öğeyi `index` Bu nesnedeki karşılık gelen öğeden çıkararak yeni bir nesne oluşturur `extent` .

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Çıkarılacak `index` öğeleri içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Yeni `extent` nesnesi.

## <a name="operator--"></a><a name="operator_min_min"></a> işleç--

' Uzantı ' nesnesindeki her öğeyi azaltır.

### <a name="syntax"></a>Syntax

```cpp
extent<_Rank>& operator--() restrict(amp,cpu);
extent<_Rank> operator--(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Önek işleci için, `extent` nesnesi ( **`*this`** ). Son ek işleci için yeni bir `extent` nesne.

## <a name="operator"></a><a name="operator_div_eq"></a> işleç/=

' Uzantı ' nesnesindeki her öğeyi belirtilen sayıda böler.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Bölünecek sayı.

### <a name="return-value"></a>Dönüş Değeri

`extent` nesnesi.

## <a name="operator-"></a><a name="operator_min_eq"></a> işleç-=

' Uzantı ' nesnesinin her öğesinden belirtilen sayıyı çıkartır.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Çıkarılacak sayı.

### <a name="return-value"></a>Dönüş Değeri

Elde edilen `extent` nesne.

## <a name="operator"></a><a name="operator_eq"></a> işleç =

Başka bir ' uzantı ' nesnesinin içeriğini buna kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
`extent`Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu nesneye bir başvuru `extent` .

## <a name="extentoperator-"></a><a name="operator_at"></a> kapsam:: işleç \[\]

Belirtilen dizindeki öğeyi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
int operator[](unsigned int _Index) const restrict(amp,cpu);
int& operator[](unsigned int _Index) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
0 ile sıra eksi 1 arasında bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizinde olan öğe.

## <a name="rank"></a><a name="rank_constant"></a> sırası

' Uzantı ' nesnesinin derecesini depolar.

### <a name="syntax"></a>Syntax

```cpp
static const int rank = _Rank;
```

## <a name="size"></a><a name="size"></a> boyutla

Nesnenin toplam doğrusal boyutunu döndürür `extent` (öğe birimleri cinsinden).

### <a name="syntax"></a>Syntax

```cpp
unsigned int size() const restrict(amp,cpu);
```

## <a name="tile"></a><a name="tile"></a> Kaldır

Belirtilen döşeme boyutlarına sahip bir tiled_extent nesnesi oluşturur.

```cpp
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```

### <a name="parameters"></a>Parametreler

*_Dim0*<br/>
Döşeli uzantının en önemli bileşeni.
*_Dim1*<br/>
Döşeli uzantının en çok önemli bir bileşeni.
*_Dim2*<br/>
Döşeli uzantının en az önemli bileşeni.

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
