---
title: Çeviri birimleri ve bağlantı (C++)
ms.date: 12/11/2019
ms.assetid: a6493ba0-24e2-4c89-956e-9da1dea660cb
ms.openlocfilehash: e964a3c70c138caf8848e6a6366097cbfb90f548
ms.sourcegitcommit: f7ebdfc3a260778c2ef938747cba1376c70ced15
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84108402"
---
# <a name="translation-units-and-linkage"></a>Çeviri birimleri ve bağlantı

Bir C++ programında bir *sembol*, örneğin bir değişken veya işlev adı, kapsamı içinde herhangi bir sayıda bildirilebilecek, ancak yalnızca bir kez tanımlanmış olabilir. Bu kural "bir tanım kuralıdır" (ODR). Bir *bildirim* programa bir adı tanıtır (veya yeniden tanıtır). *Tanım* bir ad sağlar. Ad bir değişkeni temsil ediyorsa, tanımı açıkça başlatır. Bir *işlev tanımı* , imzadan ve işlev gövdesinden oluşur. Sınıf tanımı, sınıf adından ve ardından tüm sınıf üyelerini listeleyen bir blok ile oluşur. (Üye işlevlerinin gövdeleri, isteğe bağlı olarak başka bir dosyada ayrı olarak tanımlanabilir.)

Aşağıdaki örnekte bazı bildirimler gösterilmektedir:

```cpp
int i;
int f(int x);
class C;
```

Aşağıdaki örnekte bazı tanımlar gösterilmektedir:

```cpp
int i{42};
int f(int x){ return x * i; }
class C {
public:
   void DoSomething();
};
```

Bir program bir veya daha fazla *çeviri biriminden*oluşur. Bir çeviri birimi, bir uygulama dosyasından ve doğrudan veya dolaylı olarak içerdiği tüm üst bilgilerden oluşur. Uygulama dosyaları, genellikle *cpp* veya *cxx*dosya uzantısına sahiptir. Üst bilgi dosyaları genellikle *h* veya *HPP*uzantısına sahiptir. Her çeviri birimi derleyici tarafından bağımsız olarak derlenir. Derleme tamamlandıktan sonra bağlayıcı, derlenmiş çeviri birimlerini tek bir *programda*birleştirir. ODR kuralının ihlalleri genellikle bağlayıcı hataları olarak gösterilir. Aynı adda farklı çeviri birimlerinde iki farklı tanım olduğunda bağlayıcı hataları oluşur.

Genel olarak, bir değişkeni birden çok dosya genelinde görünür yapmanın en iyi yolu, bir üst bilgi dosyasına koyulamıyor. Ardından, bildirimi gerektiren her *cpp* dosyasına bir #include yönergesi ekleyin. Üst bilgi içerikleri etrafında ekleme *koruyucuları* ekleyerek, bildirdiği adların yalnızca bir kez tanımlandığından emin olursunuz.

C++ 20 ' de, [modüller](modules-cpp.md) üstbilgi dosyalarına geliştirilmiş bir alternatif olarak sunulmuştur.

Bazı durumlarda, bir *cpp* dosyasında genel bir değişken veya sınıf bildirmek gerekebilir. Bu durumlarda, derleyiciye ve bağlayıcıya, adın ne tür bir *bağlantı* türüyle ilgili bilgi almak için bir yol gerekir. Bağlantı türü, nesne adının yalnızca bir dosyaya mi yoksa tüm dosyalara mı uygulanacağını belirtir. Bağlantı kavramı yalnızca genel adlar için geçerlidir. Bağlantı kavramı, bir kapsam içinde belirtilen adlara uygulanmaz. Bir kapsam, işlev veya sınıf tanımları gibi bir dizi kapsayan küme ile belirtilir.

## <a name="external-vs-internal-linkage"></a>Dış ve iç bağlantı

*Ücretsiz bir işlev* , genel veya ad alanı kapsamında tanımlanan bir işlevdir. Const olmayan genel değişkenler ve ücretsiz işlevler varsayılan olarak *dış bağlantıya*sahiptir; Bunlar, programdaki herhangi bir çeviri biriminden görülebilir. Bu nedenle, başka bir genel nesne bu ada sahip olamaz. *İç bağlantıya* sahip bir simge veya *hiçbir bağlantı* , yalnızca bildirildiği çeviri birimi içinde görünür. Bir adın iç bağlantısı olduğunda, aynı ad başka bir çeviri biriminde bulunabilir. Sınıf tanımları veya işlev gövdeleri içinde belirtilen değişkenlerin bağlantısı yok.

Genel bir adı, açıkça **statik**olarak bildirerek iç bağlantıya sahip olacak şekilde zorlayabilirsiniz. Bu, görünürlüğünü, bildirildiği aynı çeviri birimiyle sınırlandırır. Bu bağlamda **statik** , yerel değişkenlere uygulandığında farklı bir şey anlamına gelir.

Aşağıdaki nesneler varsayılan olarak iç bağlantıya sahiptir:

- const nesneler
- constexpr nesneleri
- tür tanımları
- ad alanı kapsamındaki statik nesneler

Bir const nesnesine dış bağlantı vermek için bunu **extern** olarak bildirin ve bir değer atayın:

```cpp
extern const int value = 42;
```

Daha fazla bilgi için bkz. [extern](extern-cpp.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Temel kavramlar](../cpp/basic-concepts-cpp.md)
