---
description: 'Hakkında daha fazla bilgi edinin: satır Içi derlemede kayıtları kullanma ve koruma'
title: Bir Satır İçi Derlemede Kayıtları Kullanma ve Koruma
ms.date: 08/30/2018
helpviewer_keywords:
- __asm keyword [C++], register values
- inline assembly, registers
- registers, inline assembly
- preserving registers
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
ms.openlocfilehash: 36758a313044190c9ee2f2a9b094325821d87635
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122011"
---
# <a name="using-and-preserving-registers-in-inline-assembly"></a>Bir Satır İçi Derlemede Kayıtları Kullanma ve Koruma

**Microsoft'a Özgü**

Genel olarak, bir blok başladığında bir kaydın verilen değere sahip olacağını varsaymamalıdır **`__asm`** . Kayıt değerlerinin ayrı bloklar genelinde korunması garanti edilmez **`__asm`** . Satır içi kod bloğunu sonlandırdıysanız ve başka bir başlangıç yaparsanız, ilk bloğundan değerlerini sürdürmek için ikinci bloktaki yazmaçlara güvenebilirsiniz. Bir **`__asm`** blok, normal denetim akışından hangi yazmaç değerlerinin sonucunu devralır.

**`__fastcall`** Çağırma kuralını kullanırsanız, derleyici yığın yerine, işlev bağımsız değişkenlerini kayıt defterlerine geçirir. Bu, **`__asm`** bir işlevin hangi parametreye kayıt olduğunu söylemesinin bir yolu olmadığından, işlevlerle işlevlerde sorunlar oluşturabilir. İşlev EAX 'te bir parametre almak ve EAX 'te başka bir şeyi hemen depoladığında, orijinal parametre kaybedilir. Ayrıca, ile belirtilen herhangi bir işlevde ECX kaydını korumanız gerekir **`__fastcall`** .

Bu tür kayıt çakışmalarını önlemek için, **`__fastcall`** bir blok içeren işlevler için kuralı kullanmayın **`__asm`** . **`__fastcall`** Kuralı/Gr derleyici seçeneğiyle küresel olarak belirtirseniz, veya ile bir blok içeren her işlevi bildirin **`__asm`** **`__cdecl`** **`__stdcall`** . ( **`__cdecl`** Özniteliği derleyiciye bu işlev Için C çağırma kuralını kullanmasını söyler.) /Gr ile derlerken, işlevi özniteliğiyle bildirmemeye özen gösterin **`__fastcall`** .

**`__asm`** C/C++ işlevlerinde derleme dilini yazmak için kullanırken EAX, EBX, ECX, EDX, ESI veya EDI yazmaçlarını korumanız gerekmez. Örneğin, POWER2. C örnek [satır Içi derleme Ile yazma işlevleri](../../assembler/inline/writing-functions-with-inline-assembly.md), `power2` işlev EAX kaydındaki değeri korumaz. Ancak, bu yazmaçların kullanılması kod kalitesini etkiler çünkü yazmaç ayırıcısı, değerleri bloklar arasında depolamak için kullanamaz **`__asm`** . Ayrıca, satır içi bütünleştirilmiş kod kodunda EBX, ESI veya EDI kullanarak, derleyicinin bu kayıtları kaydetme ve geri yükleme işlemleri için bir kayıt ve başlangıç durumuna zorlarsınız.

Bloğunun kapsamı için kullandığınız diğer kayıtları (DS, SS, SP, BP ve bayraklar Yazmaçları gibi) korumanız gerekir **`__asm`** . Değişiklik yapmak için bir nedeniniz yoksa, ESP ve EBP yazmaçlarını korumanız gerekir (örneğin, yığınları değiştirmek için). Ayrıca bkz. [satır Içi derlemeyi iyileştirme](../../assembler/inline/optimizing-inline-assembly.md).

Bazı SSE türleri sekiz baytlık yığın hizalaması gerektirir ve derleyicinin dinamik yığın hizalama kodunu yaymasına zorlanır. Hizalamadan sonra hem yerel değişkenlere hem de işlev parametrelerine erişebilmek için, derleyici iki çerçeve işaretçisi tutar.  Derleyici çerçeve işaretçisi atlama (!) işlemini gerçekleştiriyorsa, EBP ve ESP kullanır.  Derleyici, bu işlemi gerçekleştirmezse EBX ve EBP kullanacaktır. Kodun doğru şekilde çalıştığından emin olmak için, çerçeve işaretçisini değiştirebildiğinden, işlev dinamik yığın hizalaması gerektiriyorsa asm kodunda EBX 'i değiştirmeyin. Sekiz baytlık hizalanmış türleri işlevin dışına taşıyın ya da EBX kullanmaktan kaçının.

> [!NOTE]
> Satır içi derleme kodunuz STD veya CLD yönergelerini kullanarak yön bayrağını değiştirirse, bayrağını özgün değerine geri yüklemeniz gerekir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Satır içi assembler](../../assembler/inline/inline-assembler.md)<br/>
