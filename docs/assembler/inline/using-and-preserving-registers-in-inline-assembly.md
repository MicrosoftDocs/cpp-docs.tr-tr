---
title: Bir Satır İçi Derlemede Kayıtları Kullanma ve Koruma
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], register values
- inline assembly, registers
- registers, inline assembly
- preserving registers
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
ms.openlocfilehash: 30b2f9ca8c658b65819709bb2e536b5aaecad676
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643072"
---
# <a name="using-and-preserving-registers-in-inline-assembly"></a>Bir Satır İçi Derlemede Kayıtları Kullanma ve Koruma

**Microsoft'a özgü**

Genel olarak, size bir kayıt belirli bir değeri olduğunu varsayın değil, bir `__asm` blok başlar. YAZMAÇ değerlerini arasında ayrı korunması garanti edilmez `__asm` engeller. Satır içi kod bloğunu sonlandırmak ve başka başlamak, kayıtlara ilk bloğunun kendi değerlerini korumak için ikinci blok üzerinde güvenemezsiniz. Bir `__asm` blok devralan ne olursa olsun, denetiminin normal akışı sonuçtan değerleri kaydedin.

Kullanırsanız `__fastcall` çağırma kuralı, derleyici işlev bağımsız değişkenleri yerine yazmaçlarında yığında geçirir. Bu sorunları işlevleriyle oluşturabilirsiniz `__asm` bir işlevin hangi kayıttaki parametredir bildirmek için hiçbir yolu yoktur çünkü engeller. İşlev EAX bir parametre almaya olur ve hemen EAX başka bir şey depolar, özgün parametresi kaybolur. Ayrıca, ECX kasa ile bildirilen işlevde korumak `__fastcall`.

Bu tür kaydı çakışmaları önlemek için kullanmayın `__fastcall` kuralı içeren işlevler için bir `__asm` blok. Belirtirseniz `__fastcall` kuralı genel Gr derleyici seçeneği ile birlikte bildirin her işlevi içeren bir `__asm` ile block `__cdecl` veya `__stdcall`. ( `__cdecl` Özniteliği için bu işlev C çağırma kuralı kullanmak için derleyiciye.) Gr ile derleme değil, işlev ile bildirme kaçının `__fastcall` özniteliği.

Kullanırken `__asm` derleme dili C/C++ işlevleri yazmak için EAX, EBX, ECX, EDX, ESI veya EDI Yazmaçları koruma gerekmez. Örneğin, POWER2 içinde. C örnekte [satır içi derlemeyle işlevler yazma](../../assembler/inline/writing-functions-with-inline-assembly.md), `power2` işlevi kaydına değeri korumak değil. Kayıt ayırıcı bunları arasında değerleri depolamak için kullanamazsınız çünkü ancak bu kayıtları kullanarak kod kalitesini etkiler `__asm` engeller. Ayrıca, EBX, ESI veya EDI satır içi derleme kodu kullanarak, kaydetme ve geri yükleme işlevi prolog ve epilog bu kayıtlara derleyicinin zorlar.

Kapsamını (DS, SS, SP, BP ve bayrakları kayıtları gibi) kullandığınız diğer kayıtlara koruması gerektiğini `__asm` blok. (Yığınları, örneğin geçmek için) değiştirileceğini herhangi bir nedenle olmadığı sürece ESP ve EBP Yazmaçları koruma. Ayrıca bkz: [satır içi derlemeyi en iyi duruma getirme](../../assembler/inline/optimizing-inline-assembly.md).

Bazı SSE türleri dinamik yığın hizalamasını kod dönüştüğünde derleyicinin zorlama sekiz bayt yığın hizalama gerektirir. Hem yerel değişkenleri ve işlev parametrelerini sonra hizalama erişebilmesi için derleyici iki çerçeve işaretçilerini tutar.  Derleyicinin çerçeve işaretçisi atlamayı (FPO) gerçekleştiriyorsa EBP ve ESP kullanır.  Derleyici FPO yapmazsa, EBX ve EBP kullanır. Kod çalışmalarını doğru emin olmak için çerçeve işaretçisini değiştirebilir gibi işlev dinamik yığını gerektiriyorsa, EBX asm kodunda değiştirmeyin. Sekiz bayt hizalanmış türlere işlevi dışına taşıyın ya da EBX kullanmaktan kaçının.

> [!NOTE]
>  Yön bayrağı STD veya CLD yönergeleri kullanarak, satır içi derleme kodu değişirse, bayrağı özgün değerine geri yüklemeniz gerekir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>