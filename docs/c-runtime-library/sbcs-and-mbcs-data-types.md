---
title: SBCS ve MBCS veri türleri | Microsoft Docs
ms.custom: ''
ms.date: 04/11/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- MBCS
- SBCS
dev_langs:
- C++
helpviewer_keywords:
- SBCS and MBCS data types
- data types [C], MBCS and SBCS
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cd45a20557eb3a7b2af3b1c2ecba3cc858af503
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205266"
---
# <a name="sbcs-and-mbcs-data-types"></a>SBCS ve MBCS Veri Türleri

Yalnızca bir çok baytlı karakter veya çok baytlı karakterin bir bayt işleyen herhangi bir Microsoft MBCS çalışma zamanı kitaplığı rutini bekliyor bir `unsigned int` bağımsız değişken (burada 0x00 < karakter değeri = < 0xFFFF ve 0x00 = < bayt değeri = < 0xFF =). Çok baytlı bayt veya karakter dizesi bağlamda işleyen bir MBCS yordamı olarak gösterilemeyecek kadar çok baytlı karakter dizesi bekliyor. bir `unsigned char` işaretçi.

> [!CAUTION]
> Her bayt çok baytlı karakterin bir 8 bit temsil edilebilir **char**. Ancak, bir türünün SBCS veya MBCS tek baytlık karakter **char** 0x7F değerinden büyük bir değere sahip. Ne tür bir karakter dönüştürülür doğrudan bir **int** veya **uzun**, sonuç derleyici tarafından işareti genişletilmiş ve bu nedenle beklenmeyen sonuçlara yol açabilir.

Bu nedenle bir 8-bit olarak çok baytlı karakterin bir baytını temsil eden en iyisidir `unsigned char`. Veya negatif bir sonuç önlemek için yalnızca bir tek baytlı karakter türü dönüştürme **char** için bir `unsigned char` için dönüştürmeden önce bir **int** veya **uzun**.

Bazı SBCS dize işleme işlevleri (imzalanmış) çünkü **char** <strong>\*</strong> parametre türü uyuşmazlığı derleyici uyarı neden olur, **_MBCS** olduğu tanımlı. Bu uyarı, verimliliği sırasına göre listelenen önlemek için üç yol vardır:

1. Tür kullanımı uyumlu satır içi işlevleri TCHAR kullanın. H Bu varsayılan davranıştır.

1. TCHAR içinde doğrudan makroları kullanın. Tanımlayarak H **_MB_MAP_DIRECT** komut satırında. Bunu yaparsanız, el ile türlerinin eşleşmesi gerekir. Bu, en hızlı yoludur ancak tür kullanımı uyumlu değil.

1. Tür kullanımı uyumlu statik olarak bağlı bir kitaplığı işlevleri TCHAR kullanabilirsiniz. H Bunu yapmak için definovat konstantu **_NO_INLINING** komut satırında. Ancak en iyi tür açısından güvenli yavaş yöntem budur.

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategoriye göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
