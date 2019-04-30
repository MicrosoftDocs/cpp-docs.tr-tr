---
title: Derleyici Uyarısı (Düzey 3) C4792
ms.date: 11/04/2016
f1_keywords:
- C4792
helpviewer_keywords:
- C4792
ms.assetid: c047ce69-a622-44e1-9425-d41aa9261c61
ms.openlocfilehash: adf233673c4b654927aa9488565adf6ceef5d3e2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401572"
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