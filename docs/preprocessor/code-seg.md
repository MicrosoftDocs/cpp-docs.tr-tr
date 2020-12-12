---
description: 'Daha fazla bilgi edinin: code_seg pragma'
title: code_seg pragması
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.code_seg
helpviewer_keywords:
- pragmas, code_seg
- code_seg pragma
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
ms.openlocfilehash: c303d7e86dc94be3c3d76368b92915cd06010567
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300846"
---
# <a name="code_seg-pragma"></a>code_seg pragması

İşlevlerin nesne (. obj) dosyasında depolandığı metin bölümünü (kesim) belirtir.

## <a name="syntax"></a>Syntax

> **#pragma code_seg (** ["*bölüm-adı*" [ **,** "*bölüm-sınıfı*"]] **)**\
> **#pragma code_seg (** { **Push**  |  **pop** } [ **,** *tanımlayıcı* ] [ **,** "*bölüm-adı*" [ **,** "*bölüm-sınıfı*"]] **)**

### <a name="parameters"></a>Parametreler

**hareketle**\
Seçim İç derleyici yığınına bir kayıt koyar. **Gönderim** bir *tanımlayıcıya* ve *bölüm adına* sahip olabilir.

**cağımız**\
Seçim İç derleyici yığınının en üstünden bir kaydı kaldırır. Bir **pop** bir *tanımlayıcıya* ve *bölüm adına* sahip olabilir. *Tanımlayıcıyı* kullanarak yalnızca bir **pop** komutu kullanarak birden çok kayıt ekleyebilirsiniz. *Bölüm adı* , pop 'tan sonra etkin metin bölümü adı olur.

*Tanımlayıcısını*\
Seçim **Push** ile kullanıldığında, iç derleyici yığınındaki kayda bir ad atar. Pop ile kullanıldığında, *tanımlayıcı* kaldırılana kadar yönerge, iç yığının içinden **açılır**. İç yığında *tanımlayıcı* bulunmazsa hiçbir şey yapılmadı.

"*bölüm-adı*" \
Seçim Bir bölümün adı. **Pop** ile kullanıldığında, yığın çıkar ve *bölüm adı* etkin metin bölümü adı olur.

"*bölüm-sınıfı*" \
Seçim Yoksayıldı, ancak Microsoft C++ ' ın 2,0 sürümünden önceki sürümleriyle uyumluluk için eklenmiştir.

## <a name="remarks"></a>Açıklamalar

Bir nesne dosyasındaki *bölüm* , bir birim olarak belleğe yüklenen adlandırılmış veri bloğudur. Bir *metin bölümü* , yürütülebilir kod içeren bir bölümdür. Bu makalede, koşullar *segmenti* ve *bölümü* aynı anlama sahiptir.

**Code_seg** pragma yönergesi derleyiciye, sonraki tüm nesne kodunu çeviri biriminden *bölüm adı* adlı bir metin bölümüne koymasını söyler. Varsayılan olarak, bir nesne dosyasındaki işlevler için kullanılan metin bölümü adlandırılır `.text` . *Bölüm adı* parametresi olmayan bir **code_seg** pragma yönergesi, sonraki nesne kodunun metin bölümü adını olarak sıfırlar `.text` .

**Code_seg** pragma yönergesi, Örneklenmiş şablonlar için oluşturulan nesne kodunun yerleşimini denetlemez. Ayrıca, özel üye işlevleri gibi derleyici tarafından örtülü olarak oluşturulan kodu denetler. Bu kodu denetlemek için, bunun yerine [__declspec (code_seg (...))](../cpp/code-seg-declspec.md) özniteliğini kullanmanızı öneririz. Derleyicinin ürettiği kod dahil olmak üzere tüm nesne kodunun yerleştirilmesi üzerinde denetim sağlar.

Bölüm oluşturmak için kullanılmaması gereken adların bir listesi için, bkz. [/section](../build/reference/section-specify-section-attributes.md).

Başlatılmış veriler ([data_seg](../preprocessor/data-seg.md)), başlatılmamış veriler ([bss_seg](../preprocessor/bss-seg.md)) ve const değişkenleri ([const_seg](../preprocessor/const-seg.md)) için de bölümler belirtebilirsiniz.

Nesne dosyalarını görüntülemek için [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) uygulamasını kullanabilirsiniz. Desteklenen her hedef mimari için DUMPBIN sürümleri Visual Studio 'Ya dahildir.

## <a name="example"></a>Örnek

Bu örnek, nesne kodunun nereye yerleştirileceğini denetlemek için **code_seg** pragma yönergesinin nasıl kullanılacağını gösterir:

```cpp
// pragma_directive_code_seg.cpp
void func1() {                  // stored in .text
}

#pragma code_seg(".my_data1")
void func2() {                  // stored in my_data1
}

#pragma code_seg(push, r1, ".my_data2")
void func3() {                  // stored in my_data2
}

#pragma code_seg(pop, r1)      // stored in my_data1
void func4() {
}

int main() {
}
```

## <a name="see-also"></a>Ayrıca bkz.

[code_seg (__declspec)](../cpp/code-seg-declspec.md)\
[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
