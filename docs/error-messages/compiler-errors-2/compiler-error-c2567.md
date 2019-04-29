---
title: Derleyici Hatası C2567
ms.date: 11/04/2016
f1_keywords:
- C2567
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
ms.openlocfilehash: eec529f43e23810843651888ef5722c5d0a0b2c9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366361"
---
# <a name="compiler-error-c2567"></a>Derleyici Hatası C2567

'dosya' meta veriler açılamadı, dosya taşınmış veya silinmiş

Başvurulan kaynakta bir meta veri dosyası (ile `#using`) derleyici ön ucu işlemiyle haliyle aynı dizinde derleyici arka uç işlemi tarafından bulunamadı. Bkz: [#using yönergesi](../../preprocessor/hash-using-directive-cpp.md) daha fazla bilgi için.

C2567 bunun ile derleme yaparsanız **/c** bir makine ve ardından başka bir makineye bir bağlantı zamanı kod oluşturmayı deneyin. Daha fazla bilgi için [/LTCG (bağlama zamanı kodu oluşturma)](../../build/reference/ltcg-link-time-code-generation.md)).

Ayrıca, bilgisayarınıza daha fazla bellek olduğunu gösterebilir.

Bu hatayı düzeltmek için meta veri dosyası yapı işleminin tüm aşamalar için aynı dizin konumda olduğundan emin olun.