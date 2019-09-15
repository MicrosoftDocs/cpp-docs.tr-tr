---
title: Kayan nokta temel elemanları
ms.date: 01/31/2019
api_name:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
helpviewer_keywords:
- _dclass
- _ldclass
- _fdclass
- _dsign
- _ldsign
- _fdsign
- _dpcomp
- _ldpcomp
- _fdpcomp
- _dtest
- _ldtest
- _fdtest
- _d_int
- _ld_int
- _fd_int
- _dscale
- _ldscale
- _fdscale
- _dunscale
- _ldunscale
- _fdunscale
- _dexp
- _ldexp
- _fdexp
- _dnorm
- _fdnorm
- _dpoly
- _ldpoly
- _fdpoly
- _dlog
- _ldlog
- _fdlog
- _dsin
- _ldsin
- _fdsin
ms.openlocfilehash: 25d70062a76f9c32692f5df3f7abb96b49892725
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957167"
---
# <a name="floating-point-primitives"></a>Kayan nokta temel elemanları

Bazı standart C çalışma zamanı kitaplığı (CRT) kayan nokta işlevlerini uygulamak için kullanılan, Microsoft 'a özgü temel işlevler. Bunlar, tamamlanma açısından burada açıklanırlar, ancak kullanım için önerilmez. Bu işlevlerden bazıları kullanılmıyor olarak belirtilmiştir, çünkü duyarlık, özel durum işleme ve IEEE-754 davranışına uygunluk sorunları yaşar. Yalnızca geri uyumluluk için kitaplıkta bulunur. Doğru davranış, taşınabilirlik ve standartlara uyma için, bu işlevler üzerinde standart kayan nokta işlevleri tercih edin.

## <a name="_dclass-_ldclass-_fdclass"></a>_dclass, _ldclass, _fdclass

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dclass(double x);
short __cdecl _ldclass(long double x);
short __cdecl _fdclass(float x);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta işlev bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temel elemanlar, kayan nokta türleri için CRT makro [fpsınıflandırmasına](fpclassify.md) ait C sürümlerini uygular. *X* bağımsız değişkeninin sınıflandırması, Math. h içinde tanımlanan bu sabitlerden biri olarak döndürülür:

|Değer|Açıklama|
|-----------|-----------------|
| **FP_NAN** | Sessiz, sinyal veya belirsiz NaN |
| **FP_INFINITE** | Pozitif veya negatif sonsuzluk |
| **FP_NORMAL** | Pozitif veya negatif normalleştirilmiş sıfır olmayan bir değer |
| **FP_SUBNORMAL** | Pozitif veya negatif alt normal (denormallanmış) değer |
| **FP_ZERO** | Pozitif veya negatif sıfır değeri |

Ek ayrıntı için, Microsoft 'a özgü [_fpclass, _fpclassf](fpclass-fpclassf.md) işlevlerini kullanabilirsiniz. Taşınabilirlik için [fpsınıflandır](fpclassify.md) makrosunu veya işlevini kullanın.

## <a name="_dsign-_ldsign-_fdsign"></a>_dsign, _ldsign, _fdsign

### <a name="syntax"></a>Sözdizimi

