---
title: Main yerine wmain kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- wmain
dev_langs:
- C++
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d43ab12c42315d735220af8f91c40d8b6a5cc4f9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-wmain-instead-of-main"></a>main Yerine wmain Kullanma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Unicode programlama modeli bir joker karakter sürümü tanımlayabilirsiniz **ana** işlevi. Kullanım **wmain** yerine **ana** Unicode belirtimi aynılarını taşınabilir kod yazmak istiyorsanız.  
  
 Biçimsel parametresi bildirme **wmain** benzer bir biçimde kullanarak **ana**. Ardından, joker karakter bağımsız değişkenlerini ve isteğe bağlı olarak bir joker karakter ortamı işaretçisi program geçirebilirsiniz. `argv` Ve `envp` parametreleri **wmain** türü `wchar_t*`.  
  
 Programınızı kullanıyorsa, bir **ana** işlevi, çok baytlı karakter ortamı program başlatma sırasında işletim sistemi tarafından oluşturulur. Ortam geniş karakter kopyası yalnızca gerekli olduğunda oluşturulur (örneğin, bir çağrı tarafından [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) veya [_wputenv](../c-runtime-library/reference/putenv-wputenv.md) işlevleri). Bir MBCS ortamı zaten varsa, `_wputenv` veya `_wgetenv` için yapılan ilk çağrıda karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve ardından `_wenviron` genel değişkeninin geniş karakterli bir sürümü olan `_environ` genel değişkeni tarafından gösterilir. Bu noktada, ortamın iki kopyası (MBCS ve Unicode) aynı anda var olur ve program ömrü boyunca işletim sistemi tarafından korunur.  
  
 Benzer şekilde, programınız kullanıyorsa, bir **wmain** işlevi, bir MBCS (ASCII) ortamında ilk çağrıda oluşturulur `_putenv` veya `getenv`ve işaret ediyor `_environ` genel değişkeni.  
  
 MBCS ortamı hakkında daha fazla bilgi için bkz: [tek baytlı ve çok baytlı karakter kümeleri](../c-runtime-library/single-byte-and-multibyte-character-sets.md) içinde *çalışma zamanı kitaplığı başvurusu.*  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [main: Program Başlatma](../cpp/main-program-startup.md)