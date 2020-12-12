---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4399'
title: Derleyici Uyarısı (düzey 1) C4399
ms.date: 11/04/2016
f1_keywords:
- C4399
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
ms.openlocfilehash: a1d0fab62d13c08fb2117279d9173786c65d846f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97311142"
---
# <a name="compiler-warning-level-1-c4399"></a>Derleyici Uyarısı (düzey 1) C4399

> '*symbol*':/clr: Pure ile derlendiğinde işlem başına sembol __declspec (dllimport) ile işaretlenmemelidir

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

Yerel bir görüntüden veya yerel ve CLR yapılarına sahip bir görüntüden alınan veriler, saf bir görüntüye aktarılamaz. Bu uyarıyı çözmek için **/clr** ( **/clr: Pure**) veya delete ile derleyin `__declspec(dllimport)` .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4399 oluşturur.

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```
