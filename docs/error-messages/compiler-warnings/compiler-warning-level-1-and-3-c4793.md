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
ms.openlocfilehash: de6f514d8e3ad8e7715c9cd13a695e3398fffc8d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80164813"
---
# <a name="compiler-warning-level-1-and-3-c4793"></a>Derleyici Uyarısı (düzey 1 ve 3) C4793

> '*Function*': işlev yerel kod olarak derlendi: '*Reason*'

## <a name="remarks"></a>Açıklamalar

[/Clr](../../build/reference/clr-common-language-runtime-compilation.md) derleyici seçeneği belirtilmiş olsa da, derleyici yönetilen koda *işlev* derlenemiyor. Bunun yerine, derleyici uyarı C4793 ve açıklayıcı bir devamlılık iletisi yayar ve sonra *işlevi* yerel koda derler. Devamlılık iletisi *işlevin* neden `MSIL`derlenemediğini açıklayan *neden* metnini içerir.

**/Clr: Pure** derleyici seçeneğini belirttiğinizde bu düzey 1 uyarıdır.  **/Clr: Pure** derleyici seçeneği visual Studio 2015 ' de kullanımdan kaldırılmıştır ve visual Studio 2017 ' de desteklenmez.

Aşağıdaki tabloda tüm olası devamlılık iletileri listelenmektedir.

|Neden iletisi|Açıklamalar|
|--------------------|-------------|
|Yönetilen kodda hizalanmış veri türleri desteklenmez|CLR, verileri gerektiği gibi ayırabilmelidir, bu da veriler [__m128](../../cpp/m128.md) veya [Hizalama](../../cpp/align-cpp.md)gibi bildirimlerle hizalanmışsa mümkün olmayabilir.|
|' __ImageBase ' kullanan işlevler yönetilen kodda desteklenmez|`__ImageBase`, genellikle yalnızca alt düzey yerel kod tarafından bir DLL yüklemek için kullanılan özel bir bağlayıcı simgedir.|
|VarArgs, '/CLR ' derleyici seçeneği tarafından desteklenmiyor|İşlevlerin farklı yığın düzeni gereksinimleri olduğundan, yerel işlevler [değişken bağımsız değişken listelerine](../../cpp/functions-with-variable-argument-lists-cpp.md) (varargs) sahip yönetilen işlevleri çağıramaz. Ancak **/clr: Pure** derleyici seçeneğini belirtirseniz, derleme yalnızca yönetilen işlevler içerebildiğinden değişken bağımsız değişken listeleri desteklenir. Daha fazla bilgi için bkz. [saf ve Doğrulanabilen kodC++(/CLI)](../../dotnet/pure-and-verifiable-code-cpp-cli.md).|
|64 bitlik CLR __ptr32 değiştiricisiyle belirtilen verileri desteklemez|Bir işaretçinin geçerli platformda yerel işaretçiyle aynı boyutta olması gerekir. Daha fazla bilgi için bkz. [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|
|32 bitlik CLR __ptr64 değiştiricisiyle belirtilen verileri desteklemez|Bir işaretçinin geçerli platformda yerel işaretçiyle aynı boyutta olması gerekir. Daha fazla bilgi için bkz. [__ptr32, \__ptr64](../../cpp/ptr32-ptr64.md).|
|Yönetilen kodda bir veya daha fazla iç yapı desteklenmiyor|İletinin yayılışında iç öğe adı kullanılamıyor. Ancak, bu iletinin genellikle düşük düzey bir makine yönergesini temsil etmesine neden olan bir iç öğe.|
|Satır içi yerel derleme (' __asm ') yönetilen kodda desteklenmiyor|[Satır içi derleme kodu](../../assembler/inline/asm.md) , yönetilebilecek rastgele yerel kod içerebilir.|
|__Clrcall olmayan bir sanal işlev dönüştürücü yerel olarak derlenmelidir|[__Clrcall](../../cpp/clrcall.md) olmayan bir sanal işlev dönüştürücü, yönetilmeyen bir adres kullanmalıdır.|
|' _Setjmp ' kullanan bir işlev yerel olarak derlenmelidir|CLR, program yürütmeyi denetleyebilmelidir. Ancak [setjmp](../../cpp/using-setjmp-longjmp.md) işlevi, kayıt ve yürütme durumu gibi alt düzey bilgileri kaydederek ve geri yükleyerek normal program yürütmesini atlar.|

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
