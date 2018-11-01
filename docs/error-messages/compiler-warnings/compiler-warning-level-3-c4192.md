---
title: Derleyici Uyarısı (Düzey 3) C4192
ms.date: 11/04/2016
f1_keywords:
- C4192
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
ms.openlocfilehash: 56b27596296b87edcc6de406e7b6621d5723815d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519723"
---
# <a name="compiler-warning-level-3-c4192"></a>Derleyici Uyarısı (Düzey 3) C4192

otomatik olarak 'library' tür kitaplığı içeri aktarılırken 'name' hariç

A `#import` kitaplığı içeren bir öğe *adı*, yani de Win32 sistem üstbilgisinde tanımlanır. Tür kitaplıkları sınırlamaları nedeniyle, gibi adlar **IUnknown** veya GUID genellikle tanımlanmış bir tür kitaplığı sistem üstbilgileri tanımından çoğaltma. `#import` Bu öğeleri algılar ve bunları .tlh ve .tli üst bilgi dosyalarını birleştirmek reddeder.

Bu davranışı geçersiz kılmak için kullanın `#import` öznitelikleri [no_auto_exclude](../../preprocessor/no-auto-exclude.md) ve [include()](../../preprocessor/include-parens.md).