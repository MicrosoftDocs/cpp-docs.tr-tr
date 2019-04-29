---
title: Kayan nokta temelleri
ms.date: 01/31/2019
apiname:
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
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 230d0def145bcb443437b59303b2b36e348da2bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333618"
---
# <a name="floating-point-primitives"></a>Kayan nokta temelleri

Bazı standart C çalışma zamanı kitaplığı (CRT) kayan nokta işlevleri uygulamak için kullanılan Microsoft'a özgü temel işlevleri. Bütünlük açısından buraya belgelenen, ancak kullanım için önerilmez. Bu işlevlerin bazıları duyarlığı, özel durum işleme ve IEEE 754 davranışına uyum sorunları için bilinir olduğundan kullanılmayan olarak not. Bunlar, kitaplık yalnızca geriye dönük uyumluluk için bulunmaktadır. Standart kayan nokta işlevleri doğru davranışı, taşınabilirlik ve standartları kıldığı için bu işlevler üzerinde tercih eder.

## <a name="dclass-ldclass-fdclass"></a>_dclass, _ldclass, _fdclass

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

CRT makrosu C sürümleri bu kayan nokta temelleri uygulamak [fpclassify](fpclassify.md) kayan nokta türleri için. Bağımsız değişkenin sınıflandırma *x* math.h içinde tanımlanan, bu sabitlerden biri döndürülür:

|Değer|Açıklama|
|-----------|-----------------|
| **FP_NAN** | Bir sessiz, sinyal veya belirsiz NaN |
| **FP_INFINITE** | Bir pozitif veya negatif sonsuz |
| **FP_NORMAL** | Bir pozitif veya negatif normalleştirilmiş sıfır olmayan değer |
| **FP_SUBNORMAL** | Bir pozitif veya negatif subnormal (normalleştirilmişlikten çıkarılmış) değeri |
| **FP_ZERO** | Bir pozitif veya sıfır değeri negatif |

Ek ayrıntılar için Microsoft'a özgü kullanabileceğiniz [_fpclass, _fpclassf](fpclass-fpclassf.md) işlevleri. Kullanım [fpclassify](fpclassify.md) makro veya taşınabilirlik için işlev.

## <a name="dsign-ldsign-fdsign"></a>_dsign, _ldsign, _fdsign

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

Kayan nokta bu temel elemanlarına uygulayın [signbit](signbit.md) makrosu ya da CRT işlev. İmza biti mantisinin bağımsız değişkeni (Mantis) olarak ayarlanmışsa sıfır olmayan bir değer döndürürler *x*, imza biti ayarlanmamışsa 0.

## <a name="dpcomp-ldpcomp-fdpcomp"></a>_dpcomp, _ldpcomp, _fdpcomp

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

İki bağımsız değişkeni, bu kayan nokta temelleri ele *x* ve *y*ve bit düzeyinde veya bu sabitlerin math.h içinde tanımlanan ifade sıralama ilişkilerini gösteren bir değer döndürür:

| Değer | Açıklama |
|------------|-----------------|
| **_FP_LT** | *x* kabul edilebilir küçüktür *y* |
| **_FP_EQ** | *x* eşit kabul edilebilir *y* |
| **_FP_GT** | *x* büyüktür kabul edilebilir *y* |

Bu temel elemanlarına uygulayın [isgreater, isgreaterequal, isless, islessequal, islessgreater ve isunordered](floating-point-ordering.md) makroları ve CRT işlevleri.

## <a name="dtest-ldtest-fdtest"></a>_dtest, _ldtest, _fdtest

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dtest(double* px);
short __cdecl _ldtest(long double* px);
short __cdecl _fdtest(float* px);
```

### <a name="parameters"></a>Parametreler

*piksel*<br/>
Bir kayan noktalı bağımsız değişken işaretçi.

### <a name="remarks"></a>Açıklamalar

CRT işlevinin C++ sürümlerinde bu kayan nokta temelleri uygulamak [fpclassify](fpclassify.md) kayan nokta türleri için. Bağımsız değişken *x* değerlendirilir ve sınıflandırma math.h içinde tanımlanan, bu sabitlerden biri döndürülür:

|Değer|Açıklama|
|-----------|-----------------|
| **FP_NAN** | Bir sessiz, sinyal veya belirsiz NaN |
| **FP_INFINITE** | Bir pozitif veya negatif sonsuz |
| **FP_NORMAL** | Bir pozitif veya negatif normalleştirilmiş sıfır olmayan değer |
| **FP_SUBNORMAL** | Bir pozitif veya negatif subnormal (normalleştirilmişlikten çıkarılmış) değeri |
| **FP_ZERO** | Bir pozitif veya sıfır değeri negatif |

Ek ayrıntılar için Microsoft'a özgü kullanabileceğiniz [_fpclass, _fpclassf](fpclass-fpclassf.md) işlevleri. Kullanım [fpclassify](fpclassify.md) taşınabilirlik için işlevi.

## <a name="dint-ldint-fdint"></a>_d_int, _ld_int, _fd_int

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _d_int(double* px, short exp);
short __cdecl _ld_int(long double* px, short exp);
short __cdecl _fd_int(float* px, short exp);
```

