---
title: Derleyici Hatası C2011 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2011
dev_langs:
- C++
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09946a6a3e974293e65a582c735e3de42503f0c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115049"
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