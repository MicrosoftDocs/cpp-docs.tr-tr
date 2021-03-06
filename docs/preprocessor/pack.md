---
description: pragmaMicrosoft C/C++ ' da paket yönergesi hakkında daha fazla bilgi edinin
title: paketi pragma
ms.date: 01/22/2021
f1_keywords:
- pack_CPP
- vc-pragma.pack
helpviewer_keywords:
- pragma, pack
- pack pragma
no-loc:
- pragma
ms.openlocfilehash: 82086f737fb8918c62d40c60f1e1006985fbd827
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713421"
---
# <a name="pack-no-locpragma"></a>`pack` pragma

Yapı, birleşim ve sınıf üyeleri için paketleme hizalamasını belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma pack( show )`**\
> **`#pragma pack( push`** [ **`,`** *`identifier`* ] [ **`,`** *`n`* ] **`)`**\
> **`#pragma pack( pop`** [ **`,`** { *`identifier`* | *`n`* } ] **`)`**\
> **`#pragma pack(`** [ *`n`* ] **`)`**

### <a name="parameters"></a>Parametreler

**`show`**\
Seçim Paketleme hizalaması için geçerli bayt değerini görüntüler. Değer bir uyarı iletisiyle görüntülenir.

**`push`**\
Seçim İç derleyici yığınında geçerli paketleme hizalama değerini iter ve geçerli paketleme hizalama değerini *n* olarak ayarlar. *N* belirtilmezse, geçerli paketleme hizalama değeri gönderilir.

**`pop`**\
Seçim Kaydı, iç derleyici yığınının üst öğesinden kaldırır. *N* ile belirtilmediyse **`pop`** , yığının en üstündeki sonuç kaydıyla ilişkili paketleme değeri, yeni paketleme hizalama değeridir. *N* belirtilmişse, örneğin, `#pragma pack(pop, 16)` *n* yeni paketleme hizalama değeri haline gelir. , Örneğin, öğesini kullanarak yüklerseniz, *`identifier`* `#pragma pack(pop, r1)` yığındaki tüm kayıtlar, kayıt bulunana kadar doldurulur *`identifier`* . Bu kayıt oluşur ve yığının en üstünde bulunan kayıtla ilişkili paketleme değeri yeni paketleme hizalama değeri olur. *`identifier`* Yığın üzerinde bulunan herhangi bir kayıtta bulunmayan öğesini kullanarak öğesini seçerseniz, **`pop`** yok sayılır.

Deyimden `#pragma pack (pop, r1, 2)` `#pragma pack (pop, r1)` sonra ile eşdeğerdir `#pragma pack(2)` .

*`identifier`*\
Seçim İle kullanıldığında **`push`** , iç derleyici yığınındaki kayda bir ad atar. İle kullanıldığında **`pop`** , pop 'lar kaldırılana kadar iç yığının oturumunu kapatır *`identifier`* . *`identifier`* İç yığında bulunmazsa hiçbir şey yapılmadı.

*`n`*\
Seçim Paketleme için kullanılacak değeri bayt cinsinden belirtir. Derleyici seçeneği [`/Zp`](../build/reference/zp-struct-member-alignment.md) Modül için ayarlanmamışsa varsayılan değer *`n`* 8 ' dir. Geçerli değerler 1, 2, 4, 8 ve 16 ' dır. Bir üyenin hizalaması, bir veya birden çok, *`n`* üyenin boyutunun (hangisi daha küçükse) bir sınırında.

## <a name="remarks"></a>Açıklamalar

Bir sınıfı *paketledikten* sonra, kendi üyelerini belleğin birbirlerine doğrudan yerleştirebilirsiniz. Bu, bazı veya tüm üyelerin hedef mimarinin varsayılan hizalamadan daha küçük bir sınıra hizalanabilir anlamına gelebilir. **`pack`** veri bildirimi düzeyinde denetim sağlar. [`/Zp`](../build/reference/zp-struct-member-alignment.md)Yalnızca modül düzeyi denetim sağlayan derleyici seçeneğinden farklıdır. **paket** , **`struct`** **`union`** görünmeden sonra ilk, veya bildiriminde etkili olur **`class`** pragma . **`pack`** tanımlar üzerinde hiçbir etkisi yoktur. **`pack`** *`n`* Derleyici seçeneğinde ayarlanan değere bağımsız değişken kümeleri olmadan çağırma **`/Zp`** . Derleyici seçeneği ayarlanmamışsa, varsayılan değer x86, ARM ve ARM64 için 8 ' dir. X64 yerel için varsayılan değer 16 ' dır.

Bir yapının hizalamasını değiştirirseniz, bu, bellekte çok fazla alan kullanmayabilir. Ancak, hizalanmamış erişim için bir performans kaybı veya hatta donanım tarafından oluşturulan bir özel durum alabilirsiniz. Bu özel durum davranışını kullanarak değiştirebilirsiniz [`SetErrorMode`](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) .

Hizalamayı değiştirme hakkında daha fazla bilgi için şu makalelere bakın:

- [`alignof`](../cpp/alignof-operator.md)

- [`align`](../cpp/align-cpp.md)

- [`__unaligned`](../cpp/unaligned.md)

- [Yapı hizalaması örnekleri](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 'e özgü)

   > [!WARNING]
   > Visual Studio 2015 ve sonraki sürümlerde **`alignas`** **`alignof`** , **`__alignof`** derleyiciler arasında farklı ve taşınabilir standart ve işleçleri kullanabilirsiniz **`__declspec( align )`** . C++ standardı paketleme için adres oluşturmaz, bu nedenle **`pack`** hedef mimarinin sözcük boyutundan daha küçük hizalamaları belirtmek için (veya diğer derleyicilerde buna karşılık gelen uzantıyı) kullanmaya devam etmeniz gerekir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, **`pack`** pragma bir yapının hizalamasını değiştirmek için öğesinin nasıl kullanılacağını gösterir.

```cpp
// pragma_directives_pack.cpp
#include <stddef.h>
#include <stdio.h>

struct S {
   int i;   // size 4
   short j;   // size 2
   double k;   // size 8
};

#pragma pack(2)
struct T {
   int i;
   short j;
   double k;
};

int main() {
   printf("%zu ", offsetof(S, i));
   printf("%zu ", offsetof(S, j));
   printf("%zu\n", offsetof(S, k));

   printf("%zu ", offsetof(T, i));
   printf("%zu ", offsetof(T, j));
   printf("%zu\n", offsetof(T, k));
}
```

```Output
0 4 8
0 4 6
```

Aşağıdaki örnek, *Push*, *pop* ve *Show* sözdiziminin nasıl kullanılacağını göstermektedir.

```cpp
// pragma_directives_pack_2.cpp
// compile with: /W1 /c
#pragma pack()   // n defaults to 8; equivalent to /Zp8
#pragma pack(show)   // C4810
#pragma pack(4)   // n = 4
#pragma pack(show)   // C4810
#pragma pack(push, r1, 16)   // n = 16, pushed to stack
#pragma pack(show)   // C4810

// pop to the identifier and then set
// the value of the current packing alignment:
#pragma pack(pop, r1, 2)   // n = 2 , stack popped
#pragma pack(show)   // C4810
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
