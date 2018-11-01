---
title: Derleyici Uyarısı C4959
ms.date: 11/04/2016
f1_keywords:
- C4959
helpviewer_keywords:
- C4959
ms.assetid: 3a128f3e-4d8a-4565-ba1a-5d32fdeb5982
ms.openlocfilehash: 646347dec7bc2bac7fa73c8f754d2f9549cb2ba6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50473664"
---
# <a name="compiler-warning-c4959"></a>Derleyici Uyarısı C4959

> Yönetilmeyen yapı tanımlayamazsınız '*türü*' / CLR: safe, üyelerine erişilmesi doğrulanamayan bir koda neden olduğu

## <a name="remarks"></a>Açıklamalar

Yönetilmeyen bir türün bir üyeye erişilmesi doğrulanamayan (peverify.exe) görüntü oluşturur.

Daha fazla bilgi için [saf ve doğrulanabilen kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).

**/CLR: safe** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Bu uyarı hata olarak verilir ve ile devre dışı bırakılabilir [uyarı](../../preprocessor/warning.md) pragma veya [/wd](../../build/reference/compiler-option-warning-level.md) derleyici seçeneği.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4959 oluşturur:

```cpp
// C4959.cpp
// compile with: /clr:safe

// Uncomment the following line to resolve.
// #pragma warning( disable : 4959 )
struct X {
   int data;
};

int main() {
   X x;
   x.data = 10;   // C4959
}
```