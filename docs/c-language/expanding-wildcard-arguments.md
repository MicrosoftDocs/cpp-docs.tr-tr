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
ms.workload: cplusplus
ms.openlocfilehash: f710cc1695579bf1a6f873229c347966888bc745
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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