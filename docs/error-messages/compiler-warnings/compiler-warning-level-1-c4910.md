---
title: Derleyici Uyarısı (düzey 1) C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: dc5feb3613e45134a08e493b397eb738fffee8a9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174784"
---
# <a name="compiler-warning-level-1-c4910"></a>Derleyici Uyarısı (düzey 1) C4910

'\<tanımlayıcı > ': ' __declspec (dllexport) ' ve ' extern ' açık bir örnek oluşturmada uyumsuz

*\<tanımlayıcı >* adlı açık şablon örneği, hem `__declspec(dllexport)` hem de `extern` anahtar kelimeleri tarafından değiştirilir. Ancak, bu anahtar sözcükler birbirini dışlıyor. `__declspec(dllexport)` anahtar sözcüğü, şablon sınıfının örneğini oluşturma anlamına gelir, ancak `extern` anahtar sözcüğü şablon sınıfının otomatik olarak örneğini oluşturma anlamına gelir.

## <a name="see-also"></a>Ayrıca bkz.

[Açık Örnekleme](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Genel Kurallar ve Sınırlamalar](../../cpp/general-rules-and-limitations.md)
