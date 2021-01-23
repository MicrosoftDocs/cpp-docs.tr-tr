---
description: pragmaMicrosoft C/C++ ' da const_seg yönergesi hakkında daha fazla bilgi edinin
title: const_seg pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.const_seg
- const_seg_CPP
helpviewer_keywords:
- pragma, const_seg
- const_seg pragma
no-loc:
- pragma
ms.openlocfilehash: 602ef749c966f9b28d7d6fa42a2bded1148bbe0d
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712927"
---
# <a name="const_seg-no-locpragma"></a>`const_seg` pragma

[Const](../cpp/const-cpp.md) değişkenlerinin nesne (. obj) dosyasında depolandığı bölümü (segmenti) belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma const_seg(`** ["*bölüm-adı*" [ **`,`** "*bölüm-sınıfı*"]] **`)`**\
> **`#pragma const_seg(`**{ **`push`**  |  **`pop`** } [ **`,`** *tanımlayıcı* ] [ **`,`** "*bölüm-adı*" [ **`,`** "*bölüm-sınıfı*"]]**`)`**

### <a name="parameters"></a>Parametreler

**`push`**\
Seçim İç derleyici yığınına bir kayıt koyar. Bir **`push`** *tanımlayıcı* ve *bölüm adı* olabilir.

**`pop`**\
Seçim İç derleyici yığınının en üstünden bir kaydı kaldırır. Bir **`pop`** *tanımlayıcı* ve *bölüm adı* olabilir. Tanımlayıcıyı kullanarak yalnızca bir komutu kullanarak birden çok kayıt ekleyebilirsiniz **`pop`** .  *Bölüm adı* , pop sonrasında etkin const bölüm adı olur.

*Tanımlayıcısını*\
Seçim İle kullanıldığında **`push`** , iç derleyici yığınındaki kayda bir ad atar. İle birlikte kullanıldığında **`pop`** , *tanıtıcı* kaldırılana kadar yönerge, iç yığının içinden açılır. İç yığında *tanımlayıcı* bulunmazsa hiçbir şey yapılmadı.

"*bölüm-adı*" \
Seçim Bir bölümün adı. İle kullanıldığında **`pop`** , yığın alınır ve *bölüm adı* etkin const bölüm adı olur.

"*bölüm-sınıfı*" \
Seçim Yoksayıldı, ancak Microsoft C++ ' ın 2,0 sürümünden önceki sürümleriyle uyumluluk için eklenmiştir.

## <a name="remarks"></a>Açıklamalar

Bir nesne dosyasındaki *bölüm* , bir birim olarak belleğe yüklenen adlandırılmış veri bloğudur. *Const bölümü* , sabit veri içeren bir bölümdür. Bu makalede, koşullar *segmenti* ve *bölümü* aynı anlama sahiptir.

**`const_seg`** pragma Yönergesi derleyiciye çeviri biriminden tüm sabit veri öğelerini *bölüm adı* adlı bir const bölümüne koymasını söyler. Değişkenler için nesne dosyasındaki varsayılan bölüm **`const`** `.rdata` . Yapı değerleri gibi bazı **`const`** değişkenler otomatik olarak kod akışına eklenir. Satır içi kod içinde görünmez `.rdata` . **`const_seg`** pragma *Bölüm adı* parametresi olmayan bir yönerge, sonraki **`const`** veri öğelerinin bölüm adını olarak sıfırlar `.rdata` .

Bir içinde dinamik başlatma gerektiren bir nesne tanımlarsanız `const_seg` , sonuç tanımsız bir davranıştır.

Bölüm oluşturmak için kullanılmaması gereken adların bir listesi için, bkz [`/SECTION`](../build/reference/section-specify-section-attributes.md) ..

Başlatılmış veriler ( [`data_seg`](../preprocessor/data-seg.md) ), başlatılmamış veriler () [`bss_seg`](../preprocessor/bss-seg.md) ve işlevler () için de bölümler belirtebilirsiniz [`code_seg`](../preprocessor/code-seg.md) .

Nesne dosyalarını görüntülemek için [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) uygulamasını kullanabilirsiniz. Desteklenen her hedef mimari için DUMPBIN sürümleri Visual Studio 'Ya dahildir.

## <a name="example"></a>Örnek

```cpp
// pragma_directive_const_seg.cpp
// compile with: /EHsc
#include <iostream>

const int i = 7;               // inlined, not stored in .rdata
const char sz1[]= "test1";     // stored in .rdata

#pragma const_seg(".my_data1")
const char sz2[]= "test2";     // stored in .my_data1

#pragma const_seg(push, stack1, ".my_data2")
const char sz3[]= "test3";     // stored in .my_data2

#pragma const_seg(pop, stack1) // pop stack1 from stack
const char sz4[]= "test4";     // stored in .my_data1

int main() {
    using namespace std;
   // const data must be referenced to be put in .obj
   cout << sz1 << endl;
   cout << sz2 << endl;
   cout << sz3 << endl;
   cout << sz4 << endl;
}
```

```Output
test1
test2
test3
test4
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
