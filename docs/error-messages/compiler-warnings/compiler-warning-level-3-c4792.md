---
title: Derleyici Uyarısı (Düzey 3) C4792
ms.date: 11/04/2016
f1_keywords:
- C4792
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
ms.openlocfilehash: adf233673c4b654927aa9488565adf6ceef5d3e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50501198"
---
# <a name="compiler-warning-level-3-c4792"></a>Derleyici Uyarısı (Düzey 3) C4792

'function' işlevi sysimport kullanılarak bildirildi ve yerel koddan başvuruldu; bağlanmak için gerekli içeri aktarma kitaplığı

Yönetilmeyen bir işlevden programa DllImport ile içeri aktarılan yerel bir işlev çağrıldı. Bu nedenle, DLL için içeri aktarma kitaplığına bağlamanız gerekir.

Bu uyarı, kod içinde çözümlenemiyor veya değiştirerek derleyin. Kullanım [uyarı](../../preprocessor/warning.md) pragması, bu uyarıyı devre dışı bırakmak için.

Aşağıdaki örnek, C4792 oluşturur:

```
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