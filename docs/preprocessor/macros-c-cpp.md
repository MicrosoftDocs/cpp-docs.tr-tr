---
description: 'Daha fazla bilgi edinin: makrolar (C/C++)'
title: Makrolar (C/C++)
ms.date: 08/29/2019
helpviewer_keywords:
- preprocessor
- preprocessor, macros
- Visual C++, preprocessor macros
ms.assetid: a7bfc5d4-2537-4fe0-bef0-70cec0b43388
ms.openlocfilehash: 460fd993ae27ab2603c3d2f832481c07713f4f98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333414"
---
# <a name="macros-cc"></a>Makrolar (C/C++)

Ön işlemci, ön *işlemci yönergeleri* dışındaki tüm satırlardaki makroları, **#** ilk boşluk olmayan karakter olarak içeren satırları genişletir. Bir Koşullu derlemenin parçası olarak atlanan bazı yönergelerin bölümlerinde makroları genişletir. *Koşullu derleme yönergeleri* , kaynak dosyanın bölümlerinin derlemesini gizlenmesini sağlar. Derleyiciye hangi metin bloklarının geçeceğini ve ön işleme sırasında kaynak dosyadan kaldırıların belirlenmesi için bir sabit ifade veya tanımlayıcıyı test ederler.

`#define`Yönerge genellikle sabitler, anahtar sözcükler ve yaygın olarak kullanılan deyimler veya ifadeler ile anlamlı tanımlayıcıları ilişkilendirmek için kullanılır. Sabitleri temsil eden tanımlayıcılar bazen *sembolik sabitler* veya *bildirim sabitleri* olarak adlandırılır. Deyimlerini veya ifadeleri temsil eden tanımlayıcılar *makrolar* olarak adlandırılır. Bu Önişlemci belgelerinde yalnızca "makro" terimi kullanılır.

Bir makronun adı program kaynak metninde tanındığında veya bazı diğer Önişlemci komutlarının bağımsız değişkenlerinde, bu makroya yönelik bir çağrı olarak değerlendirilir. Makro adı makro gövdesinin bir kopyasıyla değiştirilmiştir. Makro bağımsız değişkenleri kabul ediyorsa, makro adını izleyen gerçek bağımsız değişkenler makro gövdesinde biçimsel parametrelerin yerine konur. Bir makro çağrısını, gövdenin işlenen kopyasıyla değiştirme işlemi, makro çağrısının *genişlemesi* olarak adlandırılır.

Pratik koşullarda, iki tür makro vardır. *Nesne benzeri* makrolar bağımsız değişken almaz. İşlev *gibi* makrolar, bağımsız değişkenleri kabul etmek için tanımlanabilir, bu sayede işlev çağrıları gibi davranır. Makrolar gerçek işlev çağrıları oluşturmadığı için bazen işlev çağrılarını makrolarla değiştirerek programları daha hızlı bir şekilde çalıştırabilirsiniz. (C++ ' da, satır içi işlevler genellikle tercih edilen yöntemdir.) Ancak, makroları tanımlamadıysanız ve kullanmıyorsanız, makrolar sorunlar oluşturabilir. Bir ifadede doğru önceliği korumak için bağımsız değişkenlerle makro tanımlarında parantez kullanmanız gerekebilir. Ayrıca, makrolar yan etkileri olan ifadeleri düzgün şekilde işleyemeyebilir. Daha fazla bilgi için `getrandom` [#define yönergesinin](../preprocessor/hash-define-directive-c-cpp.md)örneğine bakın.

Bir makro tanımladıktan sonra özgün tanımı kaldırmadan onu farklı bir değere yeniden tanımlayamazsınız. Ancak, makroyu tam olarak aynı tanım ile yeniden tanımlayabilirsiniz. Bu nedenle, aynı tanım bir programda birden çok kez görünebilir.

`#undef`Yönergesi bir makronun tanımını kaldırır. Tanımı kaldırdıktan sonra, makroyu farklı bir değer olarak yeniden tanımlayabilirsiniz. [#Define yönergesi](../preprocessor/hash-define-directive-c-cpp.md) ve [#undef yönergesi](../preprocessor/hash-undef-directive-c-cpp.md) `#define` `#undef` sırasıyla ve yönergelerini tartışır.

Daha fazla bilgi için bkz.,

- [Makrolar ve C++](../preprocessor/macros-and-cpp.md)

- [Variadic Makrolar](../preprocessor/variadic-macros.md)

- [Önceden tanımlanmış makrolar](../preprocessor/predefined-macros.md)

## <a name="see-also"></a>Ayrıca bkz.

[C/C++ ön işlemci başvurusu](../preprocessor/c-cpp-preprocessor-reference.md)
