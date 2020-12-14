---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2011'
title: Derleyici hatası C2011
ms.date: 11/04/2016
f1_keywords:
- C2011
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
ms.openlocfilehash: c310495c570a2259cf5abe6acea951ca996bfb26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221026"
---
# <a name="compiler-error-c2011"></a>Derleyici hatası C2011

' tanımlayıcı ': ' Type ' türü yeniden tanımı

Tanımlayıcı zaten olarak tanımlandı `type` . Tanımlayıcının yeniden tanımlarını denetleyin.

Ayrıca, bir üst bilgi dosyasını veya tür kitaplığını aynı dosyaya birden fazla kez içeri aktarırsanız de C2011 alabilirsiniz. Üst bilgi dosyasında tanımlı türlerin birden çok eklemeyi engellemek için, üstbilgi dosyasında ekleme koruyucuları veya bir `#pragma` [bir kez](../../preprocessor/once.md) yönergesi kullanın.

Yeniden tanımlanmış türün ilk bildirimini bulmanız gerekiyorsa, derleyiciye geçirilen önceden işlenmiş çıktıyı oluşturmak için [/p](../../build/reference/p-preprocess-to-a-file.md) derleyici bayrağını kullanabilirsiniz. Çıkış dosyasında yeniden tanımlanmış tanımlayıcının örneklerini bulmak için metin arama araçları 'nı kullanabilirsiniz.

Aşağıdaki örnek C2011 oluşturur ve bunu çözmek için bir yol gösterir:

```cpp
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```
