---
title: C komut satırı işlemini özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- _spawn functions
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _exec function
ms.assetid: c20fa11d-b35b-4f3e-93b6-2cd5a1c3c993
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 824de86ec0930fb93bf5fa0a2a8ac15a4237e4fb
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="customizing-c-command-line-processing"></a>C Komut Satırı İşlemini Özelleştirme
Programınızı komut satırı bağımsız değişken almaz, komut satırı işlemini gerçekleştiren kitaplık yordamı kullanımını gizleme tarafından az miktarda alan kaydedebilirsiniz. Bu yordam adlı **_setargv** (veya **_wsetargv** joker karakter ortamında), açıklandığı gibi [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md). Kullanımını engellemek için dosyayı içeren içinde hiçbir şey yapmaz bir yordamı tanımlayın **ana** işlev ve adlandırın **_setargv** (veya **_wsetargv** geniş karakter ortam). Çağrı **_setargv** veya **_wsetargv** sonra tanımınızı tarafından sağlanıyorsa **_setargv** veya **_wsetargv** , ve kitaplığı sürümü yüklü değil.  
  
 Benzer şekilde, ortam tabloda hiç erişirseniz `envp` bağımsız değişkeni, yerine kullanılacak kendi boş yordamı sağlayabilir **_setenvp** (veya **_wsetenvp**), ortam işleme yordamı.  
  
 Programınızı çağrılar yaparsa **_spawn** veya **_exec** C Çalışma Zamanı Kitaplığı'nda yordamları ailesi, size değil bastırmak ortam işleme yordamı geçirmek için bu yordamı kullanıldığından bir Yeni işlem ortamına spawning işlemi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)