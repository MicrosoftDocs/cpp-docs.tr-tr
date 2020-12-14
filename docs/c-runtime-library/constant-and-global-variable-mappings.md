---
description: 'Daha fazla bilgi edinin: sabit ve global değişken eşlemeleri'
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
ms.openlocfilehash: 6078564a5f9d6ef28de704f4991264b5de58041b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195768"
---
# <a name="constant-and-global-variable-mappings"></a>Sabit ve Global Değişken Eşlemeleri

Bu genel metin sabiti, genel değişken ve standart tür eşlemeleri TCHAR 'da tanımlanmıştır. H ve sabit `_UNICODE` veya `_MBCS` programınızda tanımlanıp tanımlanmadığına bağlı olarak değişir.

### <a name="generic-text-constant-and-global-variable-mappings"></a>Generic-Text sabit ve global değişken eşlemeleri

|Genel metin-nesne adı|SBCS (_UNICODE, _MBCS tanımlanmadı)|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|----------------------------------|--------------------------------------------|--------------------|-----------------------|
|`_TEOF`|`EOF`|`EOF`|`WEOF`|
|`_tenviron`|`_environ`|`_environ`|`_wenviron`|
|`_tpgmptr`|`_pgmptr`|`_pgmptr`|`_wpgmptr`|

## <a name="see-also"></a>Ayrıca bkz.

[Genel metin eşlemeleri](../c-runtime-library/generic-text-mappings.md)<br/>
[Veri türü eşlemeleri](../c-runtime-library/data-type-mappings.md)<br/>
[Rutin eşlemeler](../c-runtime-library/routine-mappings.md)<br/>
[Örnek bir Generic-Text programı](../c-runtime-library/a-sample-generic-text-program.md)<br/>
[Generic-Text eşlemelerini kullanma](../c-runtime-library/using-generic-text-mappings.md)
