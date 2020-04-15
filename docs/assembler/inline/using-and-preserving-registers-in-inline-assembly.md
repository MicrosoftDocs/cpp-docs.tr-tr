---
title: Bir Satır İçi Derlemede Kayıtları Kullanma ve Koruma
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], register values
- inline assembly, registers
- registers, inline assembly
- preserving registers
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
ms.openlocfilehash: 97db09ac7652c00e9599a6938f4114de080906c0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318022"
---
# <a name="using-and-preserving-registers-in-inline-assembly"></a>Bir Satır İçi Derlemede Kayıtları Kullanma ve Koruma

**Microsoft'a Özgü**

Genel olarak, bir `__asm` blok başladığında bir kaydın belirli bir değere sahip olacağını varsaymamalısınız. Kayıt değerlerinin ayrı `__asm` bloklar arasında korunması garanti edilmez. Satır altı kod bloğunu sona erdirip başka bir kod başlatırsanız, ilk bloktaki değerlerini korumak için ikinci bloktaki kayıtlara güvenemezsiniz. Bir `__asm` blok, normal denetim akışından kaynaklanan kayıt değerleri ne olursa olsun devralır.

Çağrı kuralını `__fastcall` kullanırsanız, derleyici yığın yerine kasalarda işlev bağımsız değişkenlerini geçirir. Bir işlevin hangi `__asm` parametrenin hangi kayıtta olduğunu söylemenin bir yolu olmadığından, bloklarla işlevlerde sorun yaratabilir. İşlev EAX'ta bir parametre alırsa ve hemen EAX'ta başka bir şey depolarsa, orijinal parametre kaybolur. Buna ek olarak, ECX kaydını `__fastcall`.

Bu tür kayıt çakışmalarını `__fastcall` önlemek için, bir `__asm` blok içeren işlevler için kuralı kullanmayın. /Gr derleyici seopsiyonuyla kuralı genel olarak belirtirseniz, `__asm` `__cdecl` bir `__stdcall`blok içeren her işlevi bildirin veya . `__fastcall` (Öznitelik `__cdecl` derleyiciye bu işlev için C çağrı kuralını kullanmasını söyler.) /Gr ile derleme değilseniz, işlevi öznitelik ile `__fastcall` bildirmekten kaçının.

C/C++ işlevlerinde montaj dili yazmak için kullanırken, `__asm` EAX, EBX, ECX, EDX, ESI veya EDI kayıtlarının korunması gerekmez. Örneğin, POWER2'de. [Satır Altı Montajlı İşlevler Yazmada](../../assembler/inline/writing-functions-with-inline-assembly.md)C örneği, `power2` işlev EAX kaydındaki değeri korumaz. Ancak, bu kayıtların kullanılması kod kalitesini etkiler, çünkü kayıt tahsisatçısı bunları blokların arasında `__asm` değerleri depolamak için kullanamaz. Buna ek olarak, satır satırlı montaj kodunda EBX, ESI veya EDI kullanarak, derleyiciyi işlev prologunda ve sonunda bu kayıtları kaydetmeye ve geri yüklemeye zorlarsınız.

`__asm` Bloğun kapsamı için kullandığınız diğer kayıtları (DS, SS, SP, BP ve bayrak kayıtları gibi) korumanız gerekir. Değiştirmek için bir nedeniniz yoksa (örneğin yığınları değiştirmek için) ESP ve EBP kayıtlarınızı korumalısınız. Ayrıca [bkz.](../../assembler/inline/optimizing-inline-assembly.md)

Bazı SSE türleri sekiz bayt lık yığın hizalaması gerektirerek derleyiciyi dinamik yığın hizalama kodu yatmaya zorlar. Hizalamadan sonra hem yerel değişkenlere hem de işlev parametrelerine erişebilmek için derleyiciiki kare işaretçisi tutar.  Derleyici çerçeve işaretçisi ihmali (FPO) gerçekleştirirse, EBP ve ESP kullanır.  Derleyici FPO gerçekleştirmezse, EBX ve EBP kullanır. Kodun doğru çalıştığından emin olmak için, işlev çerçeve işaretçisini değiştirebileceğinden dinamik yığın hizalaması gerektiriyorsa, ASM kodunda EBX'i değiştirmeyin. Sekiz bayt hizalanmış türleri işlevin dışına taşıyın veya EBX kullanmaktan kaçının.

> [!NOTE]
> Satır satırlı montaj kodunuz STD veya CLD yönergelerini kullanarak yön bayrağını değiştirirse, bayrağı özgün değerine geri yüklemeniz gerekir.

**END Microsoft Özel**

## <a name="see-also"></a>Ayrıca bkz.

[Sıralı Assembler](../../assembler/inline/inline-assembler.md)<br/>
