---
title: SafeInt İşlevleri
ms.date: 06/23/2020
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
ms.openlocfilehash: c968601d95403dd63540a7a8ec2190a199fa1c5a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219345"
---
# <a name="safeint-functions"></a>SafeInt İşlevleri

SafeInt Kitaplığı, [SafeInt sınıfının](safeint-class.md)bir örneğini oluşturmadan kullanabileceğiniz çeşitli işlevler sağlar. Tek bir matematik işlemini tamsayı taşmadan korumak istiyorsanız, bu işlevleri kullanabilirsiniz. Birden çok matematik işlemini korumak istiyorsanız nesneler oluşturmanız gerekir `SafeInt` . `SafeInt`Bu işlevleri birden çok kez kullanmak yerine nesneleri oluşturmak daha etkilidir.

Bu işlevler, bu parametreleri ilk olarak aynı türe dönüştürmek zorunda kalmadan iki farklı parametre türü üzerinde karşılaştırmanıza veya gerçekleştirmenize olanak tanır.

Bu işlevlerin her biri iki şablon türüne sahiptir: `T` ve `U` . Bu türlerin her biri bir Boole, karakter veya integral türü olabilir. Integral türleri imzalanabilir veya imzasız ve 8 bitten 64 bite kadar herhangi bir boyutta olabilir.

