---
title: Derleyici Uyarısı (Düzey 2 ve 3) C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: 99b78e1426cf1618e68ae74ae7e16dd0f08606ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62359975"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Derleyici Uyarısı (Düzey 2 ve 3) C4008

'identifier': 'öznitelik' özniteliği yoksayıldı

Derleyicinin göz ardı `__fastcall`, **statik**, veya **satır içi** işlevi (uyarı Düzey 3) veya veri (uyarı Düzey 2) için özniteliği.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. `__fastcall` verilerle özniteliği.

1. **statik** veya **satır içi** özniteliğini **ana** işlevi.