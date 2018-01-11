---
title: "Uygulama etki alanları ve Visual C++ | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- interop [C++], application domains
- application domains [C++], C++
- /clr compiler option [C++], application domains
- interoperability [C++], application domains
- mixed assemblies [C++], application domains
ms.assetid: 75a08efc-9b02-40ba-99b7-dcbd71010bbf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a66731b9645458441f1c3e1f211c74be698e7231
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="application-domains-and-visual-c"></a>Uygulama Etki Alanları ve Visual C++
Varsa bir `__clrcall` sanal işlev vtable (appdomain) uygulama etki alanı başına olacaktır. Bir appdomain içinde bir nesne oluşturursanız, yalnızca o appdomain içinde sanal işlevden çağırabilir. İçinde tanımlanan tüm işlevleri **/CLR: pure** derlenecek dosyalar kullanmak `__clrcall` çağırma. Bu nedenle, içindeki tüm vtable tanımlanan **/CLR: pure** derlenecek dosyalar olan appdomain. Karma modda (**/CLR**) türünüz Hayır varsa işlem başına vtable olacaktır `__clrcall` sanal işlevleri. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 Daha fazla bilgi için bkz.  
  
-   [appdomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [Nasıl yapılır: pure'a Geçiş: Saf (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [process](../cpp/process.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)