---
title: Derleyici Uyarısı (düzey 1) C4910 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e6db959e467ea449a66feb3ee07c202f4dee002
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018957"
---
# <a name="compiler-warning-level-1-c4910"></a>Derleyici Uyarısı (düzey 1) C4910

'\<tanımlayıcısı >': '__declspec(dllexport)' ve 'extern' açık bir örnek oluşturmada uyumsuz

Adlı açık şablon örneklemesi  *\<tanımlayıcısı >* her ikisi için de değiştirilmiş `__declspec(dllexport)` ve `extern` anahtar sözcükleri. Ancak, bu anahtar sözcükler birbirini dışlar. `__declspec(dllexport)` Anahtar sözcüğü, şablon sınıfının örneği anlamına gelir ancak `extern` anahtar sözcüğü anlamına gelir değil otomatik olarak örneğini bir şablon sınıfı.

## <a name="see-also"></a>Ayrıca Bkz.

[Açık Örnekleme](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Genel Kurallar ve Sınırlamalar](../../cpp/general-rules-and-limitations.md)