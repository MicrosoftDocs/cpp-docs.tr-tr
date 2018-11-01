---
title: Derleyici Uyarısı (düzey 4) C4471
ms.date: 04/24/2017
f1_keywords:
- C4471
helpviewer_keywords:
- C4471
ms.assetid: ccfd8bd5-bc1b-4be7-a6ea-0e3a7add6607
ms.openlocfilehash: 0345b730b8fc37329f632bb5d8486c67efd8e3b8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462224"
---
# <a name="compiler-warning-level-4-c4471"></a>Derleyici Uyarısı (düzey 4) C4471

'*numaralandırma*': kapsamsız bir numaralandırmanın İleri dönük bildiriminin bir temel türü (int varsayıldı) olmalıdır

Kapsamsız bir numaralandırmanın İleri dönük bildiriminin bir tanımlayıcı temel alınan türü için bulunamadı. Varsayılan olarak, Visual C++ varsayar `int` numaralandırma için temel alınan türü. Farklı bir açık tür belirtilirse, farklı bir tür numaralandırma tanımında, örneğin, kullanılıyorsa veya farklı bir tür bir başlatıcısı tarafından örtük olarak ayarlanırsa bu sorunlara neden olabilir. Taşınabilirlik sorunlarını da olabilir; diğer derleyiciler değil varsayar `int` temel numaralandırma türüdür.

Varsayılan olarak bu uyarıyı kapalıdır; /Wall veya /w kullanabileceğiniz*N*komut satırında etkinleştirmek veya #pragma 4471 [uyarı](../../preprocessor/warning.md) , kaynak dosyanızdaki.

Bazı durumlarda bu sahte bir uyarıdır. Bu uyarı, İleri dönük bildiriminin bir sabit listesi için tanımından sonra görünüyorsa, harekete. Örneğin, C4471 neden olsa bile bu kod geçerli şöyledir:

```cpp
// C4471a.cpp
// Compile with: cl /c /w14471 C4471a.cpp
enum Example { item = 0x80000000UL };
enum Example;    // Spurious C4471
// ...
```

## <a name="example"></a>Örnek

Genel olarak, İleri dönük bildirimi yerine kapsamlı olmayan numaralandırma için tam tanımı kullanmak güvenlidir. Tanımı bir üstbilgi dosyasında yerleştirin ve ona başvuran kaynak dosyaları dahil edin. Bu, C ++ 98 ve üzeri için yazılmış kod içinde çalışır. Bu çözüm taşınabilirlik ve Bakım kolaylığı için öneririz.

```cpp
// C4471b.cpp
// Compile with: cl /c /w14471 C4471b.cpp
enum Example;    // C4471
// To fix, replace the line above with the enumeration definition:
// enum Example { item = 0x80000000UL };
// ...
```

## <a name="example"></a>Örnek

C ++ 11'de, kapsamlı olmayan numaralandırma ve kendi İleri dönük bildirimi için açık bir tür ekleyebilirsiniz. Karmaşık üstbilgi ekleme mantığı kullanmak yerine İleri dönük bildiriminin tanımının engelliyorsa Bu çözüm öneririz. Bu çözüm için bir bakım sorunu neden olabilir: numaralandırma tanımı için kullanılan temel alınan türünü değiştirmek tüm eşleştirilecek bildirimleri ayrıca değiştirmeli veya kodunuzda sessiz hataları olabilir. Bu sorunu en aza indirmek için bir üstbilgi dosyasına İleri dönük bildirimi koyabilirsiniz.

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

Bir numaralandırma için açık bir tür belirtirseniz, uyarı de etkinleştirmeniz önerilir [C4369](compiler-warning-level-1-C4369.md), hangi varsayılan olarak açıktır. Bu, burada bir sabit listesi öğesi farklı bir türe açıkça belirtilen türe ihtiyaç duyması tanımlar.

## <a name="example"></a>Örnek

C ++ 11'de yeni bir özellik kapsamlı enum kullanmak için kodunuzu değiştirebilirsiniz. Hem tanımı hem de sabit listesi türünü kullanan herhangi bir istemci kod kapsamlı enum kullanmak için değiştirilmesi gerekir. Ad alanı kirliliği ile ilgili sorunlar varsa, tanımlanan numaralandırma öğelerin adlarını enum kapsamına sınırlı olduğu gibi kapsamlı bir numaralandırma kullanmanızı öneririz. Başka bir kapsamlı numaralandırma üyelerini küçük hatalar, kaynak olabilecek başka bir integral veya numaralandırma türü, örtük olarak dönüştürülemez özelliğidir.

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

