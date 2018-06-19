---
title: Derleyici Uyarısı (düzey 4) C4471 | Microsoft Docs
ms.custom: ''
ms.date: 04/24/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4471
dev_langs:
- C++
helpviewer_keywords:
- C4471
ms.assetid: ccfd8bd5-bc1b-4be7-a6ea-0e3a7add6607
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a530cee3c3fcfec8566d46b116fcc4e71760ed11
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33302691"
---
# <a name="compiler-warning-level-4-c4471"></a>Derleyici Uyarısı (düzey 4) C4471
'*numaralandırma*': dizininden kapsam dışı numaralandırma ileriye dönük bildirimi bir temel alınan türü (int olduğu varsayılır) olması gerekir  
  
Dizininden kapsam dışı numaralandırma ileriye dönük bildirimi tanımlayıcısı için temel alınan tür bulundu. Varsayılan olarak, Visual C++ varsayar `int` numaralandırması için temel alınan tür değil. Farklı bir açık tür belirtilirse, farklı bir tür numaralandırma tanımı'nda, örneğin, kullanılıyorsa veya farklı bir tür başlatıcısı tarafından dolaylı olarak ayarlanmışsa, bu sorunlara neden olabilir. Taşınabilirlik sorunlarını da olabilir; diğer derleyiciler değil varsayın `int` numaralandırma temel türü.  
  
Varsayılan olarak bu uyarı kapalıdır; wln veya /w kullanabilirsiniz*N*komut satırında etkinleştirmek veya #pragma kullanmak için 4471 [uyarı](../../preprocessor/warning.md) kaynak dosyanızdaki.  
  
Bazı durumlarda, bu uyarıyı alacaklardır. Bir sabit listesi için ileriye dönük bildirimi sonra tanımı görünüyorsa, bu uyarıyı harekete. Örneğin, C4471 neden olabilir olsa bile bu kodu geçerli verilmiştir:  
  
```cpp  
// C4471a.cpp
// Compile with: cl /c /w14471 C4471a.cpp
enum Example { item = 0x80000000UL };
enum Example;    // Spurious C4471
// ...
```  
  
## <a name="example"></a>Örnek  
Genel olarak, ileriye dönük bildirimi yerine dizininden kapsam dışı numaralandırması için tam tanımı kullanmak güvenlidir. Tanımı bir üstbilgi dosyasında koyun ve başvurduğu kaynak dosyaları dahil edin. Bu, C ++ 98 ve daha sonra yazılan kodu çalışır. Bu çözüm taşınabilirlik ve Bakım kolaylığı için öneririz.  
  
```cpp  
// C4471b.cpp
// Compile with: cl /c /w14471 C4471b.cpp
enum Example;    // C4471
// To fix, replace the line above with the enumeration definition:
// enum Example { item = 0x80000000UL };
// ...
```  
  
## <a name="example"></a>Örnek  
C ++ 11'de, bir açık tür dizininden kapsam dışı numaralandırma ve iletme bildiriminden ekleyebilirsiniz. Karmaşık üstbilgi ekleme mantığı ileriye dönük bildirimi yerine tanımı kullanımını engelliyorsa Bu çözüm öneririz. Bu çözüm bir bakım soruna yol açabilir: numaralandırma tanımı için kullanılan temel türünü değiştirmek tüm eşleşecek şekilde iletme bildirimlerinin da değiştirmelisiniz veya kodunuzda sessiz hataları olabilir. Bu sorunu en aza indirmek için bir üstbilgi dosyasına ileriye dönük bildirimi koyabilirsiniz.  
  
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
  
Bir sabit listesi için açık bir tür belirtirseniz, uyarı da etkinleştirmeniz önerilir [C4369](compiler-warning-level-1-C4369.md), hangi varsayılan olarak açıktır. Bu, burada açıkça belirtilen türü farklı bir type numaralandırması öğe gerektirdiği durumlar tanımlar.
  
## <a name="example"></a>Örnek  
Kapsamlı bir liste, C ++ 11'de yeni bir özelliğini kullanmak için kodunuzu değiştirebilirsiniz. Tanım ve numaralandırma türü kullanan tüm istemci kodu kapsamlı bir liste kullanmak için değiştirilmesi gerekir. Ad alanı kirliliği sorunlar varsa, tanımlanan numaralandırma öğelerin adlarını enum kapsamına sınırlı olduğu gibi kapsamlı bir liste kullanmanızı öneririz. Başka bir kapsamlı bir liste üyeleri Zarif hataların bir kaynak olabilen başka bir tamsayı veya numaralandırma türüne örtük olarak dönüştürülemiyor özelliğidir.

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
  
