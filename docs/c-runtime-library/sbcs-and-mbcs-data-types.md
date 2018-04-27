---
title: SBCS ve MBCS veri türleri | Microsoft Docs
ms.custom: ''
ms.date: 04/11/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f75999b1436ef350e12c47405cac911367ffda2b
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="sbcs-and-mbcs-data-types"></a>SBCS ve MBCS Veri Türleri

Yalnızca tek baytlı karakter veya birden çok baytlı karakter tek baytlık işleyen herhangi Microsoft MBCS çalışma zamanı kitaplığı yordamı bekliyor bir `unsigned int` bağımsız değişkeni (burada 0x00 < karakter değeri = < 0xFFFF ve 0x00 = < bayt değeri = < 0xFF =). Birden çok baytlı bayt veya karakter dizesi bağlamda işleyen bir MBCS yordamı olarak gösterilemeyecek kadar çok baytlı karakter dizesi bekliyor bir `unsigned char` işaretçi.

> [!CAUTION]
> Birden çok baytlı karakter her baytlık bir 8 bit temsil edilebilir **char**. Ancak, bir SBCS veya MBCS tek baytlı karakter türü **char** 0x7F negatifse büyük bir değere sahip. Ne zaman böyle bir karakter dönüştürülür doğrudan bir **int** veya **uzun**, sonuç derleyici tarafından oturum genişletilmiş olacak ve bu nedenle beklenmeyen sonuçlara yol açabilir.

Bu nedenle bir 8 bit olarak birden çok baytlı karakter baytını temsil etmek en iyisidir `unsigned char`. Veya negatif bir sonuç önlemek için yalnızca tek baytlı karakter türü dönüştürme **char** için bir `unsigned char` için dönüştürmeden önce bir **int** veya **uzun**.

Bazı SBCS dize işleme (işaretli) gördüğünden **char\***  parametreleri, bir tür uyuşmazlığı derleyici uyarısı sonuçlanacak zaman **_MBCS** tanımlanır. Bu uyarı, verimliliği sırasına önlemek için üç yol vardır:

1. Tür kullanımı uyumlu satır içi işlevler içinde TCHAR kullanın. H. Bu varsayılan davranıştır.

1. Doğrudan makroları TCHAR içinde kullanın. Tanımlayarak H **_MB_MAP_DIRECT** komut satırında. Bunu yaparsanız, türleri el ile eşleşmelidir. Bu en hızlı yoludur ancak tür kullanımı uyumlu değil.

1. Tür kullanımı uyumlu statik olarak bağlantılı kitaplık işlevleri TCHAR kullanabilirsiniz. H. Bunu yapmak için sabit tanımlamak **_NO_INLINING** komut satırında. En fazla tür kullanımı uyumlu ancak yavaş yöntem budur.

## <a name="see-also"></a>Ayrıca Bkz.

[Uluslararası duruma getirme](../c-runtime-library/internationalization.md)<br/>
[Kategorilere göre Evrensel C çalışma zamanı yordamları](../c-runtime-library/run-time-routines-by-category.md)<br/>