```C
int __cdecl _dsign(double x);
int __cdecl _ldsign(long double x);
int __cdecl _fdsign(float x);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta işlev bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temel elemanlar, CRT içindeki [signbit](signbit.md) makrosunu veya işlevini uygular. *X*bağımsız değişkeninin mantisinin (Mantis) öğesinde işaret biti ayarlandıysa sıfır olmayan bir değer döndürür ve işaret biti ayarlanmamışsa 0 olur.

## <a name="_dpcomp-_ldpcomp-_fdpcomp"></a>_dpcomp, _ldpcomp, _fdpcomp

### <a name="syntax"></a>Sözdizimi

```C
int __cdecl _dpcomp(double x, double y);
int __cdecl _ldpcomp(long double x, long double y);
int __cdecl _fdpcomp(float x, float y);
```

### <a name="parameters"></a>Parametreler

*x*, *y*<br/>
Kayan nokta işlev bağımsız değişkenleri.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temel elemanlar iki bağımsız değişken ( *x* ve *y*) alır ve, Math. h içinde tanımlanan bit düzeyinde veya Bu sabitler olarak ifade edilen sıralama ilişkilerini gösteren bir değer döndürür:

| Değer | Açıklama |
|------------|-----------------|
| **_FP_LT** | *x* , *y* 'den küçük kabul edilebilir |
| **_FP_EQ** | *x* , *y* 'ye eşit kabul edilebilir |
| **_FP_GT** | *x* , *y* 'den büyük olarak düşünülebilir |

Bu temel elemanlar, [ısbüyüktür, isgreaterequal, ıless, islessequal, ılessdaha büyük ve ısıralanmamış](floating-point-ordering.md) makrolar ve IŞLEVLERI de CRT içinde uygular.

## <a name="_dtest-_ldtest-_fdtest"></a>_dtest, _ldtest, _fdtest

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dtest(double* px);
short __cdecl _ldtest(long double* px);
short __cdecl _fdtest(float* px);
```

### <a name="parameters"></a>Parametreler

*20*<br/>
Kayan nokta bağımsız değişkenine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temel elemanlar, kayan C++ nokta türleri için [FPSıNıFLANDıR](fpclassify.md) CRT işlevi sürümlerini uygular. *X* bağımsız değişkeni değerlendirilir ve sınıflandırma, Math. h içinde tanımlanan bu sabitlerden biri olarak döndürülür:

|Değer|Açıklama|
|-----------|-----------------|
| **FP_NAN** | Sessiz, sinyal veya belirsiz NaN |
| **FP_INFINITE** | Pozitif veya negatif sonsuzluk |
| **FP_NORMAL** | Pozitif veya negatif normalleştirilmiş sıfır olmayan bir değer |
| **FP_SUBNORMAL** | Pozitif veya negatif alt normal (denormallanmış) değer |
| **FP_ZERO** | Pozitif veya negatif sıfır değeri |

Ek ayrıntı için, Microsoft 'a özgü [_fpclass, _fpclassf](fpclass-fpclassf.md) işlevlerini kullanabilirsiniz. Taşınabilirlik için [fpsınıflandır](fpclassify.md) işlevini kullanın.

## <a name="_d_int-_ld_int-_fd_int"></a>_d_int, _ld_ınt, _fd_ınt

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _d_int(double* px, short exp);
short __cdecl _ld_int(long double* px, short exp);
short __cdecl _fd_int(float* px, short exp);
```

### <a name="parameters"></a>Parametreler

*20*<br/>
Kayan nokta bağımsız değişkenine yönelik işaretçi.

*exp*<br/>
İntegral türü olarak üs.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temelleri, bir kayan nokta değeri *px* ve üs değer *Exp*işaretçisi alır ve mümkünse kayan nokta değerinin kesirli kısmını belirtilen üs altında kaldırır. Döndürülen değer, bir NaN veya Infinity ise ve *piksel* olarak çıkış değeri değilse, *IPX* 'teki giriş değerindeki **fpsınıflandırın** sonucudur.

## <a name="_dscale-_ldscale-_fdscale"></a>_dscale, _ldscale, _fdscale

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dscale(double* px, long exp);
short __cdecl _ldscale(long double* px, long exp);
short __cdecl _fdscale(float* px, long exp);
```

### <a name="parameters"></a>Parametreler

*20*<br/>
Kayan nokta bağımsız değişkenine yönelik işaretçi.

*exp*<br/>
İntegral türü olarak üs.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temelleri bir kayan nokta değeri *px* ve üs değer *Exp*için bir işaretçi alır ve mümkünse değeri 2<sup>*Exp*</sup> *olarak ölçeklendirir* . Döndürülen değer, bir NaN veya Infinity ise ve *piksel* olarak çıkış değeri değilse, *IPX* 'teki giriş değerindeki **fpsınıflandırın** sonucudur. Taşınabilirlik için [ldexp, ldexpf ve ldexpl](ldexp.md) işlevlerini tercih edin.

