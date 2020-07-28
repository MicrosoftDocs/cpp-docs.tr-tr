---
title: Derleyici Uyarısı (düzey 1) C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: b17df9d7a9997e5d8ef37a4721de8693968cbbdf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214457"
---
# <a name="compiler-warning-level-1-c4910"></a>Derleyici Uyarısı (düzey 1) C4910

' \<identifier> ': ' __declspec (dllexport) ' ve ' extern ' açık bir örnek oluşturmada uyumsuz

Adlı açık şablon örneği oluşturma, *\<identifier>* hem hem de `__declspec(dllexport)` **`extern`** anahtar kelimeleri tarafından değiştirilir. Ancak, bu anahtar sözcükler birbirini dışlıyor. `__declspec(dllexport)`Anahtar sözcüğü, şablon sınıfının örneğini oluşturma anlamına gelir, ancak **`extern`** anahtar sözcüğü şablon sınıfının otomatik olarak örneğini oluşturma anlamına gelir.

## <a name="see-also"></a>Ayrıca bkz.

[Açık örnek oluşturma](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Genel kurallar ve sınırlamalar](../../cpp/general-rules-and-limitations.md)
