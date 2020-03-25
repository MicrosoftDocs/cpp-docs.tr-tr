---
title: Bir Satır İçi Derlemede Kayıtları Kullanma ve Koruma
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], register values
- inline assembly, registers
- registers, inline assembly
- preserving registers
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
ms.openlocfilehash: 51147a217ec56c525fc01e1b36a9381b9356ba4d
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80169161"
---
# <a name="using-and-preserving-registers-in-inline-assembly"></a>Bir Satır İçi Derlemede Kayıtları Kullanma ve Koruma

**Microsoft 'a özgü**

Genel olarak, bir `__asm` bloğu başladığında bir kaydın verilen değere sahip olacağını varsaymamalıdır. Kayıt değerlerinin ayrı `__asm` blokları genelinde korunması garanti edilmez. Satır içi kod bloğunu sonlandırdıysanız ve başka bir başlangıç yaparsanız, ilk bloğundan değerlerini sürdürmek için ikinci bloktaki yazmaçlara güvenebilirsiniz. `__asm` bloğu, normal denetim akışından hangi yazmaç değerlerinin sonucunu devralır.

`__fastcall` çağırma kuralını kullanırsanız, derleyici yığın yerine kayıt sırasında işlev bağımsız değişkenlerini geçirir. Bu, bir işlevin hangi parametreye kayıt olduğunu söylemesinin bir yolu olmadığından `__asm` blokları olan işlevlerde sorunlar oluşturabilir. İşlev EAX 'te bir parametre almak ve EAX 'te başka bir şeyi hemen depoladığında, orijinal parametre kaybedilir. Ayrıca, `__fastcall`ile belirtilen herhangi bir işlevde ECX kaydını korumanız gerekir.

Bu tür kayıt çakışmalarını önlemek için, `__asm` bloğunu içeren işlevler için `__fastcall` kuralını kullanmayın. /Gr derleyici seçeneğiyle genel olarak `__fastcall` kuralı belirtirseniz, `__cdecl` veya `__stdcall`ile `__asm` bloğu içeren her işlevi bildirin. (`__cdecl` özniteliği derleyiciye bu işlev için C çağırma kuralını kullanmasını söyler.) /Gr ile derlerken, işlevi `__fastcall` özniteliğiyle bildirmemeye özen gösterin.

C/C++ işlevlerde derleme dilini yazmak için `__asm` kullanırken EAX, EBX, ecx, EDX, ESI veya EDI yazmaçlarını korumanız gerekmez. Örneğin, POWER2. C örnek [satır Içi derleme Ile yazma işlevleri](../../assembler/inline/writing-functions-with-inline-assembly.md), `power2` işlevi EAX kaydındaki değeri korumaz. Ancak, bu yazmaçların kullanılması kod kalitesini etkiler çünkü kayıt ayırıcısı bu değerleri `__asm` blokları genelinde depolamak için kullanamaz. Ayrıca, satır içi bütünleştirilmiş kod kodunda EBX, ESI veya EDI kullanarak, derleyicinin bu kayıtları kaydetme ve geri yükleme işlemleri için bir kayıt ve başlangıç durumuna zorlarsınız.

`__asm` bloğunun kapsamı için kullandığınız diğer kayıtları (DS, SS, SP, BP ve bayraklar Yazmaçları gibi) korumanız gerekir. Değişiklik yapmak için bir nedeniniz yoksa, ESP ve EBP yazmaçlarını korumanız gerekir (örneğin, yığınları değiştirmek için). Ayrıca bkz. [satır Içi derlemeyi iyileştirme](../../assembler/inline/optimizing-inline-assembly.md).

Bazı SSE türleri sekiz baytlık yığın hizalaması gerektirir ve derleyicinin dinamik yığın hizalama kodunu yaymasına zorlanır. Hizalamadan sonra hem yerel değişkenlere hem de işlev parametrelerine erişebilmek için, derleyici iki çerçeve işaretçisi tutar.  Derleyici çerçeve işaretçisi atlama (!) işlemini gerçekleştiriyorsa, EBP ve ESP kullanır.  Derleyici, bu işlemi gerçekleştirmezse EBX ve EBP kullanacaktır. Kodun doğru şekilde çalıştığından emin olmak için, çerçeve işaretçisini değiştirebildiğinden, işlev dinamik yığın hizalaması gerektiriyorsa asm kodunda EBX 'i değiştirmeyin. Sekiz baytlık hizalanmış türleri işlevin dışına taşıyın ya da EBX kullanmaktan kaçının.

> [!NOTE]
>  Satır içi derleme kodunuz STD veya CLD yönergelerini kullanarak yön bayrağını değiştirirse, bayrağını özgün değerine geri yüklemeniz gerekir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır İçi Assembler](../../assembler/inline/inline-assembler.md)<br/>
