---
title: Derleyici Uyarısı (düzey 1 ve 3) C4793 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4793
dev_langs:
- C++
helpviewer_keywords:
- C6634
- C6635
- C6640
- C6630
- C6639
- C6636
- C6638
- C6631
- C6637
- C4793
ms.assetid: 819ada53-1d9c-49b8-a629-baf8c12314e6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3942d09e823fc6bd2f370a8c8ee72b8d00e9a98
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704938"
---
# <a name="compiler-warning-level-1-and-3-c4793"></a>Derleyici Uyarısı (düzey 1 ve 3) C4793

> '*işlevi*': işlevi yerel koda derlenmiş: '*neden*'

## <a name="remarks"></a>Açıklamalar

Derleyici derlenemiyor *işlevi* yönetilen koda olsa bile [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği belirtildi. Bunun yerine, derleyicinin uyarı C4793 ve açıklayıcı devamlılık iletisine yayar ve ardından derler *işlevi* yerel kod içine. Devamlılık iletisini içeren *neden* nedenini açıklayan metin *işlevi* için derlenemez `MSIL`.

Belirttiğiniz zaman bir düzey 1 uyarı budur **/CLR: pure** derleyici seçeneği.  **/CLR: pure** derleyici seçeneği Visual Studio 2015'te kullanım dışı ve Visual Studio 2017 içinde desteklenmiyor.

Aşağıdaki tabloda tüm olası devamlılık iletileri listeler.

|Neden iletisi|Açıklamalar|
|--------------------|-------------|
|Yönetilen kodda hizalanmış veri türleri desteklenmiyor|Hangi veri bildirimlerle gibi hizalanır varsa mümkün olmayabilir CLR veri gerektiği gibi ayırabilirsiniz olmalıdır [__m128](../../cpp/m128.md) veya [Hizala](../../cpp/align-cpp.md).|
|Yönetilen kodda '__ImageBase' kullanan işlevler desteklenmez.|`__ImageBase` DLL yüklemek için yalnızca alt düzey yerel kod tarafından genellikle kullanılan bir özel bağlayıcı simge olur.|
|VarArgs tarafından desteklenmeyen ' / clr' derleyici seçeneği|Yerel işlevler sahip yönetilen işlevler çağıramaz [değişken bağımsız değişken listeleri](../../cpp/functions-with-variable-argument-lists-cpp.md) (varargs) işlevleri farklı yığın düzeni gereksinimlere sahip olduğundan. Ancak, belirtirseniz **/CLR: pure** derleyici seçeneği, değişken bağımsız değişken listeleri derleme yönetilen işlevler yalnızca içerebileceğinden desteklenir. Daha fazla bilgi için bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).|
|64-bit CLR veri __ptr32 değiştiricisi ile bildirilmiş desteklemez|Bir işaretçi geçerli platformdaki yerel bir işaretçi aynı boyutta olmalıdır. Daha fazla bilgi için bkz: [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|
|32-bit CLR veri __ptr64 değiştiricisi ile bildirilmiş desteklemez|Bir işaretçi geçerli platformdaki yerel bir işaretçi aynı boyutta olmalıdır. Daha fazla bilgi için bkz: [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|
|Bir veya daha fazla yapı yönetilen kodda desteklenmiyor|İç adı ileti yayınlaması aynı anda kullanılabilir değil. Ancak, bu ileti genellikle neden olan bir iç alt düzey makine yönerge temsil eder.|
|Yönetilen kodda satır içi yerel derleme ('__asm') desteklenmiyor|[Satır içi derleme kodunda](../../assembler/inline/asm.md) yönetilemez rasgele yerel kod içerebilir.|
|__Clrcall olmayan sanal işlev dönüştürücü gibi yerel derlenmiş gerekir|Olmayan bir[__clrcall](../../cpp/clrcall.md) sanal işlev dönüştürücü yönetilmeyen bir adresi kullanmanız gerekir.|
|'_Setjmp' kullanarak bir işlevi olarak yerel derlenmiş gerekir|CLR program yürütme denetim sahibi olması gerekir. Ancak, [setjmp](../../cpp/using-setjmp-longjmp.md) işlevi kaydetme ve düşük düzey bilgileri kaydeder ve yürütme durumu gibi geri yükleme tarafından normal program yürütme atlar.|

## <a name="example"></a>Örnek

Aşağıdaki örnek C4793 oluşturur.

```cpp
// C4793.cpp
// compile with: /c /clr /W3
// processor: x86
int asmfunc(void) {   // C4793, compiled as unmanaged, native code
   __asm {
      mov eax, 0
   }
}
```

```Output
warning C4793: 'asmfunc' : function is compiled as native code:
        Inline native assembly ('__asm') is not supported in managed code
```

Aşağıdaki örnek C4793 oluşturur.

```cpp
// C4793_b.cpp
// compile with: /c /clr /W3
#include <setjmp.h>
jmp_buf test_buf;

void f() {
   setjmp(test_buf);   // C4793 warning
}
```

```Output
warning C4793: 'f' : function is compiled as native code:
        A function using '_setjmp' must be compiled as native
```