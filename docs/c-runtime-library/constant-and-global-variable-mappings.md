---
title: Sabit ve Global Değişken Eşlemeleri
ms.date: 11/04/2016
f1_keywords:
- _tenviron
- _TEOF
- _tfinddata_t
helpviewer_keywords:
- tfinddatat function
- tenviron function
- TEOF type
- _TEOF type
- generic-text mappings
- _tenviron function
- _tfinddata_t function
ms.assetid: 3af4fd3e-9ed5-4ed9-96fd-7031e5126fd1
ms.openlocfilehash: 1bd96c7a305f588a24b0c6d31b2a0132d6546574
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/11/2019
ms.locfileid: "57750209"
---
# <a name="constant-and-global-variable-mappings"></a>Sabit ve Global Değişken Eşlemeleri

Bu genel metin sabiti, genel değişken ve standart türü eşlemeleri TCHAR içinde tanımlanır. H ve olup olmadığına göre bağlı sabiti `_UNICODE` veya `_MBCS` programınızda tanımlanmış.

### <a name="generic-text-constant-and-global-variable-mappings"></a>Genel metin sabit ve Global değişken eşlemeleri

|Genel metin - nesne adı|SBCS (_UNICODE, _MBCS tanımlanmamış)|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|----------------------------------|--------------------------------------------|--------------------|-----------------------|
|`_TEOF`|`EOF`|`EOF`|`WEOF`|
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|

## <a name="see-also"></a>Ayrıca bkz.

[Genel Metin Eşlemeleri](../c-runtime-library/generic-text-mappings.md)<br/>
[Veri Türü Eşlemeleri](../c-runtime-library/data-type-mappings.md)<br/>
[Rutin Eşlemeler](../c-runtime-library/routine-mappings.md)<br/>
[Örnek Genel Metin Programı](../c-runtime-library/a-sample-generic-text-program.md)<br/>
[Genel Metin Eşlemelerini Kullanma](../c-runtime-library/using-generic-text-mappings.md)
