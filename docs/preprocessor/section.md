---
description: 'Daha fazla bilgi edinin: Section pragma'
title: bölüm pragması
ms.date: 08/29/2019
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
ms.openlocfilehash: f4a719c60fd5bdf4f8e8841aab88f82c30b92a95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342289"
---
# <a name="section-pragma"></a>bölüm pragması

Bir. obj dosyasında bir bölüm oluşturur.

## <a name="syntax"></a>Syntax

> **#pragma bölümü (** "*bölüm-adı*" [ **,** *öznitelikler* ] **)**

## <a name="remarks"></a>Açıklamalar

Koşullar *segmenti* ve *bölümü* Bu makalede aynı anlama sahiptir.

Bir bölüm tanımlandıktan sonra, derlemenin geri kalanı için geçerli kalır. Ancak, [__declspec (tahsis)](../cpp/allocate.md)kullanmanız gerekir veya bölüme hiçbir şey yerleştirilmelidir.

*bölüm adı* , bölümün adı haline gelen gerekli bir parametredir. Ad hiçbir standart bölüm adıyla çakışmamalıdır. Bir bölüm oluştururken kullanmamanız gereki adların listesi için bkz. [/section](../build/reference/section-specify-section-attributes.md) .

*öznitelikler* , bölüme atanacak bir veya daha fazla virgülle ayrılmış özniteliği içeren isteğe bağlı bir parametredir. Olası *öznitelikler* şunlardır:

|Öznitelik|Açıklama|
|-|-|
|**okuyamaz**|Verilerde okuma işlemlerine izin verir.|
|**write**|Veriler üzerinde yazma işlemlerine izin verir.|
|**yürütme**|Kodun yürütülmesini sağlar.|
|**Paylaşılan**|, Görüntüyü yükleyen tüm süreçler arasında bölümü paylaşır.|
|**nopage**|Bölümü disk belleğine değil olarak işaretler. Win32 cihaz sürücüleri için faydalıdır.|
|**NoCache**|Bölümü önbelleklenebilir olarak işaretler. Win32 cihaz sürücüleri için faydalıdır.|
|**mı**|Bölümü discardable olarak işaretler. Win32 cihaz sürücüleri için faydalıdır.|
|**temizlenmesine**|Bölümü bellekte yerleşik değil olarak işaretler. Yalnızca sanal aygıt sürücüleri (V *x* D) için.|

Herhangi bir öznitelik belirtmezseniz, bölümünde **okuma** ve **yazma** öznitelikleri vardır.

## <a name="example"></a>Örnek

Bu örnekte, birinci bölüm pragması bölümü ve özniteliklerini tanımlar. `j`Kullanılarak bildirilmemiş olduğundan tamsayı yerleştirmiyor `mysec` `__declspec(allocate)` . Bunun yerine, `j` veri bölümüne gider. Tamsayı, `i` `mysec` depolama sınıfı özniteliğinin bir sonucu olarak ' a gider `__declspec(allocate)` .

```cpp
// pragma_section.cpp
#pragma section("mysec",read,write)
int j = 0;

__declspec(allocate("mysec"))
int i = 0;

int main(){}
```

## <a name="see-also"></a>Ayrıca bkz.

[Pragma yönergeleri ve __pragma anahtar sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
