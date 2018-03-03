---
title: "SBCS ve MBCS veri türleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- MBCS
- SBCS
dev_langs:
- C++
helpviewer_keywords:
- SBCS and MBCS data types
- data types [C], MBCS and SBCS
ms.assetid: 4c3ef9da-e397-48d4-800e-49dba36db171
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c54b6e9716e7f0aee9a0b211148b76804d9520bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="sbcs-and-mbcs-data-types"></a>SBCS ve MBCS Veri Türleri
Herhangi bir Microsoft `MBCS` yalnızca tek baytlı karakter veya birden çok baytlı karakter, bir bayt işler çalışma zamanı kitaplığı yordamı bekliyor bir `unsigned int` bağımsız değişkeni (burada 0x00 < karakter değeri = < 0xFFFF ve 0x00 = < bayt değeri = < 0xFF =). Bir `MBCS` birden çok baytlı bayt veya karakter dizesi bağlamda işleme yordamı bekliyor olarak gösterilemeyecek kadar çok baytlı karakter dizesi bir `unsigned char` işaretçi.  
  
> [!CAUTION]
>  Birden çok baytlı karakter her baytlık bir 8 bit temsil edilebilir `char`. Ancak, bir `SBCS` veya `MBCS` tek baytlı karakter türü `char` 0x7F negatifse büyük bir değere sahip. Ne zaman böyle bir karakter dönüştürülür doğrudan bir `int` veya `long`, sonuç derleyici tarafından oturum genişletilmiş olacak ve bu nedenle beklenmeyen sonuçlara yol açabilir.  
  
 Bu nedenle bir 8 bit olarak birden çok baytlı karakter baytını temsil etmek en iyisidir `unsigned char`. Veya negatif bir sonuç önlemek için yalnızca tek baytlı karakter türü dönüştürme `char` için bir `unsigned char` için dönüştürmeden önce bir `int` veya `long`.  
  
 Çünkü bazı `SBCS` (imzalanmış) dize işleme işlevleri Al `char*` parametreleri, bir tür uyuşmazlığı derleyici uyarısı sonuçlanacak zaman `_MBCS` tanımlanır. Bu uyarı, verimliliği sırasına önlemek için üç yol vardır:  
  
1.  "Tür kullanımı uyumlu" satır içi işlevler içinde TCHAR kullanın. H. Bu varsayılan davranıştır.  
  
2.  "Doğrudan" makroları TCHAR içinde kullanın. Tanımlayarak H `_MB_MAP_DIRECT` komut satırında. Bunu yaparsanız, türleri el ile eşleşmelidir. Bu en hızlı yoludur ancak tür kullanımı uyumlu değil.  
  
3.  "Tür kullanımı uyumlu" statik olarak bağlantılı kitaplık işlevleri TCHAR kullanabilirsiniz. H. Bunu yapmak için sabit tanımlamak `_NO_INLINING` komut satırında. En fazla tür kullanımı uyumlu ancak yavaş yöntem budur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Uluslararası duruma getirme](../c-runtime-library/internationalization.md)   
 [Kategorilere Göre Çalışma Zamanı Yordamları](../c-runtime-library/run-time-routines-by-category.md)