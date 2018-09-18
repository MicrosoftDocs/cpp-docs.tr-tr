---
title: Önemli hata C1047 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1047
dev_langs:
- C++
helpviewer_keywords:
- C1047
ms.assetid: e1bbbc6b-a5bc-4c23-8203-488120a0ec78
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1983fa0a18667d98f84dfe5049afd4e872d87d93
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021596"
---
# <a name="fatal-error-c1047"></a>Önemli hata C1047

'Dosya' nesne veya kitaplık dosyası diğer nesnelerden daha eski bir derleyici ile oluşturulmuş; eski nesneleri ve kitaplıkları yeniden oluşturun

Nesne dosyalarında veya kitaplıklarındaki ile yapılandırıldığında C1047 neden **/LTCG** birlikte, ancak bu nesne dosyalarında veya kitaplıklarındaki Visual C++ araç takımı farklı sürümleriyle burada yerleşik bağlanır.

Yeni bir derleyici sürümü kullanmaya başlamak, ancak varolan nesne dosyalarında veya kitaplıklarındaki temiz yeniden yapmayın bu durum oluşabilir.

C1047 çözmek için tüm nesne dosyalarında veya kitaplıklarındaki yeniden oluşturun.