---
title: Wmain kullanma | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: wmain function
ms.assetid: d0300812-adc4-40c6-bba3-b2da25468c80
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3dcad032c8a77309d66f02a1b58c46a4e6d526b8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="using-wmain"></a>wmain Kullanma
**Microsoft özel**  
  
 Unicode programlama modeli bir joker karakter sürümü tanımlayabilirsiniz **ana** işlevi. Kullanım **wmain** yerine **ana** programlama modeli Unicode aynılarını taşınabilir kod yazmak istiyorsanız.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Biçimsel parametresi bildirme **wmain** benzer bir biçimde kullanarak **ana**. Ardından, joker karakter bağımsız değişkenlerini ve isteğe bağlı olarak bir joker karakter ortamı işaretçisi program geçirebilirsiniz. `argv` Ve `envp` parametreleri **wmain** türü `wchar_t*`. Örneğin:  
  
 Programınızı kullanıyorsa, bir **ana** işlevi, çok baytlı karakter ortamı program başlatma sırasında çalışma zamanı kitaplığı tarafından oluşturulur. Ortam geniş karakter kopyası yalnızca gerekli olduğunda oluşturulur (örneğin, bir çağrı tarafından `_wgetenv` veya `_wputenv` işlevleri). Bir MBCS ortamı zaten varsa, `_wputenv` veya `_wgetenv` için yapılan ilk çağrıda karşılık gelen bir geniş karakterli dize ortamı oluşturulur ve ardından `_wenviron` genel değişkeninin geniş karakterli bir sürümü olan `_environ` genel değişkeni tarafından gösterilir. Bu noktada, ortamın iki kopyası (MBCS ve Unicode) aynı anda var olur ve program ömrü boyunca işletim sistemi tarafından korunur.  
  
 Benzer şekilde, program kullanıyorsa, bir **wmain** işlevi, bir joker karakter ortamı program başlangıcında oluşturulur ve işaret ediyor `_wenviron` genel değişkeni. MBCS (ASCII) ortamı ilk çağrıda oluşturulur `_putenv` veya `getenv`ve işaret ediyor `_environ` genel değişkeni.  
  
 MBCS ortamı hakkında daha fazla bilgi için bkz: [uluslararası](../c-runtime-library/internationalization.md) içinde *çalışma zamanı kitaplığı başvurusu.*  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Main işlevi ve Program yürütme](../c-language/main-function-and-program-execution.md)