---
title: bss_seg | Microsoft Docs
ms.custom: ''
ms.date: 10/22/2018
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.bss_seg
- bss_seg_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, bss_seg
- bss_seg pragma
ms.assetid: 755f0154-de51-4778-97d3-c9b24e445079
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 77d234acdc02a2fefeca45ca0a925603e0ff9984
ms.sourcegitcommit: 80fc7b0452aafa36b0c915cbd29c75e1ffa25630
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50003565"
---
# <a name="bssseg"></a>bss_seg

Başlatılmamış değişkenler .obj dosyasında depolandığı segmenti belirtir.

## <a name="syntax"></a>Sözdizimi

```
#pragma bss_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )
```

### <a name="parameters"></a>Parametreler

**push**<br/>
(İsteğe bağlı) İç derleyici yığınına bir kayıt yerleştirir. A *pu*sh * olabilir bir *tanımlayıcı* ve *segment-name*.

**POP**<br/>
(İsteğe bağlı) Derleyici iç yığının en üstünden bir kayıt kaldırır.

*tanımlayıcı*<br/>
(İsteğe bağlı) İle kullanıldığında **anında iletme**, iç derleyici yığınındaki kayda bir ad atar. *tanımlayıcı* tek bir POP birden çok kayıt getirir **pop** komutu. İle kullanıldığında **pop**, yönergesi kadar iç yığından kayıtları POP *tanımlayıcı* ; kaldırılır *tanımlayıcı* bulunamazsa iç yığında hiçbir şey POP.

*"segment-name"*<br/>
(İsteğe bağlı) Segmentin adı. İle kullanıldığında **pop**, yığın silinir ve *segment-name* etkin segment adı haline gelir.

*"segment-class"*<br/>
(İsteğe bağlı) 2.0. sürümden önceki C++ ile uyumluluk için dahildir. Yoksayılır.

## <a name="remarks"></a>Açıklamalar

. Obj dosyaları görüntülenebilir [dumpbin](../build/reference/dumpbin-command-line.md) uygulama. Başlatılmamış veriler için .obj dosyasındaki varsayılan segment .bss ' dir. Bazı durumlarda kullanımını **bss_seg** hızlandırabilirsiniz yükleme sürelerini bir bölüme başlatılmamış veri gruplandırarak.

**bss_seg** hiçbir parametre olmadan için .bss kesimi sıfırlar.

Kullanılarak yer ayrılmış veri **bss_seg** pragma konumuna hakkındaki tüm bilgileri korumak değil.

Başlatılmış veriler için bölümler belirtebilirsiniz ([data_seg](../preprocessor/data-seg.md)), İşlevler ([code_seg](../preprocessor/code-seg.md)) ve const değişkenleri ([const_seg](../preprocessor/const-seg.md)).

Bkz: [/SECTION](../build/reference/section-specify-section-attributes.md) kullanmamanız bölüm oluştururken adları listesi.

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

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