## <a name="_dunscale-_ldunscale-_fdunscale"></a>_dunscale, _ldunscale, _fdunscale

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dunscale(short* pexp, double* px);
short __cdecl _ldunscale(short* pexp, long double* px);
short __cdecl _fdunscale(short* pexp, float* px);
```

### <a name="parameters"></a>Parametreler

*pexp*<br/>
İntegral türü olarak üs için bir işaretçi.

*20*<br/>
Kayan nokta bağımsız değişkenine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temel elemanlar, mantisinin (Mantis) ve mümkünse üs bir değere *göre işaret* edilen kayan nokta değerini ayırır. Mantisinin, mutlak değer 0,5 ' e eşit veya daha büyük ve 1,0 ' den küçük olacak şekilde ölçeklendirilir. Üs değeri, özgün kayan nokta değerinin<sup>*ölçeği 2 '* </sup>nin ölçeklendirmantisinin süreleriyle eşit olduğu *n*değeridir. Bu tamsayı üssü *n* , *pexp*tarafından işaret edilen konumda depolanır. Döndürülen değer, bir NaN veya Infinity ise ve çıkış değerinde değilse, *IPX* 'teki giriş değerindeki **fpsınıflandırın** sonucudur. Taşınabilirlik için [frexp, frexpf, frexpl](frexp.md) işlevlerini tercih edin.

## <a name="_dexp-_ldexp-_fdexp"></a>_dexp, _ldexp, _fdexp

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dexp(double* px, double y, long exp);
short __cdecl _ldexp(long double* px, long double y, long exp);
short __cdecl _fdexp(float* px, float y, long exp);
```

### <a name="parameters"></a>Parametreler

*Iz*<br/>
Kayan nokta işlev bağımsız değişkeni.

*20*<br/>
Kayan nokta bağımsız değişkenine yönelik işaretçi.

*exp*<br/>
İntegral türü olarak üs.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temel elemanlar, *px* , *y* <sup> ** 2 '* </sup>ye eşit olan konumda işaret eden bir kayan nokta değeri oluşturur. Döndürülen değer, bir NaN veya Infinity ise ve *piksel* olarak çıkış değerinde, *Aksi takdirde giriş* değerindeki **fpsınıflandırın** sonucudur. Taşınabilirlik için [ldexp, ldexpf ve ldexpl](ldexp.md) işlevlerini tercih edin.

## <a name="_dnorm-_fdnorm"></a>_dnorm, _fdnorm

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dnorm(unsigned short* ps);
short __cdecl _fdnorm(unsigned short* ps);
```

### <a name="parameters"></a>Parametreler

*PS*<br/>
**İşaretsiz** **kısa**bir dizi olarak ifade edilen kayan noktalı değerin bit düzeyinde gösterimine yönelik işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temel elemanlar, yetersiz bir kayan nokta değerinin kesirli kısmını normalleştirin ve *özellikleri*veya taraflı düzeyi eşleşecek şekilde ayarlar. Değer,, veya `_double_val` `_ldouble_val` Math.hiçindebelirtilentüratlamaUNIONöğesindenbirişaretsizShortdizisinedönüştürülenkayannoktatürününbitdüzeyinde`_float_val` temsili olarak geçirilir. Dönüş değeri, bir NaN veya Infinity, aksi takdirde çıkış değerinde giriş kayan nokta değerindeki **fpsınıflandırın** sonucudur.

## <a name="_dpoly-_ldpoly-_fdpoly"></a>_dpoly, _ldpoly, _fdpoly

### <a name="syntax"></a>Sözdizimi

```C
double __cdecl _dpoly(double x, double const* table, int n);
long double __cdecl _ldpoly(long double x, long double const* table, int n);
float __cdecl _fdpoly(float x, _float const* table, int n);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta işlev bağımsız değişkeni.

