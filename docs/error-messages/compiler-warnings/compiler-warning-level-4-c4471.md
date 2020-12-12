---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4471'
title: Derleyici Uyarısı (düzey 4) C4471
ms.date: 04/24/2017
f1_keywords:
- C4471
helpviewer_keywords:
- C4471
ms.assetid: ccfd8bd5-bc1b-4be7-a6ea-0e3a7add6607
ms.openlocfilehash: cef492bf8aab33f46b3f590a13ffa5462a7ca41d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203503"
---
# <a name="compiler-warning-level-4-c4471"></a>Derleyici Uyarısı (düzey 4) C4471

'*Enumeration*': kapsamlı olmayan numaralandırmanın ileri bir bildiriminin temel bir türü olmalıdır (int varsayıldı)

Temel alınan tür için tanımlayıcı olmadan kapsamlı olmayan numaralandırmanın ileri bir bildirimi bulundu. Varsayılan olarak Visual C++, **`int`** bir numaralandırma için temeldeki tür olarak varsayılır. Bu, sabit listesi tanımında farklı bir tür kullanılırsa, örneğin, farklı bir açık tür belirtilmişse veya farklı bir tür bir başlatıcı tarafından örtük olarak ayarlandıysa soruna neden olabilir. Ayrıca taşınabilirlik sorunlarınız da olabilir; diğer derleyiciler, **`int`** numaralandırmanın temel alınan türüdür.

Bu uyarı varsayılan olarak kapalıdır; komut satırında etkinleştirmek için/Duvarveya/w *N* 4471 kullanabilirsiniz veya kaynak dosyanızda #pragma [Uyarı](../../preprocessor/warning.md) kullanabilirsiniz.

## <a name="examples"></a>Örnekler

Bazı durumlarda bu uyarı, smerak ediyor. Bir numaralandırma için ileri bildirim, tanımdan sonra görünürse, bu uyarı harekete çıkabilir. Örneğin, bu kod C4471 neden olabilir, ancak şu şekilde geçerlidir:

```cpp
// C4471a.cpp
// Compile with: cl /c /w14471 C4471a.cpp
enum Example { item = 0x80000000UL };
enum Example;    // Spurious C4471
// ...
```

Genel olarak, ileri bildirim yerine kapsamlı olmayan numaralandırma için tam tanımı kullanmak güvenlidir. Tanımı bir başlık dosyasına yerleştirebilir ve buna başvuran kaynak dosyalara dahil edebilirsiniz. Bu, C++ 98 ve üzeri için yazılmış kodda kullanılır. Bu çözümü taşınabilirlik ve bakım kolaylığı için öneririz.

```cpp
// C4471b.cpp
// Compile with: cl /c /w14471 C4471b.cpp
enum Example;    // C4471
// To fix, replace the line above with the enumeration definition:
// enum Example { item = 0x80000000UL };
// ...
```

C++ 11 ' de, kapsamlı olmayan bir numaralandırmaya ve ileri bildirimine açık bir tür ekleyebilirsiniz. Bu çözümü yalnızca karmaşık üstbilgi ekleme mantığı, bir iletme bildirimi yerine tanımın kullanılmasını engelliyorsa önerilir. Bu çözüm bir bakım sorununa yol açabilir: sabit listesi tanımı için kullanılan temel türü değiştirirseniz, aynı zamanda tüm ileriye doğru bildirimleri de değiştirmeniz gerekir veya kodunuzda sessiz hatalara sahip olabilirsiniz. Bu sorunu en aza indirmek için ileri bildirimini bir üstbilgi dosyasına koyabilirsiniz.

```cpp
// C4471c.cpp
// Client code for enumeration defined in C4471d.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example;    // C4471, int assumed
// To fix, replace the lines above with the forward declarations:
// enum Example : unsigned;
// ...
```

```cpp
// C4471d.cpp
// Definition for enumeration used in C4471c.cpp
// Compile with: cl /c /w14471 C4471c.cpp C4471d.cpp
enum Example : unsigned { item = 0x80000000 }; // explicit type
// ...
```

Bir numaralandırma için açık bir tür belirtirseniz, varsayılan olarak açık olan uyarı [C4369](compiler-warning-level-1-C4369.md)de etkinleştirmenizi öneririz. Bu, bir numaralandırma öğesinin açıkça belirtilen türden farklı türde olması gereken durumları tanımlar.

C++ 11 ' deki yeni bir özellik olan kapsamlı bir sabit listesi kullanmak için kodunuzu değiştirebilirsiniz. Hem tanım hem de numaralandırma türünü kullanan istemci kodları kapsamlı bir sabit listesi kullanacak şekilde değiştirilmelidir. Tanımlı numaralandırma öğelerinin adları, numaralandırmanın kapsamıyla sınırlı olduğu için, ad alanı kirliliğine sahip sorunlarınız varsa kapsamlı bir sabit listesi kullanmanızı öneririz. Kapsamlı bir numaralandırmanın başka bir özelliği, üyelerinin örtük olarak başka bir integral veya numaralandırma türüne dönüştürülemeymesidir ve bu da hafif hataların kaynağı olabilir.

```cpp
// C4471e.cpp
// Client code for scoped enumeration defined in C4471f.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum Example;    // C4471
// To fix, replace the line above with the forward declaration:
// enum class Example;
// ...
```

```cpp
// C4471f.cpp
// Definition for scoped enumeration used in C4471e.cpp
// Compile with: cl /c /w14471 C4471e.cpp C4471f.cpp
enum class Example { item = 0 };
// ...
```
