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
ms.openlocfilehash: 0cf1418e3bf00c037faaa67de2bc76ad2b7cc5e0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578405"
---
# <a name="safeint-functions"></a>SafeInt İşlevleri

SafeInt Kitaplığı örneği oluşturulmadan kullanabileceğiniz çeşitli işlevler sağlar [SafeInt sınıfı](../windows/safeint-class.md). Tek bir matematiksel işlem tamsayı taşmasından korumak istiyorsanız, bu işlevleri kullanabilirsiniz. Birden çok matematik işlemi korumak istiyorsanız, oluşturmalısınız `SafeInt` nesneleri. Oluşturmak için daha verimlidir `SafeInt` birden çok kez bu işlevlerin kullanımı çok nesneleri.

Bu işlevler karşılaştırmak ya da önce aynı türe dönüştürmek zorunda kalmadan iki farklı türde parametreler matematik işlemlerini gerçekleştirmek etkinleştirin.

Bu işlevlerin her biri iki şablon türü vardır: `T` ve `U`. Bu türlerinin her biri bir Boole değeri, karakter veya bir tamsayı türü olabilir. Tam sayı türleri imzalı veya imzasız tüm boyutlardaki 8 bitten 64 bite.

> [!NOTE]
> Bu kitaplık en son sürümünü şu konumdadır [ https://github.com/dcleblanc/SafeInt ](https://github.com/dcleblanc/SafeInt).

## <a name="in-this-section"></a>Bu Bölümde

İşlev                      | Açıklama
----------------------------- | --------------------------------------------------------------
[SafeAdd](#safeadd)           | İki sayı ekleyen ve taşmasına karşı korur.
[SafeCast](#safecast)         | Başka bir tür parametresine bir tür çevirir.
[SafeDivide](#safedivide)     | İki sayıyı böler ve sıfıra bölme karşı korur.
[SafeEquals](#safeequals), [SafeGreaterThan](#safegreaterthan), [SafeGreaterThanEquals](#safegreaterthanequals), [SafeLessThan](#safelessthan), [SafeLessThanEquals](#safelessthanequals), [ SafeNotEquals](#safenotequals) | İki sayıyı karşılaştırır. Bu işlevler, iki farklı tür sayı türlerini değiştirmeden karşılaştırmanızı sağlar.
[SafeModulus](#safemodulus)   | İki sayıyı mod işlemi gerçekleştirir.
[SafeMultiply](#safemultiply) | Birlikte iki sayıyı çarpar ve taşmasına karşı korur.
[SafeSubtract](#safesubtract) | İki sayıyı çıkarır ve taşmasına karşı korur.

## <a name="related-sections"></a>İlgili Bölümler

Bölüm                                                  | Açıklama
-------------------------------------------------------- | ----------------------------------------------------
[SafeInt](../windows/safeint-class.md)                   | `SafeInt` Sınıfı.
[Safeıntexception](../windows/safeintexception-class.md) | SafeInt Kitaplığı'na belirli özel durum sınıfı.

## <a name="safeadd"></a>SafeAdd

İki sayıyı taşmasına karşı koruyan bir şekilde ekler.

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
[in] Eklenecek ilk sayı. Bu t türünde olmalıdır

*u*<br/>
[in] Eklenecek ikinci sayı. Bu u türü olmalıdır

*Sonuç*<br/>
[out] Parametrenin nereden `SafeAdd` sonucu depolar.

### <a name="return-value"></a>Dönüş Değeri

**doğru** Eğer hiç Hata oluşmazsa; **false** hata oluşması durumunda.

## <a name="safecast"></a>SafeCast

Bir başka bir türe sayı türü çevirir.

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>Parametreler

*Kaynak*<br/>
[in] Dönüştürülecek kaynak sayısı. Bu tür olmalıdır `T`.

*Hedef*<br/>
[out] Yeni bir sayı türü referansı. Bu tür olmalıdır `U`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** Eğer hiç Hata oluşmazsa; **false** hata oluşması durumunda.

## <a name="safedivide"></a>SafeDivide

Sıfıra bölme karşı koruyan bir şekilde iki sayıyı böler.

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
[in] Bölen. Bu t türünde olmalıdır

*u*<br/>
[in] Bölünen. Bu u türü olmalıdır

*Sonuç*<br/>
[out] Parametrenin nereden `SafeDivide` sonucu depolar.

### <a name="return-value"></a>Dönüş Değeri

**doğru** Eğer hiç Hata oluşmazsa; **false** hata oluşması durumunda.

## <a name="safeequals"></a>SafeEquals

Eşit olup olmadığını belirlemek için iki sayının karşılaştırır.

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[in] Karşılaştırılacak birinci sayı. Bu t türünde olmalıdır

*u*<br/>
[in] Karşılaştırılacak ikinci sayı. Bu u türü olmalıdır

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *t* ve *u* Aksi takdirde eşit **false**.

### <a name="remarks"></a>Açıklamalar

Yöntem geliştirir `==` çünkü `SafeEquals` iki farklı tür sayı karşılaştırmanızı sağlar.

## <a name="safegreaterthan"></a>SafeGreaterThan

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
[in] Karşılaştırılacak birinci sayı. Bu tür olmalıdır `T`.

*u*<br/>
[in] Karşılaştırılacak ikinci sayı. Bu tür olmalıdır `U`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *t* büyüktür *u*; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

`SafeGreaterThan` Normal karşılaştırma işleci iki farklı tür sayı Karşılaştırılacak sağlayarak genişletir.

## <a name="safegreaterthanequals"></a>SafeGreaterThanEquals

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
[in] Karşılaştırılacak birinci sayı. Bu tür olmalıdır `T`.

*u*<br/>
[in] Karşılaştırılacak ikinci sayı. Bu tür olmalıdır `U`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *t* büyüktür veya eşittir *u*; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

`SafeGreaterThanEquals` iki farklı tür sayı karşılaştırmanıza olanak sağladığından, standart karşılaştırma işleci geliştirir.

## <a name="safelessthan"></a>SafeLessThan

Bir sayı daha az olup olmadığını belirler.

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[in] İlk sayı. Bu tür olmalıdır `T`.

*u*<br/>
[in] İkinci numarası. Bu tür olmalıdır `U`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *t* olduğu küçüktür *u*; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

Bu yöntem standart karşılaştırma işleci, çünkü geliştirir. `SafeLessThan` numarası iki farklı türde karşılaştırmanızı sağlar.

## <a name="safelessthanequals"></a>SafeLessThanEquals

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
[in] Karşılaştırılacak birinci sayı. Bu tür olmalıdır `T`.

*u*<br/>
[in] Karşılaştırılacak ikinci sayı. Bu tür olmalıdır `U`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *t* küçüktür veya eşittir *u*; Aksi takdirde **false**.

### <a name="remarks"></a>Açıklamalar

`SafeLessThanEquals` Normal karşılaştırma işleci iki farklı tür sayı Karşılaştırılacak sağlayarak genişletir.

## <a name="safemodulus"></a>SafeModulus

İki sayıyı mod işlemi gerçekleştirir.

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
[in] Bölen. Bu tür olmalıdır `T`.

*u*<br/>
[in] Bölünen. Bu tür olmalıdır `U`.

*Sonuç*<br/>
[out] Parametrenin nereden `SafeModulus` sonucu depolar.

### <a name="return-value"></a>Dönüş Değeri

**doğru** Eğer hiç Hata oluşmazsa; **false** hata oluşması durumunda.

## <a name="safemultiply"></a>SafeMultiply

Birlikte taşmasına karşı koruyan bir şekilde iki sayıyı çarpar.

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
[in] Çarpılacak ilk sayı. Bu tür olmalıdır `T`.

*u*<br/>
[in] Çarpılacak ikinci sayı. Bu tür olmalıdır `U`.

*Sonuç*<br/>
[out] Parametrenin nereden `SafeMultiply` sonucu depolar.

### <a name="return-value"></a>Dönüş Değeri

`true` Eğer hiç Hata oluşmazsa; `false` hata oluşması durumunda.

## <a name="safenotequals"></a>SafeNotEquals

İki sayıyı eşit olup olmadığını belirler.

```cpp
template<typename T, typename U>
inline bool SafeNotEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*T*<br/>
[in] Karşılaştırılacak birinci sayı. Bu tür olmalıdır `T`.

*u*<br/>
[in] Karşılaştırılacak ikinci sayı. Bu tür olmalıdır `U`.

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa *t* ve *u* olmayan Aksi takdirde eşit **false**.

### <a name="remarks"></a>Açıklamalar

Yöntem geliştirir `!=` çünkü `SafeNotEquals` iki farklı tür sayı karşılaştırmanızı sağlar.

## <a name="safesubtract"></a>SafeSubtract

İki sayıyı taşmasına karşı koruyan bir şekilde çıkarır.

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
[in] Çıkarma ilk numarası. Bu tür olmalıdır `T`.

*u*<br/>
[in] Den çıkarılacak sayı *t*. Bu tür olmalıdır `U`.

*Sonuç*<br/>
[out] Parametrenin nereden `SafeSubtract` sonucu depolar.

### <a name="return-value"></a>Dönüş Değeri

**doğru** Eğer hiç Hata oluşmazsa; **false** hata oluşması durumunda.
