---
title: 'Değer kategoriler: Lvalues ve Rvalues (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 04/06/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- R-values [C++]
- L-values [C++]
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bbe048ee6667aaf71b2a3cf52e82993f90ab1c7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32419147"
---
# <a name="lvalues-and-rvalues-visual-c"></a>Lvalues ve Rvalues (Visual C++)

Her C++ ifadesi bir türe sahip ve ait bir *değeri kategori*. Değer kategorileri derleyiciler oluştururken, kopyalama ve ifade değerlendirme sırasında geçici nesneleri taşıma izlemeniz gereken kuralların temelidir.

 C ++ 17 standart ifade değeri kategorileri şu şekilde tanımlar:

- A *glvalue* , değerlendirme bir nesne, bit alanı veya işlevi kimliğini belirleyen bir ifadedir.
- A *prvalue* , değerlendirme bir nesneyi veya bir bit alanı başlatır veya görünür durumda içerik tarafından belirtildiği gibi bir işlecinin işleneni değerini hesaplar bir ifadedir.
- Bir *xvalue* bir nesneye veya bit alanı (genellikle yaşam süresinin sonuna yakın olduğundan), kaynaklara yeniden kullanılabilir gösterir glvalue değil. [Örnek: rvalue başvuru (8.3.2) içeren ifadeler belirli türde bir dönüş türü olan bir rvalue başvuru işlevi çağrısı veya bir rvalue başvuru türüne dönüştürme gibi x değerleri verim. ]
- Bir *lvalue* bir xvalue değil glvalue değil.
- Bir *rvalue* bir prvalue ya da bir xvalue.

Aşağıdaki diyagramda kategorileri arasındaki ilişkiler gösterilmektedir:

 ![C++ ifade değeri kategorileri](media/value_categories.png "C++ ifade değeri kategorileri")

 Bir lvalue programınıza erişebilirsiniz bir adresi vardır. Lvalue ifade örnekleri dahil olmak üzere değişken adları `const` değişkenleri, dizi öğeleri lvalue başvuru, bit alanları, birleşimler ve sınıf üyeleri dönen çağrıları işlev.

 Prvalue ifade programınız tarafından erişilebilen bir adresi vardır. Prvalue ifadeleri örnekleri değişmez değerleri, bir başvuru olmayan türü dönen işlev çağrıları ve ifade evalution sırasında ancak erişilebilir yalnızca derleyici tarafından oluşturulan geçici nesneleri içerir.

 Bir adresi xvalue ifade içeriyor, erişilemez, program tarafından ancak ifade erişim sağlayan bir rvalue başvuru başlatmak için kullanılabilir. Örnekler dizi veya nesne rvalue başvuru olduğu için üye ifadeleri rvalue başvuru ve dizi alt simge, üye ve işaretçi döndüren işlev çağrılarını içerir.

## <a name="example"></a>Örnek

 Aşağıdaki örnek, birkaç doğru ve yanlış kullanım lvalues ve rvalues gösterir:

```cpp
// lvalues_and_rvalues2.cpp
int main()
{
 int i, j, *p;

 // Correct usage: the variable i is an lvalue and the literal 7 is a prvalue.
 i = 7;

 // Incorrect usage: The left operand must be an lvalue (C2106).`j * 4` is a prvalue.
 7 = i; // C2106
 j * 4 = 7; // C2106

 // Correct usage: the dereferenced pointer is an lvalue.
 *p = i;

 const int ci = 7;
 // Incorrect usage: the variable is a non-modifiable lvalue (C3892).
 ci = 9; // C3892

 // Correct usage: the conditional operator returns an lvalue.
 ((i < 3) ? i : j) = 7;
}
```

> [!NOTE]
> İşleçleri aşırı yüklü değil, bu konudaki örnekler doğru ve yanlış kullanımı gösterilmiştir. İşleç aşırı yüklemesi tarafından bir ifade gibi yapabileceğiniz `j * 4` bir lvalue.

Koşulları *lvalue* ve *rvalue* nesne başvuruları başvurduğunuzda genellikle kullanılır. Başvurular hakkında daha fazla bilgi için bkz: [Lvalue başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md) ve [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>Ayrıca Bkz.

 [Temel kavramları](../cpp/basic-concepts-cpp.md) [Lvalue başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md) [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md)