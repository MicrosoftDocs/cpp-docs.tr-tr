---
title: Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları
ms.date: 12/17/2018
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
ms.openlocfilehash: ca09d31d3d8d50ca94543c5e02262edd7b2deefc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184406"
---
# <a name="argument-passing-and-naming-conventions"></a>Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları

**Microsoft'a özgü**

Visual C++ Derleyicileri, bağımsız değişkenleri geçirme için kuralları belirtin ve işlevler ile çağrı yapanlar arasında dönüş değerleri olanak tanır. Kuralların tüm desteklenen platformlarda kullanılabilir ve bazı kurallar platforma özel uygulamalar kullanır. Çoğu durumda, anahtar sözcükler veya belirli bir platformda desteklenmeyen bir kuralı belirten derleyici anahtarları dikkate alınmaz ve platform varsayılan kuralı kullanılır.

X86 bunlar geçirildiğinde, platformlarında, tüm bağımsız değişkenler 32 bit'e genişletilmiş. Dönüş değerleri de 32 bit olarak genişletilmiş ve dışında edx: eax kayıt çiftine döndürülen 8 baytlık yapılar, EAX kaydına döndürülür. Daha büyük yapılar döndürülür EAX kaydına işaretçileri olarak gizli dönüş yapılarına. Parametreler sağdan sola yığın üstüne itilir. Pod olmayan yapılar yazmaçlarda döndürülmez.

Derleyici giriş oluşturur ve işlev kullandıysanız ve bitiş kodu kaydedin ve ESI, EDI, EBX ve EBP geri yüklemek için kaydeder.

> [!NOTE]
> Bir yapı, birlik veya değerle bir işlevden döndürüldüğünde, türün tüm tanımları aynı olması gerekir, aksi takdirde program çalışma zamanında başarısız olabilir.

Kendi işlev giriş ve bitiş kodunuzun nasıl tanımlanacağı hakkında daha fazla bilgi için bkz: [Naked işlev çağrıları](../cpp/naked-function-calls.md).

Varsayılan hakkında bilgi için çağrı kuralları hedefleri x64 platformları görmek kodda [x64 çağırma kuralı](../build/x64-calling-convention.md). ARM platformlarını hedefleyen kodda kuralı sorunları çağırma hakkında daha fazla bilgi için bkz: [genel Visual C++ ARM geçiş sorunları](../build/common-visual-cpp-arm-migration-issues.md).

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