> [!NOTE]
> Bu kitaplığın en son sürümü konumunda bulunur [https://github.com/dcleblanc/SafeInt](https://github.com/dcleblanc/SafeInt) .

## <a name="in-this-section"></a>Bu Bölümde

İşlev                      | Açıklama
----------------------------- | --------------------------------------------------------------
[SafeAdd](#safeadd)           | İki sayı ekler ve taşmaya karşı koruma sağlar.
[SafeCast](#safecast)         | Bir parametre türünü başka bir türe yayınlar.
[SafeDivide](#safedivide)     | İki sayıyı böler ve sıfıra bölmek için koruma sağlar.
[SafeEquals](#safeequals), [SafeGreaterThan](#safegreaterthan), [SafeGreaterThanEquals](#safegreaterthanequals), [SafeLessThan](#safelessthan), [safelessmon eşittir](#safelessthanequals), [SafeNotEquals](#safenotequals) | İki sayıyı karşılaştırır. Bu işlevler, iki farklı sayıyı türlerini değiştirmeden karşılaştırmanızı sağlar.
[SafeModulus](#safemodulus)   | İki sayı üzerinde mod işlemini gerçekleştirir.
[SafeMultiply](#safemultiply) | İki sayıyı birlikte çarpar ve taşmaya karşı koruma sağlar.
[SafeSubtract](#safesubtract) | İki sayıyı çıkartır ve taşmaya karşı korur.

## <a name="related-sections"></a>İlgili Bölümler

Section                                                  | Açıklama
-------------------------------------------------------- | ----------------------------------------------------
[SafeInt](safeint-class.md)                   | `SafeInt`Sınıfı.
[SafeIntException](safeintexception-class.md) | SafeInt kitaplığına özgü özel durum sınıfı.

## <a name="safeadd"></a><a name="safeadd"></a>SafeAdd

Taşmaya karşı koruyan bir şekilde iki sayı ekler.

```cpp
template<typename T, typename U>
inline bool SafeAdd (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
'ndaki Eklenecek ilk sayı. Bu T türünde olmalıdır.

*larınız*<br/>
'ndaki Eklenecek ikinci sayı. Bu, U türünde olmalıdır.

*kaynaklanan*<br/>
dışı `SafeAdd`Sonucu depolayan parametre.

### <a name="return-value"></a>Dönüş Değeri

**`true`** bir hata oluşursa; **`false`** bir hata oluşursa.

## <a name="safecast"></a><a name="safecast"></a>SafeCast

Bir sayı türünü başka bir türe yayınlar.

```cpp
template<typename T, typename U>
inline bool SafeCast (
   const T From,
   U& To
);
```

### <a name="parameters"></a>Parametreler

*Kaynak*<br/>
'ndaki Dönüştürülecek kaynak numara. Bu, türünde olmalıdır `T` .

*Hedef*<br/>
dışı Yeni sayı türüne bir başvuru. Bu, türünde olmalıdır `U` .

### <a name="return-value"></a>Dönüş Değeri

**`true`** bir hata oluşursa; **`false`** bir hata oluşursa.

## <a name="safedivide"></a><a name="safedivide"></a>SafeDivide

İki sayıyı sıfıra bölmek için koruyan bir şekilde böler.

```cpp
template<typename T, typename U>
inline bool SafeDivide (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
'ndaki Bölünen. Bu T türünde olmalıdır.

*larınız*<br/>
'ndaki Bölen. Bu, U türünde olmalıdır.

*kaynaklanan*<br/>
dışı `SafeDivide`Sonucu depolayan parametre.

### <a name="return-value"></a>Dönüş Değeri

**`true`** bir hata oluşursa; **`false`** bir hata oluşursa.

## <a name="safeequals"></a><a name="safeequals"></a>SafeEquals

Eşit olup olmadığını anlamak için iki sayıyı karşılaştırır.

```cpp
template<typename T, typename U>
inline bool SafeEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
'ndaki Karşılaştırılacak ilk sayı. Bu T türünde olmalıdır.

*larınız*<br/>
'ndaki Karşılaştırılacak ikinci sayı. Bu, U türünde olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

**`true`***t* ve *u* eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Yöntemi geliştirir, `==` çünkü `SafeEquals` iki farklı sayı türünü karşılaştırmanızı sağlar.

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

*şı*<br/>
'ndaki Karşılaştırılacak ilk sayı. Bu, türünde olmalıdır `T` .

*larınız*<br/>
'ndaki Karşılaştırılacak ikinci sayı. Bu, türünde olmalıdır `U` .

### <a name="return-value"></a>Dönüş Değeri

**`true`***t* *u*'den büyükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

`SafeGreaterThan`iki farklı sayı türünü karşılaştırmanızı sağlayarak normal karşılaştırma işlecini genişletir.

## <a name="safegreaterthanequals"></a><a name="safegreaterthanequals"></a>SafeGreaterThanEquals

İki sayıyı karşılaştırır.

```cpp
template <typename T, typename U>
inline bool SafeGreaterThanEquals (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
'ndaki Karşılaştırılacak ilk sayı. Bu, türünde olmalıdır `T` .

*larınız*<br/>
'ndaki Karşılaştırılacak ikinci sayı. Bu, türünde olmalıdır `U` .

### <a name="return-value"></a>Dönüş Değeri

**`true`***t* , *u*'dan büyükse veya eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

`SafeGreaterThanEquals`iki farklı sayı türünü karşılaştırmanızı sağladığından Standart karşılaştırma işlecini geliştirir.

## <a name="safelessthan"></a><a name="safelessthan"></a>SafeLessThan

Bir sayının diğerinden daha küçük olup olmadığını belirler.

```cpp
template<typename T, typename U>
inline bool SafeLessThan (
   const T t,
   const U u
) throw ();
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
'ndaki İlk sayı. Bu, türünde olmalıdır `T` .

*larınız*<br/>
'ndaki İkinci sayı. Bu, türünde olmalıdır `U` .

### <a name="return-value"></a>Dönüş Değeri

**`true`***t* *u*'den küçükse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Bu yöntem, `SafeLessThan` iki farklı türden sayıyı karşılaştırmanızı sağladığından Standart karşılaştırma işlecini geliştirir.

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

*şı*<br/>
'ndaki Karşılaştırılacak ilk sayı. Bu, türünde olmalıdır `T` .

*larınız*<br/>
'ndaki Karşılaştırılacak ikinci sayı. Bu, türünde olmalıdır `U` .

### <a name="return-value"></a>Dönüş Değeri

**`true`***t* , *u*'den küçükse veya eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

`SafeLessThanEquals`iki farklı sayı türünü karşılaştırmanızı sağlayarak normal karşılaştırma işlecini genişletir.

## <a name="safemodulus"></a><a name="safemodulus"></a>SafeModulus

İki sayı üzerinde mod işlemini gerçekleştirir.

```cpp
template<typename T, typename U>
inline bool SafeModulus (
   const T t,
   const U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
'ndaki Bölen. Bu, türünde olmalıdır `T` .

*larınız*<br/>
'ndaki Bölünen. Bu, türünde olmalıdır `U` .

*kaynaklanan*<br/>
dışı `SafeModulus`Sonucu depolayan parametre.

### <a name="return-value"></a>Dönüş Değeri

**`true`** bir hata oluşursa; **`false`** bir hata oluşursa.

## <a name="safemultiply"></a><a name="safemultiply"></a>SafeMultiply

İki sayıyı taşmayı koruyan bir şekilde birbiriyle çarpar.

```cpp
template<typename T, typename U>
inline bool SafeMultiply (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
'ndaki Çarpılacak ilk sayı. Bu, türünde olmalıdır `T` .

*larınız*<br/>
'ndaki Çarpılacak ikinci sayı. Bu, türünde olmalıdır `U` .

*kaynaklanan*<br/>
dışı `SafeMultiply`Sonucu depolayan parametre.

### <a name="return-value"></a>Dönüş Değeri

**`true`** bir hata oluşursa; **`false`** bir hata oluşursa.

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

*şı*<br/>
'ndaki Karşılaştırılacak ilk sayı. Bu, türünde olmalıdır `T` .

*larınız*<br/>
'ndaki Karşılaştırılacak ikinci sayı. Bu, türünde olmalıdır `U` .

### <a name="return-value"></a>Dönüş Değeri

**`true`***t* ve *u* eşitse; Aksi takdirde **`false`** .

### <a name="remarks"></a>Açıklamalar

Yöntemi geliştirir, `!=` çünkü `SafeNotEquals` iki farklı sayı türünü karşılaştırmanızı sağlar.

## <a name="safesubtract"></a><a name="safesubtract"></a>SafeSubtract

İki sayıyı taşmayı koruyacak şekilde çıkartır.

```cpp
template<typename T, typename U>
inline bool SafeSubtract (
   T t,
   U u,
   T& result
) throw ();
```

### <a name="parameters"></a>Parametreler

*şı*<br/>
'ndaki Çıkarma sırasında ilk sayı. Bu, türünde olmalıdır `T` .

*larınız*<br/>
'ndaki *T*'den çıkarılacak sayı. Bu, türünde olmalıdır `U` .

*kaynaklanan*<br/>
dışı `SafeSubtract`Sonucu depolayan parametre.

### <a name="return-value"></a>Dönüş Değeri

**`true`** bir hata oluşursa; **`false`** bir hata oluşursa.
