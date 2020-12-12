---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4792'
title: Derleyici Uyarısı (düzey 3) C4792
ms.date: 11/04/2016
f1_keywords:
- C4792
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
ms.openlocfilehash: 37dc805477e3150eedaffe7eb5d900b7903b1d48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332128"
---
# <a name="compiler-warning-level-3-c4792"></a>Derleyici Uyarısı (düzey 3) C4792

' function ' işlevi, SysImport kullanılarak bildirilmiştir ve yerel koddan başvuruluyor; bağlantı için içeri aktarma kitaplığı gerekiyor

Yönetilmeyen bir işlevden DllImport ile programa aktarılmış yerel bir işlev çağrıldı. Bu nedenle, DLL için içeri aktarma kitaplığına bağlantı oluşturmanız gerekir.

Bu uyarı, kod içinde veya derleyebileceğiniz şekilde değiştirilerek çözümlenemez. Bu uyarıyı devre dışı bırakmak için [Uyarı](../../preprocessor/warning.md) pragmasını kullanın.

Aşağıdaki örnek C4792 oluşturur:

```cpp
// C4792.cpp
// compile with: /clr /W3
// C4792 expected
using namespace System::Runtime::InteropServices;
[DllImport("msvcrt")]
extern "C" int __cdecl puts(const char *);
int main() {}

// Uncomment the following line to resolve.
// #pragma warning(disable : 4792)
#pragma unmanaged
void func(void){
   puts("test");
}
```
