---
title: Derleyici Uyarısı (düzey 1 ve 3) C4793
ms.date: 11/04/2016
f1_keywords:
- C4793
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
ms.openlocfilehash: e7ca3b10e09b0d6818fbc7f5607ebc9c95c7f15c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62280548"
---
# <a name="compiler-warning-level-1-and-3-c4793"></a>Derleyici Uyarısı (düzey 1 ve 3) C4793

> '*işlevi*': işlev yerel kod derlenen: '*neden*'

## <a name="remarks"></a>Açıklamalar

Derleyici derlenemez *işlevi* yönetilen koda olsa bile [/CLR](../../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği belirtildi. Bunun yerine, derleyici uyarı C4793 ve bir açıklayıcı devamlılık iletisi gönderir ve ardından derler *işlevi* yerel koda. Devamlılık iletisini içeren *neden* nedenini açıklayan metin *işlevi* için derlenemez `MSIL`.

Bu, belirttiğiniz zaman bir düzey 1 uyarı **/CLR: pure** derleyici seçeneği.  **/CLR: pure** derleyici seçeneğini Visual Studio 2015'te kullanım dışı ve Visual Studio 2017'de desteklenmiyor.

Aşağıdaki tablo, tüm olası devamlılık iletileri listeler.

|Sebep message|Açıklamalar|
|--------------------|-------------|
|Yönetilen kodda hizalanmış veri türleri desteklenmiyor|CLR hangi verileri bildirimlerle gibi hizalanır varsa mümkün olmayabilir gerektiği gibi verileri ayırmak gereken [__m128](../../cpp/m128.md) veya [hizalama](../../cpp/align-cpp.md).|
|'__ImageBase' kullanan işlevler yönetilen kodda desteklenmiyor|`__ImageBase` genellikle bir DLL'yi yalnızca alt düzey yerel kod tarafından kullanılan bir özel bağlayıcı semboldür.|
|VarArgs tarafından desteklenmez ' / clr' derleyici seçeneği|Yerel işlevleri sahip yönetilen işlevlerin çağıramaz [değişken bağımsız değişken listeleri](../../cpp/functions-with-variable-argument-lists-cpp.md) (varargs) işlevleri farklı bir yığın düzeni gereksinimleri bulunduğundan. Ancak, belirtirseniz **/CLR: pure** derleyici seçeneği, değişken bağımsız değişken listeleri yalnızca işlevler yönetilen bütünleştirilmiş kod içerebileceğinden desteklenir. Daha fazla bilgi için [saf ve doğrulanabilen kod (C++/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).|
|64 bit CLR veri __ptr32 değiştiriciyle bildirildi desteklemiyor|Bir işaretçi yerel işaretçiye geçerli platform aynı boyutta olması gerekir. Daha fazla bilgi için [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|
|32 bitlik CLR veri __ptr64 değiştiriciyle bildirildi desteklemiyor|Bir işaretçi yerel işaretçiye geçerli platform aynı boyutta olması gerekir. Daha fazla bilgi için [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|
|Bir veya daha fazla yapı içleri yönetilen kodda desteklenmiyor|İç adını ileti yayılan anda kullanılabilir değil. Ancak, bir iç öğe genellikle bu iletiyi neden olan bir alt düzey makine yönergesi temsil eder.|
|Satır içi yerel derleme ('__asm'), yönetilen kodda desteklenmiyor|[Satır içi derleme kodu](../../assembler/inline/asm.md) yönetilemez rastgele yerel kod içerebilir.|
|__Clrcall olmayan bir sanal işlev dönüştürücü yerel olarak derlenmelidir.|Olmayan bir[__clrcall](../../cpp/clrcall.md) sanal işlev dönüştürücü, yönetilmeyen bir adresi kullanmanız gerekir.|
|'_Setjmp' kullanarak bir işlev yerel olarak derlenmelidir.|CLR program yürütmesini denetlemek mümkün olması gerekir. Ancak, [setjmp](../../cpp/using-setjmp-longjmp.md) işlevi, kaydetme ve geri yükleme kayıtları ve yürütme durumu gibi alt düzey bilgileri tarafından normal program yürütme atlar.|

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4793 oluşturur.

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

Aşağıdaki örnek, C4793 oluşturur.

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