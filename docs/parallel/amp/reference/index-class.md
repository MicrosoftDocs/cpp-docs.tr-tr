---
title: index sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
dev_langs:
- C++
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 154f9b4835f7dc18fcf45de53b078d3d5b649e37
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46446928"
---
# <a name="index-class"></a>index Sınıfı

Tanımlayan bir *N*-boyutlu dizin pographics cpp amp.md.

## <a name="syntax"></a>Sözdizimi

```
template <int _Rank>
class index;
```

#### <a name="parameters"></a>Parametreler

*_Dizin*<br/>
Boyut veya boyut sayısı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Dizin Oluşturucu](#ctor)|Yeni bir örneğini başlatır `index` sınıfı.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[--işleci](#operator--)|Azaltır her öğeye `index` nesne.|
|[operator(mod) =](#operator_mod_eq)|Her bir öğenin modunu (kalanını) hesaplar `index` o öğe bir sayıya bölündüğünde nesne.|
|[operator*=](#operator_star_eq)|Her öğeyi çarpar `index` nesne bir sayı.|
|[/ = işleci](#operator_div_eq)|Her öğeye böler `index` nesne bir sayı.|
|[index::operator\[\]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|
|[operator ++](#operator_add_add)|Her öğeyi artırır `index` nesne.|
|[operator+=](#operator_add_eq)|Her öğeye belirtilen sayıyı ekler `index` nesne.|
|[operator=](#operator_eq)|Belirtilen içeriğini kopyalar `index` bu nesne içine.|
|[-= işleci](#operator_-_eq)|Her öğeden belirtilen sayıyı çıkartır `index` nesne.|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıra sabiti](#rank)|Boyut sayısını tutar `index` nesne.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`index`

## <a name="remarks"></a>Açıklamalar

`index` Yapısı sayıdan oluşan koordinat vektörünü temsil eder *N* benzersiz bir konumu belirten Tamsayı bir *N*-boyutlu boşluk. Vektördeki değerler en önemliden en az önemliye doğru sıralanır. Kullanarak bileşenlerini değerlerini alabilirsiniz [işleç =](#operator_eq).

## <a name="requirements"></a>Gereksinimler

**Başlık:** amp.h

**Namespace:** eşzamanlılık

## <a name="index_ctor"></a> Dizin Oluşturucu

Dizin sınıfının yeni bir örneğini başlatır.

```
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Dizisi*<br/>
Boyut sayısı değerlerini içeren tek boyutlu bir dizi.

*_I*<br/>
Tek boyutlu bir dizinin içindeki dizin konumu.

*_I0*<br/>
En önemli boyutun uzunluğu.

*_I1*<br/>
Sonraki-en-önemli boyutun uzunluğu.

*_I2*<br/>
En az önemli boyutun uzunluğu.

*_Diğer*<br/>
Yeni dizin nesnesi, temel bir dizin nesnesi.

## <a name="operator--"></a>  --işleci

Azaltır dizin nesnesinin her öğesi.
```
index<_Rank>& operator--() restrict(amp,cpu);

index operator--(
   int
) restrict(amp,cpu);
```
### <a name="return-values"></a>Döndürülen değerler

Önek işleci için dizin nesnesi (* Bu). Sonek operatörü için yeni bir dizin nesnesi.

## <a name="operator_mod_eq"></a>  operator(mod) =

Bu öğe tarafından belirtilen sayı bölündüğünde dizin nesnesi içindeki her öğenin modunu (kalanını) hesaplar.

```
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```
### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Modulus bulmak için göre bölüneceği sayı.

## <a name="return-value"></a>Dönüş Değeri
Dizin nesnesi.

## <a name="operator_star_eq"></a>  operator * =

Belirtilen sayıda dizin nesnesi içindeki her öğeyi çarpar.
```
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Çarpılacağı sayı.

## <a name="operator_div_eq"></a>  / = işleci

Dizin nesnesi içindeki her öğeyi belirtilen sayı böler.

```
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
```
### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Bölecek sayı.

## <a name="operator_at"></a>  İşleci\[\]

Belirtilen konumda dizini bileşenini döndürür.

```
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
0 ile boyut sayısı eksi 1 arasında bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizindeki öğe.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki örnek dizinin bileşen değerlerini görüntüler.
```
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>  operator ++

Index nesnesinin her öğeyi artırır.
```
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```
### <a name="return-value"></a>Dönüş Değeri

Önek işleci için dizin nesnesi (* Bu). Sonek operatörü için yeni bir dizin nesnesi.

## <a name="operator_add_eq"></a>  += işleci

Dizin nesnesi her öğeye belirtilen sayıyı ekler.
```
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
```
### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Eklenecek sayı.

### <a name="return-value"></a>Dönüş Değeri

Dizin nesnesi.

## <a name="operator_eq"></a>  işleç =

Belirtilen dizin nesnenin içeriğini, bunu kopyalar.
```
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
```
### <a name="parameters"></a>Parametreler

*_Diğer*<br/>
Kopyalamak için dizin nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu dizin nesnesine bir başvuru.

## <a name="operator_-_eq"></a>  -= işleci

Dizin nesnesi her öğeden belirtilen sayıyı çıkartır.
```
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```
### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Çıkarılacak sayı.

### <a name="return-value"></a>Dönüş Değeri

Dizin nesnesi.

## <a name="rank"></a>  boyut sayısı
  Boyut sayısı dizin nesnesi alır.
```
static const int rank = _Rank;
```
## <a name="see-also"></a>Ayrıca Bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
