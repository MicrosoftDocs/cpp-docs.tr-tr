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
ms.openlocfilehash: 32f32ceb56267dc39b58b8eed1b30af697ca6d74
ms.sourcegitcommit: d5a7ea8e462f555fbb3852d6fe5112521fef3133
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/30/2020
ms.locfileid: "96324182"
---
# <a name="argument-passing-and-naming-conventions"></a>Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları

**Microsoft'a Özgü**

Microsoft C++ derleyicileri, bağımsız değişkenleri geçirme ve işlevler ile çağıranlar arasında değer döndürme kurallarını belirtmenize olanak tanır. Tüm kurallar desteklenen platformlarda kullanılabilir değildir ve bazı kurallar platforma özgü uygulamalar kullanır. Çoğu durumda, belirli bir platformda desteklenmeyen bir kural belirten anahtar sözcükler veya derleyici anahtarları yok sayılır ve platform varsayılan kuralı kullanılır.

X86 platformlarında, tüm bağımsız değişkenler iletildiklerinde bit, geçirildiğinde 32 bittir. Dönüş değerleri Ayrıca 32 bite iletildiklerinde ve EAX kaydındaki, EDX: EAX kayıt çiftinin döndürdüğü 8 baytlık yapılar hariç döndürülür. Daha büyük yapılar, EAX kaydındaki gizli dönüş yapılarına işaretçiler olarak döndürülür. Parametreler, sağdan sola yığına gönderilir. PODs olmayan yapılar, Yazmaçlarda döndürülmeyecektir.

Derleyici, işlevinde kullanılıyorsa ESI, EDI, EBX ve EBP yazmaçlarını kaydetmek ve geri yüklemek için giriş ve bitiş kodu oluşturur.

> [!NOTE]
> Bir struct, Union veya Class bir işlevden değere göre döndürüldüğünde, türün tüm tanımlarının aynı olması gerekir, aksi takdirde program çalışma zamanında başarısız olabilir.

Kendi işlev giriş ve bitiş kodunuzu tanımlama hakkında daha fazla bilgi için bkz. [Naked Işlev çağrıları](../cpp/naked-function-calls.md).

X64 platformlarını hedefleyen koddaki varsayılan çağırma kuralları hakkında daha fazla bilgi için, bkz. [x64 çağırma kuralı](../build/x64-calling-convention.md). ARM platformlarını hedefleyen koddaki kural sorunlarını çağırma hakkında daha fazla bilgi için bkz. [Common VISUAL C++ ARM geçiş sorunları](../build/common-visual-cpp-arm-migration-issues.md).

Aşağıdaki çağırma kuralları, Visual C/C++ derleyicisi tarafından desteklenir.

|Sözcükle|Yığın Temizleme|Parametre geçirme|
|-------------|-------------------|-----------------------|
|[__cdecl](../cpp/cdecl.md)|Çağıran|Yığındaki parametreleri ters sırada (sağdan sola) iter|
|[__clrcall](../cpp/clrcall.md)|yok|Parametreleri, CLR ifade yığınına sırasıyla (soldan sağa) yükleyin.|
|[__stdcall](../cpp/stdcall.md)|Çağrılan|Yığındaki parametreleri ters sırada (sağdan sola) iter|
|[__fastcall](../cpp/fastcall.md)|Çağrılan|Kayıtlarda depolanır ve sonra yığına gönderilir|
|[__thiscall](../cpp/thiscall.md)|Çağrılan|Yığına gönderildi; **`this`** ECX 'de depolanan işaretçi|
|[__vectorcall](../cpp/vectorcall.md)|Çağrılan|Kayıtlarda depolanır ve sonra yığına ters sırada (sağdan sola) gönderilir|

İlgili bilgiler için bkz. [eski çağırma kuralları](../cpp/obsolete-calling-conventions.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma kuralları](../cpp/calling-conventions.md)
