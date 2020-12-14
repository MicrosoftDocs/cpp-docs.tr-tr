---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 2 ve 3) C4008'
title: Derleyici Uyarısı (düzey 2 ve 3) C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: 6f13ef60efabeaffe549189431aa04c65a12cbe5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234429"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Derleyici Uyarısı (düzey 2 ve 3) C4008

' Identifier ': ' Attribute ' özniteliği yoksayıldı

Derleyici **`__fastcall`** , **`static`** **`inline`** bir işlev (düzey 3 uyarısı) veya veri (düzey 2 uyarısı) için, veya özniteliğini yok sayıldı.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. **`__fastcall`** verileri olan öznitelik.

1. **`static`** ya da **`inline`** **Main** işlevi olan özniteliği.
