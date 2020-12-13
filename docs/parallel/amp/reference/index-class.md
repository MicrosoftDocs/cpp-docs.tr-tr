---
description: 'Daha fazla bilgi edinin: Dizin sınıfı'
title: index Sınıfı
ms.date: 03/27/2019
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
ms.openlocfilehash: 46b49a7e0f65f06ad64ed32367cdfe6f6ca5ed1e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330047"
---
# <a name="index-class"></a>index Sınıfı

*N* boyutlu bir dizin vektörü tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <int _Rank>
class index;
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
Boyut veya boyut sayısı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[Dizin Oluşturucu](#index_ctor)|`index` sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[işleç--](#operator--)|Nesnenin her öğesini azaltır `index` .|
|[işleç% =](#operator_mod_eq)|`index`Bu öğe bir sayıyla bölündüğünde nesnedeki her öğenin mod (geri kalanı) sayısını hesaplar.|
|[işleç * =](#operator_star_eq)|Nesne öğelerinin her birini `index` bir sayı ile çarpar.|
|[işleç/=](#operator_div_eq)|Nesnenin her öğesini `index` bir sayıya böler.|
|[index:: operator\[\]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|
|[işleç + +](#operator_add_add)|Nesnenin her öğesini arttırır `index` .|
|[işleç + =](#operator_add_eq)|Nesnenin her öğesine belirtilen sayıyı ekler `index` .|
|[işleç =](#operator_eq)|Belirtilen `index` nesnenin içeriğini buna kopyalar.|
|[işleç-=](#operator_-_eq)|Nesnenin her öğesinden belirtilen sayıyı çıkartır `index` .|

### <a name="public-constants"></a>Genel sabitler

|Ad|Açıklama|
|----------|-----------------|
|[sıralama sabiti](#rank)|Nesnenin derecesini depolar `index` .|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`index`

## <a name="remarks"></a>Açıklamalar

Yapı, n `index` boyutlu bir alanda benzersiz bir konum belirten *n* tamsayının koordinat vektörünü temsil eder. Vektördeki değerler en önemli değerden en az önemli olarak sıralanır. [İşleç =](#operator_eq)kullanarak bileşenlerin değerlerini alabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** amp. h

**Ad alanı:** Zamanlı

## <a name="index-constructor"></a><a name="index_ctor"></a> Dizin Oluşturucu

Dizin sınıfının yeni bir örneğini başlatır.

```cpp
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

*_Array*<br/>
Sıralama değerleriyle tek boyutlu bir dizi.

*_I*<br/>
Tek boyutlu dizindeki dizin konumu.

*_I0*<br/>
En önemli boyutun uzunluğu.

*_I1*<br/>
Bir sonraki en-önemli boyutun uzunluğu.

*_I2*<br/>
En az önemli boyutun uzunluğu.

*_Other*<br/>
Yeni dizin nesnesinin temel aldığı bir dizin nesnesi.

## <a name="operator--"></a><a name="operator--"></a> işleç--

Index nesnesinin her bir öğesini azaltır.

```cpp
index<_Rank>& operator--() restrict(amp,cpu);

index operator--(
   int
) restrict(amp,cpu);
```

### <a name="return-values"></a>Dönüş değerleri

Önek işleci için dizin nesnesi (* this). Son ek işleci için yeni bir dizin nesnesi.

## <a name="operator"></a><a name="operator_mod_eq"></a> işleç% =

Bu öğe belirtilen sayıya bölündüğünde Dizin nesnesindeki her öğenin mod (geri kalanı) sayısını hesaplar.

```cpp
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Mod sayısını bulmak için bölünecek sayı.

## <a name="return-value"></a>Dönüş Değeri

Dizin nesnesi.

## <a name="operator"></a><a name="operator_star_eq"></a> işleç * =

Dizin nesnesindeki her öğeyi belirtilen sayı ile çarpar.

```cpp
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Çarpılacak sayı.

## <a name="operator"></a><a name="operator_div_eq"></a> işleç/=

Dizin nesnesindeki her öğeyi belirtilen sayıda böler.

```cpp
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Bölünecek sayı.

## <a name="operator"></a><a name="operator_at"></a> işlecinde\[\]

Belirtilen konumdaki dizinin bileşenini döndürür.

```cpp
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Index*<br/>
0 ile sıra eksi 1 arasında bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen dizinde olan öğe.

### <a name="remarks"></a>Açıklamalar

Aşağıdaki örnek, dizinin bileşen değerlerini görüntüler.

```cpp
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator"></a><a name="operator_add_add"></a> işleç + +

Index nesnesinin her bir öğesini arttırır.

```cpp
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Önek işleci için dizin nesnesi (* this). Son ek işleci için yeni bir dizin nesnesi.

## <a name="operator"></a><a name="operator_add_eq"></a> işleç + =

Dizin nesnesinin her öğesine belirtilen sayıyı ekler.

```cpp
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

## <a name="operator"></a><a name="operator_eq"></a> işleç =

Belirtilen dizin nesnesinin içeriğini buna kopyalar.

```cpp
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalanacak dizin nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu dizin nesnesine bir başvuru.

## <a name="operator-"></a><a name="operator_-_eq"></a> işleç-=

Dizin nesnesinin her öğesinden belirtilen sayıyı çıkartır.

```cpp
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

## <a name="rank"></a><a name="rank"></a> Sırası

Dizin nesnesinin derecesini alır.

```cpp
static const int rank = _Rank;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık ad alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
