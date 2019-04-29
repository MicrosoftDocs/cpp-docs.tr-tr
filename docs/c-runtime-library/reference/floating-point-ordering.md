---
title: isgreater, isgreaterequal, isless, islessequal, islessgreater, isunordered
ms.date: 01/31/2019
f1_keywords:
- isgreater
- math/isgreater
- isgreaterequal
- math/isgreaterequal
- isless
- math/isless
- islessequal
- math/islessequal
- islessgreater
- math/islessgreater
- isunordered
- math/isunordered
helpviewer_keywords:
- isgreater function
- isgreaterequal function
- isless function
- islessequal function
- islessgreater function
- isunordered function
ms.openlocfilehash: 748360cae1dd0ee43645dee369c60c835246ed03
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333709"
---
# <a name="isgreater-isgreaterequal-isless-islessequal-islessgreater-isunordered"></a>isgreater, isgreaterequal, isless, islessequal, islessgreater, isunordered

İki kayan nokta değerleri arasında sıralama ilişkisi belirler.

## <a name="syntax"></a>Sözdizimi

```C
int isgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isgreaterequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isless(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessequal(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int islessgreater(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */

int isunordered(
   /* floating-point */ x,
   /* floating-point */ y
); /* C-only macro */
```

```C++
template <class FloatingType1, class FloatingType2>
inline bool isgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isgreaterequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isless(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessequal(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool islessgreater(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */

template <class FloatingType1, class FloatingType2>
inline bool isunordered(
   FloatingType1 x,
   FloatingType2 y
) throw(); /* C++-only template function */
```

### <a name="parameters"></a>Parametreler

*x*, *y*<br/>
Karşılaştırılacak kayan nokta değerleri.

## <a name="return-value"></a>Dönüş Değeri

Tüm karşılaştırmalar aynı oturum sonsuz eşit olarak karşılaştırılır. Az sınırlı veya pozitif sonsuz, negatif sonsuz değerdir. Pozitif sonsuz, herhangi bir değer sınırlı veya negatif sonsuz büyüktür. Sıfır bağımsız olarak oturum eşit olur. NaN'ler diğerinden daha küçük, ona eşit veya ondan büyük başka bir NaN dahil olmak üzere herhangi bir değer değildir.

Her iki bağımsız değişken, bir NaN sıralama makroları olduğunda **isgreater**, **isgreaterequal**, **isless**, ve **islessequal** sıfır olmayan değerini döndürür değeri belirtilen sıralama ilişki arasında *x* ve *y* geçerlidir. Bu makrolar, NaN'ler biri veya her ikisi bağımsız değişkenler veya sıralama ilişki false ise, 0 değerini döndürür. İşlev forms aynı şekilde davranır, ancak iade **true** veya **false**.

**İslessgreater** makrosu, her iki sıfır olmayan bir değer döndürür *x* ve *y* , NaN'ler değil ve *x* ya da küçük veya bu büyüktür*y*. NaN'ler biri veya her ikisi bağımsız değişkenler veya değerler eşitse 0 döndürür. İşlev formun aynı şekilde davranır, ancak döndürür **true** veya **false**.

**İsunordered** makrosu ya da sıfır olmayan bir değer döndürür *x*, *y*, veya her ikisi de NaN'ler olan. Aksi durumda 0 döndürür. İşlev formun aynı şekilde davranır, ancak döndürür **true** veya **false**.

## <a name="remarks"></a>Açıklamalar

Bu karşılaştırma işlemleri, C ve C++ derlendiğinde şablon işlevleri satır içi olarak derlendiğinde makrolar olarak uygulanır.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık (C)|Gerekli başlık (C++)|
|--------------|---------------------------|-------------------------------|
| **isgreater**, **isgreaterequal**, **isless**,<br/>**islessequal**, **islessgreater**, **isunordered** | \<Math.h > | \<Math.h > veya \<cmath > |

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan Nokta Desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