### <a name="parameters"></a>Parametreler

*piksel*<br/>
Bir kayan noktalı bağımsız değişken işaretçi.

*exp*<br/>
Üs olarak bir tamsayı türü.

### <a name="remarks"></a>Açıklamalar

Kayan nokta bu ilkel bir kayan noktalı değere bir işaretçi olması *px* ve üs değeri *exp*ve eğer mümkünse verilen üs aşağıdaki kayan nokta değeri kesirli kısmını kaldırın . Döndürülen değer sonucudur **fpclassify** giriş değeri *px* NaN veya sonsuz ise ve çıkış değeri *px* Aksi takdirde.

## <a name="dscale-ldscale-fdscale"></a>_dscale, _ldscale, _fdscale

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dscale(double* px, long exp);
short __cdecl _ldscale(long double* px, long exp);
short __cdecl _fdscale(float* px, long exp);
```

### <a name="parameters"></a>Parametreler

*piksel*<br/>
Bir kayan noktalı bağımsız değişken işaretçi.

*exp*<br/>
Üs olarak bir tamsayı türü.

### <a name="remarks"></a>Açıklamalar

Kayan nokta bu ilkel bir kayan noktalı değere bir işaretçi olması *px* ve üs değeri *exp*, ve değer ölçeklendirme *px* 2<sup> *exp*</sup>, mümkünse. Döndürülen değer sonucudur **fpclassify** giriş değeri *px* NaN veya sonsuz ise ve çıkış değeri *px* Aksi takdirde. Taşınabilirlik için tercih ettiğiniz [ldexp, ldexpf ve ldexpl](ldexp.md) işlevleri.

## <a name="dunscale-ldunscale-fdunscale"></a>_dunscale, _ldunscale, _fdunscale

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dunscale(short* pexp, double* px);
short __cdecl _ldunscale(short* pexp, long double* px);
short __cdecl _fdunscale(short* pexp, float* px);
```

### <a name="parameters"></a>Parametreler

*pexp*<br/>
Bir üssü bir integral türü işaretçi.

*piksel*<br/>
Bir kayan noktalı bağımsız değişken işaretçi.

### <a name="remarks"></a>Açıklamalar

Kayan nokta değeri tarafından işaret bu kayan nokta temelleri ayırmanız *px* bir anlam (Mantis) ve bir üs, mümkün olduğunda. Büyüktür veya eşittir 0,5 ve az 1.0 olmasını gibi mutlak değeri, anlam ölçeklendirilir. Değer üstür *n*, orijinal kayan nokta değerine Ölçeklendirildi anlam 2 süreleri için eşit olduğu<sup>*n*</sup>. Bu tamsayı üs *n* tarafından işaret edilen konumda depolanır *pexp*. Döndürülen değer sonucudur **fpclassify** giriş değeri *px* NaN veya sonsuzluk olup olmadığını ve değilse çıkış değeri. Taşınabilirlik için tercih ettiğiniz [frexp, frexpf, frexpl](frexp.md) işlevleri.

## <a name="dexp-ldexp-fdexp"></a>_dexp, _ldexp, _fdexp

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dexp(double* px, double y, long exp);
short __cdecl _ldexp(long double* px, long double y, long exp);
short __cdecl _fdexp(float* px, float y, long exp);
```

### <a name="parameters"></a>Parametreler

*Y*<br/>
Kayan nokta işlev bağımsız değişkeni.

*piksel*<br/>
Bir kayan noktalı bağımsız değişken işaretçi.

*exp*<br/>
Üs olarak bir tamsayı türü.

### <a name="remarks"></a>Açıklamalar

Bir kayan nokta değeri tarafından işaret konumda bu kayan nokta temelleri oluşturmak *px* eşit *y* * 2<sup>*exp*</sup>. Döndürülen değer sonucudur **fpclassify** giriş değeri *y* NaN veya sonsuz ise ve çıkış değeri *px* Aksi takdirde. Taşınabilirlik için tercih ettiğiniz [ldexp, ldexpf ve ldexpl](ldexp.md) işlevleri.

## <a name="dnorm-fdnorm"></a>_dnorm, _fdnorm

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dnorm(unsigned short* ps);
short __cdecl _fdnorm(unsigned short* ps);
```

