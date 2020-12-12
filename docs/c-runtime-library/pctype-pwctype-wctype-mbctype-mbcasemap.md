---
description: 'Hakkında daha fazla bilgi edinin: _pctype, _pwctype, _wctype, _mbctype, _mbcasemap'
title: _pctype, _pwctype, _wctype, _mbctype, _mbcasemap
ms.date: 11/04/2016
api_name:
- _pctype
- _pwctype
- _wctype
- _mbctype
- _mbcasemap
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- pwctype
- pctype
- mbctype
- mbcasemap
- _mbcasemap
- _mbctype
- _pctype
- _wctype
- _pcwtype
helpviewer_keywords:
- _wctype function
- _pwctype function
- _pctype function
- _mbctype function
- wctype function
- pwctype function
- pctype function
- mbcasemap function
- mbctype function
- _mbcasemap function
ms.assetid: 7f5e1107-c43b-4b9b-b387-781e6d2373cb
ms.openlocfilehash: 4122d282b3b205af3d6fb67f9755f9c13c4bb5e2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97213461"
---
# <a name="_pctype-_pwctype-_wctype-_mbctype-_mbcasemap"></a>_pctype, _pwctype, _wctype, _mbctype, _mbcasemap

Bu genel değişkenler, karakter sınıflandırma işlevleri tarafından kullanılan bilgileri içerir. Yalnızca iç kullanım içindir.

## <a name="syntax"></a>Syntax

```
extern const unsigned short *_pctype;
extern const wctype_t *_pwctype;
extern const unsigned short _wctype[];
extern unsigned char _mbctype[];
extern unsigned char _mbcasemap[];
```

## <a name="remarks"></a>Açıklamalar

`_pctype`, Ve içindeki bilgiler `_pwctype` , `_wctype` [IsUpper, _isupper_l, ıswupper, _iswupper_l](../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md), [IsLower, ıwıwlower, _islower_l, _iswlower_l](../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md), [ısdigit, ıswdigit, _isdigit_l, _iswdigit_l](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md), [ısxdigit, ıswxdigit](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md), _isxdigit_l, _iswxdigit_l, [ısspace, ıswspace, _isspace_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md), ile dahili olarak kullanılır. _iswspace_l, [ısalnum, iswalnum, _isalnum_l, _iswalnum_l](../c-runtime-library/reference/isalnum-iswalnum-isalnum-l-iswalnum-l.md), [ıspunct, iswpunct, _ispunct_l, _iswpunct_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md), [ısgraph, iswgraf, _isgraph_l, _iswgraph_l](../c-runtime-library/reference/isgraph-iswgraph-isgraph-l-iswgraph-l.md), [SCC nvaya, iswcnu, _iscntrl_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md), _iswcntrl_l, [ToUpper, _toupper, kasaüstü](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md), _toupper_l, _towupper_l, [ToLower, _tolower, towlower, _tolower_l ve _towlower_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md) işlevleri. Bu işlevler, bu genel değişkenlere erişmek yerine kullanılmalıdır.

Ve içindeki bilgiler `_mbctype` `_mbcasemap` [_ismbbkalnum, _ismbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md), [_ismbbkana, _ismbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md), [_ismbbkpunct, _ismbbkpunct_l](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md), [_ismbbkprint, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md), [_ismbbalpha](reference/ismbbalpha-ismbbalpha-l.md), [_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md), [_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md) [](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md) [](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md) [](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md) [](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md), _ismbbprint, _ismbbprint_l, _ismbbgraph, _ismbbgraph_l, _ismbblead [, _ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md), _ismbbtrail, _ismbbtrail_l, _ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l, _ismbslead, _ismbstrail, [_ismbslead_l ve _ismbstrail_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md)tarafından dahili olarak kullanılır. Genel değişkenlere erişmek yerine bu işlevleri kullanın.

## <a name="requirements"></a>Gereksinimler

Genel kullanım için değil.

## <a name="see-also"></a>Ayrıca bkz.

[, isw yordamları](../c-runtime-library/is-isw-routines.md)<br/>
[__pctype_func](../c-runtime-library/pctype-func.md)
