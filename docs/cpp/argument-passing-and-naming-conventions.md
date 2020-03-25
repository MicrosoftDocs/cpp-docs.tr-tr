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
ms.openlocfilehash: e621db339102f1f40030bc7826d383d306a39be8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190774"
---
# <a name="argument-passing-and-naming-conventions"></a>Bağımsız Değişkeni Geçirme ve Adlandırma Kuralları

**Microsoft 'a özgü**

Microsoft C++ derleyicileri, bağımsız değişkenleri geçirme ve işlevler ile çağıranlar arasında değer döndürme kurallarını belirtmenize olanak tanır. Tüm kurallar desteklenen platformlarda kullanılabilir değildir ve bazı kurallar platforma özgü uygulamalar kullanır. Çoğu durumda, belirli bir platformda desteklenmeyen bir kural belirten anahtar sözcükler veya derleyici anahtarları yok sayılır ve platform varsayılan kuralı kullanılır.

X86 plaftorms 'de, tüm bağımsız değişkenler geçirildiğinde 32 iletildiklerinde bittir. Dönüş değerleri Ayrıca 32 bite iletildiklerinde ve EAX kaydındaki, EDX: EAX kayıt çiftinin döndürdüğü 8 baytlık yapılar hariç döndürülür. Daha büyük yapılar, EAX kaydındaki gizli dönüş yapılarına işaretçiler olarak döndürülür. Parametreler, sağdan sola yığına gönderilir. PODs olmayan yapılar, Yazmaçlarda döndürülmeyecektir.

Derleyici, işlevinde kullanılıyorsa ESI, EDI, EBX ve EBP yazmaçlarını kaydetmek ve geri yüklemek için giriş ve bitiş kodu oluşturur.

> [!NOTE]
> Bir struct, Union veya Class bir işlevden değere göre döndürüldüğünde, türün tüm tanımlarının aynı olması gerekir, aksi takdirde program çalışma zamanında başarısız olabilir.

Kendi işlev giriş ve bitiş kodunuzu tanımlama hakkında daha fazla bilgi için bkz. [Naked Işlev çağrıları](../cpp/naked-function-calls.md).

X64 platformlarını hedefleyen koddaki varsayılan çağırma kuralları hakkında daha fazla bilgi için, bkz. [x64 çağırma kuralı](../build/x64-calling-convention.md). ARM platformlarını hedefleyen koddaki kural sorunlarını çağırma hakkında daha fazla bilgi için bkz. [genel C++ görsel ARM geçiş sorunları](../build/common-visual-cpp-arm-migration-issues.md).

Aşağıdaki çağırma kuralları, Visual C/C++ derleyicisi tarafından desteklenir.

|Anahtar sözcüğü|Yığın Temizleme|Parametre geçirme|
|-------------|-------------------|-----------------------|
|[__cdecl](../cpp/cdecl.md)|Çağıran|Yığındaki parametreleri ters sırada (sağdan sola) iter|
|[__clrcall](../cpp/clrcall.md)|yok|Parametreleri, CLR ifade yığınına sırasıyla (soldan sağa) yükleyin.|
|[__stdcall](../cpp/stdcall.md)|Çağrılan|Yığındaki parametreleri ters sırada (sağdan sola) iter|
|[__fastcall](../cpp/fastcall.md)|Çağrılan|Kayıtlarda depolanır ve sonra yığına gönderilir|
|[__thiscall](../cpp/thiscall.md)|Çağrılan|Yığına gönderildi; **Bu** işaretçi ecx 'te depolandı|
|[__vectorcall](../cpp/vectorcall.md)|Çağrılan|Kayıtlarda depolanır ve sonra yığına ters sırada (sağdan sola) gönderilir|

İlgili bilgiler için bkz. [eski çağırma kuralları](../cpp/obsolete-calling-conventions.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Çağırma Kuralları](../cpp/calling-conventions.md)
