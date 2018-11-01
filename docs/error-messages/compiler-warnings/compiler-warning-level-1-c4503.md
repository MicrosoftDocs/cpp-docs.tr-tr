---
title: Derleyici Uyarısı (düzey 1) C4503
ms.date: 05/14/2018
f1_keywords:
- C4503
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
ms.openlocfilehash: 94c88511d87c3adf3cf5687a94948c83ebc5b3d5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50459793"
---
# <a name="compiler-warning-level-1-c4503"></a>Derleyici Uyarısı (düzey 1) C4503

> '*tanımlayıcı*': düzenlenmiş adı uzunluğu aşıldı, ad kesildi

## <a name="remarks"></a>Açıklamalar

Bu derleyici uyarı artık kullanılmıyor ve Visual Studio 2017 ve sonraki derleyiciler oluşturulmaz.

Düzenlenmiş adı (4096) derleyici sınırından daha uzun ve kesildi. Bu uyarı ve kesilmesini önlemek için bağımsız değişken sayısı veya kullanılan tanımlayıcı adı uzunluğu azaltın. Düzenlenmiş olan derleyici sınırı daha uzun olan uygulanan bir karma değer ve bir ad çakışması tehlikesi olmayan adları.

Visual Studio'nun daha eski bir sürümü kullanırken, kodunuzu şablonları içerdiğinde bu uyarı verilebilir şablonlarındaki art arda özelleştirilmiş. Örneğin, bir haritasını haritaları (C++ Standart Kitaplığı). Bu durumda, bir tür, tür tanımları yapabilirsiniz (bir **yapı**, örneğin) map içeren.

Ancak, kodunuzu yeniden yapılandırmayı değil isteyebilirsiniz.  Böylece C4503 oluşturan bir uygulama göndermeye mümkündür, ancak kesilmiş bir sembol sunucusunda bağlantı zamanı hataları alırsanız, hata simgenin türünü belirlemek daha zor olabilir. Mayıs de hata ayıklama daha zor; hata ayıklayıcı sembol adı tür adına difficultly eşleme olabilir. Doğruluk programın ancak kesilmiş adı tarafından etkilenmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek Visual Studio 2017 derleyicilerinde C4503 oluşturur:

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

Bu örnek, böylelikle C4503 çözümlemek için kodunuzu yeniden yazma yollarından biri gösterilmektedir:

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