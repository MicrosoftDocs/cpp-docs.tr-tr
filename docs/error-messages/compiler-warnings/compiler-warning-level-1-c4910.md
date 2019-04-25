---
title: Derleyici Uyarısı (düzey 1) C4910
ms.date: 11/04/2016
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: 49cbbf3369fc4765d93e67e2dca84a4d975560d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242896"
---
# <a name="compiler-warning-level-1-c4910"></a>Derleyici Uyarısı (düzey 1) C4910

'\<tanımlayıcısı >': '__declspec(dllexport)' ve 'extern' açık bir örnek oluşturmada uyumsuz

Adlı açık şablon örneklemesi  *\<tanımlayıcısı >* her ikisi için de değiştirilmiş `__declspec(dllexport)` ve `extern` anahtar sözcükleri. Ancak, bu anahtar sözcükler birbirini dışlar. `__declspec(dllexport)` Anahtar sözcüğü, şablon sınıfının örneği anlamına gelir ancak `extern` anahtar sözcüğü anlamına gelir değil otomatik olarak örneğini bir şablon sınıfı.

## <a name="see-also"></a>Ayrıca bkz.

[Açık Örnekleme](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Genel Kurallar ve Sınırlamalar](../../cpp/general-rules-and-limitations.md)