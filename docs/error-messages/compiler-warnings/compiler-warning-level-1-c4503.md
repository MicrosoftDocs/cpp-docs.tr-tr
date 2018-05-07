---
title: Derleyici Uyarısı (düzey 1) C4503 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
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
ms.openlocfilehash: adafddff679cbe04cf26a39647760bf595af0bd3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4503"></a>Derleyici Uyarısı (düzey 1) C4503
'tanımlayıcısı': ad uzunluğu aşıldı, donatılmış adı kesildi  
  
 Düzenlenmiş adı (4096) derleyici sınırdan daha uzun ve kesildi. Bu uyarı ve kesme önlemek için bağımsız değişken sayısı ve kullanılan tanımlayıcıları adı uzunluğunu azaltın.  
  
 Kodunuzu içerdiğinde bu uyarı burada verilecek bir şablonları şablonlarındaki art arda özel durumdur.  Örneğin, bir haritasını haritaları (C++ Standart Kitaplığı).  Bu durumda, eşleme içeren bir türü (örneğin, yapı), tür tanımları yapabilirsiniz.  
  
 Ancak, kodunuzu yeniden yapılandırmayı değil isteyebilirsiniz.  C4503 oluşturan bir uygulama sevk mümkündür, ancak kesilmiş simgesinin üzerine bağlantı zamanı hataları alırsanız, hata simgesi türünü belirleme daha zor olacaktır.  Hata ayıklama aynı zamanda bu kadar daha zor olacaktır; hata ayıklayıcı difficultly adını yazmanız için sembol adı eşleme da sahip olursunuz.  Program doğruluğunu ancak kesilmiş adıyla etkilenmez.  
  
 Aşağıdaki örnek C4503 oluşturur:  
  
```  
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
  
 Aşağıdaki örnek, C4503 çözümlemek için kodunuzu yeniden yazma için bir yol gösterir:  
  
```  
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