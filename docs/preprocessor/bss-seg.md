---
description: pragmaMicrosoft C/C++ ' da bss_seg yönergesi hakkında daha fazla bilgi edinin
title: bss_seg pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
helpviewer_keywords:
- pragma, bss_seg
- bss_seg pragma
no-loc:
- pragma
ms.openlocfilehash: 380d3c465145c3409e86ea6e76cd0b41890574fa
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713108"
---
# <a name="bss_seg-no-locpragma"></a>`bss_seg` pragma

Başlatılmamış değişkenlerin nesne (. obj) dosyasında depolandığı bölümü (segment) belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma bss_seg(`** ["*bölüm-adı*" [ **`,`** "*bölüm-sınıfı*"]] **`)`**\
> **`#pragma bss_seg(`**{ **`push`**  |  **`pop`** } [ **`,`** *tanımlayıcı* ] [ **`,`** "*bölüm-adı*" [ **`,`** "*bölüm-sınıfı*"]]**`)`**

### <a name="parameters"></a>Parametreler

**`push`**\
Seçim İç derleyici yığınına bir kayıt koyar. Bir **`push`** *tanımlayıcı* ve *bölüm adı* olabilir.

**`pop`**\
Seçim İç derleyici yığınının en üstünden bir kaydı kaldırır. Bir **`pop`** *tanımlayıcı* ve *bölüm adı* olabilir. Tanımlayıcıyı kullanarak yalnızca bir komutu kullanarak birden çok kayıt ekleyebilirsiniz **`pop`** .  *Bölüm adı* , pop SONRASıNDA etkin BSS bölüm adı olur.

*Tanımlayıcısını*\
Seçim İle kullanıldığında **`push`** , iç derleyici yığınındaki kayda bir ad atar. İle birlikte kullanıldığında **`pop`** , *tanıtıcı* kaldırılana kadar yönerge, iç yığının içinden açılır. İç yığında *tanımlayıcı* bulunmazsa hiçbir şey yapılmadı.

*"bölüm-adı"*\
Seçim Bir bölümün adı. İle kullanıldığında **`pop`** , yığın alınır ve *bölüm adı* etkin BSS bölüm adı olur.

*"Section-Class"*\
Seçim Yoksayıldı, ancak Microsoft C++ ' ın 2,0 sürümünden önceki sürümleriyle uyumluluk için eklenmiştir.

## <a name="remarks"></a>Açıklamalar

Bir nesne dosyasındaki *bölüm* , bir birim olarak belleğe yüklenen adlandırılmış veri bloğudur. *Bss bölümü* başlatılmamış veri içeren bir bölümdür. Bu makalede, koşullar *segmenti* ve *bölümü* aynı anlama sahiptir.

**`bss_seg`** pragma Yönergesi derleyiciye, tüm başlatılmamış veri öğelerini çeviri biriminden *bölüm adı* adlı bir BSS bölümüne koymasını söyler. Bazı durumlarda, ' nin kullanımı, **`bss_seg`** Başlatılmamış verileri tek bir bölümde gruplandırarak yükleme sürelerini hızlandırabilir. Varsayılan olarak, bir nesne dosyasındaki başlatılmamış veriler için kullanılan BSS bölümü adlandırılır `.bss` . **`bss_seg`** pragma *Bölüm adı* parametresi olmayan bir yönerge, sonrakı başlatılmamış veri öğelerinin BSS bölüm adını ' a sıfırlar `.bss` .

Kullanılarak ayrılan veriler, **`bss_seg`** pragma konumuyla ilgili hiçbir bilgiyi korumaz.

Bölüm oluşturmak için kullanılmaması gereken adların bir listesi için, bkz [`/SECTION`](../build/reference/section-specify-section-attributes.md) ..

Başlatılmış veriler ( [`data_seg`](../preprocessor/data-seg.md) ), işlevler ( [`code_seg`](../preprocessor/code-seg.md) ) ve const değişkenleri () için de bölümler belirtebilirsiniz [`const_seg`](../preprocessor/const-seg.md) .

Nesne dosyalarını görüntülemek için [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) uygulamasını kullanabilirsiniz. Desteklenen her hedef mimari için DUMPBIN sürümleri Visual Studio 'Ya dahildir.

## <a name="example"></a>Örnek

```cpp
// pragma_directive_bss_seg.cpp
int i;                     // stored in .bss
#pragma bss_seg(".my_data1")
int j;                     // stored in .my_data1

#pragma bss_seg(push, stack1, ".my_data2")
int l;                     // stored in .my_data2

#pragma bss_seg(pop, stack1)   // pop stack1 from stack
int m;                     // stored in .my_data1

int main() {
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
