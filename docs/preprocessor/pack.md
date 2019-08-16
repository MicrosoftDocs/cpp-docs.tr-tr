---
title: pack
ms.date: 12/17/2018
f1_keywords:
- pack_CPP
- vc-pragma.pack
helpviewer_keywords:
- pragmas, pack
- pack pragma
ms.assetid: e4209cbb-5437-4b53-b3fe-ac264501d404
ms.openlocfilehash: da4484ec86d39c8fa55a741eadd53a1d614b20dc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510170"
---
# <a name="pack"></a>pack
Yapı, birleşim ve sınıf üyeleri için paketleme hizalamasını belirtir.

## <a name="syntax"></a>Sözdizimi

```
#pragma pack( [ show ] | [ push | pop ] [, identifier ] , n  )
```

### <a name="parameters"></a>Parametreler

**göster**<br/>
Seçim Paketleme hizalaması için geçerli bayt değerini görüntüler. Değer bir uyarı iletisiyle görüntülenir.

**push**<br/>
Seçim İç derleyici yığınında geçerli paketleme hizalama değerini iter ve geçerli paketleme hizalama değerini *n*olarak ayarlar. *N* belirtilmemişse, geçerli paketleme hizalama değeri gönderilir.

**cağımız**<br/>
Seçim Kaydı, iç derleyici yığınının üst öğesinden kaldırır. *Hayır* , **pop**ile belirtilmediyse, yığının en üstündeki sonuç kaydıyla ilişkili paketleme değeri, yeni paketleme hizalama değeridir. *N* belirtilmişse, örneğin `#pragma pack(pop, 16)`, *n* yeni paketleme hizalama değeri haline gelir. Örneğin `#pragma pack(pop, r1)`, tanımlayıcı ile birlikte açarsanız,, *tanımlayıcı* içeren kayıt bulunana kadar yığındaki tüm kayıtlar işlenir. Bu kayıt oluşur ve en üstündeki sonuç kaydıyla ilişkili paketleme değeri, yeni paketleme hizalama değerinin yığınlamasıdır. Yığındaki herhangi bir kayıtta bulunmayan bir *tanımlayıcı* ile birlikte açarsanız, **pop** yok sayılır.

*Tanımlayıcısını*<br/>
Seçim *Push*ile kullanıldığında, iç derleyici yığınındaki kayda bir ad atar. Pop ile kullanıldığında, *tanımlayıcı* kaldırılana kadar iç yığının pop 'ları **açılır**. iç yığında *tanımlayıcı* bulunamazsa hiçbir şey yapılmadı.

*n*<br/>
Seçim Paketleme için kullanılacak değeri bayt cinsinden belirtir. Modül için [/ZP](../build/reference/zp-struct-member-alignment.md) derleyici seçeneği ayarlanmamışsa, *n* için varsayılan değer 8 ' dir. Geçerli değerler 1, 2, 4, 8 ve 16 ' dır. Üyenin hizalaması, ne kadar küçük bir değer olan *n* veya üyenin boyutunun birden çok katı olan bir sınırın üzerinde olacaktır.

`#pragma pack(pop, identifier, n)`tanımlı değil.

## <a name="remarks"></a>Açıklamalar

Bir sınıfı paketlemesini sağlamak için, üyelerini doğrudan bellekteki her bir yerde yerleştirmekten bağımsız olarak, bazı veya tüm Üyeler hedef mimarinin varsayılan hizalamadan daha küçük bir sınıra hizalanabilir anlamına gelebilir. **paket** , veri bildirimi düzeyinde denetim sağlar. Bu, yalnızca modül düzeyi denetim sağlayan [/ZP](../build/reference/zp-struct-member-alignment.md)derleyici seçeneğinden farklıdır. **paket** , pragma görüntülendikten sonra ilk **Yapı**, **birleşim**veya **sınıf** bildiriminde devreye girer. **paketin** tanımları üzerinde hiçbir etkisi yoktur. Bağımsız değişken içermeyen çağrı **paketi** , derleyici seçeneğinde `/Zp`ayarlanan değere n olarak ayarlanır. Derleyici seçeneği ayarlanmamışsa, varsayılan değer 8 ' dir.

Bir yapının hizalamasını değiştirirseniz bu, bellekte çok fazla alan kullanamaz, ancak performansın azaldığını veya hatta hizalanmamış erişim için donanım tarafından oluşturulan bir özel durum elde edebilir.  Bu özel durum davranışını [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode)kullanarak değiştirebilirsiniz.

Hizalamayı değiştirme hakkında daha fazla bilgi için şu konulara bakın:

- [__hizalaması](../cpp/alignof-operator.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [Yapı hizalaması örnekleri](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 'e özgü)

   > [!WARNING]
   > Visual Studio 2015 ve sonraki sürümlerde, derleyicilerin aksine `__alignof` ve `declspec( align )` bunlar arasında taşınabilen standart alignas ve hizalama değerlerini kullanabileceğinizi unutmayın. C++ Standart paketleme ' a yönelik değildir, bu nedenle hedef mimarinin sözcük boyutundan daha küçük hizalamaları belirtmek için **paketi** (veya diğer derleyicilerde karşılık gelen uzantıyı) kullanmaya devam etmeniz gerekir.

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
#pragma pack(pop, r1, 2)   // n = 2 , stack popped
#pragma pack(show)   // C4810
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)