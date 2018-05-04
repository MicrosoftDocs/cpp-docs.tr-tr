---
title: C++ komut satırı işlemini özelleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _setenvp
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- command line [C++], processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line [C++], processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e2691ba3b83cd536c6f0a152bf4de2a855f81e0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="customizing-c-command-line-processing"></a>C++ Komut Satırı İşlemini Özelleştirme
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Programınızı komut satırı bağımsız değişken almaz, komut satırı işlemini gerçekleştiren kitaplık yordamı kullanımını gizleme tarafından az miktarda alan kaydedebilirsiniz. Bu yordam adlı **_setargv** ve açıklanan [joker karakter genişletmesi](../cpp/wildcard-expansion.md). Kullanımını engellemek için dosyayı içeren içinde hiçbir şey yapmaz bir yordamı tanımlayın **ana** işlev ve adlandırın **_setargv**. Çağrı **_setargv** sonra tanımınızı tarafından sağlanıyorsa **_setargv**, ve kitaplığı sürümü yüklenmedi.  
  
 Benzer şekilde, ortam tabloda hiç erişirseniz `envp` bağımsız değişkeni, yerine kullanılacak kendi boş yordamı sağlayabilir **_setenvp**, ortam işleme yordamı. İle olarak yalnızca **_setargv** işlevi, **_setenvp** olarak bildirilmelidir **extern "C"**.  
  
 Programınızı çağrıları yapabileceğiniz **spawn** veya `exec` C Çalışma Zamanı Kitaplığı'nda yordamları ailesi. Bu durumda, bu yordam bir ortamda üst işleminden alt sürecine iletmek için kullanıldığından, ortam işleme yordamı engelleme.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [main: Program Başlatma](../cpp/main-program-startup.md)