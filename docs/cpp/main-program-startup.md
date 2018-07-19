---
title: 'Main: Program başlatma | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2f78a122837fc2cb9a89083d5be8fd2b488c1772
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37939230"
---
# <a name="main-program-startup"></a>main: Program Başlatma
Adlı bir özel işlev `main` yürütme tüm C ve C++ programları için başlangıç noktasıdır. Aynılarını kod yazma varsa [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] kullanabileceğiniz programlama modeli, `wmain`, geniş karakter sürümünü olduğu `main`.  
  
 `main` İşlevi derleyici tarafından önceden değil. Program metni sağlanmalıdır.  
  
 Bildirim sözdizimi `main` olduğu  
  
```cpp 
int main();  
```  
  
 veya isteğe bağlı olarak,  
  
```cpp 
int main(int argc, char *argv[], char *envp[]);  
```  
  
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Bildirim sözdizimi `wmain` aşağıdaki gibidir:  
  
```cpp 
int wmain( );  
```  
  
 veya isteğe bağlı olarak,  
  
```cpp 
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 Ayrıca `_tmain`, TCHAR.h içinde tanımlanır. `_tmain` çözümler `main` _UNICODE tanımlanmış sürece. Bu durumda, `_tmain` çözümler `wmain`.  
  
 Alternatif olarak, `main` ve `wmain` olarak döndüren işlevleri bildirilebilir **void** (dönüş değeri). Bildirirseniz `main` veya `wmain` döndüren olarak **void**, kullanarak üst işleme ya da işletim sistemi için bir çıkış kodu döndürülemez bir [dönüş](../cpp/return-statement-in-program-termination-cpp.md) deyimi. Döndürülecek bir çıkış kodu ne zaman `main` veya `wmain` olarak bildirilen **void**, kullanmalısınız [çıkmak](../cpp/exit-function.md) işlevi.  
  
**END Microsoft özgü**  
 Türleri için `argc` ve `argv` dil tarafından tanımlanır. Adları `argc`, `argv`, ve `envp` Geleneksel, ancak derleyici tarafından gerekli değildir. Daha fazla bilgi ve örnek için bkz. [bağımsız değişken tanımları](../cpp/argument-definitions.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Main yerine wmain kullanma](../cpp/using-wmain-instead-of-main.md)   
 [Main işlevi kısıtlamaları](../cpp/main-function-restrictions.md)   
 [C++ Komut Satırı Bağımsız Değişkenlerini Ayrıştırma](../cpp/parsing-cpp-command-line-arguments.md)
