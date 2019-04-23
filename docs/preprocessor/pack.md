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
ms.openlocfilehash: bf1ae81184d53dd271f63c26e8f9a52a6410b232
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038453"
---
# <a name="pack"></a>pack
Yapı, birleşim ve sınıf üyeleri için paketleme hizalamasını belirtir.

## <a name="syntax"></a>Sözdizimi

```
#pragma pack( [ show ] | [ push | pop ] [, identifier ] , n  )
```

### <a name="parameters"></a>Parametreler

**Show**<br/>
(İsteğe bağlı) Hizalama sevk geçerli bayt değeri görüntüler. Değer, bir uyarı iletisi görüntülenir.

**push**<br/>
(İsteğe bağlı) Bildirim geçerli paketleme hizalama değeri iç derleyici yığınındaki ve geçerli paketleme hizalama değeri için kümeleri *n*. Varsa *n* belirtilmezse, geçerli hizalama değeri paketleme gönderildi.

**POP**<br/>
(İsteğe bağlı) Kayıt, derleyici iç yığının üst kısmından kaldırır. Varsa *n* ile belirtilmemiş **pop**, yığının en üstündeki sonuç kaydıyla ilişkili paketleme değer yeni ise hizalama değeri paketleme. Varsa *n* , örneğin, belirtilen `#pragma pack(pop, 16)`, *n* yeni olur paketleme hizalama değeri. İle pop, *tanımlayıcı*, örneğin, `#pragma pack(pop, r1)`, yığında tüm kayıtları sahip kaydının kadar POP sonra *tanımlayıcı* bulunur. Kaydı silinmez ve yeni paketleme yığını üzerindeki bir sonuç kaydıyla ilişkili paket değeri olduğunu hizalama değeri. İle pop varsa bir *tanımlayıcı* bulunmayan yığını üzerinde herhangi bir kayıttaki sonra **pop** göz ardı edilir.

*tanımlayıcı*<br/>
(İsteğe bağlı) İle kullanıldığında *anında iletme*, iç derleyici yığınındaki kayda bir ad atar. İle kullanıldığında **pop**, yığından kayıtları kadar iç yığının *tanımlayıcı* ; kaldırılır *tanımlayıcı* bulunamazsa iç yığında hiçbir şey kaldırılmaz.

*n*<br/>
(İsteğe bağlı) Bayt cinsinden paketleme için kullanılacak değeri belirtir. Varsa derleyici seçeneği [/ZP](../build/reference/zp-struct-member-alignment.md) modülü için varsayılan değer ayarlanmadı *n* 8'dir. Geçerli değerler 1, 2, 4, 8 ve 16:. Bir üyenin hizalaması olduğunu veya bir sınır üzerinde katlarından biri olacak *n* veya üye boyutunun bir katı hangisi daha küçükse.

`#pragma pack(pop, identifier, n)` tanımlı değil.

## <a name="remarks"></a>Açıklamalar

Bir sınıf paketlenecek üyelerini doğrudan diğer bazı veya tüm üyeleri varsayılan hizalama hedef mimari daha küçük bir sınır üzerinde hizalanabilir gelebilir bellekte sonra yerleştirmektir. **Paketi** veri bildirimi düzeyinde denetim sağlar. Bu derleyici seçeneğini farklıdır [/ZP](../build/reference/zp-struct-member-alignment.md), modül düzeyi denetimi yalnızca sağlar. **Paketi** etkinleşir ilk **yapı**, **birleşim**, veya **sınıfı** pragma görüldüğünde sonra bildirimi. **Paketi** tanımları üzerinde hiçbir etkisi olmaz. Çağırma **paketi** hiçbir bağımsız değişken kümeleriyle *n* derleyici seçeneğini ayarlamak değerine `/Zp`. Derleyici seçeneği ayarlanmamışsa varsayılan değer 8'dir.

Bir yapının hizalanması değiştirirseniz, bellek, ancak kadar alan performans bakın veya donanım tarafından oluşturulan bir özel durum hizalanmamış erişim için bile almak kullanamazsınız.  Bu özel durum davranışını kullanarak değiştirebileceğiniz [SetErrorMode](https://msdn.microsoft.com/library/windows/desktop/ms680621).

Hizalama değiştirme hakkında daha fazla bilgi için şu konulara bakın:

- [__alignof](../cpp/alignof-operator.md)

- [align](../cpp/align-cpp.md)

- [__unaligned](../cpp/unaligned.md)

- [Yapı hizalama örnekleri](../build/x64-software-conventions.md#examples-of-structure-alignment) (x64 belirli)

   > [!WARNING]
   > Visual Studio 2015 ve sonraki işleçleri alignof ve alignas standart kullanabileceğinizi unutmayın, aksine `__alignof` ve `declspec( align )` derleyiciler arasında taşınabilen. Yine de kullanmalısınız C++ Standart paketleme, adres değil **paketi** (veya diğer derleyiciler karşılık gelen uzantının) hedef mimarisinin word boyuttan küçük hizalamaları belirtmek için.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek nasıl kullanılacağını gösterir **paketi** pragması, bir yapının hizalanması değiştirmek için.

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

Aşağıdaki örnek nasıl kullanılacağını gösterir *anında iletme*, *pop*, ve *Göster* söz dizimi.

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