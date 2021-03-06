---
description: 'Daha fazla bilgi edinin: &lt; karmaşık&gt;'
title: '&lt;ş&gt;'
ms.date: 01/15/2021
f1_keywords:
- <complex>
- complex/std::literals::complex_literals
- std::literals::complex_literals
- complex_literals
- complex/std::literals::complex_literals::operator "i
- std::literals::complex_literals::operator i
- complex/std::literals::complex_literals::operator "if
- std::literals::complex_literals::operator if
- complex/std::literals::complex_literals::operator "i
- std::literals::complex_literals::operator i
helpviewer_keywords:
- complex header
ms.openlocfilehash: 4fb309d46ff6f7cba84dc8a4f0c7cf41fbf7d4d6
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667377"
---
# `<complex>`

Kapsayıcı sınıfı şablonunu `complex` ve destekleyici şablonlarını tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<complex>

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

*Karmaşık bir sayı* , gerçek sayıların sıralı bir çiftidir. Yalnızca geometrik olarak, *karmaşık düzlem* gerçek ve iki boyutlu düzledir. Gerçek düzleden ayırt eden karmaşık düzlemin özel nitelikleri, ek bir cebirsel yapısına sahip olmasından kaynaklanır. Bu cebirsel yapısında iki temel işlem vardır:

- Toplama, (*a*, *b*) + (*c*, *d*) = (  +  *c*, *b*  +  *d*) olarak tanımlanır

- Çarpma, (*a*, *b*) \* (*c*, *d*) = (*AC*  -  *BD*, *ad*  +  *BC*) olarak tanımlanır

Karmaşık ek ve karmaşık çarpma işlemlerine sahip karmaşık sayıların kümesi, standart cebirsel Sense içindeki bir *alandır* :

- Toplama ve çarpma işlemleri, tam olarak gerçek sayı alanı üzerinde gerçek ekleme ve çarpma ile aynı şekilde, ek olarak, aynı şekilde dağıtılır ve çarpıcı olur.

- Karmaşık sayı (0, 0), eklenebilir kimliktir ve (1, 0), çarpma kimliğidir.

- Karmaşık bir sayı (*a*, *b*) için ek ters çevirme, (0,*0) hariç* olmak üzere bu tür karmaşık sayılar için çarpma tersidir

   (*a**/(*<sup>2</sup>  +  *b*<sup></sup>2),-*b*/(2 <sup></sup>  +  *b*<sup></sup>2))

*Z* a bı biçiminde *z* = (*a*, *b*) karmaşık numarasını temsil ederek  =    +  , *ı*<sup>2</sup> =-1 olduğunda, gerçek sayı kümesinin algebi kuralları, karmaşık sayılar ve bileşenleri kümesine uygulanabilir. Örnek:

   (1 + 2 *ı*) \* (2 + 3 *ı*) = 1 \* (2 + 3 *ı)*+ 2 *ı* \* (2 + 3 *ı*) = (2 + 3 *ı*) + (4 *i* + 6 *ı*<sup>2</sup>) = (2-6) + (3 + 4)*i* =-4 + 7 *ı*

Karmaşık sayıların sistemi bir alandır, ancak sıralı bir alan değildir. Gerçek sayıların ve alt kümelerinin alanı için olduğu gibi karmaşık sayıların sıralaması yoktur; bu nedenle, gerçek sayılara göre karmaşık sayılara uygulanamaz.

Bir karmaşık sayı olan *z*'yi temsil eden üç ortak biçim vardır:

- Kartezyen: *z*  =  *a*  +  *bı*

- Kutupsal: *z*  =  *r* (cos *p*  +  *i* *y*)

- Üstel: *z*  =  *r* \* *e*<sup>*IP*</sup>

Karmaşık bir sayının bu standart temsillerinde kullanılan terimler şu şekilde adlandırılır:

- Gerçek Kartezyen bileşen veya gerçek bölüm *a*.

- Sanal Kartezyen bileşeni veya sanal bölüm *b*.

