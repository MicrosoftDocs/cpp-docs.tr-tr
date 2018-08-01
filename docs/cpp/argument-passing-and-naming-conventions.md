---
title: Bağımsız değişkeni geçirme ve adlandırma kuralları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- argument passing [C++], conventions
- arguments [C++], widening
- coding conventions, arguments
- arguments [C++], passing
- registers, return values
- thiscall keyword [C++]
- naming conventions [C++], arguments
- arguments [C++], naming
- passing arguments [C++], conventions
- conventions [C++], argument names
ms.assetid: de468979-eab8-4158-90c5-c198932f93b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4e1a6a8e837a44a966f262f581db04f1589233c8
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404047"
---
# <a name="argument-passing-and-naming-conventions"></a>Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları
**Microsoft'a özgü**  
  
 Visual C++ Derleyicileri, bağımsız değişkenleri geçirme için kuralları belirtin ve işlevler ile çağrı yapanlar arasında dönüş değerleri olanak tanır. Kuralların tüm desteklenen platformlarda kullanılabilir ve bazı kurallar platforma özel uygulamalar kullanır. Çoğu durumda, anahtar sözcükler veya belirli bir platformda desteklenmeyen bir kuralı belirten derleyici anahtarları dikkate alınmaz ve platform varsayılan kuralı kullanılır.  
  
 X86 bunlar geçirildiğinde, platformlarında, tüm bağımsız değişkenler 32 bit'e genişletilmiş. Dönüş değerleri de 32 bit olarak genişletilmiş ve dışında edx: eax kayıt çiftine döndürülen 8 baytlık yapılar, EAX kaydına döndürülür. Daha büyük yapılar döndürülür EAX kaydına işaretçileri olarak gizli dönüş yapılarına. Parametreler sağdan sola yığın üstüne itilir. Pod olmayan yapılar yazmaçlarda döndürülmez.  
  
 Derleyici giriş oluşturur ve işlev kullandıysanız ve bitiş kodu kaydedin ve ESI, EDI, EBX ve EBP geri yüklemek için kaydeder.  
  
> [!NOTE]
>  Bir yapı, birlik veya değerle bir işlevden döndürüldüğünde, türün tüm tanımları aynı olması gerekir, aksi takdirde program çalışma zamanında başarısız olabilir.  
  
 Kendi işlev giriş ve bitiş kodunuzun nasıl tanımlanacağı hakkında daha fazla bilgi için bkz: [Naked işlev çağrıları](../cpp/naked-function-calls.md).  
  
 Varsayılan hakkında bilgi için çağrı kuralları hedefleri x64 platformları görmek kodda [x64 bakış çağırma kuralları](../build/overview-of-x64-calling-conventions.md). ARM platformlarını hedefleyen kodda kuralı sorunları çağırma hakkında daha fazla bilgi için bkz: [genel Visual C++ ARM geçiş sorunları](../build/common-visual-cpp-arm-migration-issues.md).  
  
 Aşağıdaki çağrı kuralları Visual C/C++ Derleyici tarafından desteklenir.  
  
|Anahtar sözcüğü|Yığın temizleme|Parametre geçirme|  
|-------------|-------------------|-----------------------|  
|[__cdecl](../cpp/cdecl.md)|Çağıran|Parametreleri, ters sırada (sağdan sola) yığına|  
|[__clrcall](../cpp/clrcall.md)|yok|Parametreleri CLR ifade yığınına (soldan sağa) sırada yükleyin.|  
|[__stdcall](../cpp/stdcall.md)|Çağrılan|Parametreleri, ters sırada (sağdan sola) yığına|  
|[__fastcall](../cpp/fastcall.md)|Çağrılan|Kayıtlar, sonra yığına itildi depolanır|  
|[__thiscall](../cpp/thiscall.md)|Çağrılan|Yığına itildi; **bu** işaretçi ECX içine depolandı|  
|[__vectorcall](../cpp/vectorcall.md)|Çağrılan|Kayıtlar, ardından ters sırada (sağdan sola) yığına depolanır|  
  
 İlgili bilgiler için bkz. [eski çağırma kuralları](../cpp/obsolete-calling-conventions.md).  
  
 **END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Çağırma Kuralları](../cpp/calling-conventions.md)