### <a name="parameters"></a>Parametreler

*PS*<br/>
Bit düzeyinde bir kayan nokta değeri bir dizi ifade gösterimini işaretçisine **işaretsiz** **kısa**.

### <a name="remarks"></a>Açıklamalar

Kayan nokta bu temelleri kesirli kısmını underflowed bir kayan nokta değeri Normalleştir ve ayarlama *karakteristik*, veya eşleştirilecek popülasyon üs. Bit düzeyinde temsili bir dizisi olarak dönüştürülen kayan nokta türü olarak geçirilen değer **işaretsiz** **kısa** aracılığıyla `_double_val`, `_ldouble_val`, veya `_float_val` türü punning birleşim math.h içinde bildirilmiş. Dönüş değeri sonucudur **fpclassify** NaN veya sonsuz ise giriş kayan nokta değeri ve başka bir çıkış değeri.

## <a name="dpoly-ldpoly-fdpoly"></a>_dpoly, _ldpoly, _fdpoly

### <a name="syntax"></a>Sözdizimi

```C
double __cdecl _dpoly(double x, double const* table, int n);
long double __cdecl _ldpoly(long double x, long double const* table, int n);
float __cdecl _fdpoly(float x, _float const* table, int n);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta işlev bağımsız değişkeni.

*Tablo*<br/>
Bir polinom için sabit katsayıları tablosu işaretçisi.

*n*<br/>
Değerlendirilecek Polinomun sırası.

### <a name="remarks"></a>Açıklamalar

Kayan nokta bu temel değerlendirmesi dönüş *x* siparişinin Polinomun içinde *n* , katsayıları ilgili sabit değerleri temsil edilir *tablo*. Örneğin, varsa *tablo*\[0] = 3.0, *tablo*\[= 1] 4.0, *tablo*\[= 2] 5.0 ve *n* = 2, temsil ettiği polinom 5.0 x<sup>2</sup> 4.0 + x + 3.0. Bu Polinomun için değerlendirildiği taktirde *x* 2.0, 31.0 sonucudur. Bu işlevler, dahili olarak kullanılmaz.

## <a name="dlog-dlog-dlog"></a>_dlog, _dlog, _dlog

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
Kullanmak için 0 tabanı için temel denetleyen bayrak *e* ve sıfır olmayan taban 10.

### <a name="remarks"></a>Açıklamalar

Kayan nokta bu temelleri doğal dönüş *x*, ln (*x*) veya günlük<sub>*e*</sub>(*x*), zaman *base_flag* 0'dır. Taban 10 günlük döndürmeleri *x*, ya da günlük<sub>10</sub>(*x*), *base_flag* sıfır değil. Bu işlevler, dahili olarak kullanılmaz. Taşınabilirlik için tercih ettiğiniz işlevler [günlük, logf, logl, log10, log10f ve log10l](log-logf-log10-log10f.md).

## <a name="dsin-ldsin-fdsin"></a>_dsin, _ldsin, _fdsin

### <a name="syntax"></a>Sözdizimi

```C
double __cdecl _dsin(double x, unsigned int quadrant);
long double __cdecl _ldsin(long double x, unsigned int quadrant);
float __cdecl _fdsin(float x, unsigned int quadrant);
```

### <a name="parameters"></a>Parametreler

*x*<br/>
Kayan nokta işlev bağımsız değişkeni.

*Quadrant*<br/>
0, 1, 2 veya 3 üretmek için kullanılacak Quadrant uzaklığı `sin`, `cos`, `-sin`, ve `-cos` sonuçları.

### <a name="remarks"></a>Açıklamalar

Kayan nokta bu temelleri sinüsünü Döndür *x* tarafından uzaklık *quadrant* 4 modül. Sinüs etkili bir şekilde döndürmeleri Kosinüs, - Sinüs ve - kosinüsünü *x* olduğunda *quadrant* 0, 1, 2 veya 3, 4 sırasıyla olduğu. Bu işlevler, dahili olarak kullanılmaz. Taşınabilirlik için tercih ettiğiniz [sinüs, sinf sinl](sin-sinf-sinl.md), [cos, cosf ve cosl](cos-cosf-cosl.md) işlevleri.

## <a name="requirements"></a>Gereksinimler

Başlık: \<math.h >

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
[ldexp ldexpf ve ldexpl](ldexp.md)<br/>
[Günlük, logf, logl, log10, log10f, log10l](log-logf-log10-log10f.md)<br/>
[sin, sinf, sinl](sin-sinf-sinl.md)<br/>
