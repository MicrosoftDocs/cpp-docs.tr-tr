---
title: SafeInt İşlevleri
ms.date: 10/22/2018
ms.topic: reference
f1_keywords:
- SafeInt functions
- SafeAdd
- SafeCast
- SafeDivide
- SafeEquals
- SafeGreaterThan
- SafeGreaterThanEquals
- SafeLessThan
- SafeLessThanEquals
- SafeModulus
- SafeMultiply
- SafeNotEquals
- SafeSubtract
helpviewer_keywords:
- functions, SafeInt
- SafeAdd function
- SafeCast function
- SafeDivide function
- SafeEquals function
- SafeGreaterThan function
- SafeGreaterThanEquals function
- SafeLessThan function
- SafeLessThanEquals function
- SafeModulus function
- SafeMultiply function
- SafeNotEquals function
- SafeSubtract function
ms.assetid: fdc208e5-5d8a-41a9-8271-567fd438958d
ms.openlocfilehash: c1c5593aee19254d4348d4e8658ffe9c3f0cf1b2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368245"
---
# <a name="safeint-functions"></a>SafeInt İşlevleri

SafeInt kitaplığı, [SafeInt sınıfının](../safeint/safeint-class.md)bir örneğini oluşturmadan kullanabileceğiniz çeşitli işlevler sağlar. Tek bir matematiksel işlemi tamsayı taşmasına karşı korumak istiyorsanız, bu işlevleri kullanabilirsiniz. Birden çok matematiksel işlemi korumak istiyorsanız, `SafeInt` nesneler oluşturmanız gerekir. Nesneleri oluşturmak, `SafeInt` bu işlevleri birden çok kez kullanmaktan daha verimlidir.

Bu işlevler, önce aynı türe dönüştürmek zorunda kalmadan iki farklı türde parametre üzerinde matematiksel işlemleri karşılaştırmanızı veya gerçekleştirmenizi sağlar.

Bu işlevlerin her biri `T` iki `U`şablon türü vardır: ve. Bu türlerin her biri boolean, karakter veya integral türü olabilir. İntegral türleri imzalanabilir veya imzasız olabilir ve 8 bitten 64 bit'e kadar herhangi bir boyut.

> [!NOTE]
> Bu kitaplığın en son sürümü [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt).

## <a name="in-this-section"></a>Bu Bölümde

