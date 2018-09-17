---
title: Parametre geçirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: e838ee5f-c2fe-40b0-9a23-8023c949c820
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e8db6b61936b2122cd984e594c1ff3f162fa3dfe
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45724457"
---
# <a name="parameter-passing"></a>Parametre Geçirme

İlk dört tamsayı bağımsız değişkeni kayıtlara geçirilir. Tamsayı değerleri (sırayla soldan sağa) RCX, RDX, R8 ve R9 geçirilir. Bağımsız değişkenler 5 ve üzeri yığına geçirilir. Yazmaçlarda sağa yaslanmış tüm bağımsız değişkenler. Aranan üst bitlerini yoksayabilirsiniz şekilde yapıldığını olması ve yalnızca gerekli kayıt bölümü erişebilirsiniz.

Kayan nokta ve çift duyarlıklı bağımsız değişkenler XMM0'da geçirilir: XMM3 (avc'de 4) genellikle söz konusu olan Kardinal yuvası için kullanılacak tamsayı yuvayı (RCX, RDX, R8 ve R9) ile (örneğe bakın) yoksayıldı ve bunun tersi de geçerlidir.

[__m128](../cpp/m128.md) türleri, diziler ve dizeleri hiçbir zaman hemen değerine göre geçirilir, ancak bunun yerine bir işaretçi çağırıcı tarafından ayrılan bellek geçirilir. Aynı boyutta tamsayı değilmiş gibi yapılar/birleşimler boyutu 8, 16, 32 veya 64 bit ve __m64 geçirilir. Bu boyutları dışında yapılar/birleşimler, çağırıcı tarafından ayrılan bellek için bir işaretçi olarak geçirilir. Bu toplam değer türleri için bir işaretçi olarak geçirilen (dahil olmak üzere \__m128), arayana ayrılan geçici bellek 16 bayt hizalı olacaktır.

Yığın alanı ayrılamadı. ve diğer işlevleri çağırmayın iç işlevleri diğer geçici kayıtları, derleyici iç işlev uygulaması arasındaki sıkı bağlamanın olduğundan ek yazmaç bağımsız değişkenleri geçirmek için kullanabilirsiniz. Bu, performansı artırmak için ek bir fırsattır.

Çağrılan kayıt parametreleri gerekirse kendi gölge alanı dökme sorumluluğuna sahip.

Parametrelerin nasıl geçirildiğini aşağıdaki tabloda özetlenmiştir:

|Parametre türü|Nasıl geçti|
|--------------------|----------------|
|Kayan nokta|İlk 4 parametre - XMM0 ila XMM3. Diğerleri, yığın olarak geçirilir.|
|Tamsayı|İlk 4 parametre - RCX, RDX, R8'de, R9. Diğerleri, yığın olarak geçirilir.|
|Toplamlar (8, 16, 32 veya 64 bit) ve __m64|İlk 4 parametre - RCX, RDX, R8'de, R9. Diğerleri, yığın olarak geçirilir.|
|Toplamlar (diğer)|İşaretçi tarafından. İlk 4 parametre RCX, RDX, R8 ve R9 işaretçi olarak geçirildi|
|__m128|İşaretçi tarafından. İlk 4 parametre RCX, RDX, R8 ve R9 işaretçi olarak geçirildi|

## <a name="example-of-argument-passing-1---all-integers"></a>Bağımsız değişken geçirme 1 - tüm tamsayıların örneği

```
func1(int a, int b, int c, int d, int e);
// a in RCX, b in RDX, c in R8, d in R9, e pushed on stack
```

## <a name="example-of-argument-passing-2---all-floats"></a>Bağımsız değişken 2 - tüm float'lar geçirme örneği

```
func2(float a, double b, float c, double d, float e);
// a in XMM0, b in XMM1, c in XMM2, d in XMM3, e pushed on stack
```

## <a name="example-of-argument-passing-3---mixed-ints-and-floats"></a>Bağımsız değişken 3 - karma tamsayılar ve float'lar geçirme örneği

```
func3(int a, double b, int c, float d);
// a in RCX, b in XMM1, c in R8, d in XMM3
```

## <a name="example-of-argument-passing-4--m64-m128-and-aggregates"></a>Bağımsız değişken geçirme 4 örneği-__m64, \__m128 ve toplamlar

```
func4(__m64 a, _m128 b, struct c, float d);
// a in RCX, ptr to b in RDX, ptr to c in R8, d in XMM3
```

## <a name="see-also"></a>Ayrıca Bkz.

[Çağırma Kuralı](../build/calling-convention.md)