*tablosundan*<br/>
Polinom için sabit katsayıların bir tablosuna yönelik işaretçi.

*n*<br/>
Değerlendirilecek polinom 'un sırası.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temel elemanlar, *x* 'in, katlarının *tablo*içindeki karşılık gelen sabit değerlerle temsil edildiği sıra *n* olarak değerlendirilmesi. Örneğin, *tablo*\[0] = 3,0, *tablo*\[1] = 4,0, *tablo*\[2] = 5,0 ve *n* = 2 ise, polinom 5.0 x<sup>2</sup> + 4.0 x + 3,0 ' i temsil eder. Bu polinom, *x* /2,0 için değerlendirilirse, sonuç 31,0 ' dir. Bu işlevler dahili olarak kullanılmaz.

## <a name="_dlog-_dlog-_dlog"></a>_dlog, _dlog, _dlog

### <a name="syntax"></a>Sözdizimi

```C
double __cdecl _dlog(double x, int base_flag);
long double __cdecl _ldlog(long double x, int base_flag);
float __cdecl _fdlog(float x, int base_flag);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta işlev bağımsız değişkeni.

*base_flag*<br/>
Tabanı desteklemeyen bayrak, taban *e* için 0 ve taban 10 için sıfır olmayan.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temel elemanlar, *base_flag* 0 olduğunda *x*, LN (*x*) veya log<sub>*e*</sub>(*x*) doğal günlüğünü döndürür. Bu, *base_flag* sıfır olmayan bir *x*(x) günlük tabanını veya günlük<sub>10</sub>' u (*x*) döndürür. Bu işlevler dahili olarak kullanılmaz. Taşınabilirlik için, [log, logf, logl, log10, log10f ve log10l](log-logf-log10-log10f.md)işlevlerini tercih edin.

## <a name="_dsin-_ldsin-_fdsin"></a>_dsin, _ldsin, _fdsin

### <a name="syntax"></a>Sözdizimi

```C
double __cdecl _dsin(double x, unsigned int quadrant);
long double __cdecl _ldsin(long double x, unsigned int quadrant);
float __cdecl _fdsin(float x, unsigned int quadrant);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta işlev bağımsız değişkeni.

*ğine*<br/>
`sin` ,`cos`,, Ve`-cos` sonuçlarını oluşturmak için kullanılan, çeyrek daire 0, 1, 2 veya 3. `-sin`

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta temel elemanlar, *çeyrek* modül 4 ' ün *x* sapmasını sinüsünü döndürür. Etkin olarak, *çeyrek* modül 4, sırasıyla 0, 1, 2 veya 3 olduğunda *x* 'in sinüs, kosinüs,-sinüs ve-kosinüs değerini getirirler. Bu işlevler dahili olarak kullanılmaz. Taşınabilirlik için [Sin, sinf, sinl](sin-sinf-sinl.md), [cos, cosf ve COSL](cos-cosf-cosl.md) işlevlerini tercih edin.

## <a name="requirements"></a>Gereksinimler

Üstbilgi: \<Math. h >

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Kayan nokta desteği](../floating-point-support.md)<br/>
[fpclassify](fpclassify.md)<br/>
[_fpclass, _fpclassf](fpclass-fpclassf.md)<br/>
[isfinite, _finite, _finitef](finite-finitef.md)<br/>
[isinf](isinf.md)<br/>
[isnan, _isnan, _isnanf](isnan-isnan-isnanf.md)<br/>
[isnormal](isnormal.md)<br/>
[cos, cosf, cosl](cos-cosf-cosl.md)<br/>
[frexp, frexpf, frexpl](frexp.md)<br/>
[ldexp, ldexpf ve ldexpl](ldexp.md)<br/>
[log, logf, logl, log10, log10f, log10l](log-logf-log10-log10f.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
