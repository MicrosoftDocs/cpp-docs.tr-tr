---
title: Çağırma kuralları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- calling conventions
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e9e65dfd7f7cff25debd8eb0d00a7e3bb0397692
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="calling-conventions"></a>Çağırma Kuralları
Visual C/C++ derleyicisi, iç ve dış işlevleri çağırmak için birkaç farklı kural sağlar. Bu farklı yaklaşımların anlaşılması, programınızdaki hataları ayıklamanıza ve kodunuzu derleme dili yordamlarına bağlamanıza yardımcı olur.  
  
 Bu bölümdeki konular, çağırma kuralları arasındaki farkları, bağımsız değişkenlerin nasıl geçirildiğini ve değerlerin işlevler tarafından nasıl döndürüldüğünü açıklamaktadır. Bunlar, kendi giriş ve sonuç kodunuzu yazmanızı sağlayan gelişmiş bir işlev olan çıplak işlev çağrılarını da açıklamaktadır.  
  
 Çağırma kuralları için x64 hakkında bilgi için bkz: işlemciler, [arama kuralı](../build/calling-convention.md).  
  
## <a name="topics-in-this-section"></a>Bu bölümdeki konular  
  
-   [Bağımsız değişken geçirme ve adlandırma kuralları](../cpp/argument-passing-and-naming-conventions.md) (`__cdecl`, `__stdcall`, `__fastcall`ve diğerleri)  
  
-   [Çağırma Örneği: İşlev Prototipi ve Çağrı](../cpp/calling-example-function-prototype-and-call.md)  
  
-   [Çıplak işlev çağrıları özel giriş ve bitiş kodu yazmak için kullanma](../cpp/naked-function-calls.md)  
  
-   [Kayan Nokta Eşişlemcisi ve Çağırma Kuralları](../cpp/floating-point-coprocessor-and-calling-conventions.md)  
  
-   [Kullanılmayan çağırma kuralları](../cpp/obsolete-calling-conventions.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Microsoft'a Özel Değiştiriciler](../cpp/microsoft-specific-modifiers.md)