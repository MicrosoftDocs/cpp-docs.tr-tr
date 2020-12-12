---
description: 'Daha fazla bilgi edinin: data_seg pragma'
title: data_seg pragması
ms.date: 08/29/2019
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
helpviewer_keywords:
- data_seg pragma
- pragmas, data_seg
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
ms.openlocfilehash: f7caff65273b2fc0d51c6bfd1cede42cce7103d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300794"
---
# <a name="data_seg-pragma"></a>data_seg pragması

Başlatılmış değişkenlerin nesne (. obj) dosyasında depolandığı veri bölümünü (segmenti) belirtir.

## <a name="syntax"></a>Syntax

> **#pragma data_seg (** ["*bölüm-adı*" [ **,** "*bölüm-sınıfı*"]] **)**\
> **#pragma data_seg (** { **Push**  |  **pop** } [ **,** *tanımlayıcı* ] [ **,** "*bölüm-adı*" [ **,** "*bölüm-sınıfı*"]] **)**

### <a name="parameters"></a>Parametreler

**hareketle**\
Seçim İç derleyici yığınına bir kayıt koyar. **Gönderim** bir *tanımlayıcıya* ve *bölüm adına* sahip olabilir.

**cağımız**\
Seçim İç derleyici yığınının en üstünden bir kaydı kaldırır. Bir **pop** bir *tanımlayıcıya* ve *bölüm adına* sahip olabilir. *Tanımlayıcıyı* kullanarak yalnızca bir **pop** komutu kullanarak birden çok kayıt ekleyebilirsiniz. *Bölüm adı* , pop 'tan sonra etkin veri bölümü adı olur.

*Tanımlayıcısını*\
Seçim **Push** ile kullanıldığında, iç derleyici yığınındaki kayda bir ad atar. **Pop** ile kullanıldığında, kayıt *kaldırıldığında, pop* 'lar iç yığının dışına çıkar. İç yığında *tanımlayıcı* bulunmazsa hiçbir şey yapılmadı.

*tanımlayıcı* , birden çok kaydın tek bir **pop** komutuyla yer almasını sağlar.

*"bölüm-adı"*\
Seçim Bir bölümün adı. **Pop** ile kullanıldığında, yığın çıkar ve *bölüm adı* etkin veri bölümü adı olur.

*"Section-Class"*\
Seçim Yoksayıldı, ancak Microsoft C++ ' ın 2,0 sürümünden önceki sürümleriyle uyumluluk için eklenmiştir.

## <a name="remarks"></a>Açıklamalar

Bir nesne dosyasındaki *bölüm* , bir birim olarak belleğe yüklenen adlandırılmış veri bloğudur. *Veri bölümü* , başlatılmış verileri içeren bir bölümdür. Bu makalede, koşullar *segmenti* ve *bölümü* aynı anlama sahiptir.

Başlatılmış değişkenler için. obj dosyasındaki varsayılan bölüm `.data` . Başlatılmamış değişkenler sıfıra başlatılmak ve ' de depolanır olarak değerlendirilir `.bss` .

**Data_seg** pragma yönergesi, derleyicinin tüm başlatılan veri öğelerini çeviri biriminden *bölüm adı* adlı bir veri bölümüne koymasını söyler. Varsayılan olarak, bir nesne dosyasındaki başlatılmış veriler için kullanılan veri bölümü adlandırılır `.data` . Başlatılmamış değişkenler sıfıra başlatılmak üzere değerlendirilir ve içinde depolanır `.bss` . *Bölüm adı* parametresi olmayan **data_seg** pragma yönergesi, sonraki başlatılmış veri öğelerinin veri bölümü adını ' a sıfırlar `.data` .

**Data_seg** kullanılarak ayrılan veriler, konumuyla ilgili hiçbir bilgiyi korumaz.

Bölüm oluşturmak için kullanılmaması gereken adların bir listesi için, bkz. [/section](../build/reference/section-specify-section-attributes.md).

Const değişkenleri ([const_seg](../preprocessor/const-seg.md)), başlatılmamış veriler ([bss_seg](../preprocessor/bss-seg.md)) ve işlevleri ([code_seg](../preprocessor/code-seg.md)) için de bölümler belirtebilirsiniz.

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

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
