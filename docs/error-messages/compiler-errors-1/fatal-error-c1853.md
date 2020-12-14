---
description: 'Daha fazla bilgi edinin: önemli hata C1853'
title: Önemli Hata C1853
ms.date: 11/04/2016
f1_keywords:
- C1853
helpviewer_keywords:
- C1853
ms.assetid: ceb9b4a5-92bf-4573-8a9f-3109cc7743ce
ms.openlocfilehash: 60c8e254e9bd36f52bddb4d6dce56c987b6c31e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276237"
---
# <a name="fatal-error-c1853"></a>Önemli Hata C1853

> '*filename*' ön derlenmiş üstbilgi dosyası derleyicinin önceki bir sürümünden veya ön derlenmiş üstbilgi C++ ve bunu C 'den kullanıyorsunuz (veya tersi)

Olası nedenler:

- Ön derlenmiş üstbilgi önceki bir derleyici sürümü ile derlendi. Üstbilgiyi geçerli derleyiciyle yeniden derleme yapmayı deneyin.

- Ön derlenmiş üstbilgi C++ ve bunu C 'den kullanıyorsunuz. [/TC](../../build/reference/tc-tp-tc-tp-specify-source-file-type.md) derleyici seçeneklerinden birini belirterek veya kaynak dosyanın sonekini "C" olarak değiştirerek c ile kullanmak üzere üstbilgiyi yeniden yeniden derleyerek deneyin. Daha fazla bilgi için bkz. [önceden derleme kodu Için Iki seçenek](../../build/creating-precompiled-header-files.md#two-choices-for-precompiling-code).
