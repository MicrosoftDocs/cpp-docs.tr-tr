---
title: Veri Türü Eşlemeleri
ms.date: 11/04/2016
f1_keywords:
- _TXCHAR
- _TUCHAR
- _TINT
- _TSCHAR
- _TCHAR
- TCHAR::H
- TCHAR
- _T
- _TEXT
helpviewer_keywords:
- _TXCHAR type
- TINT type
- _TCHAR type
- TSCHAR type
- TEXT type
- TCHAR type
- TCHAR.H data types, mappings defined in
- generic-text data types
- _TINT type
- TUCHAR type
- TXCHAR type
- _TSCHAR type
- T type
- _TUCHAR type
- _TEXT type
- _T type
ms.assetid: 4e573c05-8800-468b-ae5f-76ff7409835e
ms.openlocfilehash: d77ac4fa9afcd5a6b8f86261c7a3ba466adc64a4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215159"
---
# <a name="data-type-mappings"></a>Veri Türü Eşlemeleri

Bu veri türü eşlemeleri TCHAR 'da tanımlanmıştır. H ve sabit `_UNICODE` veya `_MBCS` programınızda tanımlanıp tanımlanmadığına bağlı olarak değişir.

İlgili bilgiler için bkz [. TCHAR kullanma. _MBCS koduna sahip H veri türleri](../text/using-tchar-h-data-types-with-mbcs-code.md).

### <a name="generic-text-data-type-mappings"></a>Genel metin veri türü eşlemeleri

|Genel metin<br /><br /> veri türü adı|SBCS (_UNICODE,<br /><br /> _MBCS<br /><br /> tanımlı|_MBCS<br /><br /> tanımlanmış|_UNICODE<br /><br /> tanımlanmış|
|--------------------------------------|----------------------------------------------------|------------------------|---------------------------|
|`_TCHAR`|**`char`**|**`char`**|**`wchar_t`**|
|`_tfinddata_t`|`_finddata_t`|`_finddata_t`|`_wfinddata_t`|
|`_tfinddata64_t`|`__finddata64_t`|`__finddata64_t`|`__wfinddata64_t`|
|`_tfinddatai64_t`|`_finddatai64_t`|`_finddatai64_t`|`_wfinddatai64_t`|
|`_TINT`|**`int`**|**`int`**|`wint_t`|
|`_TSCHAR`|**`signed char`**|**`signed char`**|**`wchar_t`**|
|`_TUCHAR`|**`unsigned char`**|**`unsigned char`**|**`wchar_t`**|
|`_TXCHAR`|**`char`**|**`unsigned char`**|**`wchar_t`**|
|`_T` veya `_TEXT`|Efekt yok (ön işlemci tarafından kaldırıldı)|Efekt yok (ön işlemci tarafından kaldırıldı)|`L`(aşağıdaki karakter veya dizeyi Unicode karşılığına dönüştürür)|

## <a name="see-also"></a>Ayrıca bkz.

[Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md)<br/>
[Sabit ve global değişken eşlemeleri](../c-runtime-library/constant-and-global-variable-mappings.md)<br/>
[Rutin eşlemeler](../c-runtime-library/routine-mappings.md)<br/>
[Örnek bir genel metin programı](../c-runtime-library/a-sample-generic-text-program.md)<br/>
[Genel metin eşlemelerini kullanma](../c-runtime-library/using-generic-text-mappings.md)
