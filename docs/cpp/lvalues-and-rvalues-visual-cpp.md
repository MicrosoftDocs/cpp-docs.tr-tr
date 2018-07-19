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
ms.openlocfilehash: ed6f9a11b6cf2a0045729acbc79d8e45103064ea
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37940192"
---
# <a name="lvalues-and-rvalues-visual-c"></a>Lvalues ve Rvalues (Visual C++)

Her bir C++ ifadesi bir türe sahiptir ve ait olduğu bir *değeri kategori*. Değer kategorileri derleyiciler oluşturma, kopyalama ve geçici nesneler ifadesi değerlendirmesi sırasında taşıma sırada izlemelidir kuralları için temelidir.

 C ++ 17 standardına ifade değeri kategorileri gibi tanımlar:

- A *glvalue* bir ifadedir, değerlendirme, bir nesne, bit alanı veya işlev kimliğini belirler.
- A *prvalue* ifade, değerlendirme nesneyi ya da bir bit alanına başlatır veya görünür durumda bağlam tarafından belirtildiği gibi bir işlecinin işleneni değerini hesaplar.
- Bir *xvalue* bir nesne veya bit alanı (genellikle yaşam sonuna yakın olduğundan) kaynaklarını yeniden kullanılabilir gösteren bir glvalue olduğu. [Örnek: belirli türde bir rvalue başvuruları (8.3.2) içeren ifadeler yield, dönüş türü bir rvalue başvurusu olan bir işlev çağrısı veya rvalue başvuru türüne atamak gibi x değerleri. ]
- Bir *lvalue* bir xvalue değil bir glvalue olduğu.
- Bir *rvalue* bir prvalue veya bir xvalue.

Aşağıdaki diyagramda, kategoriler arasındaki ilişkiler gösterilmektedir:

 ![C++ ifade değeri kategorileri](media/value_categories.png "C++ ifade değeri kategorileri")

 Lvalue programınızı erişebilen bir adresi vardır. Lvalue örnekleri dahil olmak üzere değişken adları dahil **const** değişkenleri, dizi öğelerinin işlevi bir lvalue başvurusuna, bit alanları, birleşimler ve sınıf üyeleri dönen çağrıları.

 Programınız tarafından erişilebilir olan adresi bir prvalue ifadesi yok. Değişmez değerler, bir başvuru türü olmayan dönen işlev çağrıları ve ifade evalution sırasında ancak erişilebilir yalnızca derleyici tarafından oluşturulan geçici nesneler prvalue örnekleri içerir.

 Xvalue ifade bir adresi olduğundan, programınız tarafından artık erişilebilir ancak ifade erişim sağlayan bir rvalue başvurusu başlatmak için kullanılabilir. Diziye veya nesneye bir rvalue başvurusu olduğu bir rvalue başvurusu ve dizi indisi, üye ve işaretçi üye ifadeleri dönen işlev çağrıları örneklerindendir.

## <a name="example"></a>Örnek

 Aşağıdaki örnek, çeşitli doğru ve hatalı kullanımları lvalues ve rvalues gösterir:

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
> Değil işleçler aşırı yüklendiğinde örnekler bölümüne doğru ve yanlış kullanımı gösterir. Aşırı yükleme işleçleri tarafından bir ifade gibi yapabileceğiniz `j * 4` lvalue.

Koşulları *lvalue* ve *rvalue* nesne başvuruları başvurduğunuzda sık sık kullanılır. Başvurular hakkında daha fazla bilgi için bkz. [Lvalue başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md) ve [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>Ayrıca Bkz.

 [Temel kavramlar](../cpp/basic-concepts-cpp.md) [Lvalue başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md) [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md)