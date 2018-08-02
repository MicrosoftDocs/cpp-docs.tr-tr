---
title: Main yerine wmain kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- wmain
dev_langs:
- C++
helpviewer_keywords:
- main function, vs. wmain
- wmain function
ms.assetid: 7abb1257-b85c-413a-b913-d45b1582a71d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7e093bc006a5b2c8ebba6fd2967a2a549d46c574
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466055"
---
# <a name="using-wmain-instead-of-main"></a>main Yerine wmain Kullanma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Unicode programlama modelinde, bir geniş karakter sürümünü tanımlayabilirsiniz `main` işlevi. Kullanım **wmain** yerine `main` Unicode belirtimine aynılarını taşınabilir kod yazmak istiyorsanız.  
  
 Biçimsel parametre bildirirsiniz **wmain** için benzer bir biçimde kullanarak `main`. Ardından, geniş karakter bağımsız değişkenlerini ve isteğe bağlı olarak bir geniş karakter ortamında işaretçi programa geçirebilirsiniz. *Argv* ve *envp* parametreleri **wmain** türü `wchar_t*`.  
  
 Programınızı kullanıyorsa bir `main` işlevi çok baytlı karakterli ortam program başlangıcında işletim sistemi tarafından oluşturulur. Ortamın geniş karakterli kopyası yalnızca gerektiğinde oluşturulur (örneğin, bir çağrı tarafından [_wgetenv](../c-runtime-library/reference/getenv-wgetenv.md) veya [_wputenv](../c-runtime-library/reference/putenv-wputenv.md) işlevler). Bir MBCS ortamı zaten varsa, `_wputenv` veya `_wgetenv` için yapılan ilk çağrıda karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve ardından `_wenviron` genel değişkeninin geniş karakterli bir sürümü olan `_environ` genel değişkeni tarafından gösterilir. Bu noktada, ortamın iki kopyası (MBCS ve Unicode) aynı anda var olur ve program ömrü boyunca işletim sistemi tarafından korunur.  
  
 Benzer şekilde, programınız kullanıyorsa bir **wmain** işlevi, bir MBCS (ASCII) ortamı oluşturulur yapılan ilk çağrı `_putenv` veya `getenv`ve tarafından işaret edilen `_environ` genel değişkeni.  
  
 MBCS ortamı hakkında daha fazla bilgi için bkz. [tek baytlı ve çok baytlı karakter kümeleri](../c-runtime-library/single-byte-and-multibyte-character-sets.md) içinde *çalışma zamanı kitaplığı başvurusu.*  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [main: Program Başlatma](../cpp/main-program-startup.md)