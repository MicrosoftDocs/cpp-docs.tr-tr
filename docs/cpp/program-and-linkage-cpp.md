---
title: Programlar ve bağlantı (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/09/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a6493ba0-24e2-4c89-956e-9da1dea660cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2ef0f08efbcdf09420d53710a3f16326381f13c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056787"
---
# <a name="program-and-linkage-c"></a>Program ve Bağlantı (C++)

C++ programında bir *sembol*, örneğin bir değişken veya işlev adı bildirilebilir kez kendi kapsamı içinde herhangi bir sayıda, ancak yalnızca de çok kez tanımlanmış. Tek Tanım Kuralı'nı (ODR) budur. A *bildirimi* programa bir ad tanıtır (veya yeniden sunar). A *tanımı* bir ad tanıtır ve bir değişken olması durumunda onu açıkça başlatır. A *işlev tanımı* imza ve işlev gövdesi karakterlerinden oluşur.

Bildirimleri şunlardır:

```cpp
int i;
int f(int x);
```

Tanımları şunlardır:

```cpp
int i{42};
int f(int x){ return x * i; }
```

Bir veya daha fazla program içerir *çeviri birimleri*. Bir çeviri birimi, bir uygulama dosyasını (.cpp, .cxx vb.) ve doğrudan veya dolaylı olarak içeren tüm üstbilgi (.h, .hpp vb.) oluşur. Her çeviri birimini bağımsız olarak sonra bağlayıcı birleştirir derlenmiş bir çeviri birimleri tek bir derleyici tarafından derlenen *program*. Aynı adlı iki farklı tanımları çeviri birimleri bakımından farklı olduğunda ODR kural ihlalleri genellikle bağlayıcı hata olarak gösterilir.

Genel olarak, bir üstbilgi dosyasına yerleştirilebilir ve eklemek için bir değişken birden çok dosyaya görünür hale getirmek için en iyi yolu olan bir #include yönergesi her .cpp dosyası bildirimi gerektirir. Ekleyerek *cf dahil* üst bilgi içeriği geçici olarak bildirir, adları yalnızca bir kez tanımlandığından emin olun.

Ancak, bazı durumlarda bir genel değişken ya da bir .cpp dosyası sınıfında bildirmek gerekli olabilir. Bu gibi durumlarda, derleyici ve bağlayıcı nesnesinin adını yalnızca bir dosyayı veya tüm dosyalar için mi geçerli olduğunu bildirmek için bir yol gerekir.

## <a name="linkage-vs-scope"></a>Bağlantı kapsamı karşılaştırması

Kavramını *bağlantı* çeviri birimlerindeki program içinde genel simgeleri (örneğin, değişkenler, tür adları ve işlev adları) görünürlüğünü bir bütün olarak başvuruyor. Kavramını *kapsam* gibi bir ad alanı, sınıf veya işlev gövdesinin bir blok içinde bildirilen sembolleri ifade eder. Tür simgeleri, yalnızca içinde tanımlandıkları kapsamı içinde görülebilir; kavram bağlantı için geçerli değildir.

## <a name="external-vs-internal-linkage"></a>Dış ve iç bağlantı

A *boş işlev* genel kapsamda tanımlanan bir işlev veya ad alanı kapsamında. Non-const genel değişkenler ve varsayılan olarak ücretsiz işlevleri *dış bağlantısı*; bunlar programın herhangi bir çeviri birimindeki görülebilir. Bu nedenle, diğer genel nesnesi yok (değişken, sınıf tanımı, vb.), bu ada sahip olabilir. Bir simgeyle *iç bağlantı* veya *bağlantısı olmayan adlar* yalnızca bu bildirilen çeviri birimi içinde görülebilir. Bir ad iç bağlantıya sahip olduğunda, aynı adı başka bir çeviri biriminde bulunabilir. Sınıf tanımları ile değişkenler veya işlev gövdeleri hiçbir bağlantısı yoktur.

Bir genel bir ad olarak açıkça bildirerek iç bağlantıya sahip olmasını zorunlu kılabilirsiniz **statik**. Bu, katmanın aynı çeviri birimi içinde bildirildiği için sınırlar. Bu bağlamda unutmayın **statik** yerel değişkenlere uygulandığında değerinden farklı bir şey anlamına gelir.

Aşağıdaki nesneler varsayılan olarak iç bağlantısı vardır:
- const nesnelerine
- constexpr nesneleri
- tür tanımları
- ad alanı kapsamında statik nesneler

Const nesne dış bağlantı vermek için olarak bildirin **extern** ve bir değer atayın:

```cpp
extern const int value = 42;
```

Bkz: [extern](extern-cpp.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[Temel Kavramlar](../cpp/basic-concepts-cpp.md)