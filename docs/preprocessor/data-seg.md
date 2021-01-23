---
description: pragmaMicrosoft C/C++ ' da data_seg yönergesi hakkında daha fazla bilgi edinin
title: data_seg pragma
ms.date: 01/22/2021
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
helpviewer_keywords:
- data_seg pragma
- pragma, data_seg
no-loc:
- pragma
ms.openlocfilehash: cd0dac6961a642b8ed2bd5d485712d259d828a64
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713694"
---
# <a name="data_seg-no-locpragma"></a>`data_seg` pragma

Başlatılmış değişkenlerin nesne (. obj) dosyasında depolandığı veri bölümünü (segmenti) belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma data_seg(`** ["*bölüm-adı*" [ **`,`** "*bölüm-sınıfı*"]] **`)`**\
> **`#pragma data_seg(`**{ **`push`**  |  **`pop`** } [ **`,`** *tanımlayıcı* ] [ **`,`** "*bölüm-adı*" [ **`,`** "*bölüm-sınıfı*"]]**`)`**

### <a name="parameters"></a>Parametreler

**`push`**\
Seçim İç derleyici yığınına bir kayıt koyar. Bir **`push`** *tanımlayıcı* ve *bölüm adı* olabilir.

**`pop`**\
Seçim İç derleyici yığınının en üstünden bir kaydı kaldırır. Bir **`pop`** *tanımlayıcı* ve *bölüm adı* olabilir. Tanımlayıcıyı kullanarak yalnızca bir komutu kullanarak birden çok kayıt ekleyebilirsiniz **`pop`** .  *Bölüm adı* , pop 'tan sonra etkin veri bölümü adı olur.

*Tanımlayıcısını*\
Seçim İle kullanıldığında **`push`** , iç derleyici yığınındaki kayda bir ad atar. İle kullanıldığında **`pop`** , bir *tanıtıcı* kaldırılana kadar, pop 'lar iç yığının oturumunu kapatır. İç yığında *tanımlayıcı* bulunmazsa hiçbir şey yapılmadı.

*tanımlayıcı* , birden çok kaydın tek bir komutla birlikte olmasını sağlar **`pop`** .

*"bölüm-adı"*\
Seçim Bir bölümün adı. İle kullanıldığında **`pop`** , yığın alınır ve *bölüm adı* etkin veri bölümü adı olur.

*"Section-Class"*\
Seçim Yoksayıldı, ancak Microsoft C++ ' ın 2,0 sürümünden önceki sürümleriyle uyumluluk için eklenmiştir.

## <a name="remarks"></a>Açıklamalar

Bir nesne dosyasındaki *bölüm* , bir birim olarak belleğe yüklenen adlandırılmış veri bloğudur. *Veri bölümü* , başlatılmış verileri içeren bir bölümdür. Bu makalede, koşullar *segmenti* ve *bölümü* aynı anlama sahiptir.

Başlatılmış değişkenler için. obj dosyasındaki varsayılan bölüm `.data` . Başlatılmamış değişkenler sıfıra başlatılmak ve ' de depolanır olarak değerlendirilir `.bss` .

**`data_seg`** pragma Yönergesi derleyiciye, tüm başlatılan veri öğelerini çeviri biriminden *bölüm adı* adlı bir veri bölümüne koymasını söyler. Varsayılan olarak, bir nesne dosyasındaki başlatılmış veriler için kullanılan veri bölümü adlandırılır `.data` . Başlatılmamış değişkenler sıfıra başlatılmak üzere değerlendirilir ve içinde depolanır `.bss` . **`data_seg`** pragma *Bölüm adı* parametresi olmayan bir yönerge, sonraki başlatılmış veri öğelerinin veri bölümü adını ' a sıfırlar `.data` .

Kullanılarak ayrılan veriler **`data_seg`** , konumuyla ilgili hiçbir bilgiyi korumaz.

Bölüm oluşturmak için kullanılmaması gereken adların bir listesi için, bkz [`/SECTION`](../build/reference/section-specify-section-attributes.md) ..

Ayrıca const değişkenleri ( [`const_seg`](../preprocessor/const-seg.md) ), başlatılmamış veriler ( [`bss_seg`](../preprocessor/bss-seg.md) ) ve işlevleri () için de bölümler belirtebilirsiniz [`code_seg`](../preprocessor/code-seg.md) .

Nesne dosyalarını görüntülemek için [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) uygulamasını kullanabilirsiniz. Desteklenen her hedef mimari için DUMPBIN sürümleri Visual Studio 'Ya dahildir.

## <a name="example"></a>Örnek

```cpp
// pragma_directive_data_seg.cpp
int h = 1;                     // stored in .data
int i = 0;                     // stored in .bss
#pragma data_seg(".my_data1")
int j = 1;                     // stored in .my_data1

#pragma data_seg(push, stack1, ".my_data2")
int l = 2;                     // stored in .my_data2

#pragma data_seg(pop, stack1)   // pop stack1 off the stack
int m = 3;                     // stored in .my_data1

int main() {
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
