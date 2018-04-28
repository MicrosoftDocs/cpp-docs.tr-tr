---
title: Kullanma ve satır içi derlemede kayıtları koruma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- __asm keyword [C++], register values
- inline assembly, registers
- registers, inline assembly
- preserving registers
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a5db1c9c4facd51b2886d93017ad87a0683b899
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/28/2018
---
# <a name="using-and-preserving-registers-in-inline-assembly"></a>Bir Satır İçi Derlemede Kayıtları Kullanma ve Koruma
## <a name="microsoft-specific"></a>Microsoft'a Özgü  
 Genel olarak, size bir kayıt belirli bir değeri olduğunu varsayımında bulunmamalıdır olduğunda bir `__asm` blok başlar. YAZMAÇ değerlerini ayrı arasında korunması garanti edilmez `__asm` engeller. Satır içi kod bloğunu sonlandırmak ve diğerine başlamak istiyorsanız, ilk bloğunun değerlerine korumak için ikinci blok kasalar Bel olamaz. Bir `__asm` blok devralır ne olursa olsun değerleri sonuç denetiminin normal akıştan kaydedin.  
  
 Kullanırsanız `__fastcall` çağırma kuralı, derleyici işlev bağımsız değişkenleri yerine yazmaçlar içinde yığında geçirir. Bu sorunları işlevleriyle oluşturabileceğiniz `__asm` bir işlev olmadığını yolu hangi kayıttaki parametredir olduğundan engeller. İşlevi parametre EAX almak için olur ve hemen EAX içinde başka bir şey depolar, özgün parametresi kaybolur. Ayrıca, ile bildirilen herhangi bir işlev ECX kayıttaki korumak `__fastcall`.  
  
 Bu tür kaydı çakışmaları önlemek için kullanmayın `__fastcall` kuralı içeren işlevler için bir `__asm` bloğu. Belirtirseniz `__fastcall` kuralı genel /Gr derleyici seçeneği ile bildirme her işlevi içeren bir `__asm` ile engelleme `__cdecl` veya `__stdcall`. ( `__cdecl` Özniteliği C çağırma kuralı için bu işlevi kullanmak için derleyicisi bildirir.) /Gr ile derleme değil, işlev bildirme kaçının `__fastcall` özniteliği.  
  
 Kullanırken `__asm` derleme dil C/C++ işlevlerde yazmak için EAX, EBX, ECX, EDX, ESI veya EDI Yazmaçları koruma gerekmez. Örneğin, POWER2 içinde. C örnekte [satır içi derlemeyle işlevler yazma](../../assembler/inline/writing-functions-with-inline-assembly.md), `power2` işlevi EAX kayıt değeri korumak değil. Kayıt ayırıcısı bunları arasında değerlerini depolamak için kullanamadığından ancak, bu kayıtları kullanarak kod kalitesini etkiler `__asm` engeller. Ayrıca, satır içi derleme kodunda EBX, ESI veya EDI kullanarak kaydetmek ve bu kayıtları işlevi giriş ve epilog geri yüklemek için derleyici zorlar.  
  
 Kapsamını (DS, SS, SP, BP ve bayrakları kasalar gibi) kullandığınız diğer kayıtları korumak `__asm` bloğu. Bunları (yığınları, örneğin geçiş yapmak için) değiştirmek için bazı nedeniniz yoksa ESP ve EBP Yazmaçları koruma. Ayrıca bkz. [en iyi duruma getirme satır içi derleme](../../assembler/inline/optimizing-inline-assembly.md).  
  
 Bazı SSE türleri sekiz baytlık yığını hizalama derleyici dinamik yığın hizalama kod yayma zorlama gerektirir. Yerel değişkenleri ve işlev parametreleri sonra hizalama erişebilmeleri için iki çerçeve işaretçisi derleyici tutar.  Derleyici çerçeve işaretçisini atlama (FPO) gerçekleştirirse, EBP ve ESP kullanır.  Derleyici FPO yapmıyorsa EBX ve EBP kullanır. Çerçeve işaretçisi değiştirebileceği gibi işlev dinamik yığını gerektiriyorsa kodu çalıştırır doğru emin olmak için EBX asm kodda değişiklik yapmayın. Sekiz bayt hizalı türleri işlevi dışında taşıyın ya da EBX kullanmaktan kaçının.  
  
> [!NOTE]
>  Satır içi derleme kodunda STD veya CLD yönergeleri kullanarak yön bayrağı değişirse bayrağı özgün değerine geri yüklemeniz gerekir.  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Satır İçi Assembler](../../assembler/inline/inline-assembler.md)