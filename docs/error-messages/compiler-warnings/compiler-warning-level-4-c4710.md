---
title: Derleyici Uyarısı (düzey 4) C4710 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4710
dev_langs:
- C++
helpviewer_keywords:
- C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1f6de17f7005db3834bfcfc93aff03f12f0293ce
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046101"
---
# <a name="compiler-warning-level-4-c4710"></a>Derleyici Uyarısı (düzey 4) C4710

'function': işlev alınmadı

Verilen işlevin satır içi genişletme için seçildi, ancak derleyicinin kullanılmayacak satır içi kullanım.

Satır içi kullanım derleyicinin denetiminde gerçekleştirilir. **Satır içi** anahtar sözcüğü gibi **kaydetme** için derleyicinin anahtar sözcüğü, bir ipucu olarak kullanılır. Derleyici, kod hızı için derleme yaparken hızlandırmak için belirli bir işlevi satır içi gerekir veya kod yazabileceğiniz derlenirken küçültmek için belirli bir işlevi satır içi gerektiğini belirlemek için buluşsal yöntemler kullanır. Derleyici olur yalnızca satır içi çok küçük işlevler için alan derlenirken.

Bazı durumlarda, derleyicinin olur satır belirli bir işlev mekanik nedenleri. Bkz: [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) nedenleri olabilir değil bir işlevi satır içi derleyici listesi.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.