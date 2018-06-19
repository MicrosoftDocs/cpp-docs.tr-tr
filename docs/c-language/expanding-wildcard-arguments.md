---
title: Joker karakter bağımsız değişkenlerini genişletme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69d7a9fc75e23a03e4db232bc798c89f89083e62
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32383637"
---
# <a name="expanding-wildcard-arguments"></a>Joker Karakter Bağımsız Değişkenlerini Genişletme
**Microsoft özel**  
  
 Bir C programı çalıştırdığınızda ya da iki joker karakterleri kullanabilirsiniz; soru işareti (?) ve yıldız işareti (*) — komut satırında dosya adını ve yolunu bağımsız değişkenlerini belirtmek için.  
  
 Varsayılan olarak, joker karakter komut satırı bağımsız değişkenleri genişletilmiş değil. Normal bağımsız değişkeni vektör değiştirebilirsiniz `argv` joker karakterler setargv.obj ya da wsetargv.obj dosyasıyla bağlayarak genişletin sürüme sahip yordamı yükleniyor. Programınızı kullanıyorsa, bir `main` işlevi, setargv.obj içeren bağlantı. Programınızı kullanıyorsa, bir `wmain` işlevi, wsetargv.obj içeren bağlantı. Bunların her ikisi de eşdeğer davranışına sahip.  
  
 Setargv.obj veya wsetargv.obj bağlamak için kullanın **/link** seçeneği. Örneğin:  
  
 **cl example.c/Link setargv.obj**  
  
 Joker karakterler, işletim sistemi komutlarını aynı şekilde genişletilir. (Joker karakter olarak bilginiz yoksa, işletim sistemi Kullanıcı Kılavuzu na bakın.)  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlantı seçenekleri](../c-runtime-library/link-options.md)   
 [main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)