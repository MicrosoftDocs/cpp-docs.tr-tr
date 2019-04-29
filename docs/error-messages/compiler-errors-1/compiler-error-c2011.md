---
title: Derleyici Hatası C2011
ms.date: 11/04/2016
f1_keywords:
- C2011
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
ms.openlocfilehash: 14969c9cdf4b00844d2001bf4817ea7ffc9bfba6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361561"
---
# <a name="compiler-error-c2011"></a>Derleyici Hatası C2011

'identifier': 'type' türü yeniden tanımı

Tanımlayıcı olarak tanımlandı `type`. Tanımlayıcı yeniden tanımlaması için denetleyin.

Bir üst bilgi dosyasını içeri aktarın ya da birden çok kez aynı dosyada tür kitaplığı C2011 de alabilirsiniz. Bir üstbilgi dosyasında tanımlanan türleri birden çok ekleme yapılmasının önlemek için kullanımını içerir cf veya `#pragma` [sonra](../../preprocessor/once.md) üstbilgi dosyasında yönergesi.

Yeniden tanımlanan tür ilk bildirimine bulmanız gerekiyorsa, kullanabileceğiniz [/P](../../build/reference/p-preprocess-to-a-file.md) önceden işlenmiş çıktı üretme derleyici bayrağı için derleyici geçirilen. Metin arama araçları, çıkış dosyasında yeniden tanımlanan tanımlayıcı örneklerini bulmak için kullanabilirsiniz.

Aşağıdaki örnek, C2011 oluşturur ve bunu çözmenin yollarından biri gösterilmektedir:

```
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```