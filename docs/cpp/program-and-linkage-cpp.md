---
title: Program ve bağlantı (C++) | Microsoft Docs
ms.custom: ''
ms.date: 04/09/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a6493ba0-24e2-4c89-956e-9da1dea660cb
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab24c552a150e5a14037d727c8d3428eb6bbf809
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="program-and-linkage--c"></a>Program ve bağlantı (C++)

Bir C++ programı program birden fazla çeviri birimleri oluşuyorsa bile her genel simge yalnızca bir kez tanımlanabilir. Çeviri birimi, bir uygulama dosyası (.cpp, .hpp, .cxx, vb.) ve doğrudan veya dolaylı olarak içeren tüm üstbilgileri oluşur. Bir program, birbirine bağlı bir veya daha fazla çeviri biriminden oluşur. 

## <a name="linkage-vs-scope"></a>Bağlantı kapsam karşılaştırması

Kavramı *bağlantı* çeviri birimleri arasında (örneğin, değişkenleri, tür adları ve işlev adları) genel semboller program içinde görünürlüğünü bir bütün olarak başvuruyor. Kavramı *kapsam* ad alanı, sınıf veya işlev gövdesi gibi bir bloğu içinde bildirilen simgeleri başvuruyor. Bu tür simgeleri tanımlı kapsamı içinde görünür; bağlantı kavramı için geçerli değildir.

## <a name="external-vs-internal-linkage"></a>Dış ve iç bağlantı

Non-const genel değişkenler ve varsayılan olarak boş işlevleri dış bağlantı vardır; Bunlar, programı herhangi bir çeviri biriminden görülebilir. Bunları olarak bildirme açıkça tarafından bu davranışı geçersiz kılabilirsiniz **statik** bunlar bildirilen aynı çeviri birimine kendi visiblity sınırlar. Bu anlamını **statik** yerel değişkenlere uygulandığında anlamlarını farklıdır. Olarak bildirilen değişkenlerin **const** varsayılan olarak iç bağlantı vardır.

## <a name="extern-constexpr-linkage"></a>Extern constexpr bağlantı

Değişkeni extern bile işaretlendi, Visual Studio'nun önceki sürümleri derleyici constexpr değişken iç bağlantı her zaman verdi. Visual Studio 2017 sürüm 15,5, yeni derleyici anahtar içinde (/ Zc:externConstexpr) doğru standartları uyumsuz davranışı etkinleştirir. Sonuç olarak bu varsayılan olur.

```cpp
extern constexpr int x = 10; //error LNK2005: "int const x" already defined
```

Üstbilgi dosyası değişken bildirilen extern constexpr içeriyorsa, işaretlenmesi gerekiyor **__declspec(selectany)** birlikte, yinelenen bildirimler doğru olması için:

```cpp
extern constexpr __declspec(selectany) int x = 10;
```

## <a name="see-also"></a>Ayrıca Bkz.

 [Temel Kavramlar](../cpp/basic-concepts-cpp.md)