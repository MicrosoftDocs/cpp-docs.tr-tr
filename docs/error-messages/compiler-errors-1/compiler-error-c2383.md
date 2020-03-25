---
title: Derleyici hatası C2383
ms.date: 11/04/2016
f1_keywords:
- C2383
helpviewer_keywords:
- C2383
ms.assetid: 6696221d-879c-477a-a0f3-a6edc15fd3d7
ms.openlocfilehash: 2aa922ebeadb374a7eac73a0f452376472b00984
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206034"
---
# <a name="compiler-error-c2383"></a>Derleyici hatası C2383

'*symbol*': Bu sembolde varsayılan bağımsız değişkenlere izin verilmiyor

Derleyici C++ , işlevlere yönelik işaretçilerde varsayılan bağımsız değişkenlere izin vermez.

Bu kod, Visual Studio 2005 ' C++ den önceki sürümlerde Microsoft derleyicisi tarafından kabul edildi, ancak şimdi bir hata veriyor. Tüm görsellerde C++çalışır olan kod için, bir işaretçiden işleve bağımsız değişkenine varsayılan değer atamayın.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2383 oluşturur ve olası bir çözümü gösterir:

```cpp
// C2383.cpp
// compile with: /c
void (*pf)(int = 0);   // C2383
void (*pf)(int);   // OK
```
