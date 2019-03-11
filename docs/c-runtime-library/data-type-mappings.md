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
ms.openlocfilehash: 60dc4329ae4c908b9bd168584c71c42c12634bb2
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57749106"
---
# <a name="data-type-mappings"></a>Veri Türü Eşlemeleri

Bu veri türü eşlemeleri TCHAR içinde tanımlanır. H ve olup olmadığına göre bağlı sabiti `_UNICODE` veya `_MBCS` programınızda tanımlanmış.

İlgili bilgiler için bkz. [TCHAR kullanarak. _MBCS Kodu ile saat veri türleri](../text/using-tchar-h-data-types-with-mbcs-code.md).

### <a name="generic-text-data-type-mappings"></a>Genel metin veri türü eşlemeleri

|Genel metin<br /><br /> veri türü adı|SBCS (_UNICODE,<br /><br /> _MBCS değil<br /><br /> tanımlanan)|_MBCS<br /><br /> tanımlanmış|_UNICODE<br /><br /> tanımlanmış|
|--------------------------------------|----------------------------------------------------|------------------------|---------------------------|
|`_TCHAR`|`char`|`char`|`wchar_t`|
|`_tfinddata_t`|`_finddata_t`|`_finddata_t`|`_wfinddata_t`|
|`_tfinddata64_t`|`__finddata64_t`|`__finddata64_t`|`__wfinddata64_t`|
|`_tfinddatai64_t`|`_finddatai64_t`|`_finddatai64_t`|`_wfinddatai64_t`|
|`_TINT`|`int`|`int`|`wint_t`|
|`_TSCHAR`|`signed char`|`signed char`|`wchar_t`|
|`_TUCHAR`|`unsigned char`|`unsigned char`|`wchar_t`|
|`_TXCHAR`|`char`|`unsigned char`|`wchar_t`|
|`_T` veya `_TEXT`|Herhangi bir etkisi (önişlemci tarafından kaldırıldı)|Herhangi bir etkisi (önişlemci tarafından kaldırıldı)|`L` (aşağıdaki karakter veya Unicode çözümlemesiyle dizeye dönüştürür)|

## <a name="see-also"></a>Ayrıca bkz.

[Genel Metin Eşlemeleri](../c-runtime-library/generic-text-mappings.md)<br/>
[Sabit ve Global Değişken Eşlemeleri](../c-runtime-library/constant-and-global-variable-mappings.md)<br/>
[Rutin Eşlemeler](../c-runtime-library/routine-mappings.md)<br/>
[Örnek Genel Metin Programı](../c-runtime-library/a-sample-generic-text-program.md)<br/>
[Genel Metin Eşlemelerini Kullanma](../c-runtime-library/using-generic-text-mappings.md)
