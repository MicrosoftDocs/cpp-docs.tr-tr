---
title: Derleyici Uyarısı (düzey 4) C4710
ms.date: 11/04/2016
f1_keywords:
- C4710
helpviewer_keywords:
- C4710
ms.assetid: 76381ec7-3fc1-4bee-9a0a-c2c8307b92e2
ms.openlocfilehash: c39848b9b3e94e35c4d0c0937a0974b717c6bd8d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198182"
---
# <a name="compiler-warning-level-4-c4710"></a>Derleyici Uyarısı (düzey 4) C4710

' function ': işlev satır içine alınmadı

Verilen işlev satır içi genişletme için seçildi, ancak derleyici satır içinde gerçekleştirmedi.

İç hat kullanımı derleyicinin kararına göre yapılır. **Register** anahtar sözcüğü gibi **satır içi** anahtar sözcük, derleyici için bir ipucu olarak kullanılır. Derleyici, hız için derleme yaparken kodun hızlandırılmasına veya belirli bir işlevin boş alana göre daha küçük olmasını sağlamak için belirli bir işlevi satır içi olarak kullanıp kullanmadığını anlamak için buluşsal yöntemler kullanır. Derleyici, alan için derleme yaparken yalnızca satır içi çok küçük işlevlere sahip olur.

Bazı durumlarda, derleyici, mekanik nedenlerle belirli bir işlevi satır içi olarak içermez. Derleyicinin bir işlevi satır içi olarak görmemesinin nedenleri listesi için bkz. [C4714](../../error-messages/compiler-warnings/compiler-warning-level-4-c4714.md) .

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .
