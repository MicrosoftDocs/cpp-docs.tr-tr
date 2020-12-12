---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4910'
title: Derleyici Uyarısı (düzey 1) C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: 4798ba8ae8005239c9cf83e109bdb0f9e4c01928
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291460"
---
# <a name="compiler-warning-level-1-c4910"></a>Derleyici Uyarısı (düzey 1) C4910

' \<identifier> ': ' __declspec (dllexport) ' ve ' extern ' açık bir örnek oluşturmada uyumsuz

Adlı açık şablon örneği oluşturma, *\<identifier>* hem hem de `__declspec(dllexport)` **`extern`** anahtar kelimeleri tarafından değiştirilir. Ancak, bu anahtar sözcükler birbirini dışlıyor. `__declspec(dllexport)`Anahtar sözcüğü, şablon sınıfının örneğini oluşturma anlamına gelir, ancak **`extern`** anahtar sözcüğü şablon sınıfının otomatik olarak örneğini oluşturma anlamına gelir.

## <a name="see-also"></a>Ayrıca bkz.

[Açık örnek oluşturma](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Genel kurallar ve sınırlamalar](../../cpp/general-rules-and-limitations.md)
