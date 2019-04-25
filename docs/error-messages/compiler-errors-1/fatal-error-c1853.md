---
title: Önemli hata C1853
ms.date: 11/04/2016
f1_keywords:
- C1853
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
ms.openlocfilehash: ec2d6bf6bac46cca8bdc2e3b8fe7cc6b7799d78a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62165924"
---
# <a name="fatal-error-c1853"></a>Önemli hata C1853

> '*filename*' Ön derlenmiş üstbilgi dosyası derleyicinin önceki bir sürümünden olduğu veya önceden derlenmiş üstbilgi C++ ve c (veya tersi) kullanıyorsanız

Olası nedenler:

- Önceden derlenmiş üst bilgi, önceki bir derleyici sürümü ile derlendi. Geçerli derleme üstbilgiyle yeniden derlemeden deneyin.

- Önceden derlenmiş üstbilgi C++ ve c üstbilgi C ile kullanmak için aşağıdakilerden birini belirterek yeniden derlemeden deneyin kullanıyorsanız [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçenekleri veya "c" soneki kaynak dosyasının değiştirme. Daha fazla bilgi için [kodu önceden derlemek için iki seçeneğiniz](../../build/creating-precompiled-header-files.md#two-choices-for-precompiling-code).