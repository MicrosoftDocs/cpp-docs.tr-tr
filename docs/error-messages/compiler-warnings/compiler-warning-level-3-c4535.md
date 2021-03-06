---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4535'
title: Derleyici Uyarısı (düzey 3) C4535
ms.date: 11/04/2016
f1_keywords:
- C4535
helpviewer_keywords:
- C4535
ms.assetid: 2c5ad1aa-2558-41d1-8f06-47fef74c8d9b
ms.openlocfilehash: 89c93088ee4f2b5a8dedb760d937083fe9121706
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97257881"
---
# <a name="compiler-warning-level-3-c4535"></a>Derleyici Uyarısı (düzey 3) C4535

_set_se_translator () çağrılırken/EHa gerekir

[_Set_se_translator](../../c-runtime-library/reference/set-se-translator.md) kullanımı, [/EHa](../../build/reference/eh-exception-handling-model.md) derleyici seçeneğini gerektiriyor ve **/EHS** değil.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4535 oluşturur.

```cpp
// C4535.cpp
// compile with: /W3 /EHsc /c
// C4535 expected
// to fix, compile with /EHa instead
#include <stdio.h>
#include <windows.h>
#include <eh.h>

void SEFunc();
void trans_func( unsigned int, EXCEPTION_POINTERS* );

class SE_Exception {
private:
   unsigned int nSE;
public:
   SE_Exception() {}
   SE_Exception( unsigned int n ) : nSE( n ) {}
   ~SE_Exception() {}
   unsigned int getSeNumber() { return nSE; }
};

int main() {
   try {
      _set_se_translator( trans_func );
      SEFunc();
   }
   catch( SE_Exception e ) {
      printf_s( "Caught a __try exception with SE_Exception.\n" );
   }
}

void SEFunc() {
   __try {
      int x, y=0;
      x = 5 / y;
   }
   __finally {
      printf_s( "In finally\n" );
   }
}

void trans_func( unsigned int u, EXCEPTION_POINTERS* pExp ) {
   printf_s( "In trans_func.\n" );
   throw SE_Exception();
}
```
