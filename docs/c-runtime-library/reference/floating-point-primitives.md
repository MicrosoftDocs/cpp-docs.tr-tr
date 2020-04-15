---
title: Kayan nokta temel elemanları
ms.date: 4/2/2020
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
- _o__d_int
- _o__dclass
- _o__dlog
- _o__dnorm
- _o__dpcomp
- _o__dpoly
- _o__dscale
- _o__dsign
- _o__dsin
- _o__dtest
- _o__dunscale
- _o__fd_int
- _o__fdclass
- _o__fdexp
- _o__fdlog
- _o__fdpcomp
- _o__fdpoly
- _o__fdscale
- _o__fdsign
- _o__fdsin
- _o__ld_int
- _o__ldclass
- _o__ldexp
- _o__ldlog
- _o__ldpcomp
- _o__ldpoly
- _o__ldscale
- _o__ldsign
- _o__ldsin
- _o__ldtest
- _o__ldunscale
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: d861fbf2b71d557354a60f65b8a76dc24ca1dd13
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346704"
---
# <a name="floating-point-primitives"></a>Kayan nokta temel elemanları

Bazı standart C çalışma zamanı kitaplığı (CRT) kayan nokta işlevlerini uygulamak için kullanılan Microsoft'a özgü ilkel işlevler. Burada eksiksiz olarak belgelenirler, ancak kullanım için önerilmezler. Bu işlevlerden bazıları kullanılmayan olarak belirtilir, çünkü hassaslık, özel durum işleme ve IEEE-754 davranışına uygunluk sorunları olduğu bilinmektedir. Bunlar yalnızca geriye dönük uyumluluk için kütüphanede bulunurlar. Doğru davranış, taşınabilirlik ve standartlara bağlılık için, bu işlevler yerine standart kayan nokta işlevlerini tercih edin.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="_dclass-_ldclass-_fdclass"></a>_dclass, _ldclass, _fdclass

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dclass(double x);
short __cdecl _ldclass(long double x);
short __cdecl _fdclass(float x);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Kayan nokta işlev bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta ilkel crt makro [fpclassify](fpclassify.md) kayan nokta türleri için C sürümlerini uygular. *X* bağımsız değişkeninin sınıflandırılması math.h'de tanımlanan bu sabitlerden biri olarak döndürülür:

|Değer|Açıklama|
|-----------|-----------------|
| **FP_NAN** | Sessiz, sinyalveya belirsiz NaN |
| **FP_INFINITE** | Pozitif veya negatif sonsuzluk |
| **FP_NORMAL** | Pozitif veya negatif normalleştirilmiş sıfır olmayan değer |
| **FP_SUBNORMAL** | Pozitif veya negatif normale göre (normalden arındırılmış) değer |
| **FP_ZERO** | Pozitif veya negatif sıfır değeri |

Ek ayrıntı için Microsoft'a özgü [_fpclass, _fpclassf](fpclass-fpclassf.md) işlevlerik kullanabilirsiniz. Taşınabilirlik için [fpclassify](fpclassify.md) makro veya işlevi kullanın.

## <a name="_dsign-_ldsign-_fdsign"></a>_dsign, _ldsign, _fdsign

### <a name="syntax"></a>Sözdizimi

```C
int __cdecl _dsign(double x);
int __cdecl _ldsign(long double x);
int __cdecl _fdsign(float x);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Kayan nokta işlev bağımsız değişkeni.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta ilkel crt [signbit](signbit.md) makro veya işlevi uygular. İşaret biti *x*bağımsız değişkeninin öneminde (mantissa) ayarlanırsa sıfır olmayan bir değer ve işaret biti ayarlanmazsa 0 döndürerler.

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

Bu kayan nokta ilkel iki bağımsız değişken alır, *x* ve *y*, ve onların sıralama ilişkisini gösteren bir değer döndürün, bitwise veya bu sabitlerin olarak ifade, math.h tanımlanan:

| Değer | Açıklama |
|------------|-----------------|
| **_FP_LT** | *x* *y'den* az olarak kabul edilebilir |
| **_FP_EQ** | *x* *y'ye* eşit olarak kabul edilebilir |
| **_FP_GT** | *x* *y'den* büyük olarak kabul edilebilir |

Bu ilkeller CRT'de [isgreater, isgreaterequal, islessequal, islessequal, islessgreater ve isisordered](floating-point-ordering.md) makrolar ve işlevleri uygular.

## <a name="_dtest-_ldtest-_fdtest"></a>_dtest, _ldtest, _fdtest

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dtest(double* px);
short __cdecl _ldtest(long double* px);
short __cdecl _fdtest(float* px);
```

### <a name="parameters"></a>Parametreler

