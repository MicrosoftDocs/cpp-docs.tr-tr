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
ms.openlocfilehash: 2dba8698461636e292771fc1e5a4f5ac0a633e73
ms.sourcegitcommit: d06966efce25c0e66286c8047726ffe743ea6be0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/19/2018
ms.locfileid: "36238675"
---
# <a name="program-and-linkage-c"></a>Program ve Bağlantı (C++)

C++ programı bir *simgesi*, örneğin bir değişken veya işlev adı bildirilebilir kez kendi kapsamı içinde herhangi bir sayıda, ancak bunu yalnızca bir kez tanımlanabilir. Bu, bir tanım Kuralı'nı (ODR) olur. A *bildirimi* bir ad programa sunar (veya yeniden tanıtır). A *tanımı* bir ad tanıtır ve bir değişkeni söz konusu olduğunda, açıkça başlatır. A *işlev tanımı* imza ve işlev gövdesi karakterlerinden oluşur.

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

Bir veya daha fazla program oluşur *çeviri birimleri*. Çeviri birimi, bir uygulama dosyası (.cpp, .cxx, vb.) ve doğrudan veya dolaylı olarak içeren tüm üstbilgileri (.h, .hpp, vb.) oluşur. Her bir çeviri birimi bağımsız olarak geçmesi bağlayıcı birleştirir derlenmiş çeviri birimleri tek bir derleyicisi tarafından derlenen *program*. Farklı çeviri birimleri iki farklı tanımları aynı ada sahip olduğunda ODR kural ihlalleri genellikle bağlayıcı hata olarak gösterilir.

Genel olarak, üstbilgi dosyaya yerleştirin ve eklemek için bir değişken birden çok dosyaya görünür hale getirmek için en iyi yolu olan bir #include yönergesi .cpp cdn'den bildirimi gerektirir. Ekleyerek *koruyucuları dahil* üstbilgisi içeriği geçici bir çözüm, onu tanımlandığı adları yalnızca bir kez tanımlandığından emin olun.

Ancak, bazı durumlarda genel değişkeni ya da bir .cpp dosyasında sınıfı bildirmek gerekli olabilir. Bu durumlarda derleyici ve bağlayıcı nesnesinin adını yalnızca bir dosyayı veya tüm dosyaları için geçerli olup olmadığını bildirmek için bir yönteme ihtiyacınız vardır.

## <a name="linkage-vs-scope"></a>Bağlantı kapsam karşılaştırması

Kavramı *bağlantı* çeviri birimleri arasında (örneğin, değişkenleri, tür adları ve işlev adları) genel semboller program içinde görünürlüğünü bir bütün olarak başvuruyor. Kavramı *kapsam* ad alanı, sınıf veya işlev gövdesi gibi bir bloğu içinde bildirilen simgeleri başvuruyor. Bu tür simgeleri tanımlı kapsamı içinde görünür; bağlantı kavramı için geçerli değildir. 

## <a name="external-vs-internal-linkage"></a>Dış ve iç bağlantı

A *serbest işlevi* genel olarak tanımlanan bir işlev değil veya ad alanı kapsamı. Non-const genel değişkenler ve varsayılan olarak boş işlevleri *dış bağlantı*; programda herhangi bir çeviri biriminden görünür. Bu nedenle, hiçbir diğer genel nesne (değişkeni, sınıf tanımı, vb.), bu ada sahip olabilir. Bir simge ile *iç bağlantı* veya *bağlantı yok* yalnızca onu bildirilen çeviri birim içinde görünür. Bir ad iç bağlantı olduğunda, aynı adı başka bir çeviri biriminde bulunabilir. Sınıf tanımları ile değişkenleri bildirilen veya bağlantı yok işlevi gövdeleri sahip. 

İç bağlantı olarak açıkça bildirerek sağlamak için genel bir ad zorlayabilirsiniz **statik**. Bu, içinde bildirildiği aynı çeviri birimine kendi visiblity sınırlar. Bu bağlamda unutmayın **statik** yerel değişkenlere uygulandığında farklı bir şey anlamına gelir.

Aşağıdaki nesneler, varsayılan olarak iç bağlantı sahiptir:
- const nesneleri
- constexpr nesneleri
- tür tanımları
- ad alanı kapsamında statik nesneleri

Const bir nesne dış bağlantı vermek için olarak bildirme **extern** ve bir değer atayabilirsiniz:

```cpp
extern const int value = 42;
```

Bkz: [extern](extern-cpp.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca Bkz.

 [Temel Kavramlar](../cpp/basic-concepts-cpp.md)