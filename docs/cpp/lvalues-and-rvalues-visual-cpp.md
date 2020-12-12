---
description: 'Daha fazla bilgi edinin: lvalues ve rvalues (C++)'
title: 'Değer kategorileri: lvalues ve rvalues (C++)'
ms.date: 05/07/2019
helpviewer_keywords:
- R-values [C++]
- L-values [C++]
ms.assetid: a8843344-cccc-40be-b701-b71f7b5cdcaf
ms.openlocfilehash: b92ddc3aad62f1eaf7af6a6bc113c1a0fdd70769
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97299247"
---
# <a name="lvalues-and-rvalues-c"></a>Lvalues ve Rvalues (C++)

Her C++ ifadesinin bir türü vardır ve bir *değer kategorisine* aittir. Değer kategorileri, derleyicilerin ifade değerlendirmesi sırasında geçici nesneleri oluştururken, kopyalarken ve taşırken izlemesi gereken kuralların temelini oluşturur.

C++ 17 standardı, ifade değeri kategorilerini aşağıdaki şekilde tanımlar:

- *Glvalue* , değerlendirmesi bir nesne, bit alanı veya işlevin kimliğini belirleyen bir ifadedir.
- *Prdeğeri* , değerlendirmesi bir nesneyi veya bir bit alanını Başlatan bir ifadedir veya bir işlecin işleneninin değerini, göründüğü bağlam tarafından belirtilen şekilde hesaplar.
- Bir bir *değer, kaynakları* yeniden kullanılabilen bir nesne veya bit alanı belirten bir glvalue değeridir (genellikle yaşam süresinin sonuna yakın olduğu için). Örnek: Rvalue başvuruları (8.3.2) içeren bazı ifade türleri, dönüş türü bir rvalue başvurusu veya bir rvalue başvuru türüne dönüştürme gibi bir işlev çağrısı gibi sonuç XValues değeri sağlar.
- *Lvalue* , bir değer olarak değil, bir glvalue değeridir.
- *Rvalue* , bir prvalue olamaz veya bir değer.

Aşağıdaki diyagramda kategoriler arasındaki ilişkiler gösterilmektedir:

![C++ ifade değeri kategorileri](media/value_categories.png "C++ ifade değeri kategorileri")

Lvalue, programınızın erişebileceği bir adrese sahiptir. Lvalue ifadeleri örnekleri, **`const`** değişkenler, dizi öğeleri, bir lvalue başvurusu döndüren işlev çağrıları, bit alanları, birleşimler ve sınıf üyeleri gibi değişken adlarını içerir.

Bir prvalue olamaz ifadesinde, programınız tarafından erişilebilen bir adres yok. Prvalue olamaz ifadelerine örnek olarak değişmez değerler, başvuru olmayan bir tür döndüren işlev çağrıları ve Evalution ifadesi sırasında oluşturulan ancak derleyici tarafından erişilebilen geçici nesneler sayılabilir.

Bir bir x ifadesi, artık programınız tarafından erişilemeyen bir adrese sahiptir ancak ifadeye erişim sağlayan bir rvalue başvurusunu başlatmak için kullanılabilir. Örnek olarak, bir rvalue başvurusu döndüren işlev çağrıları ve dizi ya da nesnenin bir rvalue başvurusu olduğu üye ifadelerine dizi alt simge, üye ve işaretçi bulunur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, lvalues ve rvalues 'un birkaç doğru ve yanlış kullanımlarını göstermektedir:

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
> Bu konudaki örneklerde, işleçler aşırı yüklü olmadığında doğru ve hatalı kullanım gösterilmektedir. İşleçleri aşırı yükleyerek, lvalue gibi bir ifade yapabilirsiniz `j * 4` .

Nesne başvurularına başvurduğunuzda, *lvalue* ve *rvalue* terimleri genellikle kullanılır. Başvurular hakkında daha fazla bilgi için bkz. [lvalue başvuru bildirimci: &](../cpp/lvalue-reference-declarator-amp.md) ve [rvalue başvuru bildirimci:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

## <a name="see-also"></a>Ayrıca bkz.

[Temel kavramlar](../cpp/basic-concepts-cpp.md)<br/>
[Lvalue Başvuru Bildirimcisi: &](../cpp/lvalue-reference-declarator-amp.md)<br/>
[Rvalue Başvuru Bildirimcisi: &&](../cpp/rvalue-reference-declarator-amp-amp.md)
