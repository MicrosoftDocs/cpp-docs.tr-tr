---
title: C Komut Satırı İşlemini Özelleştirme
ms.date: 11/04/2016
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
ms.openlocfilehash: 1abdb0c104755efc86543ac4773359078e855999
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62290696"
---
# <a name="customizing-c-command-line-processing"></a>C Komut Satırı İşlemini Özelleştirme

Programınız komut satırı bağımsız değişkenleri içermiyorsa, komut satırı işlemeyi gerçekleştiren kitaplık yordamının kullanımını kaldırarak az miktarda alan kaydedebilirsiniz. Bu yordam, [joker karakter bağımsız değişkenlerini genişletme](../c-language/expanding-wildcard-arguments.md)bölümünde açıklandığı gibi **_setargv** (veya geniş karakterli ortamda **_wsetargv** ) olarak adlandırılır. Kullanımını bastırmak için, **ana** işlevi içeren dosyada hiçbir şey yapmaz ve **_setargv** (veya geniş karakter ortamında **_wsetargv** ) adını belirleyin. **_Setargv** veya **_wsetargv** çağrısı daha sonra **_setargv** veya **_wsetargv** tanımınız tarafından karşılanır ve kitaplık sürümü yüklenmez.

Benzer şekilde, ortam tablosuna hiçbir daha `envp` bağımsız değişken aracılığıyla erişemiyorsanız, ortam işleme yordamının **_setenvp** (veya **_wsetenvp**) yerine kendi boş bir yordamını sağlayabilirsiniz.

Programınız, C çalışma zamanı kitaplığındaki **_spawn** veya **_exec** aile ailesine çağrılar yapıyorsa, bu yordam, bir ortamı oluşturma işleminden yeni işleme geçirmek için kullanıldığından, ortam işleme yordamını gizmemelisiniz.

## <a name="see-also"></a>Ayrıca bkz.

[main İşlevi ve Program Yürütme](../c-language/main-function-and-program-execution.md)
