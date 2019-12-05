---
title: C++ Komut Satırı İşlemini Özelleştirme
ms.date: 11/04/2016
f1_keywords:
- _setenvp
- _setargv
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
ms.openlocfilehash: 1541840521695658b5c4d809ba7e11767b1330a2
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857560"
---
# <a name="customizing-c-command-line-processing"></a>C++ Komut Satırı İşlemini Özelleştirme

**Microsoft 'a özgü**

Programınız komut satırı bağımsız değişkenleri içermiyorsa, komut satırı işlemeyi gerçekleştiren kitaplık yordamının kullanımını kaldırarak az miktarda alan kaydedebilirsiniz. Bu yordam `_setargv` olarak adlandırılır ve [joker karakter genişletmesi](../cpp/wildcard-expansion.md)bölümünde açıklanmıştır. Kullanımını bastırmak için `main` işlevini içeren dosyada hiçbir şey yapmaz ve `_setargv`adlandırın. `_setargv` çağrısı daha sonra `_setargv`tanımınız tarafından karşılanır ve kitaplık sürümü yüklenmez.

Benzer şekilde, ortam tablosuna hiçbir daha `envp` bağımsız değişkeni aracılığıyla erişemiyorsanız, ortam işleme yordamının `_setenvp`yerine, kendi boş bir yordamını sağlayabilirsiniz. `_setargv` işlevinde olduğu gibi, `_setenvp` **extern "C"** olarak bildirilmelidir.

Programınız, C çalışma zamanı kitaplığındaki `spawn` veya `exec` ailesinden bir yordam çağrısı yapabilir. Bu durumda, ortam işleme yordamını gizmemelisiniz, çünkü bu yordam bir ortamı üst işlemden alt işleme geçirmek için kullanılır.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[main: Program Başlatma](../cpp/main-program-startup.md)