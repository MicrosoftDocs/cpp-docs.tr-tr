---
description: 'Daha fazla bilgi edinin: bss_seg pragma'
title: bss_seg pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
ms.openlocfilehash: e7a2cf73f8ab542755e5f6e0183896ce8e64be2a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300885"
---
# <a name="bss_seg-pragma"></a>bss_seg pragması

Başlatılmamış değişkenlerin nesne (. obj) dosyasında depolandığı bölümü (segment) belirtir.

## <a name="syntax"></a>Syntax

> **#pragma bss_seg (** ["*bölüm-adı*" [ **,** "*bölüm-sınıfı*"]] **)**\
> **#pragma bss_seg (** { **Push**  |  **pop** } [ **,** *tanımlayıcı* ] [ **,** "*bölüm-adı*" [ **,** "*bölüm-sınıfı*"]] **)**

### <a name="parameters"></a>Parametreler

**hareketle**\
Seçim İç derleyici yığınına bir kayıt koyar. **Gönderim** bir *tanımlayıcıya* ve *bölüm adına* sahip olabilir.

**cağımız**\
Seçim İç derleyici yığınının en üstünden bir kaydı kaldırır. Bir **pop** bir *tanımlayıcıya* ve *bölüm adına* sahip olabilir. *Tanımlayıcıyı* kullanarak yalnızca bir **pop** komutu kullanarak birden çok kayıt ekleyebilirsiniz. *Bölüm adı* , pop SONRASıNDA etkin BSS bölüm adı olur.

*Tanımlayıcısını*\
Seçim **Push** ile kullanıldığında, iç derleyici yığınındaki kayda bir ad atar. Pop ile kullanıldığında, *tanımlayıcı* kaldırılana kadar yönerge, iç yığının içinden **açılır**. İç yığında *tanımlayıcı* bulunmazsa hiçbir şey yapılmadı.

*"bölüm-adı"*\
Seçim Bir bölümün adı. **Pop** ile kullanıldığında, yığın çıkar ve *bölüm adı* etkin BSS bölüm adı olur.

*"Section-Class"*\
Seçim Yoksayıldı, ancak Microsoft C++ ' ın 2,0 sürümünden önceki sürümleriyle uyumluluk için eklenmiştir.

## <a name="remarks"></a>Açıklamalar

Bir nesne dosyasındaki *bölüm* , bir birim olarak belleğe yüklenen adlandırılmış veri bloğudur. *Bss bölümü* başlatılmamış veri içeren bir bölümdür. Bu makalede, koşullar *segmenti* ve *bölümü* aynı anlama sahiptir.

**Bss_seg** pragma yönergesi derleyiciye, tüm başlatılmamış veri öğelerini çeviri biriminden *bölüm adı* adlı bir BSS bölümüne koymasını söyler. Bazı durumlarda **bss_seg** kullanımı, başlatılmamış verileri tek bir bölüme gruplandırarak yükleme sürelerini hızlandırabilir. Varsayılan olarak, bir nesne dosyasındaki başlatılmamış veriler için kullanılan BSS bölümü adlandırılır `.bss` . *Bölüm adı* parametresi olmayan **bss_seg** pragma yönergesi, sonrakı başlatılmamış veri öğelerinin BSS bölüm adını ' a sıfırlar `.bss` .

**Bss_seg** pragma kullanılarak ayrılan veriler, konumuyla ilgili hiçbir bilgiyi korumaz.

Bölüm oluşturmak için kullanılmaması gereken adların bir listesi için, bkz. [/section](../build/reference/section-specify-section-attributes.md).

Başlatılmış veriler ([data_seg](../preprocessor/data-seg.md)), işlevler ([code_seg](../preprocessor/code-seg.md)) ve const değişkenleri ([const_seg](../preprocessor/const-seg.md)) için de bölümler belirtebilirsiniz.

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

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
