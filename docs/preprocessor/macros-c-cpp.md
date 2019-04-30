---
title: Makrolar (C/C++)
ms.date: 11/04/2016
helpviewer_keywords:
- preprocessor
- preprocessor, macros
- Visual C++, preprocessor macros
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
ms.openlocfilehash: 281aaf686c07894b5cb1fab187ba903179c51de8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371784"
---
# <a name="macros-cc"></a>Makrolar (C/C++)
Ön işleme, önişlemci yönergeleri olmayan tüm satırları makrolarındaki genişletir (sahip olmayan satırlar bir **#** ilk boşluk olmayan karakter olarak) ve bir parçası olarak atlandı değildir yönergelerden bazıları bölümlerini bir Koşullu derleme. Hangi metin blokları belirlemek için tanımlayıcı geçirilir derleyicisi ve hangi metin blokları sırasında kaynak dosyasından kaldırılır ya da sabit bir ifade test ederek bir kaynak dosyasının bölümlerini derleme gizlemek "Koşullu derleme" yönergeleri sağlar ön işleme.

`#define` Yönergesi genellikle anlamlı tanımlayıcılar, sabitler, anahtar sözcükler ve yaygın olarak kullanılan ifadeler veya deyimler ilişkilendirmek için kullanılır. Sabitler temsil eden tanımlayıcıları bazen "sembolik sabit değerler" veya "sabitler listesi." adı verilir İfadeler veya deyimler temsil eden tanımlayıcıları "makroları." olarak adlandırılır Önişlemci bu belgede, yalnızca "makrosu" terimi kullanılır.

Makro adı program kaynak metni veya belirli bir önişlemci komutlarını bağımsız değişkenleri tanındığında, makro çağrısı olarak kabul edilir. Makro adı makrosu gövdesi bir kopyasını tarafından değiştirilir. Makro bağımsız değişkenleri kabul ederse, gerçek bağımsız değişkenler makro adından makrosu gövdesinde biçimsel parametrelerin yerine kullanılır. Makro çağrısı işlenir gövdesi kopyası ile değiştirme işlemi, makro çağrısı "genişletme" adı verilir.

Pratikte, makroları iki tür vardır. Konum ve işlev çağrıları gibi davranacak bağımsız değişkenleri kabul etmek için "işlev benzeri" makro tanımlanabilir ise bağımsız değişken, "Nesne benzeri" makroları almaz. Makrolar, gerçek işlev çağrıları oluşturmaz, çünkü bazen makrolarla işlev çağrıları değiştirerek daha hızlı çalışmasını programlar yapabilirsiniz. (C++'da, satır içi işlevleri genellikle bir tercih edilen yöntemdir.) Ancak, eğer değil tanımlayın ve bunları dikkatli kullanın makroları sorunları oluşturabilirsiniz. Bir ifade doğru önceliği korumak için bağımsız değişken içeren makro tanımlarında parantez kullanmanız gerekebilir. Ayrıca, makroları doğru ifadelerin yan etkileri olan işlememesi. Bkz: `getrandom` örnekte [#define yönergesi](../preprocessor/hash-define-directive-c-cpp.md) daha fazla bilgi için.

Makro tanımlandıktan sonra orijinal tanımını kaldırmadan farklı bir değer tanımlanamaz. Ancak, tam olarak aynı tanımıyla makrosu tanımlayabilirsiniz. Bu nedenle, aynı tanımın bir program içinde birden fazla kez görünebilir.

`#undef` Yönergesi bir makro tanımı kaldırır. Tanımı kaldırdıktan sonra farklı bir değer makrosuna tanımlayabilirsiniz. [#Define yönergesi](../preprocessor/hash-define-directive-c-cpp.md) ve [#undef yönergesi](../preprocessor/hash-undef-directive-c-cpp.md) tartışmak `#define` ve `#undef` yönergeleri, sırasıyla.

Daha fazla bilgi için bkz:

- [Makrolar ve C++](../preprocessor/macros-and-cpp.md)

- [Variadic Makrolar](../preprocessor/variadic-macros.md)

- [Önceden Tanımlanmış Makrolar](../preprocessor/predefined-macros.md)

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ Ön İşlemci Başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)