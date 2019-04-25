---
title: _ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l
ms.date: 11/04/2016
apiname:
- _ismbstrail
- _ismbslead_l
- _ismbslead
- _ismbstrail_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ismbslead
- ismbs
- ismbslead_l
- _ismbs
- ismbstrail_l
- ismbslead
- _ismbstrail
- _ismbstrail_l
- ismbstrail
- _ismbslead_l
helpviewer_keywords:
- ismbstrail function
- _ismbslead function
- ismbslead function
- ismbslead_l function
- _ismbstrail function
- _ismbslead_l function
- ismbstrail_l function
- _ismbstrail_l function
ms.assetid: 86d2cd7a-3cff-443a-b713-14cc17a231e9
ms.openlocfilehash: 5b4d3f371f4be640cc22a1bdc3d920acf88e2585
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287363"
---
# <a name="ismbslead-ismbstrail-ismbsleadl-ismbstraill"></a>_ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l

Çok baytlı karakter dizesi ön bayt ve baytlar için bağlama duyarlı testleri gerçekleştirir ve verilen alt dizenin işaretçi baytı veya sondaki baytı işaret edip etmediğini belirler.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _ismbslead(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbstrail(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbslead_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
int _ismbstrail_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*str*<br/>
Dize veya önceki bilinen bayt işaretçisi.

*Geçerli*<br/>
Test edilecek dize içindeki konumu için işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_ismbslead** karakterin ön baytı -1 döndürür ve **_ismbstrail** karakterin sondaki baytı -1 döndürür. Bu işlevler, giriş dizelerinden geçerli olan, ancak bir ön bayt veya bayt, sıfır döndürür. Her iki bağımsız değişken ise **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **NULL** ayarlayıp **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_ismbslead** ve **_ismbstrail** yavaştır **_ismbblead** ve **_ismbbtrail** sürümleri çünkü bunlar dize bağlam dikkate alın.

Sahip bu işlevlerin sürümleri **_l** sonekine yerel ayara bağlı davranışları için geçerli yerel ayarı yerine iletilen yerel ayarı kullanmaları dışında. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_ismbslead**|\<Mbctype.h > veya \<mbstring.h >|\<CType.h >, * \<lımıts.h >, \<stdlib.h >|
|**_ismbstrail**|\<Mbctype.h > veya \<mbstring.h >|\<CType.h >, * \<lımıts.h >, \<stdlib.h >|
|**_ismbslead_l**|\<Mbctype.h > veya \<mbstring.h >|\<CType.h >, * \<lımıts.h >, \<stdlib.h >|
|**_ismbstrail_l**|\<Mbctype.h > veya \<mbstring.h >|\<CType.h >, * \<lımıts.h >, \<stdlib.h >|

\* Test koşullarına ilişkin bildirim sabitleri için.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karakter Sınıflaması](../../c-runtime-library/character-classification.md)<br/>
[_ismbc Yordamları](../../c-runtime-library/ismbc-routines.md)<br/>
[is, isw Yordamları](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
