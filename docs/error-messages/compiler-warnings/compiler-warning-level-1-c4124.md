---
title: Derleyici Uyarısı (düzey 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 04732619571420e777244b81bf4b93b775477a20
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62310987"
---
# <a name="compiler-warning-level-1-c4124"></a>Derleyici Uyarısı (düzey 1) C4124

yığın denetimi ile __fastcall yetersiz

`__fastcall` Anahtar sözcüğü, etkin yığın denetimi ile kullanıldı.

`__fastcall` Kuralı daha hızlı kod oluşturur, ancak yığın denetimi daha yavaş kod neden olur. Kullanırken `__fastcall`, yığın ile denetimini kapatır **check_stack** pragma veya /Gs.

Bu uyarı, yalnızca bu koşullar altında bildirilen ilk işlev için görüntülenir.