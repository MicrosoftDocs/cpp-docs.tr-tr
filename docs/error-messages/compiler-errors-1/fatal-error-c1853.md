---
title: Önemli hata C1853 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- devlang-cpp
ms.topic: error-reference
f1_keywords:
- C1853
dev_langs:
- C++
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 016e5bbf064643ddff0f63c5e16a967ed914f3e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044957"
---
# <a name="fatal-error-c1853"></a>Önemli hata C1853

> '*filename*' Ön derlenmiş üstbilgi dosyası derleyicinin önceki bir sürümünden olduğu veya önceden derlenmiş üstbilgi C++ ve c (veya tersi) kullanıyorsanız

Olası nedenler:

- Önceden derlenmiş üst bilgi, önceki bir derleyici sürümü ile derlendi. Geçerli derleme üstbilgiyle yeniden derlemeden deneyin.

- Önceden derlenmiş üstbilgi C++ ve c üstbilgi C ile kullanmak için aşağıdakilerden birini belirterek yeniden derlemeden deneyin kullanıyorsanız [/Tc](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçenekleri veya "c" soneki kaynak dosyasının değiştirme. Daha fazla bilgi için [kodu önceden derlemek için iki seçeneğiniz](../../build/reference/creating-precompiled-header-files.md#two-choices-for-precompiling-code).