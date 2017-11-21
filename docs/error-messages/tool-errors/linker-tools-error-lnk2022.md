---
title: "Bağlayıcı araçları hatası LNK2022 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2022
dev_langs: C++
helpviewer_keywords: LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 022ad56460ad666a5d02c4f176093f16a82b4e40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2022"></a>Bağlayıcı Araçları Hatası LNK2022  
  
> meta veri işlemi başarısız oldu (*HRESULT*): *error_message*  
  
Bağlayıcı, meta veri birleştirme sırasında bir hata algıladı. Başarılı bir şekilde bağlanmak için meta veri sorunların çözülmesi gerekir.  
  
Bu sorunu tanılamak için bir yoldur çalıştırmak için **ildasm-belirteçleri** belirteçleri hangi türlerine sahip bulunacak nesne dosyaları listelenen `error_message`ve farkları bakın.  Meta verilerde aynı ada sahip iki farklı türü geçerli değil, yalnızca LayoutType öznitelik farklı olsa bile.  
  
Bir nedeni bir türü (örneğin, bir yapının) aynı ada sahip, ancak çakışan tanımları içeren birden çok derlenecek dosyalar varken LNK2022 için ve ile derlerken [/CLR](../../build/reference/clr-common-language-runtime-compilation.md).  Bu durumda, türü tüm derlenecek dosyalar özdeş bir tanımı sahip olduğundan emin olun.  Tür adı listelenir `error_message`.  
  
Bağlayıcı derleyiciye belirtilenden farklı bir konumda bir meta veri dosyası bulduğunda, başka bir olası LNK2022 nedeni (ile [#using](../../preprocessor/hash-using-directive-cpp.md) ). Derleyiciye geçirildiğinde olduğu gibi meta veri dosyasının (.dll veya .netmodule) bağlayıcıya geçirildiğinde aynı konumda olduğundan emin olun.  
  
ATL uygulamasını, makrosu kullanımını oluştururken `_ATL_MIXED` en az birinde kullanılırsa, tüm derlenecek dosyalar gereklidir.  
  
## <a name="example"></a>Örnek  
  
Aşağıdaki örnek, boş bir türü tanımlar.  
  
```cpp  
// LNK2022_a.cpp  
// compile with: /clr /c  
public ref class Test {};  
```  
  
## <a name="example"></a>Örnek  
  
Bu örnek, aynı adlı ancak farklı tanımları türlerini içeren iki kaynak kodu dosyaları bağlayamazsınız göstermektedir.  
  
Aşağıdaki örnek LNK2022 oluşturur.  
  
```cpp  
// LNK2022_b.cpp  
// compile with: LNK2022_a.cpp /clr /LD   
// LNK2022 expected  
public ref class Test {  
   void func() {}  
   int var;  
};  
```