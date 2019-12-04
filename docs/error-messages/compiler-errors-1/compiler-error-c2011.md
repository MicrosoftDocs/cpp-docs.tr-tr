---
title: Derleyici hatası C2011
ms.date: 11/04/2016
f1_keywords:
- C2011
helpviewer_keywords:
- C2011
ms.assetid: 992c9d51-e850-4d53-b86b-02e73b38249c
ms.openlocfilehash: dc13829a267deea1f412eb2d8f86057f01dc0e1c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74752424"
---
# <a name="compiler-error-c2011"></a>Derleyici hatası C2011

' tanımlayıcı ': ' Type ' türü yeniden tanımı

Tanımlayıcı zaten `type`olarak tanımlandı. Tanımlayıcının yeniden tanımlarını denetleyin.

Ayrıca, bir üst bilgi dosyasını veya tür kitaplığını aynı dosyaya birden fazla kez içeri aktarırsanız de C2011 alabilirsiniz. Üst bilgi dosyasında tanımlı türlerin birden çok eklemeyi engellemek için, üstbilgi dosyasındaki ekleme koruyucuları veya bir [kez](../../preprocessor/once.md) `#pragma`kullanın.

Yeniden tanımlanmış türün ilk bildirimini bulmanız gerekiyorsa, derleyiciye geçirilen önceden işlenmiş çıktıyı oluşturmak için [/p](../../build/reference/p-preprocess-to-a-file.md) derleyici bayrağını kullanabilirsiniz. Çıkış dosyasında yeniden tanımlanmış tanımlayıcının örneklerini bulmak için metin arama araçları 'nı kullanabilirsiniz.

Aşağıdaki örnek C2011 oluşturur ve bunu çözmek için bir yol gösterir:

```cpp
// C2011.cpp
// compile with: /c
struct S;
union S;   // C2011
union S2;   // OK
```
