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
ms.openlocfilehash: d78ca2a195ac60e31e01bbe271b7f92536cc1a05
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401488"
---
# <a name="main-program-startup"></a>main: Program Başlatma
Adlı bir özel işlev **ana** yürütme tüm C ve C++ programları için başlangıç noktasıdır. Aynılarını kod yazma varsa [!INCLUDE[TLA#tla_unicode](../atl-mfc-shared/reference/includes/tlasharptla_unicode_md.md)] kullanabileceğiniz programlama modeli, `wmain`, geniş karakter sürümünü olduğu **ana**.  
  
 **Ana** işlevi derleyici tarafından önceden değil. Program metni sağlanmalıdır.  
  
 Bildirim sözdizimi **ana** olduğu  
  
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
  
 Ayrıca `_tmain`, TCHAR.h içinde tanımlanır. `_tmain` çözümler **ana** _UNICODE tanımlanmış sürece. Bu durumda, `_tmain` çözümler `wmain`.  
  
 Alternatif olarak, **ana** ve `wmain` olarak döndüren işlevleri bildirilebilir **void** (dönüş değeri). Bildirirseniz **ana** veya `wmain` döndüren olarak **void**, kullanarak üst işleme ya da işletim sistemi için bir çıkış kodu döndürülemez bir [dönüş](../cpp/return-statement-in-program-termination-cpp.md) deyimi. Döndürülecek bir çıkış kodu ne zaman **ana** veya `wmain` olarak bildirilen **void**, kullanmalısınız [çıkmak](../cpp/exit-function.md) işlevi.  
  
**END Microsoft özgü**  
 Türleri için `argc` ve `argv` dil tarafından tanımlanır. Adları `argc`, `argv`, ve `envp` Geleneksel, ancak derleyici tarafından gerekli değildir. Daha fazla bilgi ve örnek için bkz. [bağımsız değişken tanımları](../cpp/argument-definitions.md).  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [anahtar sözcükler](../cpp/keywords-cpp.md)   
 [Main yerine wmain kullanma](../cpp/using-wmain-instead-of-main.md)   
 [Main işlevi kısıtlamaları](../cpp/main-function-restrictions.md)   
 [C++ Komut Satırı Bağımsız Değişkenlerini Ayrıştırma](../cpp/parsing-cpp-command-line-arguments.md)