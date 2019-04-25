---
title: Derleyici Uyarısı (düzey 1) C4109
ms.date: 11/04/2016
f1_keywords:
- C4109
helpviewer_keywords:
- C4109
ms.assetid: 9e8d95c6-e05d-47e0-bd87-78974b3cc06c
ms.openlocfilehash: 1156bbfbed7aed9524b24b046b9ce9acdbdc8b8a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62300212"
---
# <a name="compiler-warning-level-1-c4109"></a>Derleyici Uyarısı (düzey 1) C4109

Beklenmeyen tanımlayıcı 'identifier'

Beklenmeyen tanımlayıcı içeren pragma yoksayıldı.

## <a name="example"></a>Örnek

```
// C4109.cpp
// compile with: /W1 /LD
#pragma init_seg( abc ) // C4109
```