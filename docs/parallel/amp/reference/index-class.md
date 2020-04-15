---
title: index Sınıfı
ms.date: 03/27/2019
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
ms.openlocfilehash: 50222015e6b365dc161fd4334067c26c7f288337
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365158"
---
# <a name="index-class"></a>index Sınıfı

*N*boyutlu dizin vektörü tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <int _Rank>
class index;
```

### <a name="parameters"></a>Parametreler

*_Rank*<br/>
Boyutların sıralaması veya sayısı.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[dizin Oluşturucu](#index_ctor)|`index` sınıfının yeni bir örneğini başlatır.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[işleç-](#operator--)|Nesnenin her öğesini `index` eriter.|
|[işleç%=](#operator_mod_eq)|Bu öğe bir sayıya bölündüğünde nesnedeki her öğenin `index` modüllerini (kalan) hesaplar.|
|[işleç*=](#operator_star_eq)|Nesnenin her öğesini `index` bir sayıyla çarpar.|
|[işleç/=](#operator_div_eq)|Nesnenin her öğesini bir sayıya `index` böler.|
|[dizin::operatör\[\]](#operator_at)|Belirtilen dizinde olan öğeyi döndürür.|
|[işleç++](#operator_add_add)|Nesnenin her öğesini `index` decrements.|
|[işleç+=](#operator_add_eq)|Nesnenin her öğesine belirtilen `index` sayıyı ekler.|
|[işleç=](#operator_eq)|Belirtilen `index` nesnenin içeriğini buna kopyalar.|
|[işleç-=](#operator_-_eq)|Nesnenin her öğesinden belirtilen sayıyı `index` çıkarır.|

### <a name="public-constants"></a>Genel Sabitler

|Adı|Açıklama|
|----------|-----------------|
|[sıralama Sabit](#rank)|Nesnenin sıralamasını `index` depolar.|

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`index`

## <a name="remarks"></a>Açıklamalar

Yapı, `index` *N-boyutlu*bir boşlukta benzersiz bir konum belirten *N* tamsayılarının koordinat vektörütemsil eder. Vektördeki değerler en önemliden en az anlamlıya doğru sıralanır. [Operatör=](#operator_eq)kullanarak bileşenlerin değerlerini alabilirsiniz.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** amp.h

**Ad alanı:** Eşzamanlılık

## <a name="index-constructor"></a><a name="index_ctor"></a>dizin Oluşturucu

Dizin sınıfının yeni bir örneğini başolarak karşılar.

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
Rütbe değerlerine sahip tek boyutlu bir dizi.

*_I*<br/>
Tek boyutlu bir dizinde dizin konumu.

*_I0*<br/>
En önemli boyutun uzunluğu.

*_I1*<br/>
Bir sonrakien-en önemli boyutun uzunluğu.

*_I2*<br/>
En az önemli boyutun uzunluğu.

*_Other*<br/>
Yeni dizin nesnesinin dayandığı bir dizin nesnesi.

## <a name="operator--"></a><a name="operator--"></a>işleç-

Dizin nesnesinin her öğesini kararları.

```cpp
index<_Rank>& operator--() restrict(amp,cpu);

index operator--(
   int
) restrict(amp,cpu);
```

### <a name="return-values"></a>Döndürülen değerler

Önek işleci için dizin nesnesi (*bu). Sonek işleci için yeni bir dizin nesnesi.

## <a name="operator"></a><a name="operator_mod_eq"></a>işleç%=

Dizin nesnesindeki her öğenin modüllerini (kalan) hesaplar, bu öğe belirtilen sayıya bölündüğünde.

```cpp
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Modülü bulmak için bölünecek sayı.

## <a name="return-value"></a>Dönüş Değeri

Dizin nesnesi.

## <a name="operator"></a><a name="operator_star_eq"></a>işleç*=

Dizin nesnesindeki her öğeyi belirtilen sayıyla çarpar.

```cpp
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Çarpımı gereken sayı.

## <a name="operator"></a><a name="operator_div_eq"></a>işleç/=

Dizin nesnesindeki her öğeyi belirtilen sayıya böler.

```cpp
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Rhs*<br/>
Bölünecek sayı.

## <a name="operator"></a><a name="operator_at"></a>Işleç\[\]

Dizin bileşenini belirtilen konumda döndürür.

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
0'dan eksi 1'e kadar bir sonda.

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

## <a name="operator"></a><a name="operator_add_add"></a>işleç++

Dizin nesnesinin her öğesini artışlar.

```cpp
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```

### <a name="return-value"></a>Dönüş Değeri

Önek işleci için dizin nesnesi (*bu). Sonek işleci için yeni bir dizin nesnesi.

## <a name="operator"></a><a name="operator_add_eq"></a>işleç+=

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

## <a name="operator"></a><a name="operator_eq"></a>işleç=

Belirtilen dizin nesnesinin içeriğini buna kopyalar.

```cpp
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler

*_Other*<br/>
Kopyalanması gereken dizin nesnesi.

### <a name="return-value"></a>Dönüş Değeri

Bu dizin nesnesine bir başvuru.

## <a name="operator-"></a><a name="operator_-_eq"></a>işleç-=

Dizin nesnesinin her öğesinden belirtilen sayıyı çıkarır.

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
Çıkarılabilen numara.

### <a name="return-value"></a>Dönüş Değeri

Dizin nesnesi.

## <a name="rank"></a><a name="rank"></a>Rütbe

Dizin nesnesinin sıralamasını alır.

```cpp
static const int rank = _Rank;
```

## <a name="see-also"></a>Ayrıca bkz.

[Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
