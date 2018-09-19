---
title: Derleyici Uyarısı (Düzey 3) C4192 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4192
dev_langs:
- C++
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 671a8c83dcadcaa89372e53b6c3d677c5810b4a5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114416"
---
# <a name="compiler-warning-level-3-c4192"></a>Derleyici Uyarısı (Düzey 3) C4192

otomatik olarak 'library' tür kitaplığı içeri aktarılırken 'name' hariç

A `#import` kitaplığı içeren bir öğe *adı*, yani de Win32 sistem üstbilgisinde tanımlanır. Tür kitaplıkları sınırlamaları nedeniyle, gibi adlar **IUnknown** veya GUID genellikle tanımlanmış bir tür kitaplığı sistem üstbilgileri tanımından çoğaltma. `#import` Bu öğeleri algılar ve bunları .tlh ve .tli üst bilgi dosyalarını birleştirmek reddeder.

Bu davranışı geçersiz kılmak için kullanın `#import` öznitelikleri [no_auto_exclude](../../preprocessor/no-auto-exclude.md) ve [include()](../../preprocessor/include-parens.md).