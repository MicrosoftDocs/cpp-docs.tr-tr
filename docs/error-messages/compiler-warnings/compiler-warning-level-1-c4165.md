---
title: Derleyici Uyarısı (düzey 1) C4165
ms.date: 11/04/2016
f1_keywords:
- C4165
helpviewer_keywords:
- C4165
ms.assetid: f5bed515-2290-4f88-8dab-b45d95fe26ef
ms.openlocfilehash: bb036f7672a074e859d3e19083e256bd80c93578
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80176110"
---
# <a name="compiler-warning-level-1-c4165"></a>Derleyici Uyarısı (düzey 1) C4165

' HRESULT ' ' bool ' olarak dönüştürülüyor; Bunun istediğiniz durum olduğundan emin misiniz?

Bir [if](../../cpp/if-else-statement-cpp.md) ifadesinde HRESULT kullanırken, DEĞIŞKENI bir hresult olarak açıkça test ETMEDIĞINIZ sürece HRESULT [bool](../../cpp/bool-cpp.md) değerine dönüştürülür. Bu uyarı varsayılan olarak kapalıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4165 oluşturur

```cpp
// C4165.cpp
// compile with: /W1
#include <windows.h>
#pragma warning(1:4165)

extern HRESULT hr;
int main() {
   if (hr) {
   // try either of the following ...
   // if (FAILED(hr)) { // C4165 expected
   // if (hr != S_OK) {
   }
}
```
