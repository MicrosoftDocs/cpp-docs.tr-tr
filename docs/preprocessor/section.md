---
title: bölüm pragması
ms.date: 08/29/2019
f1_keywords:
- section_CPP
- vc-pragma.section
helpviewer_keywords:
- pragmas, section
- section pragma
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
ms.openlocfilehash: 47ae2ff2503317e937e2b3a497357afbd5522a64
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216605"
---
# <a name="section-pragma"></a>bölüm pragması

Bir. obj dosyasında bir bölüm oluşturur.

## <a name="syntax"></a>Sözdizimi

> **#pragma bölümü (** "*bölüm-adı*" [ **,** *öznitelikler* ] **)**

## <a name="remarks"></a>Açıklamalar

Koşullar *segmenti* ve *bölümü* Bu makalede aynı anlama sahiptir.

Bir bölüm tanımlandıktan sonra, derlemenin geri kalanı için geçerli kalır. Ancak, [__declspec (allocate)](../cpp/allocate.md)kullanmanız gerekir veya bölümüne hiçbir şey konmazsınız.

*bölüm adı* , bölümün adı haline gelen gerekli bir parametredir. Ad hiçbir standart bölüm adıyla çakışmamalıdır. Bir bölüm oluştururken kullanmamanız gereki adların listesi için bkz. [/section](../build/reference/section-specify-section-attributes.md) .

*öznitelikler* , bölüme atanacak bir veya daha fazla virgülle ayrılmış özniteliği içeren isteğe bağlı bir parametredir. Olası *öznitelikler* şunlardır:

|Öznitelik|Açıklama|
|-|-|
|**read**|Verilerde okuma işlemlerine izin verir.|
|**write**|Veriler üzerinde yazma işlemlerine izin verir.|
|**yürütme**|Kodun yürütülmesini sağlar.|
|**Paylaşılan**|, Görüntüyü yükleyen tüm süreçler arasında bölümü paylaşır.|
|**nopage**|Bölümü disk belleğine değil olarak işaretler. Win32 cihaz sürücüleri için faydalıdır.|
|**NoCache**|Bölümü önbelleklenebilir olarak işaretler. Win32 cihaz sürücüleri için faydalıdır.|
|**mı**|Bölümü discardable olarak işaretler. Win32 cihaz sürücüleri için faydalıdır.|
|**remove**|Bölümü bellekte yerleşik değil olarak işaretler. Yalnızca sanal aygıt sürücüleri (V*x*D) için.|

Herhangi bir öznitelik belirtmezseniz, bölümünde **okuma** ve **yazma** öznitelikleri vardır.

## <a name="example"></a>Örnek

Bu örnekte, birinci bölüm pragması bölümü ve özniteliklerini tanımlar. Kullanılarak `mysec` `j` bildirilmemişolduğundan`__declspec(allocate)`tamsayı yerleştirmiyor. Bunun yerine `j` , veri bölümüne gider. Tamsayı `i` , `__declspec(allocate)` depolama sınıfı özniteliğinin `mysec` bir sonucu olarak ' a gider.

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
