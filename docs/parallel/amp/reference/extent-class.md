---
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
ms.openlocfilehash: 3e8dae7b76ea2efc852486a19f5d298cda477012
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77126727"
---
# <a name="extent-class-c-amp"></a>extent Sınıfı (C++ AMP)

0 ' ın kaynağına sahip *n*boyutlu bir alanın sınırlarını belirten *n* tamsayı değerlerinin bir vektörünü temsil eder. Vektördeki değerler en önemli değerden en az önemli olarak sıralanır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <int _Rank>
class extent;
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
`extent` nesnesinin sıralaması.

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
|[vardır](#contains)|Belirtilen `extent` nesnesinin belirtilen dereceye sahip olduğunu doğrular.|
|[boyutla](#size)|Kapsamın toplam doğrusal boyutunu döndürür (öğe birimleri cinsinden).|
|[Kaldır](#tile)|Belirtilen boyutlar tarafından verilen kutucuk uzantılarına sahip bir `tiled_extent` nesnesi oluşturur.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işlecinde](#operator_min)|Karşılık gelen `extent` öğelerinden `index` öğelerini çıkararak oluşturulan yeni bir `extent` nesnesi döndürür.|
|[işleç--](#operator_min_min)|`extent` nesnesinin her öğesini azaltır.|
|[işleç% =](#operator_mod_eq)|Bu öğe bir sayıyla bölündüğünde `extent` nesnesindeki her öğenin mod (kalanı) sayısını hesaplar.|
|[işleç * =](#operator_star_eq)|`extent` nesnesinin her öğesini bir sayı ile çarpar.|
|[işleç/=](#operator_min_eq)|`extent` nesnesinin her öğesini bir sayıya böler.|
|[kapsam:: operator\[\]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|
|[işleç +](#operator_add)|Karşılık gelen `index` ve `extent` öğeleri eklenerek oluşturulan yeni bir `extent` nesnesi döndürür.|
|[işleç + +](#operator_add_add)|`extent` nesnesinin her bir öğesini arttırır.|
|[işleç + =](#operator_add_eq)|`extent` nesnesinin her öğesine belirtilen sayıyı ekler.|
|[işleç =](#operator_eq)|Başka bir `extent` nesnesinin içeriğini buna kopyalar.|
|[işleç-=](#operator_min_eq)|`extent` nesnesinin her öğesinden belirtilen sayıyı çıkartır.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıralama sabiti](#rank_constant)|`extent` nesnesinin derecesini alır.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`extent`

## <a name="contains"></a>vardır

Belirtilen [Dizin](index-class.md) değerinin ' uzantı ' nesnesi içinde içerilip içerilmeyeceğini gösterir.

### <a name="syntax"></a>Sözdizimi

```cpp
bool contains(const index<rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
Sınanacak `index` değeri.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen *Dizin* değeri `extent` nesnesinde içeriyorsa **true** . Aksi takdirde, **false**.

## <a name="ctor"></a>genişliğini

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
Yeni `extent` nesnesini oluşturmak için kullanılan `_Rank` tamsayılar dizisi.

*_I*<br/>
Kapsamın uzunluğu.

*_I0*<br/>
En önemli boyutun uzunluğu.

*_I1*<br/>
Bir sonraki en-önemli boyutun uzunluğu.

*_I2*<br/>
En az önemli boyutun uzunluğu.

*_Other*<br/>
Yeni `extent` nesnesinin temel aldığı `extent` nesne.

## <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu, üç dereceye sahip bir `extent` nesnesini başlatır.

Bir dizi `extent` nesnesi oluşturmak için kullanılırsa, dizi uzunluğu `extent` nesnesinin sırasıyla eşleşmelidir.

## <a name="operator_mod_eq"></a>işleç% =

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

## <a name="operator_star_eq"></a>işleç * =

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

## <a name="operator_add"></a>işleç +

Karşılık gelen `index` ve `extent` öğeleri eklenerek oluşturulan yeni bir `extent` nesnesi döndürür.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Eklenecek öğeleri içeren `index` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Yeni `extent` nesnesi.

## <a name="operator_add_add"></a>işleç + +

' Uzantı ' nesnesinin her bir öğesini arttırır.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank>& operator++() restrict(amp,cpu);
extent<_Rank> operator++(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Önek işleci için, `extent` nesnesi (`*this`). Son ek işleci için yeni bir `extent` nesnesi.

## <a name="operator_add_eq"></a>işleç + =

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

Elde edilen `extent` nesnesi.

## <a name="operator_min"></a>işlecinde

Bu `extent` nesnesindeki karşılık gelen öğeden belirtilen `index` nesnesindeki her öğeyi çıkararak yeni bir `extent` nesnesi oluşturur.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Çıkarılacak öğeleri içeren `index` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Yeni `extent` nesnesi.

## <a name="operator_min_min"></a>işleç--

' Uzantı ' nesnesindeki her öğeyi azaltır.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank>& operator--() restrict(amp,cpu);
extent<_Rank> operator--(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Önek işleci için, `extent` nesnesi (`*this`). Son ek işleci için yeni bir `extent` nesnesi.

## <a name="operator_div_eq"></a>işleç/=

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

## <a name="operator_min_eq"></a>işleç-=

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

Elde edilen `extent` nesnesi.

## <a name="operator_eq"></a>işleç =

Başka bir ' uzantı ' nesnesinin içeriğini buna kopyalar.

### <a name="syntax"></a>Sözdizimi

```cpp
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalamanın `extent` nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu `extent` nesnesine bir başvuru.

## <a name="operator_at"></a>kapsam:: operator \[\]

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

## <a name="rank_constant"></a>sırası

' Uzantı ' nesnesinin derecesini depolar.

### <a name="syntax"></a>Sözdizimi

```cpp
static const int rank = _Rank;
```

## <a name="size"></a>boyutla

`extent` nesnesinin toplam doğrusal boyutunu döndürür (öğe birimleri cinsinden).

### <a name="syntax"></a>Sözdizimi

```cpp
unsigned int size() const restrict(amp,cpu);
```

## <a name="tile"></a>Kaldır

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

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
