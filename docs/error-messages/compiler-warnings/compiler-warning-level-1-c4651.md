---
title: Derleyici Uyarısı (düzey 1) C4651 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4651
dev_langs:
- C++
helpviewer_keywords:
- C4651
ms.assetid: f1ea82aa-4dc1-4972-b55a-57fdb962f0dd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b516ef86372901d00dd20d94ed10d5e361bbab8d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099479"
---
# <a name="compiler-warning-level-1-c4651"></a>Derleyici Uyarısı (düzey 1) C4651

'Ön derlenmiş üstbilgi için geçerli derleme ancak belirtilen tanım'

Ön derlenmiş üstbilgi oluşturulduğunda, ancak bu derleme tanımı belirtilmedi.

Tanımı içinde önceden derlenmiş üst bilgi, ancak kodun geri kalanını uygulanmaz.

Önceden derlenmiş üstbilgi /DSYMBOL ile oluşturulduysa, derleyici /Yu derleme /DSYMBOL sahip değilse bu uyarı oluşturur.  /Yu komut satırına /DSYMBOL ekleme, bu uyarıyı çözümler.