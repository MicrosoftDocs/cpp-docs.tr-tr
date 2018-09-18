---
title: Derleyici Uyarısı C4746 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
dev_langs:
- C++
ms.assetid: 5e79ab46-6031-499a-a986-716c866b6c0e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5e6abce7ebbcdc41effed05ccf54337e3976c34e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46054876"
---
# <a name="compiler-warning-c4746"></a>Derleyici Uyarısı C4746

Geçici Erişim '\<ifadesi >' / volatile tabi olduğu: [ISO&#124;ms] ayarlama; iç işlevleri __iso_volatile_load depolama kullanmayı düşünün.

Geçici bir değişkene doğrudan erişildiğinde C4746 yayılır. Şu anda belirtilen belirli geçici modeli tarafından etkilenen kod konumlarını tanımlamak geliştiricilerin yardımcı olmak için tasarlanmıştır (hangi denetlenebilir ile [/volatile](../../build/reference/volatile-volatile-keyword-interpretation.md) derleyici seçeneği). Özellikle, derleyicinin ürettiği donanım belleği engelleri bulma /volatile:ms kullanıldığında yararlı olabilir.

Depolama __iso_volatile_load yapı içlerini açıkça geçici modeli tarafından etkilenmeden geçici bir bellek erişmek için kullanılabilir. Bu iç kullanarak C4746 tetiklemez.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.