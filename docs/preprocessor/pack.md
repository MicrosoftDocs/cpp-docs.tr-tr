---
title: pack pragması
ms.date: 11/11/2019
f1_keywords:
- pack_CPP
- vc-pragma.pack
helpviewer_keywords:
- pragmas, pack
- pack pragma
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
ms.openlocfilehash: 335289802b6c370158fc655646b710914a07a3f5
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80160339"
---
# <a name="pack-pragma"></a>pack pragması

Yapı, birleşim ve sınıf üyeleri için paketleme hizalamasını belirtir.

## <a name="syntax"></a>Sözdizimi

> **#pragma paketi (göster)** \
> **#pragma paketi (push** [ **,** *tanımlayıcı* ] [ **,** *n* ] **)** \
> **#pragma Pack (pop** [ **,** { *Identifier* | *n* }] **)** \
> **#pragma paketi (** [ *n* ] **)**

### <a name="parameters"></a>Parametreler

\ **göster**
Seçim Paketleme hizalaması için geçerli bayt değerini görüntüler. Değer bir uyarı iletisiyle görüntülenir.

**gönderim**\
Seçim İç derleyici yığınında geçerli paketleme hizalama değerini iter ve geçerli paketleme hizalama değerini *n*olarak ayarlar. *N* belirtilmezse, geçerli paketleme hizalama değeri gönderilir.

**pop**\
Seçim Kaydı, iç derleyici yığınının üst öğesinden kaldırır. *Hayır* , **pop**ile belirtilmediyse, yığının en üstündeki sonuç kaydıyla ilişkili paketleme değeri, yeni paketleme hizalama değeridir. *N* belirtilirse, örneğin `#pragma pack(pop, 16)`, *n* yeni paketleme hizalama değeri haline gelir. Bir *tanımlayıcı*kullanarak (örneğin, `#pragma pack(pop, r1)`) seçerseniz, yığındaki tüm kayıtlar, *tanımlayıcı* bulunana kadar doldurulur. Bu kayıt oluşur ve yığının en üstündeki sonuç kaydıyla ilişkili paketleme değeri yeni paketleme hizalama değeridir. Yığındaki herhangi bir kayıtta bulunmayan bir *tanımlayıcıyı* kullanarak öğesini seçerseniz, **pop** yok sayılır.

`#pragma pack (pop, r1, 2)` deyimin `#pragma pack (pop, r1)`, ardından `#pragma pack(2)`ile eşdeğerdir.

*tanımlayıcı*\
Seçim **Push**ile kullanıldığında, iç derleyici yığınındaki kayda bir ad atar. **Pop**ile kullanıldığında, kayıt *kaldırıldığında, pop* 'lar iç yığının dışına çıkar. İç yığında *tanımlayıcı* bulunmazsa hiçbir şey yapılmadı.

*n*\
Seçim Paketleme için kullanılacak değeri bayt cinsinden belirtir. Modül için [/ZP](../build/reference/zp-struct-member-alignment.md) derleyici seçeneği ayarlanmamışsa, *n* için varsayılan değer 8 ' dir. Geçerli değerler 1, 2, 4, 8 ve 16 ' dır. Bir üyenin hizalaması, *n*' nin katı olan veya üyenin boyutunun (hangisi daha küçükse) bir sınırından fazla.

## <a name="remarks"></a>Açıklamalar

Bir sınıfı *paketledikten* sonra, kendi üyelerini belleğin birbirlerine doğrudan yerleştirebilirsiniz. Bu, bazı veya tüm üyelerin hedef mimarinin varsayılan hizalamadan daha küçük bir sınıra hizalanabilir anlamına gelebilir. **paket** , veri bildirimi düzeyinde denetim sağlar. Yalnızca modül düzeyi denetim sağlayan [/ZP](../build/reference/zp-struct-member-alignment.md)derleyici seçeneğinden farklıdır. **paket** , pragma görüntülendikten sonra ilk **Yapı**, **birleşim**veya **sınıf** bildiriminde devreye girer. **paketin** tanımları üzerinde hiçbir etkisi yoktur. Bağımsız değişken içermeyen çağrı **paketi** , `/Zp`derleyici seçeneğinde ayarlanan *değere ayarlanır.* Derleyici seçeneği ayarlanmamışsa, varsayılan değer 8 ' dir.

Bir yapının hizalamasını değiştirirseniz bu, bellekte çok fazla alan kullanamaz, ancak performansın azaldığını veya hatta hizalanmamış erişim için donanım tarafından oluşturulan bir özel durum elde edebilir.  Bu özel durum davranışını [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode)kullanarak değiştirebilirsiniz.

Hizalamayı değiştirme hakkında daha fazla bilgi için şu makalelere bakın:

- [__alignof](../cpp/alignof-operator.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [Yapı hizalaması örnekleri](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 'e özgü)

   > [!WARNING]
   > Visual Studio 2015 ve sonraki sürümlerde, `__alignof` ve `declspec( align )` farklı olarak derleyiciler arasında taşınabilen standart **alignas** ve **Hizalama** işleçlerini kullanabilirsiniz. C++ Standart paketleme, bu nedenle hedef mimarinin sözcük boyutundan daha küçük hizalamaları belirtmek için **paketi** (veya diğer derleyicilerde karşılık gelen uzantıyı) kullanmaya devam etmeniz gerekir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, bir yapının hizalamasını değiştirmek için **Pack** pragma 'ın nasıl kullanılacağını gösterir.

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

Aşağıdaki örnek, *Push*, *pop*ve *Show* sözdiziminin nasıl kullanılacağını göstermektedir.

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

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