*px*<br/>
Kayan nokta bağımsız değişkenini işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta ilkel crt işlevinin C++ sürümlerini kayan nokta türleri için [fpclassify](fpclassify.md) uygular. *X* bağımsız değişkeni değerlendirilir ve sınıflandırma math.h'de tanımlanan bu sabitlerden biri olarak döndürülür:

|Değer|Açıklama|
|-----------|-----------------|
| **FP_NAN** | Sessiz, sinyalveya belirsiz NaN |
| **FP_INFINITE** | Pozitif veya negatif sonsuzluk |
| **FP_NORMAL** | Pozitif veya negatif normalleştirilmiş sıfır olmayan değer |
| **FP_SUBNORMAL** | Pozitif veya negatif normale göre (normalden arındırılmış) değer |
| **FP_ZERO** | Pozitif veya negatif sıfır değeri |

Ek ayrıntı için Microsoft'a özgü [_fpclass, _fpclassf](fpclass-fpclassf.md) işlevlerik kullanabilirsiniz. Taşınabilirlik için [fpclassify](fpclassify.md) işlevini kullanın.

## <a name="_d_int-_ld_int-_fd_int"></a>_d_int, _ld_int, _fd_int

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _d_int(double* px, short exp);
short __cdecl _ld_int(long double* px, short exp);
short __cdecl _fd_int(float* px, short exp);
```

### <a name="parameters"></a>Parametreler

*px*<br/>
Kayan nokta bağımsız değişkenini işaretçi.

*Exp*<br/>
Ayrılmaz bir tür olarak bir üs.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta ilkel bir kayan nokta değeri *px* ve üs değeri *için*bir işaretçi almak ve kayan nokta değerinin kesirli kısmını kaldırmak için verilen üs altında, mümkünse. Döndürülen değer, nan veya sonsuz ise px'teki giriş değeri ndeki **fpclassify'nin** ve aksi takdirde *px'teki* çıkış değerinin sonucudur. *px*

## <a name="_dscale-_ldscale-_fdscale"></a>_dscale, _ldscale, _fdscale

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dscale(double* px, long exp);
short __cdecl _ldscale(long double* px, long exp);
short __cdecl _fdscale(float* px, long exp);
```

### <a name="parameters"></a>Parametreler

*px*<br/>
Kayan nokta bağımsız değişkenini işaretçi.

*Exp*<br/>
Ayrılmaz bir tür olarak bir üs.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta ilkel bir kayan nokta değeri *px* ve üs değeri *exp*bir işaretçi almak ve 2 exp *px* değeri ölçeklendirmek , mümkünse.<sup>*exp*</sup> Döndürülen değer, nan veya sonsuz ise px'teki giriş değeri ndeki **fpclassify'nin** ve aksi takdirde *px'teki* çıkış değerinin sonucudur. *px* Taşınabilirlik için [ldexp, ldexpf ve ldexpl](ldexp.md) işlevlerini tercih edin.

## <a name="_dunscale-_ldunscale-_fdunscale"></a>_dunscale, _ldunscale, _fdunscale

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dunscale(short* pexp, double* px);
short __cdecl _ldunscale(short* pexp, long double* px);
short __cdecl _fdunscale(short* pexp, float* px);
```

### <a name="parameters"></a>Parametreler

*pexp*<br/>
Integral türü olarak üs için bir işaretçi.

*px*<br/>
Kayan nokta bağımsız değişkenini işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta ilkel *px* tarafından işaret yüzen nokta değeri bir anlamlı (mantissa) ve bir üs, mümkünse içine yıkmak. Önemi, mutlak değerin 0,5'ten büyük veya eşit ve 1,0'dan küçük olması gibi ölçeklendirilir. Üs, özgün kayan nokta değerinin ölçeklenen öneme 2<sup>*n*</sup>eşit olduğu *n*değeridir. Bu tamsayı üs *n* *pexp*tarafından işaret edilen yerde saklanır. Döndürülen değer, *px'teki* giriş değeri ne nn veya sonsuz ise ve çıktı değeri üzerinde **fpclassify** sonucudur. Taşınabilirlik için [frexp, frexpf, frexpl](frexp.md) fonksiyonlarını tercih edin.

## <a name="_dexp-_ldexp-_fdexp"></a>_dexp, _ldexp, _fdexp

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dexp(double* px, double y, long exp);
short __cdecl _ldexp(long double* px, long double y, long exp);
short __cdecl _fdexp(float* px, float y, long exp);
```

### <a name="parameters"></a>Parametreler

*Y*<br/>
Kayan nokta işlev bağımsız değişkeni.

*px*<br/>
Kayan nokta bağımsız değişkenini işaretçi.

*Exp*<br/>
Ayrılmaz bir tür olarak bir üs.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta ilkel *y* * 2<sup>*exp*</sup> *eşit px* tarafından işaret edilen yerde kayan nokta değeri inşa . Döndürülen değer, *nan* veya sonsuz ise y'deki giriş değeri ve *px'teki* çıkış değeri üzerinde **fpclassify** sonucudur. Taşınabilirlik için [ldexp, ldexpf ve ldexpl](ldexp.md) işlevlerini tercih edin.

