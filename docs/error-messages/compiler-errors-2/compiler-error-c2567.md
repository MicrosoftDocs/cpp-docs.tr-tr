---
title: Derleyici Hatası C2567 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2567
dev_langs:
- C++
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb09aacc1b81e9f0e0c9c96a496eccc89a061f37
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104251"
---
# <a name="compiler-error-c2567"></a>Derleyici Hatası C2567

'dosya' meta veriler açılamadı, dosya taşınmış veya silinmiş

Başvurulan kaynakta bir meta veri dosyası (ile `#using`) derleyici ön ucu işlemiyle haliyle aynı dizinde derleyici arka uç işlemi tarafından bulunamadı. Bkz: [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md) daha fazla bilgi için.

C2567 bunun ile derleme yaparsanız **/c** bir makine ve ardından başka bir makineye bir bağlantı zamanı kod oluşturmayı deneyin. Daha fazla bilgi için [/LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)).

Ayrıca, bilgisayarınıza daha fazla bellek olduğunu gösterebilir.

Bu hatayı düzeltmek için meta veri dosyası yapı işleminin tüm aşamalar için aynı dizin konumda olduğundan emin olun.