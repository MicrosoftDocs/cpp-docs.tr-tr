---
title: data_seg pragması
ms.date: 08/29/2019
f1_keywords:
- data_seg_CPP
- vc-pragma.data_seg
helpviewer_keywords:
- data_seg pragma
- pragmas, data_seg
ms.assetid: 65c66466-4c98-494f-93af-106beb4caf78
ms.openlocfilehash: f67a9f39695adf5067c61288cf09ea7eb481c7dd
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220386"
---
# <a name="data_seg-pragma"></a>data_seg pragması

Başlatılmış değişkenlerin nesne (. obj) dosyasında depolandığı veri bölümünü (segmenti) belirtir.

## <a name="syntax"></a>Sözdizimi

> **#pragma data_seg (** ["*bölüm-adı*" [ **,** "*bölüm-sınıfı*"]] **)** \
> **#pragma data_seg (** { **Push** | **pop** } [ **,** *tanımlayıcı* ] [ **,** "*bölüm-adı*" [ **,** "*bölüm-sınıfı*"]] **)**

### <a name="parameters"></a>Parametreler

**hareketle**\
Seçim İç derleyici yığınına bir kayıt koyar. **Gönderim** bir *tanımlayıcıya* ve *bölüm adına*sahip olabilir.

**cağımız**\
Seçim İç derleyici yığınının en üstünden bir kaydı kaldırır. Bir **pop** bir *tanımlayıcıya* ve *bölüm adına*sahip olabilir. *Tanımlayıcıyı*kullanarak yalnızca bir **pop** komutu kullanarak birden çok kayıt ekleyebilirsiniz. *Bölüm adı* , pop 'tan sonra etkin veri bölümü adı olur.

*Tanımlayıcısını*\
Seçim **Push**ile kullanıldığında, iç derleyici yığınındaki kayda bir ad atar. **Pop**ile kullanıldığında, kayıt kaldırıldığında, pop 'lar iç yığının dışına çıkar. İç yığında *tanımlayıcı* bulunmazsa hiçbir şey yapılmadı.

*tanımlayıcı* , birden çok kaydın tek bir **pop** komutuyla yer almasını sağlar.

*"bölüm-adı"* \
Seçim Bir bölümün adı. **Pop**ile kullanıldığında, yığın çıkar ve *bölüm adı* etkin veri bölümü adı olur.

*"Section-Class"* \
Seçim Yoksayıldı, ancak sürüm 2,0 ' den önceki Microsoft C++ sürümleriyle uyumluluk için eklenmiştir.

## <a name="remarks"></a>Açıklamalar

Bir nesne dosyasındaki *bölüm* , bir birim olarak belleğe yüklenen adlandırılmış veri bloğudur. *Veri bölümü* , başlatılmış verileri içeren bir bölümdür. Bu makalede, koşullar *segmenti* ve *bölümü* aynı anlama sahiptir.

Başlatılmış değişkenler `.data`için. obj dosyasındaki varsayılan bölüm. Başlatılmamış değişkenler sıfıra başlatılmak ve ' de `.bss`depolanır olarak değerlendirilir.

**Data_seg** pragma yönergesi derleyiciye, tüm başlatılan veri öğelerini çeviri biriminden *bölüm adı*adlı bir veri bölümüne koymasını söyler. Varsayılan olarak, bir nesne dosyasındaki başlatılmış veriler için kullanılan veri bölümü adlandırılır `.data`. Başlatılmamış değişkenler sıfıra başlatılmak üzere değerlendirilir ve içinde `.bss`depolanır. *Bölüm adı* parametresi olmayan bir `.data` **data_seg** pragma yönergesi, sonraki başlatılmış veri öğelerinin veri bölümü adını ' a sıfırlar.

**Data_seg** kullanılarak ayrılan veriler, konumuyla ilgili hiçbir bilgiyi korumaz.

Bölüm oluşturmak için kullanılmaması gereken adların bir listesi için, bkz. [/section](../build/reference/section-specify-section-attributes.md).

Const değişkenleri ([const_seg](../preprocessor/const-seg.md)), başlatılmamış veriler ([bss_seg](../preprocessor/bss-seg.md)) ve işlevler ([code_seg](../preprocessor/code-seg.md)) için de bölümler belirtebilirsiniz.

Dumpbin ' i kullanabilirsiniz [. ](../build/reference/dumpbin-command-line.md)Nesne dosyalarını görüntülemek IÇIN exe uygulaması. Desteklenen her hedef mimari için DUMPBIN sürümleri Visual Studio 'Ya dahildir.

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
