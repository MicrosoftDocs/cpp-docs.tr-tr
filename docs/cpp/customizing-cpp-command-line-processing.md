---
title: "C++ komut satırı işlemini özelleştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 396f2a314c185f39593c92745346f988d666980f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="customizing-c-command-line-processing"></a>C++ Komut Satırı İşlemini Özelleştirme
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Programınızı komut satırı bağımsız değişken almaz, komut satırı işlemini gerçekleştiren kitaplık yordamı kullanımını gizleme tarafından az miktarda alan kaydedebilirsiniz. Bu yordam adlı **_setargv** ve açıklanan [joker karakter genişletmesi](../cpp/wildcard-expansion.md). Kullanımını engellemek için dosyayı içeren içinde hiçbir şey yapmaz bir yordamı tanımlayın **ana** işlev ve adlandırın **_setargv**. Çağrı **_setargv** sonra tanımınızı tarafından sağlanıyorsa **_setargv**, ve kitaplığı sürümü yüklenmedi.  
  
 Benzer şekilde, ortam tabloda hiç erişirseniz `envp` bağımsız değişkeni, yerine kullanılacak kendi boş yordamı sağlayabilir **_setenvp**, ortam işleme yordamı. İle olarak yalnızca **_setargv** işlevi, **_setenvp** olarak bildirilmelidir **extern "C"**.  
  
 Programınızı çağrıları yapabileceğiniz **spawn** veya `exec` C Çalışma Zamanı Kitaplığı'nda yordamları ailesi. Bu durumda, bu yordam bir ortamda üst işleminden alt sürecine iletmek için kullanıldığından, ortam işleme yordamı engelleme.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [main: Program Başlatma](../cpp/main-program-startup.md)