## <a name="_dnorm-_fdnorm"></a>_dnorm, _fdnorm

### <a name="syntax"></a>Sözdizimi

```C
short __cdecl _dnorm(unsigned short* ps);
short __cdecl _fdnorm(unsigned short* ps);
```

### <a name="parameters"></a>Parametreler

*Ps*<br/>
**İmzalanmamış** **kısa**bir dizi olarak ifade edilen kayan nokta değerinin bitwise gösterimine işaretçi.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta ilkel bir underflowed kayan nokta değerinin kesirli kısmını normalleştirmek ve *karakteristik*ayarlamak , ya da önyargılı üs, maç. Değer, math.h'de beyan edilen **imzasız** **kısa** `_double_val` `_ldouble_val` `_float_val` bir diziye dönüştürülen kayan nokta türünün bit yönünden gösterimi olarak geçirilir. İade değeri, nan veya sonsuz ise giriş kayan nokta değeri ve aksi takdirde çıktı değeri üzerinde **fpclassify** sonucudur.

## <a name="_dpoly-_ldpoly-_fdpoly"></a>_dpoly, _ldpoly, _fdpoly

### <a name="syntax"></a>Sözdizimi

```C
double __cdecl _dpoly(double x, double const* table, int n);
long double __cdecl _ldpoly(long double x, long double const* table, int n);
float __cdecl _fdpoly(float x, _float const* table, int n);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Kayan nokta işlev bağımsız değişkeni.

*Tablo*<br/>
Bir polinom için sabit katsayılar tablosuna işaretçi.

*n*<br/>
Polinomun sırasını değerlendirmek.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta ilkelleri, katsayıları *tablodaki*karşılık gelen sabit değerlerle temsil edilen *n.* sıranın polinomundaki *x* değerlendirmesini döndürürler. Örneğin, *tablo*\[0] = 3.0, *tablo*\[1] = 4.0, *tablo*\[2] = 5.0 ve *n* = 2 ise, polinom 5.0x<sup>2</sup> + 4.0x + 3.0'ı temsil eder. Bu polinom 2.0 *x* için değerlendirilirse, sonuç 31.0'dır. Bu işlevler dahili olarak kullanılmaz.

## <a name="_dlog-_dlog-_dlog"></a>_dlog, _dlog, _dlog

### <a name="syntax"></a>Sözdizimi

```C
double __cdecl _dlog(double x, int base_flag);
long double __cdecl _ldlog(long double x, int base_flag);
float __cdecl _fdlog(float x, int base_flag);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Kayan nokta işlev bağımsız değişkeni.

*base_flag*<br/>
Kullanılacak tabanı kontrol eden bayrak, taban *e* için 0 ve temel 10 için sıfır olmayan.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta ilkelx *doğal*günlük dönmek , ln (*x*) veya günlük<sub>*e*</sub>(*x*), *base_flag* 0 olduğunda. *base_flag* sıfır olmadığında *x'in*günlük tabanını 10 veya günlük<sub>10</sub>*(x)* döndürerler. Bu işlevler dahili olarak kullanılmaz. Taşınabilirlik için, [günlük, logf, logl, log10, log10f ve log10l](log-logf-log10-log10f.md)işlevlerini tercih edin.

## <a name="_dsin-_ldsin-_fdsin"></a>_dsin, _ldsin, _fdsin

### <a name="syntax"></a>Sözdizimi

```C
double __cdecl _dsin(double x, unsigned int quadrant);
long double __cdecl _ldsin(long double x, unsigned int quadrant);
float __cdecl _fdsin(float x, unsigned int quadrant);
```

### <a name="parameters"></a>Parametreler

*X*<br/>
Kayan nokta işlev bağımsız değişkeni.

*Çeyreği*<br/>
0, 1, 2 veya 3 quadrant ofset `sin`üretmek için kullanmak , , `cos` `-sin`, ve `-cos` sonuçlar.

### <a name="remarks"></a>Açıklamalar

Bu kayan nokta ilkel ler *x* x'in sinüs'ini *quadrant* modulo 4 ile dengeler. Etkili bir şekilde, x'in sinüs, kosinüs, -sinüs ve -kosinüslerini, *quadrant* modulo 4'ün sırasıyla 0, 1, 2 veya 3 olduğunda geri verirler. *x* Bu işlevler dahili olarak kullanılmaz. Taşınabilirlik için, [günah, günah, günah,](sin-sinf-sinl.md) [cos, cosf ve cosl](cos-cosf-cosl.md) fonksiyonları tercih edin.

## <a name="requirements"></a>Gereksinimler

Başlık: \<math.h>

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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
