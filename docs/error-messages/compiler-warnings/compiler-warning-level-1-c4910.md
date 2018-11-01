---
title: Derleyici Uyarısı (düzey 1) C4910
ms.date: 11/04/2016
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: f0d1df0a383b6646d52fc2babc53ca656d49ace6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428203"
---
# <a name="compiler-warning-level-1-c4910"></a>Derleyici Uyarısı (düzey 1) C4910

'\<tanımlayıcısı >': '__declspec(dllexport)' ve 'extern' açık bir örnek oluşturmada uyumsuz

Adlı açık şablon örneklemesi  *\<tanımlayıcısı >* her ikisi için de değiştirilmiş `__declspec(dllexport)` ve `extern` anahtar sözcükleri. Ancak, bu anahtar sözcükler birbirini dışlar. `__declspec(dllexport)` Anahtar sözcüğü, şablon sınıfının örneği anlamına gelir ancak `extern` anahtar sözcüğü anlamına gelir değil otomatik olarak örneğini bir şablon sınıfı.

## <a name="see-also"></a>Ayrıca Bkz.

[Açık Örnekleme](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Genel Kurallar ve Sınırlamalar](../../cpp/general-rules-and-limitations.md)