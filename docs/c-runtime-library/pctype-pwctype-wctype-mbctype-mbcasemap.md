---
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
ms.openlocfilehash: 8ffb46dc410bc1397e3d592f68339b4a58dae86c
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70939974"
---
# <a name="_pctype-_pwctype-_wctype-_mbctype-_mbcasemap"></a>_pctype, _pwctype, _wctype, _mbctype, _mbcasemap

Bu genel değişkenler, karakter sınıflandırma işlevleri tarafından kullanılan bilgileri içerir. Yalnızca iç kullanım içindir.

## <a name="syntax"></a>Sözdizimi

```
extern const unsigned short *_pctype;
extern const wctype_t *_pwctype;
extern const unsigned short _wctype[];
extern unsigned char _mbctype[];
extern unsigned char _mbcasemap[];
```

## <a name="remarks"></a>Açıklamalar

`_pctype` ,`_pwctype`Ve içindeki`_wctype` bilgiler, [IsUpper, _ıüste_l, ıswupper, _ıswüste_l](../c-runtime-library/reference/isupper-isupper-l-iswupper-iswupper-l.md), [IsLower, ıswlower, _isalk_l, _iswbüyük_l](../c-runtime-library/reference/islower-iswlower-islower-l-iswlower-l.md), [isdigit, ıswdigit, _ısdigit_l, _iswdigit_l tarafından dahili olarak kullanılır ](../c-runtime-library/reference/isdigit-iswdigit-isdigit-l-iswdigit-l.md), [ısxdigit, ıswxdigit, _isxdigit_l, _iswxdigit_l](../c-runtime-library/reference/isxdigit-iswxdigit-isxdigit-l-iswxdigit-l.md), [ısspace, ıswspace, _isspace_l, _iswspace_l](../c-runtime-library/reference/isspace-iswspace-isspace-l-iswspace-l.md), [ısalnum, iswalnum, _ısalnum_l, _iswalnum_l](../c-runtime-library/reference/isalnum-iswalnum-isalnum-l-iswalnum-l.md), [ıspunct, iswpunct, _ıspunct_l, _iswpunct_l](../c-runtime-library/reference/ispunct-iswpunct-ispunct-l-iswpunct-l.md), [ısgraph, iswgraf, _isgraph_l, _iswgraph_l](../c-runtime-library/reference/isgraph-iswgraph-isgraph-l-iswgraph-l.md), [SCC, ıbwcnu, _scc, bir _ıswcntrl_l](../c-runtime-library/reference/iscntrl-iswcntrl-iscntrl-l-iswcntrl-l.md), [ToUpper, _toupper, towupper, _toüste_l, _towüst_l](../c-runtime-library/reference/toupper-toupper-towupper-toupper-l-towupper-l.md), [ToLower, _tolower, towlower, _tonet_l ve _towbüyük_l](../c-runtime-library/reference/tolower-tolower-towlower-tolower-l-towlower-l.md) işlevleri. Bu işlevler, bu genel değişkenlere erişmek yerine kullanılmalıdır.

`_mbctype` Ve`_mbcasemap` içindeki bilgiler [_ismbbkalnum, _ısmbbkalnum_l](../c-runtime-library/reference/ismbbkalnum-ismbbkalnum-l.md), [_ismbbkana, _ısmbbkana_l](../c-runtime-library/reference/ismbbkana-ismbbkana-l.md), _ismbbkpunct, _ısmbbkpunct_l, [_ismbbkprınt, _ismbbkprint_l](../c-runtime-library/reference/ismbbkprint-ismbbkprint-l.md), [](../c-runtime-library/reference/ismbbkpunct-ismbbkpunct-l.md) [_ismbbalpha tarafından dahili olarak kullanılır. ](reference/ismbbalpha-ismbbalpha-l.md), [_ismbbpunct, _ismbbpunct_l](../c-runtime-library/reference/ismbbpunct-ismbbpunct-l.md), [_ismbbalnum, _ismbbalnum_l](../c-runtime-library/reference/ismbbalnum-ismbbalnum-l.md), [_ismbbprint, _ismbbprint_l](../c-runtime-library/reference/ismbbprint-ismbbprint-l.md), [_ismbbgraph, _ismbbgraph_l](../c-runtime-library/reference/ismbbgraph-ismbbgraph-l.md), _ismbbıngıl, [_ismbblead_l](../c-runtime-library/reference/ismbblead-ismbblead-l.md), _ismbbiz [, _ismbbtrail_l](../c-runtime-library/reference/ismbbtrail-ismbbtrail-l.md), [_ismbslider, _ismbstraıl, _ismbslead_l, _ismbstrail_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md), [_ismbslider, _ismbstraıl, _ismbslead_l ve _ismbstrail_l](../c-runtime-library/reference/ismbslead-ismbstrail-ismbslead-l-ismbstrail-l.md). Genel değişkenlere erişmek yerine bu işlevleri kullanın.

## <a name="requirements"></a>Gereksinimler

Genel kullanım için değil.

## <a name="see-also"></a>Ayrıca bkz.

[is, isw Yordamları](../c-runtime-library/is-isw-routines.md)<br/>
[__pctype_func](../c-runtime-library/pctype-func.md)
