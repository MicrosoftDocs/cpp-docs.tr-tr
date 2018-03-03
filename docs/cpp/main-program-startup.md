---
title: "Main: Program başlatma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- vc.main.startup
- _tmain
dev_langs:
- C++
helpviewer_keywords:
- program startup [C++]
- entry points, program
- wmain function
- _tmain function
- startup code, main function
- main function, program startup
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1fbb3d19101358012df795000907a0b3e8139601
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="main-program-startup"></a>main: Program Başlatma
Adlı özel bir işlev `main` yürütme tüm C ve C++ programları için başlangıç noktasıdır. Aynılarını kod yazma varsa [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] kullanabileceğiniz programlama modeli, `wmain`, joker karakter sürümü olduğu `main`.  
  
 `main` Derleyici tarafından işlevi önceden değil. Program metinde sağlanmalıdır.  
  
 Bildirim sözdizimi `main` olduğu  
  
```  
int main();  
```  
  
 veya isteğe bağlı olarak,  
  
```  
int main(int argc, char *argv[], char *envp[]);  
```  
  
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bildirim sözdizimi için `wmain` aşağıdaki gibidir:  
  
```  
int wmain( );  
```  
  
 veya isteğe bağlı olarak,  
  
```  
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 Aynı zamanda `_tmain`, TCHAR.h içinde tanımlanır. `_tmain`çözümler `main` _UNICODE tanımlanmadığı sürece. Bu durumda, `_tmain` çözümler `wmain`.  
  
 Alternatif olarak, `main` ve `wmain` işlevleri döndürme olarak bildirilebilir `void` (dönüş değeri yok). Bildirirseniz `main` veya `wmain` döndürme olarak `void`, kullanarak üst işleme veya işletim sistemi için bir çıkış kodu döndüremez bir [dönmek](../cpp/return-statement-in-program-termination-cpp.md) deyimi. Döndürülecek bir çıkış kodu ne zaman `main` veya `wmain` olarak bildirilen `void`, kullanmalısınız [çıkmak](../cpp/exit-function.md) işlevi.  
  
**SON Microsoft özel**  
 Türleri için `argc` ve `argv` dil tarafından tanımlanır. Adları `argc`, `argv`, ve `envp` geleneksel ancak derleyici tarafından gerekli değildir. Daha fazla bilgi ve bir örnek için bkz: [bağımsız değişken tanımları](../cpp/argument-definitions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Main yerine wmain kullanma](../cpp/using-wmain-instead-of-main.md)   
 [main İşlevi Kısıtlamaları](../cpp/main-function-restrictions.md)