---
title: Çeviri birimleri ve bağlantı (C++)
ms.date: 12/11/2019
ms.assetid: a6493ba0-24e2-4c89-956e-9da1dea660cb
ms.openlocfilehash: 791ec53d4df863b218db463f2b9b9401bf6f466d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374325"
---
# <a name="translation-units-and-linkage"></a>Çeviri birimleri ve bağlantı

Bir C++ programında, bir *sembol*( örneğin bir değişken veya işlev adı, kapsamı içinde herhangi bir sayıda ilan edilebilir, ancak yalnızca bir kez tanımlanabilir. Bu kural "Tek Tanım Kuralı" (ODR) kuralıdır. Bir *bildirge* programa bir ad tanıtır (veya yeniden tanıtır). Bir *tanım* bir ad tanır. Ad bir değişkeni temsil ediyorsa, bir tanım onu açıkça başolarak gösterir. Bir *işlev tanımı* imza artı işlev gövdesioluşur. Sınıf tanımı, tüm sınıf üyelerini listeleyen bir blok tarafından izlenen sınıf adından oluşur. (Üye işlevlerin gövdeleri isteğe bağlı olarak başka bir dosyada ayrı olarak tanımlanabilir.)

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

Bir program bir veya daha fazla *çeviri biriminden*oluşur. Çeviri birimi, bir uygulama dosyasından ve doğrudan veya dolaylı olarak içerdiği tüm üstbilgilerden oluşur. Uygulama dosyaları genellikle *cpp* veya *cxx*bir dosya uzantısı var. Üstbilgi dosyaları genellikle *h* veya *hpp*bir uzantısı var. Her çeviri birimi derleyici tarafından bağımsız olarak derlenir. Derleme tamamlandıktan sonra, bağlayıcı derlenen çeviri birimlerini tek bir *programda*birleştirir. ODR kuralıihlalleri genellikle bağlayıcı hataları olarak gösterir. Bağlayıcı hataları, aynı adın farklı çeviri birimlerinde iki farklı tanımı olduğunda oluşur.

Genel olarak, bir değişkeni birden çok dosya arasında görünür hale getirmenin en iyi yolu, bir üstbilgi dosyasına koymaktır. Ardından, her *cpp* dosyasına, beyanname gerektiren bir #include yönergesi ekleyin. Üstbilgi içeriğinin etrafına *korumaekleme* ekleyerek, bildirdiği adların yalnızca bir kez tanımlandığından emin olursunuz.

C++20'de [modüller](modules-cpp.md) üstbilgi dosyalarına geliştirilmiş bir alternatif olarak tanıtılır.

Bazı durumlarda, bir *cpp* dosyasında genel değişken veya sınıf bildirmek gerekebilir. Bu gibi durumlarda, derleyiciye ve bağlayıcıya adın ne tür *bir bağlantıya* sahip olduğunu söylemenin bir yolunu bulabilmeniz gerekir. Bağlantı türü, nesnenin adının yalnızca bir dosyaya mı yoksa tüm dosyalara mı geçerli olduğunu belirtir. Bağlantı kavramı yalnızca genel adlar için geçerlidir. Bağlantı kavramı, kapsam dahilinde bildirilen adlar için geçerli değildir. Kapsam, işlev veya sınıf tanımları gibi bir parantez kümesi tarafından belirtilir.

## <a name="external-vs-internal-linkage"></a>Dış ve dahili bağlantı

Boş işlev, genel veya ad alanı kapsamında tanımlanan bir *işlevdir.* Const olmayan global değişkenler ve varsayılan olarak serbest işlevler *dış bağlantıya sahiptir;* programdaki herhangi bir çeviri biriminden görülebilirler. Bu nedenle, başka hiçbir genel nesne bu ada sahip olamaz. *İç bağlantıya sahip* veya *bağlantısı olmayan* bir sembol yalnızca beyan edildiği çeviri biriminde görünür. Bir adın iç bağlantısı varsa, aynı ad başka bir çeviri biriminde bulunabilir. Sınıf tanımları veya işlev gövdeleri ile bildirilen değişkenlerin bağlantısı yoktur.

Genel bir adı, statik **olarak**açıkça belirterek iç bağlantıya sahip olmaya zorlayabilirsiniz. Bu, görünürlüğünü beyan edildiği aynı çeviri birimiyle sınırlar. Bu bağlamda, **statik** yerel değişkenlere uygulandığında farklı bir şey anlamına gelir.

Aşağıdaki nesnelerin varsayılan olarak iç bağlantısı vardır:

- const nesneler
- constexpr nesneleri
- tür tanımları
- ad alanı kapsamındaki statik nesneler

Const nesneye dış bağlantı vermek için, onu **extern** olarak bildirin ve bir değer atayın:

```cpp
extern const int value = 42;
```

Daha fazla bilgi için [extern'e](extern-cpp.md) bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Temel Kavramlar](../cpp/basic-concepts-cpp.md)
