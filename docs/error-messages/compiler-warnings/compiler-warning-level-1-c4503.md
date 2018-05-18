---
title: Derleyici Uyarısı (düzey 1) C4503 | Microsoft Docs
ms.custom: ''
ms.date: 05/14/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4503
dev_langs:
- C++
helpviewer_keywords:
- C4503
ms.assetid: 7c5a98ae-5b6d-41d8-b881-12d3ffd5e392
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f60fdb44c5368ccc5c5f089002614332d95a63fe
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/17/2018
---
# <a name="compiler-warning-level-1-c4503"></a>Derleyici Uyarısı (düzey 1) C4503

> '*tanımlayıcısı*': ad uzunluğu aşıldı, donatılmış adı kesildi

## <a name="remarks"></a>Açıklamalar

Bu derleyici uyarısı kullanımdan kalkmıştır ve Visual Studio 2017 ve sonraki derleyicileri oluşturulmaz.

Düzenlenmiş adı (4096) derleyici sınırdan daha uzun ve kesildi. Bu uyarı ve kesme önlemek için bağımsız değişken sayısı ve kullanılan tanımlayıcıları adı uzunluklarının azaltın. Düzenlenmiş olan derleyici sınırdan daha uzun uygulanan bir karma olabilir ve bir ad çakışması tehlike içinde olmayan adlar.

Visual Studio'nun daha eski bir sürümünü kullanırken, kodunuzu şablonları içerdiğinde bu uyarı verilebilir şablonlarındaki art arda özelleştirilmiş. Örneğin, bir haritasını haritaları (C++ Standart Kitaplığı). Bu durumda, bir tür, tür tanımları yapabilirsiniz (bir **yapısı**, örneğin) eşlemesi içerir.

Ancak, kodunuzu yeniden yapılandırmayı değil isteyebilirsiniz.  C4503 oluşturan bir uygulama sevk mümkündür, ancak kesilmiş simgesinin üzerine bağlantı zamanı hataları alırsanız, hata simgesi türünü belirleme daha zor olabilir. Mayıs de hata ayıklama daha zor; hata ayıklayıcı difficultly sembol adı türü adına eşleme olabilir. Program doğruluğunu ancak kesilmiş adıyla etkilenmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek Visual Studio 2017 önce derleyicileri C4503 oluşturur:

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

Bu örnek C4503 çözümlemek için kodunuzu yeniden yazma için bir yol göstermektedir:

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