- Bir karmaşık sayının mod veya mutlak değeri *r*.

- Radyan *cinsinden bağımsız* değişken veya aşama açısı.

Aksi belirtilmediği takdirde, birden çok değer döndürebilmesine olanak veren işlevler, tek değerli tutmak için-π ' dan büyük ve + π ' den küçük veya buna eşit olan bağımsız değişkenlerin bir asıl değerini döndürmesi gerekir. Tüm açıların radyan cinsinden ifade edilmesi gerekir, burada bir daire içinde 2π radyan (360 derece) bulunur.

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

| Ad | Açıklama |
|--|--|
| [`abs`](../standard-library/complex-functions.md#abs) | Karmaşık bir sayının mod sayısını hesaplar. |
| [`acos`](../standard-library/complex-functions.md#acos) |  |
| [`acosh`](../standard-library/complex-functions.md#acosh) |  |
| [`arg`](../standard-library/complex-functions.md#arg) | Bağımsız değişkeni karmaşık bir sayıdan ayıklar. |
| [`asin`](../standard-library/complex-functions.md#asin) |  |
| [`asinh`](../standard-library/complex-functions.md#asinh) |  |
| [`atan`](../standard-library/complex-functions.md#atan) |  |
| [`atanh`](../standard-library/complex-functions.md#atanh) |  |
| [`conj`](../standard-library/complex-functions.md#conj) | Karmaşık bir sayının karmaşık eşleniğini döndürür. |
| [`cos`](../standard-library/complex-functions.md#cos) | Karmaşık bir sayının kosinüsünü döndürür. |
| [`cosh`](../standard-library/complex-functions.md#cosh) | Karmaşık bir sayının hiperbolik kosinüsünü döndürür. |
| [`exp`](../standard-library/complex-functions.md#exp) | Karmaşık bir sayının üstel fonksiyonunu döndürür. |
| [`imag`](../standard-library/complex-functions.md#imag) | Karmaşık bir sayının sanal bileşenini ayıklar. |
| [`log`](../standard-library/complex-functions.md#log) | Karmaşık bir sayının doğal logaritmasını döndürür. |
| [`log10`](../standard-library/complex-functions.md#log10) | Karmaşık bir sayının 10 tabanında logaritmasını döndürür. |
| [`norm`](../standard-library/complex-functions.md#norm) | Karmaşık bir sayının norm sayısını ayıklar. |
| [`polar`](../standard-library/complex-functions.md#polar) | Kartezyen biçiminde, belirtilen mod ve bağımsız değişkene karşılık gelen karmaşık sayıyı döndürür. |
| [`pow`](../standard-library/complex-functions.md#pow) | Karmaşık bir sayı olan bir tabanı başka bir karmaşık sayının gücüne yükselterek elde edilen karmaşık sayıyı değerlendirir. |
| [`proj`](../standard-library/complex-functions.md#proj) |  |
| [`real`](../standard-library/complex-functions.md#real) | Karmaşık bir sayının gerçek bileşenini ayıklar. |
| [`sin`](../standard-library/complex-functions.md#sin) | Karmaşık bir sayının sinüsünü döndürür. |
| [`sinh`](../standard-library/complex-functions.md#sinh) | Karmaşık bir sayının hiperbolik sinüsünü döndürür. |
| [`sqrt`](../standard-library/complex-functions.md#sqrt) | Karmaşık bir sayının kare kökünü döndürür. |
| [`tan`](../standard-library/complex-functions.md#tan) | Karmaşık bir sayının tanjantını döndürür. |
| [tanh](../standard-library/complex-functions.md#tanh) | Karmaşık bir sayının hiperbolik tanjantını döndürür. |

### <a name="operators"></a>İşleçler

| Ad | Açıklama |
|--|--|
| [`operator!=`](../standard-library/complex-operators.md#op_neq) | İki karmaşık sayı arasında eşitsizlik için, biri veya her ikisi de gerçek ve sanal parçalar için türün alt kümesine ait olabilir. |
| [`operator*`](../standard-library/complex-operators.md#op_star) | , Biri veya her ikisi de gerçek ve sanal parçalar için türün alt kümesine ait olabilen iki karmaşık sayıyı çarpar. |
| [`operator+`](../standard-library/complex-operators.md#op_add) | , Biri veya her ikisi de gerçek ve sanal parçalar için türün alt kümesine ait olabilen iki karmaşık sayı ekler. |
| [`operator-`](../standard-library/complex-operators.md#operator-) | , Bir veya her ikisini de gerçek ve sanal parçalar için türün alt kümesine ait olabilen iki karmaşık sayıyı çıkartır. |
| [`operator/`](../standard-library/complex-operators.md#op_div) | İki karmaşık sayıyı, birini veya her ikisini de gerçek ve sanal parçalar için türün alt kümesine ait olabilir. |
| [`operator<<`](../standard-library/complex-operators.md#op_lt_lt) | Çıkış akışına karmaşık bir sayı ekleyen bir şablon işlevi. |
| [`operator==`](../standard-library/complex-operators.md#op_eq_eq) | İki karmaşık sayı arasındaki eşitlik için bir veya her ikisinin de gerçek ve sanal parçalar için türün alt kümesine ait olabileceğini sınar. |
| [`operator>>`](../standard-library/complex-operators.md#op_gt_gt) | Giriş akışından karmaşık bir değer çıkaran bir şablon işlevi. |

### <a name="classes"></a>Sınıflar

| Ad | Açıklama |
|--|--|
| [`complex<double>`](../standard-library/complex-double.md) | Açıkça özelleştirilmiş sınıf şablonu, her ikisi de türünde, her ikisi de **`double`** karmaşık bir sayının gerçek bölümünü temsil eden ve ikincisi sanal parçayı temsil eden, sıralı bir nesne çifti depolayan bir nesneyi tanımlar. |
| [`complex<float>`](../standard-library/complex-float.md) | Açıkça özelleştirilmiş sınıf şablonu, her ikisi de türünde, her ikisi de **`float`** karmaşık bir sayının gerçek bölümünü temsil eden ve ikincisi sanal parçayı temsil eden, sıralı bir nesne çifti depolayan bir nesneyi tanımlar. |
| [`complex<long double>`](../standard-library/complex-long-double.md) | Açıkça özelleştirilmiş sınıf şablonu, her ikisi de türünde, her ikisi de **`long double`** karmaşık bir sayının gerçek bölümünü temsil eden ve ikincisi sanal parçayı temsil eden, sıralı bir nesne çifti depolayan bir nesneyi tanımlar. |
| [`complex`](../standard-library/complex-class.md) | Sınıf şablonu, karmaşık sayı sistemini temsil etmek için kullanılan bir nesneyi tanımlar ve karmaşık aritmetik işlemler gerçekleştirir. |

### <a name="literals"></a>Değişmez Değerler

\<complex>Üst bilgi, aşağıdaki [Kullanıcı tanımlı sabit değerleri](../cpp/user-defined-literals-cpp.md)tanımlar. Değişmez değerler, sıfır değerinin gerçek bir bölümü ve giriş parametresinin değeri olan bir sanal bölüm olan karmaşık bir sayı oluşturur.

| Bildirim | Description |
|--|--|
| `constexpr complex<long double> operator""il(long double d)`<br />`constexpr complex<long double> operator""il(unsigned long long d)` | Döndürdüğü `complex<long double>{0.0L, static_cast<long double>(d)}` |
| `constexpr complex<double> operator""i(long double d)`<br />`constexpr complex<double> operator""i(unsigned long long d)` | Döndürür: `complex<double>{0.0, static_cast<double>(d)}` . |
| `constexpr complex<float> operator""if(long double d)`<br />`constexpr complex<float> operator""if(unsigned long long d)` | Döndürür: `complex<float>{0.0f, static_cast<float>(d)}` . |

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
