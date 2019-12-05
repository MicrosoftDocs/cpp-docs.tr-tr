---
title: İfade Semantikleri
ms.date: 11/19/2018
helpviewer_keywords:
- grammar, expressions
- expressions [C++], semantics
- expression evaluation
- expression evaluation, about expression evaluation
ms.assetid: 4a792154-533b-48b9-8709-31bfc170f0a7
ms.openlocfilehash: 6770d3fb314222c7c58b6b97fa42d74cbc1e9b33
ms.sourcegitcommit: a6d63c07ab9ec251c48bc003ab2933cf01263f19
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74857326"
---
# <a name="semantics-of-expressions"></a>İfade Semantikleri

İfadeler, işleçlerinin önceliğine ve gruplandırılmasına göre değerlendirilir. ( [Sözcük temelli kurallar](../cpp/lexical-conventions.md)Içindeki C++ [Işleç önceliği ve ilişkilendirilebilirliği](../cpp/cpp-built-in-operators-precedence-and-associativity.md) , işleçlerin ifadeler üzerinde getirme ilişkilerini gösterir.)

## <a name="order-of-evaluation"></a>Değerlendirme sırası

Şu örneği göz önünde bulundurun:

```cpp
// Order_of_Evaluation.cpp
// compile with: /EHsc
#include <iostream>
using namespace std;
int main()
{
    int a = 2, b = 4, c = 9;

    cout << a + b * c << "\n";
    cout << a + (b * c) << "\n";
    cout << (a + b) * c << "\n";
}
```

```Output
38
38
54
```

![Bir ifadede değerlendirme sırası](../cpp/media/vc38zv1.gif "Bir ifadede değerlendirme sırası") <br/>
İfade-değerlendirme sırası

Yukarıdaki şekilde gösterilen ifadenin değerlendirilme sırası, işleçlerin öncelik ve birleşimlerine göre belirlenir:

1. Çarpma (*), bu ifadede en yüksek önceliğe sahiptir; bu yüzden `b * c` alt ifadesi ilk olarak değerlendirilir.

1. Toplama (+), sıradaki en yüksek önceliğe sahiptir, dolayısıyla `a` ve `b` ürününe `c` eklenir.

1. Sol SHIFT (< <) ifadede en düşük önceliğe sahiptir, ancak iki oluşum vardır. Sola kaydırma işleci soldan sağa doğru gruplama yaptığından, ilk önce sol alt ifade, ardından sağdaki değerlendirilir.

Alt ifadeleri gruplamak için parantez kullanıldığında, aşağıdaki şekilde gösterildiği gibi önceliği ve ayrıca ifadenin değerlendirilme sırasını değiştirir.

![Parantezli ifadenin değerlendirme sırası](../cpp/media/vc38zv2.gif "Parantezli ifadenin değerlendirme sırası") <br/>
Parantez ile ifade değerlendirmesi sırası

Yukarıdaki şekildeki gibi ifadeler yalnızca yan etkileri için (bu örnekte bilgileri standart çıktı cihazına aktarmak için) değerlendirilir.

## <a name="notation-in-expressions"></a>İfadelerdeki gösterim

Dil C++ , işlenenleri belirtirken belirli uyumluluk belirler. Aşağıdaki tabloda *, türünde işlenenler*gerektiren işleçlerde kabul edilebilir işlenen türleri gösterilmektedir.

### <a name="operand-types-acceptable-to-operators"></a>İşleç için kabul edilebilir işlenen türleri

|Tür bekleniyor|İzin verilen türler|
|-------------------|-------------------|
|*type*|`const` *türü*<br /> `volatile` *türü*<br /> *tür*&<br /> `const` *türü*&<br /> `volatile` *türü*&<br /> `volatile const` *türü*<br /> `volatile const` *türü*&|
|*tür* \*|*tür* \*<br /> `const` *türü* \*<br /> `volatile` *türü* \*<br /> `volatile const` *türü* \*|
|`const` *türü*|*type*<br /> `const` *türü*<br />`const` *türü*&|
|`volatile` *türü*|*type*<br /> `volatile` *türü*<br /> `volatile` *türü*&|

Yukarıdaki kurallar her zaman birleşimde kullanılabilir olduğundan, bir işaretçi beklendiğinde geçici bir nesneye bir const işaretçisi sağlanabilir.

