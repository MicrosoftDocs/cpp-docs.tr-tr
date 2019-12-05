---
title: Derleyici Uyarısı (düzey 1) C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: a3f29cb895da8c06ed43dd5c9956426f3f6014f1
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810721"
---
# <a name="compiler-warning-level-1-c4910"></a>Derleyici Uyarısı (düzey 1) C4910

'\<tanımlayıcı > ': ' __declspec (dllexport) ' ve ' extern ' açık bir örnek oluşturmada uyumsuz

*\<tanımlayıcı >* adlı açık şablon örneği, hem `__declspec(dllexport)` hem de `extern` anahtar kelimeleri tarafından değiştirilir. Ancak, bu anahtar sözcükler birbirini dışlıyor. `__declspec(dllexport)` anahtar sözcüğü, şablon sınıfının örneğini oluşturma anlamına gelir, ancak `extern` anahtar sözcüğü şablon sınıfının otomatik olarak örneğini oluşturma anlamına gelir.

## <a name="see-also"></a>Ayrıca bkz.

[Açık Örnekleme](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Genel Kurallar ve Sınırlamalar](../../cpp/general-rules-and-limitations.md)