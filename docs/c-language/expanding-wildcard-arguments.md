---
title: "Joker karakter bağımsız değişkenlerini genişletme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.assetid: 80a11c4b-0199-420e-a342-cf1d803be5bc
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b0c1deca52e74241b56c3c152e66a74d652b4829
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Main işlevi ve Program yürütme](../c-language/main-function-and-program-execution.md)