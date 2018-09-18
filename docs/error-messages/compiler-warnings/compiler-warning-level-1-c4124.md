---
title: Derleyici Uyarısı (düzey 1) C4124 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4124
dev_langs:
- C++
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a69190487c22987ead2d00ec102785ed42ea93c4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090938"
---
# <a name="compiler-warning-level-1-c4124"></a>Derleyici Uyarısı (düzey 1) C4124

yığın denetimi ile __fastcall yetersiz

`__fastcall` Anahtar sözcüğü, etkin yığın denetimi ile kullanıldı.

`__fastcall` Kuralı daha hızlı kod oluşturur, ancak yığın denetimi daha yavaş kod neden olur. Kullanırken `__fastcall`, yığın ile denetimini kapatır **check_stack** pragma veya /Gs.

Bu uyarı, yalnızca bu koşullar altında bildirilen ilk işlev için görüntülenir.