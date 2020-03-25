---
title: Derleyici Uyarısı (düzey 1) C4399
ms.date: 11/04/2016
f1_keywords:
- C4399
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
ms.openlocfilehash: a556fbffad41d04b3eb0ea1acfd5e8739ddd5b68
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186809"
---
# <a name="compiler-warning-level-1-c4399"></a>Derleyici Uyarısı (düzey 1) C4399

> '*symbol*':/clr: Pure ile derlendiğinde işlem başına sembol __declspec (dllimport) ile işaretlenmemelidir

## <a name="remarks"></a>Açıklamalar

**/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

Yerel bir görüntüden veya yerel ve CLR yapılarına sahip bir görüntüden alınan veriler, saf bir görüntüye aktarılamaz. Bu uyarıyı çözmek için **/clr** ( **/clr: Pure**) ile derleyin veya `__declspec(dllimport)`silin.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4399 oluşturur.

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```
