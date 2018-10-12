---
title: Extent sınıfı (C++ AMP) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- extent
- AMP/extent
- AMP/Concurrency::extent::extent
- AMP/Concurrency::extent::contains
- AMP/Concurrency::extent::size
- AMP/Concurrency::extent::tile
- AMP/Concurrency::extent::rank Constant
dev_langs:
- C++
helpviewer_keywords:
- extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ca17d81aa1712bcf6222b0ec0888f3a987269f03
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163133"
---
# <a name="extent-class-c-amp"></a>extent Sınıfı (C++ AMP)

Oluşan bir vektörü temsil eder *N* uzayın sınırlarını belirten bir tamsayı değerleri bir *N*-kaynağı 0 olan boyutlu boşluk. Vektördeki değerler en önemliden en az önemliye doğru sıralanır.

### <a name="syntax"></a>Sözdizimi

```
template <int _Rank>
class extent;
```

### <a name="parameters"></a>Parametreler

*_Dizin*<br/>
Boyut sayısı `extent` nesne.

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp.h

**Namespace:** eşzamanlılık

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Uzantı Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `extent` sınıfı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[içerir](#contains)|Doğrular belirtilen `extent` nesnesinin belirtilen boyut sayısına sahip.|
|[Boyutu](#size)|(Birimlerindeki öğelerin) kapsamın toplam doğrusal boyutu döndürür.|
|[kutucuğu](#tile)|Üreten bir `tiled_extent` belirtilen boyutlar tarafından verilen döşeme kapsamları ile bir nesne.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator-](#operator_min)|Yeni bir `extent` çıkararak oluşturulan nesne `index` öğelerinden karşılık gelen öğeleri `extent` öğeleri.|
|[--işleci](#operator_min_min)|Azaltır her öğeye `extent` nesne.|
|[operator%=](#operator_mod_eq)|Her bir öğenin modunu (kalanını) hesaplar `extent` o öğe bir sayıya bölündüğünde nesne.|
|[operator*=](#operator_star_eq)|Her öğeyi çarpar `extent` nesne bir sayı.|
|[/ = işleci](#operator_min_eq)|Her öğeye böler `extent` nesne bir sayı.|
|[Extent::operator\[\]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|
|[operator +](#operator_add)|Yeni bir `extent` karşılık gelen toplayarak oluşturulan nesne `index` ve `extent` öğeleri.|
|[operator ++](#operator_add_add)|Her öğeyi artırır `extent` nesne.|
|[operator+=](#operator_add_eq)|Her öğeye belirtilen sayıyı ekler `extent` nesne.|
|[operator=](#operator_eq)|Başka bir deponun içeriğini kopyalar `extent` bu nesne içine.|
|[-= işleci](#operator_min_eq)|Her öğeden belirtilen sayıyı çıkartır `extent` nesne.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıra sabiti](#rank)|Boyut sayısını alır `extent` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`extent`

## <a name="contains"></a> içerir

Belirtir olup olmadığını belirtilen [dizin](index-class.md) değeri 'kapsam' nesnesinde yer alan.

### <a name="syntax"></a>Sözdizimi

```
bool contains(const index<rank>& _Index) const restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
`index` Test etmek için değer.

### <a name="return-value"></a>Dönüş Değeri

**doğru** , belirtilen *dizin* değer kapsanıyorsa `extent` nesne; Aksi takdirde, **false**.

##  <a name="ctor"></a> Kapsam

'Kapsam' sınıfının yeni bir örneğini başlatır.

### <a name="syntax"></a>Sözdizimi

```
extent() restrict(amp,cpu);
extent(const extent<_Rank>& _Other) restrict(amp,cpu);
explicit extent(int _I) restrict(amp,cpu);
extent(int _I0,  int _I1) restrict(amp,cpu);
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);
explicit extent(const int _Array[_Rank])restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Dizisi*<br/>
Bir dizi `_Rank` yeni oluşturmak için kullanılan tamsayılar `extent` nesne.

*_I*<br/>
Kapsamın uzunluğu.

*_I0*<br/>
En önemli boyutun uzunluğu.

*_I1*<br/>
Sonraki-en-önemli boyutun uzunluğu.

*_I2*<br/>
En az önemli boyutun uzunluğu.

*_Diğer*<br/>
Bir `extent` nesne yeni `extent` nesne dayanır.

## <a name="remarks"></a>Açıklamalar

Parametresiz oluşturucusu başlatan bir `extent` üç dereceli bir nesne.

Bir dizi oluşturmak için kullanılıyorsa bir `extent` nesne, dizi uzunluğu, boyut sayısı eşleşmelidir `extent` nesne.

##  <a name="operator_mod_eq"></a> operator % =

Bu öğe bir sayıya bölündüğünde 'kapsam' içindeki her öğenin modunu (kalanını) hesaplar.

### <a name="syntax"></a>Sözdizimi

```
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Modüllerini bulunacak sayı.

### <a name="return-value"></a>Dönüş Değeri

`extent` Nesne.

##  <a name="operator_star_eq"></a> operator * =

Her bir öğesinde 'kapsam' nesnesini belirtilen sayı ile çarpar.

### <a name="syntax"></a>Sözdizimi

```
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Çarpılacağı sayı.

### <a name="return-value"></a>Dönüş Değeri

`extent` Nesne.

## <a name="operator_add"></a> operator +

Yeni bir `extent` karşılık gelen ekleyerek oluşturulan nesne `index` ve `extent` öğeleri.

### <a name="syntax"></a>Sözdizimi

```
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
`index` Eklenecek öğeleri içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Yeni `extent` nesne.

##  <a name="operator_add_add"></a> operator ++

'Kapsam' nesnesini her öğeyi artırır.

### <a name="syntax"></a>Sözdizimi

```
extent<_Rank>& operator++() restrict(amp,cpu);
extent<_Rank> operator++(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Önek işleci için `extent` nesne (`*this`). Sonek operatörü için yeni bir `extent` nesne.

##  <a name="operator_add_eq"></a> += işleci

'Kapsam' nesnesini her öğeye belirtilen sayıyı ekler.

### <a name="syntax"></a>Sözdizimi

```
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Sayı, dizin veya kapsam eklemek için.

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan `extent` nesne.

##  <a name="operator_min"></a> operator-

Yeni bir oluşturur `extent` belirtilen içindeki her öğeyi çıkararak nesneyi `index` karşılık gelen öğe bu nesneden `extent` nesne.

### <a name="syntax"></a>Sözdizimi

```
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
`index` Çıkarılacak öğeleri içeren nesne.

### <a name="return-value"></a>Dönüş Değeri

Yeni `extent` nesne.

##  <a name="operator_min_min"></a> --işleci

Azaltır 'kapsam' nesnesindeki her öğe.

### <a name="syntax"></a>Sözdizimi

```
extent<_Rank>& operator--() restrict(amp,cpu);
extent<_Rank> operator--(int)restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Önek işleci için `extent` nesne (`*this`). Sonek operatörü için yeni bir `extent` nesne.

##  <a name="operator_div_eq"></a> / = işleci

'Kapsam' nesnesindeki her öğe tarafından belirtilen sayıda böler.

### <a name="syntax"></a>Sözdizimi

```
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Bölecek sayı.

### <a name="return-value"></a>Dönüş Değeri

`extent` Nesne.

##  <a name="operator_min_eq"></a> -= işleci

'Kapsam' nesnesini her öğeden belirtilen sayıyı çıkartır.

### <a name="syntax"></a>Sözdizimi

```
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Çıkarılacak sayı.

### <a name="return-value"></a>Dönüş Değeri

Ortaya çıkan `extent` nesne.

##  <a name="operator_eq"></a> işleç =

Başka bir 'kapsam' nesnenin içeriğini, bunu kopyalar.

### <a name="syntax"></a>Sözdizimi

```
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
`extent` Kopyalanacak nesne.

### <a name="return-value"></a>Dönüş Değeri

Bu başvuru `extent` nesne.

##  <a name="operator_at"></a> Extent::operator \[\]

Belirtilen dizindeki öğeyi döndürür.

### <a name="syntax"></a>Sözdizimi

```
int operator[](unsigned int _Index) const restrict(amp,cpu);
int& operator[](unsigned int _Index) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
0 ile boyut sayısı eksi 1 arasında bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizindeki öğe.

##  <a name="rank_constant"></a> boyut sayısı

Boyut sayısı 'kapsam' nesnesini depolar.

### <a name="syntax"></a>Sözdizimi

```
static const int rank = _Rank;
```

##  <a name="size"></a> Boyutu

Toplam doğrusal boyutunu döndürür `extent` nesne (birimlerindeki öğeleri).

### <a name="syntax"></a>Sözdizimi

```
unsigned int size() const restrict(amp,cpu);
```

## <a name="tile"></a> kutucuğu

Belirtilen döşeme boyutları ile bir tiled_extent nesnesi oluşturur.

```
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```
### <a name="parameters"></a>Parametreler

*_Dim0*<br/>
Döşenmiş kapsamın en önemli bileşeni.
*_Dim1*<br/>
Döşenmiş kapsamın sonraki-en-önemli bileşeni.
*_Dim2*<br/>
Döşenmiş kapsamın en az önemli bileşeni.

## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