İşlev                      | Açıklama
----------------------------- | --------------------------------------------------------------
[SafeAdd](#safeadd)           | İki sayı ekler ve taşmalara karşı korur.
[SafeCast](#safecast)         | Bir parametre türünü başka bir türe atar.
[SafeDivide](#safedivide)     | İki sayıyı böler ve sıfıra bölmeye karşı korur.
[SafeEquals](#safeequals), [SafeGreaterThan](#safegreaterthan), [SafeGreaterThanEquals](#safegreaterthanequals), [SafeLessThan](#safelessthan), [SafeLessThanEquals](#safelessthanequals), [SafeNotEquals](#safenotequals) | İki sayıyı karşılaştırır. Bu işlevler, türlerini değiştirmeden iki farklı sayı türünü karşılaştırmanızı sağlar.
[SafeModulus](#safemodulus)   | Modül işlemini iki sayı üzerinde gerçekleştirir.
[SafeMultiply](#safemultiply) | İki sayıyı bir araya getirir ve taşmalara karşı korur.
[SafeSubtract](#safesubtract) | İki sayı çıkarır ve taşmalara karşı korur.

## <a name="related-sections"></a>İlgili Bölümler

Section                                                  | Açıklama
-------------------------------------------------------- | ----------------------------------------------------
[Safeınt](../safeint/safeint-class.md)                   | Sınıf. `SafeInt`
[SafeIntException](../safeint/safeintexception-class.md) | SafeInt kitaplığına özgü özel özel sınıf.

## <a name="safeadd"></a><a name="safeadd"></a>Güvenli Ekle

Taşmalara karşı koruyacak şekilde iki sayı ekler.

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[içinde] Eklenecek ilk sayı. Bu T tipi olmalı.

*U*<br/>
[içinde] Eklenecek ikinci sayı. Bu U tipi olmalı.

*Sonuç*<br/>
[çıkış] Sonucu depoladığı `SafeAdd` parametre.

### <a name="return-value"></a>Dönüş Değeri

hata yoksa **doğrudur;** bir hata oluşursa **yanlış** olur.

## <a name="safecast"></a><a name="safecast"></a>SafeCast

Bir sayı türünü başka bir türe atar.

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>Parametreler

*Kaynak*<br/>
[içinde] Dönüştürülecek kaynak numarası. Bu tür `T`olmalı.

*Hedef*<br/>
[çıkış] Yeni sayı türüne bir başvuru. Bu tür `U`olmalı.

### <a name="return-value"></a>Dönüş Değeri

hata yoksa **doğrudur;** bir hata oluşursa **yanlış** olur.

## <a name="safedivide"></a><a name="safedivide"></a>Güvenli Bölme

İki sayıyı sıfıra bölmeye karşı koruyacak şekilde böler.

```cpp
template<typename T, typename U>
inline bool SafeDivide (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[içinde] Bölücü. Bu T tipi olmalı.

*U*<br/>
[içinde] Temettü. Bu U tipi olmalı.

*Sonuç*<br/>
[çıkış] Sonucu depoladığı `SafeDivide` parametre.

### <a name="return-value"></a>Dönüş Değeri

hata yoksa **doğrudur;** bir hata oluşursa **yanlış** olur.

## <a name="safeequals"></a><a name="safeequals"></a>Güvenli Eşitler

Eşit olup olmadıklarını belirlemek için iki sayıyı karşılaştırır.

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[içinde] Karşılaştırılacak ilk sayı. Bu T tipi olmalı.

*U*<br/>
[içinde] Karşılaştırılacak ikinci sayı. Bu U tipi olmalı.

### <a name="return-value"></a>Dönüş Değeri

*t* ve *u* eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Yöntem, iki `==` `SafeEquals` farklı sayı türünü karşılaştırmanızı sağladığından geliştirir.

## <a name="safegreaterthan"></a><a name="safegreaterthan"></a>SafeGreaterThan

İki sayıyı karşılaştırır.

```cpp
template<typename T, typename U>
inline bool SafeGreaterThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[içinde] Karşılaştırılacak ilk sayı. Bu tür `T`olmalı.

*U*<br/>
[içinde] Karşılaştırılacak ikinci sayı. Bu tür `U`olmalı.

### <a name="return-value"></a>Dönüş Değeri

*t* *u'dan*büyükse **doğrudur** ; aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

`SafeGreaterThan`iki farklı sayı türünü karşılaştırmanızı sağlayarak normal karşılaştırma işlecigenişlet.

## <a name="safegreaterthanequals"></a><a name="safegreaterthanequals"></a>SafeGreaterThanEşitler

İki sayıyı karşılaştırır.

```cpp
template <typename T, typename U>
inline bool SafeGreaterThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[içinde] Karşılaştırılacak ilk sayı. Bu tür `T`olmalı.

*U*<br/>
[içinde] Karşılaştırılacak ikinci sayı. Bu tür `U`olmalı.

### <a name="return-value"></a>Dönüş Değeri

*t* *u'dan*büyük veya eşitse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

`SafeGreaterThanEquals`iki farklı sayı türünü karşılaştırmanızı sağladığından standart karşılaştırma işlecigeliştirir.

## <a name="safelessthan"></a><a name="safelessthan"></a>SafelessThan

Bir sayının diğerinden küçük olup olmadığını belirler.

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[içinde] İlk numara. Bu tür `T`olmalı.

*U*<br/>
[içinde] İkinci sayı. Bu tür `U`olmalı.

### <a name="return-value"></a>Dönüş Değeri

*t* *u'dan*küçükse **doğrudur** ; aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem, iki farklı `SafeLessThan` sayı türünü karşılaştırmanızı sağladığından standart karşılaştırma işlecigeliştirir.

## <a name="safelessthanequals"></a><a name="safelessthanequals"></a>SafeLessThanEquals

İki sayıyı karşılaştırır.

```cpp
template <typename T, typename U>
inline bool SafeLessThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[içinde] Karşılaştırılacak ilk sayı. Bu tür `T`olmalı.

*U*<br/>
[içinde] Karşılaştırılacak ikinci sayı. Bu tür `U`olmalı.

### <a name="return-value"></a>Dönüş Değeri

*t* *u'dan*küçük veya eşitse **doğrudur** ; aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

`SafeLessThanEquals`iki farklı sayı türünü karşılaştırmanızı sağlayarak normal karşılaştırma işlecigenişlet.

## <a name="safemodulus"></a><a name="safemodulus"></a>GüvenliModulus

Modül işlemini iki sayı üzerinde gerçekleştirir.

```cpp
template<typename T, typename U>
inline bool SafeModulus (
   const T t,
   const U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[içinde] Bölücü. Bu tür `T`olmalı.

*U*<br/>
[içinde] Temettü. Bu tür `U`olmalı.

*Sonuç*<br/>
[çıkış] Sonucu depoladığı `SafeModulus` parametre.

### <a name="return-value"></a>Dönüş Değeri

hata yoksa **doğrudur;** bir hata oluşursa **yanlış** olur.

## <a name="safemultiply"></a><a name="safemultiply"></a>Güvenli Çarpma

İki sayıyı taşmalara karşı koruyacak şekilde çarpar.

```cpp
template<typename T, typename U>
inline bool SafeMultiply (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[içinde] Çarpılacak ilk sayı. Bu tür `T`olmalı.

*U*<br/>
[içinde] Çarpılacak ikinci sayı. Bu tür `U`olmalı.

*Sonuç*<br/>
[çıkış] Sonucu depoladığı `SafeMultiply` parametre.

### <a name="return-value"></a>Dönüş Değeri

`true`hata yoksa; `false` bir hata oluşursa.

## <a name="safenotequals"></a><a name="safenotequals"></a>SafeNotEquals

İki sayının eşit olup olmadığını belirler.

```cpp
template<typename T, typename U>
inline bool SafeNotEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[içinde] Karşılaştırılacak ilk sayı. Bu tür `T`olmalı.

*U*<br/>
[içinde] Karşılaştırılacak ikinci sayı. Bu tür `U`olmalı.

### <a name="return-value"></a>Dönüş Değeri

*t* ve *u* eşit değilse **doğrudur;** aksi takdirde **yanlış**.

### <a name="remarks"></a>Açıklamalar

Yöntem, iki `!=` `SafeNotEquals` farklı sayı türünü karşılaştırmanızı sağladığından geliştirir.

## <a name="safesubtract"></a><a name="safesubtract"></a>Güvenli Altlık

İki sayıyı taşmalara karşı koruyacak şekilde çıkarır.

```cpp
template<typename T, typename U>
inline bool SafeSubtract (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[içinde] Çıkarmadaki ilk sayı. Bu tür `T`olmalı.

*U*<br/>
[içinde] *T'den*çıkarılabilen sayı. Bu tür `U`olmalı.

*Sonuç*<br/>
[çıkış] Sonucu depoladığı `SafeSubtract` parametre.

### <a name="return-value"></a>Dönüş Değeri

hata yoksa **doğrudur;** bir hata oluşursa **yanlış** olur.
