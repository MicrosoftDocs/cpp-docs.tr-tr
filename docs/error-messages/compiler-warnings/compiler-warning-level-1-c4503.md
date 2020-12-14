---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) böylelikle C4503'
title: Derleyici Uyarısı (düzey 1) böylelikle C4503
ms.date: 05/14/2018
f1_keywords:
- C4503
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
ms.openlocfilehash: 4ff438c3ae9e698bdaaf476d022b8914add4169e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294905"
---
# <a name="compiler-warning-level-1-c4503"></a>Derleyici Uyarısı (düzey 1) böylelikle C4503

> '*tanımlayıcı*': düzenlenmiş ad uzunluğu aşıldı, ad kesildi

## <a name="remarks"></a>Açıklamalar

Bu derleyici uyarısı artık kullanılmıyor ve Visual Studio 2017 ve üzeri derleyicilerde oluşturulmamış.

Düzenlenmiş ad, derleyici sınırından (4096) daha uzun ve kesildi. Bu uyarıyı ve kesilmesini önlemek için, kullanılan tanımlayıcıların veya ad uzunluklarının sayısını azaltın. Derleyici sınırından daha uzun olan düzenlenmiş adların bir karması uygulanmış ve ad çarpışmanın tehlike altında olmadığı.

Visual Studio 'nun daha eski bir sürümünü kullanırken, kodunuz şablonlarda görsel olarak özelleştirilmiş şablonlar içerdiğinde bu uyarı verilebilir. Örneğin, haritalar Haritası (C++ standart kitaplığından). Bu durumda, tür tanımları ' ı eşlemeyi içeren bir tür ( **`struct`** Örneğin,) yapabilirsiniz.

Ancak, kodunuzu yeniden yapılandırmak istemediğinize karar verebilirsiniz.  Böylelikle C4503 üreten bir uygulama teslim etmek mümkündür, ancak kesilen bir sembolle bağlantı zamanı hataları alırsanız, hata içindeki sembolün türünü belirlemek daha zor olabilir. Hata ayıklama da daha zor olabilir; hata ayıklayıcının sembol adı tür adı ile difficultly eşlemesi olabilir. Ancak programın doğruluğu, kesilen adından etkilenmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, Visual Studio 2017 öncesi derleyicilerde böylelikle C4503 oluşturur:

```cpp
// C4503.cpp
// compile with: /W1 /EHsc /c
// C4503 expected
#include <string>
#include <map>

class Field{};

typedef std::map<std::string, Field> Screen;
typedef std::map<std::string, Screen> WebApp;
typedef std::map<std::string, WebApp> WebAppTest;
typedef std::map<std::string, WebAppTest> Hello;
Hello MyWAT;
```

Bu örnek, böylelikle C4503 çözümlemek için kodunuzu yeniden yazmak için bir yol gösterir:

```cpp
// C4503b.cpp
// compile with: /W1 /EHsc /c
#include <string>
#include <map>

class Field{};

struct Screen2 {
   std::map<std::string, Field> Element;
};

struct WebApp2 {
   std::map<std::string, Screen2> Element;
};

struct WebAppTest2 {
   std::map<std::string, WebApp2> Element;
};

struct Hello2 {
   std::map<std::string, WebAppTest2> Element;
};

Hello2 MyWAT2;
```
