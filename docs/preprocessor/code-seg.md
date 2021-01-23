---
description: pragmaMicrosoft C/C++ ' da code_seg yönergesi hakkında daha fazla bilgi edinin
title: code_seg pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.code_seg
helpviewer_keywords:
- pragma, code_seg
- code_seg pragma
no-loc:
- pragma
ms.openlocfilehash: 0547c745fe5d22be3684e83e0dcc2c73e13e8edc
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713109"
---
# <a name="code_seg-no-locpragma"></a>`code_seg` pragma

İşlevlerin nesne (. obj) dosyasında depolandığı metin bölümünü (kesim) belirtir.

## <a name="syntax"></a>Syntax

> **`#pragma code_seg(`** ["*bölüm-adı*" [ **`,`** "*bölüm-sınıfı*"]] **`)`**\
> **`#pragma code_seg(`**{ **`push`**  |  **`pop`** } [ **`,`** *tanımlayıcı* ] [ **`,`** "*bölüm-adı*" [ **`,`** "*bölüm-sınıfı*"]]**`)`**

### <a name="parameters"></a>Parametreler

**`push`**\
Seçim İç derleyici yığınına bir kayıt koyar. Bir **`push`** *tanımlayıcı* ve *bölüm adı* olabilir.

**`pop`**\
Seçim İç derleyici yığınının en üstünden bir kaydı kaldırır. Bir **`pop`** *tanımlayıcı* ve *bölüm adı* olabilir. Tanımlayıcıyı kullanarak yalnızca bir komutu kullanarak birden çok kayıt ekleyebilirsiniz **`pop`** .  *Bölüm adı* , pop 'tan sonra etkin metin bölümü adı olur.

*Tanımlayıcısını*\
Seçim İle kullanıldığında **`push`** , iç derleyici yığınındaki kayda bir ad atar. İle birlikte kullanıldığında **`pop`** , *tanıtıcı* kaldırılana kadar yönerge, iç yığının içinden açılır. İç yığında *tanımlayıcı* bulunmazsa hiçbir şey yapılmadı.

"*bölüm-adı*" \
Seçim Bir bölümün adı. İle kullanıldığında **`pop`** , yığın alınır ve *bölüm adı* etkin metin bölümü adı olur.

"*bölüm-sınıfı*" \
Seçim Yoksayıldı, ancak Microsoft C++ ' ın 2,0 sürümünden önceki sürümleriyle uyumluluk için eklenmiştir.

## <a name="remarks"></a>Açıklamalar

Bir nesne dosyasındaki *bölüm* , bir birim olarak belleğe yüklenen adlandırılmış veri bloğudur. Bir *metin bölümü* , yürütülebilir kod içeren bir bölümdür. Bu makalede, koşullar *segmenti* ve *bölümü* aynı anlama sahiptir.

**`code_seg`** pragma Yönergesi derleyiciye, sonraki tüm nesne kodunu çeviri biriminden *bölüm adı* adlı bir metin bölümüne koymasını söyler. Varsayılan olarak, bir nesne dosyasındaki işlevler için kullanılan metin bölümü adlandırılır `.text` . **`code_seg`** pragma *Bölüm adı* parametresi olmayan bir yönerge, sonraki nesne kodu için metin bölümü adını ' a sıfırlar `.text` .

**`code_seg`** pragma Yönergesi, Örneklenmiş şablonlar için oluşturulan nesne kodunun yerleşimini denetlemez. Ayrıca, özel üye işlevleri gibi derleyici tarafından örtülü olarak oluşturulan kodu denetler. Bu kodu denetlemek için, [`__declspec(code_seg(...))`](../cpp/code-seg-declspec.md) bunun yerine özniteliğini kullanmanızı öneririz. Derleyicinin ürettiği kod dahil olmak üzere tüm nesne kodunun yerleştirilmesi üzerinde denetim sağlar.

Bölüm oluşturmak için kullanılmaması gereken adların bir listesi için, bkz [`/SECTION`](../build/reference/section-specify-section-attributes.md) ..

Başlatılmış veriler ( [`data_seg`](../preprocessor/data-seg.md) ), başlatılmamış veriler ( [`bss_seg`](../preprocessor/bss-seg.md) ) ve const değişkenleri () için de bölümler belirtebilirsiniz [`const_seg`](../preprocessor/const-seg.md) .

Nesne dosyalarını görüntülemek için [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) uygulamasını kullanabilirsiniz. Desteklenen her hedef mimari için DUMPBIN sürümleri Visual Studio 'Ya dahildir.

## <a name="example"></a>Örnek

Bu örnek,  pragma nesne kodunun nereye yerleştirileceğini denetlemek için code_seg yönergesinin nasıl kullanılacağını gösterir:

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

[`code_seg (__declspec)`](../cpp/code-seg-declspec.md)\
[Pragma yönergeleri ve `__pragma` ve `_Pragma` anahtar sözcükleri](./pragma-directives-and-the-pragma-keyword.md)
