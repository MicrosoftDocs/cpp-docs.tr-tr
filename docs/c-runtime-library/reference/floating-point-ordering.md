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
ms.openlocfilehash: 907b26f4e1824d7ef5c7c1a36b4e4d8ccb74c978
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220723"
---
# <a name="isgreater-isgreaterequal-isless-islessequal-islessgreater-isunordered"></a>isgreater, isgreaterequal, isless, islessequal, islessgreater, isunordered

İki kayan nokta değeri arasındaki sıralama ilişkisini belirler.

## <a name="syntax"></a>Söz dizimi

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

Tüm karşılaştırmalarda, aynı imza karşılaştırmalarının eşit olduğu sonsuz. Negatif sonsuzluk, sınırlı değerden veya pozitif sonsuzdan daha az. Pozitif sonsuzluk, sınırlı değerden veya negatif sonsuzdan daha büyük. Sıfır işareti ne olursa olsun eşittir. NaNs, başka bir NaN da dahil olmak üzere herhangi bir değerden küçük, eşit veya daha büyük değil.

Bağımsız değişken bir NaN olduğunda, *x* ve *y* arasında belirtilen sıralama ilişkisi doğru tutuyorsa **sıralama makroları,** **isgreaterequal**, **ısless**ve **islessequal** sıfır olmayan bir değer döndürür. Bu makrolar, ya da her iki bağımsız değişkeni NaNs ise veya sıralama ilişkisi yanlışsa 0 döndürür. İşlev formları aynı şekilde davranır, ancak **`true`** veya döndürür **`false`** .

Her ikisi de *x* ve *y* , nans değilse ve *x* , *y*'den küçük ya da daha büyükse, **ılessdaha fazla** makro sıfır olmayan bir değer döndürür. Ya da her iki bağımsız değişken NaNs ise veya Değerler eşitse 0 döndürür. İşlev formu aynı şekilde davranır, ancak **`true`** veya döndürür **`false`** .

**Isýralanmamýþ** Macro, *x*, *y*ya da her ikisi de nans olduğunda sıfır olmayan bir değer döndürür. Aksi takdirde, 0 döndürür. İşlev formu aynı şekilde davranır, ancak **`true`** veya döndürür **`false`** .

## <a name="remarks"></a>Açıklamalar

Bu karşılaştırma işlemleri, C olarak derlendiğinde makrolar olarak ve C++ olarak derlendiğinde satır içi şablon işlevleri olarak uygulanır.

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|--------------|---------------------------|-------------------------------|
| **isbüyüktü**, **isgreaterequal**, **isküçüktür**,<br/>**islessequal**, **islessdaha büyük**, **ısýralanmamýþ** | \<math.h> | \<math.h> veya \<cmath> |

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../../c-runtime-library/floating-point-support.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
