---
title: 'Değer kategorileri: Lvalues ve Rvalues (C++)'
ms.date: 05/07/2019
helpviewer_keywords:
- R-values [C++]
- L-values [C++]
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
ms.openlocfilehash: 4e3cfa87a8f1ae9b17f7c08afd8faeabea7102b3
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222011"
---
# <a name="lvalues-and-rvalues-c"></a>Lvalues ve Rvalues (C++)

Her bir C++ ifadesi bir türe sahiptir ve ait olduğu bir *değeri kategori*. Değer kategorileri derleyiciler oluşturma, kopyalama ve geçici nesneler ifadesi değerlendirmesi sırasında taşıma sırada izlemelidir kuralları için temelidir.

C ++ 17 standardına ifade değeri kategorileri gibi tanımlar:

- A *glvalue* bir ifadedir, değerlendirme, bir nesne, bit alanı veya işlev kimliğini belirler.
- A *prvalue* ifade, değerlendirme nesneyi ya da bir bit alanına başlatır veya görünür durumda bağlam tarafından belirtildiği gibi bir işlecinin işleneni değerini hesaplar.
- Bir *xvalue* bir nesne veya bit alanı (genellikle yaşam sonuna yakın olduğundan) kaynaklarını yeniden kullanılabilir gösteren bir glvalue olduğu. Örnek: Rvalue başvuruları (8.3.2) içeren ifadeler belirli türde bir dönüş türü bir rvalue başvurusu olan bir işleve çağrı veya rvalue başvuru türüne atamak gibi x değerleri yield.
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

    // Correct usage: the conditional operator returns an lvalue.
    ((i < 3) ? i : j) = 7;
    
    // Incorrect usage: the constant ci is a non-modifiable lvalue (C3892).
    const int ci = 7;
    ci = 9; // C3892
}
```

> [!NOTE]
> Değil işleçler aşırı yüklendiğinde örnekler bölümüne doğru ve yanlış kullanımı gösterir. Aşırı yükleme işleçleri tarafından bir ifade gibi yapabileceğiniz `j * 4` lvalue.

Koşulları *lvalue* ve *rvalue* nesne başvuruları başvurduğunuzda sık sık kullanılır. Başvurular hakkında daha fazla bilgi için bkz. [Lvalue başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md) ve [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Temel Kavramlar](../cpp/basic-concepts-cpp.md)<br/>
[Lvalue Başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Rvalue Başvuru Bildirimcisi: &&](../cpp/rvalue-reference-declarator-amp-amp.md)