## <a name="ambiguous-expressions"></a>Belirsiz ifadeler

Belirli ifadeler anlamlarına göre belirsizdir. Bir nesnenin değeri aynı ifadede birden çok kez değiştirildiğinde, bu ifadeler en sık meydana gelir. Bu ifadeler, dilin bir tane tanımlamayan belirli bir değerlendirme sırasına bağımlıdır. Aşağıdaki örnek göz önünde bulundurun:

```
int i = 7;

func( i, ++i );
```

Dil C++ , bir işlev çağrısının bağımsız değişkenlerinin değerlendirilme sırasını garanti etmez. Bu nedenle, önceki örnekte, parametrelerin soldan sağa mı yoksa sağdan sola mi değerlendirilediğine bağlı olarak, `func` için 7 ve 8 veya 8 ve 8 değerlerini alabilir.

## <a name="c-sequence-points-microsoft-specific"></a>C++sıra noktaları (Microsoft 'a özgü)

Bir ifade, bir nesnenin değerini ardışık "dizi noktaları" arasında yalnızca bir kez değiştirebilir.

C++ dili tanımı şu anda dizi noktaları belirtmemektedir. Microsoft C++, C işleçleri içeren ve aşırı yüklenmiş işleçler içermeyen tüm ifadeler için ANSI C ile aynı dizi noktalarını kullanır. İşleçler aşırı yüklendiğinde, semantikler işleç sıralamasından işlev çağrısı sıralamasına dönüşür. Microsoft C++ aşağıdaki dizi noktalarını kullanır:

- Mantıksal AND işlecinin sol işleneni (& &). Mantıksal AND işlecinin sol işleneni, tamamen değerlendirilir ve devam edilmeden önce tüm yan etkiler tamamlanır. Mantıksal AND işlecinin sağ işleneninin değerlendirileceği kesin değildir.

- Mantıksal OR işlecinin sol işleneni (&#124;&#124;). Mantıksal OR işlecinin sol işleneni, tamamen değerlendirilir ve devam edilmeden önce tüm yan etkiler tamamlanır. Mantıksal OR işlecinin sağ işleneninin değerlendirileceği kesin değildir.

- Virgül işlecinin sol işleneni. Virgül işlecinin sol işleneni tamamen değerlendirilir ve devam edilmeden önce tüm yan etkiler tamamlanır. Virgül işlecinin her iki işleneni de her zaman değerlendirilir.

- İşlev çağrısı işleci. İşlev çağrısı ifadesi ve işlevin varsayılan bağımsız değişkenler de dahil tüm bağımsız değişkenleri değerlendirilir ve işleve giriş yapılmadan önce tüm yan etkiler tamamlanır. Bağımsız değişkenler veya işlev çağrısı ifadesi arasında belirli bir değerlendirme sırası yoktur.

- Koşullu işlecin ilk işleneni. Koşullu işlecin ilk işleneni tamamen değerlendirilir ve devam edilmeden önce tüm yan etkiler tamamlanır.

- Bir bildirim deyiminde başlatmanın sonu gibi bir tam başlatma ifadesinin sonu.

- Bir ifade deyimindeki ifade. İfade deyimleri, sırasıyla isteğe bağlı bir ifadeden ve noktalı virgülden (;) oluşur. İfade, yan etkilere karşı tamamen değerlendirilir.

- Bir seçme (if veya switch) deyimindeki denetim ifadesi. İfade tamamen değerlendirilir ve seçime bağlı kod yürütülmeden önce tüm yan etkiler tamamlanır.

- While veya do deyiminin denetim ifadesi. İfade tamamen değerlendirilir ve while veya do döngüsünün sonraki yinelemesinde yer alan herhangi bir deyim yürütülmeden önce tüm yan etkiler tamamlanır.

- For deyiminin üç ifadesinden her biri. Her ifade tamamen değerlendirilir ve sonraki ifadeye geçilmeden önce tüm yan etkiler tamamlanır.

- Dönüş deyimindeki ifade. İfade tamamen değerlendirilir ve denetim çağırma işlevine dönmeden önce tüm yan etkiler tamamlanır.

## <a name="see-also"></a>Ayrıca bkz.

[İfadeler](../cpp/expressions-cpp.md)