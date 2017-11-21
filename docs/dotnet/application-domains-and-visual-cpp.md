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
ms.openlocfilehash: 57a45bd6f73040623fe90626b1c3896df3258dd8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="application-domains-and-visual-c"></a>Uygulama Etki Alanları ve Visual C++
Varsa bir `__clrcall` sanal işlev vtable (appdomain) uygulama etki alanı başına olacaktır. Bir appdomain içinde bir nesne oluşturursanız, yalnızca o appdomain içinde sanal işlevden çağırabilir. İçinde tanımlanan tüm işlevleri **/CLR: pure** derlenecek dosyalar kullanmak `__clrcall` çağırma. Bu nedenle, içindeki tüm vtable tanımlanan **/CLR: pure** derlenecek dosyalar olan appdomain. Karma modda (**/CLR**) türünüz Hayır varsa işlem başına vtable olacaktır `__clrcall` sanal işlevleri. **/CLR: pure** ve **/CLR: safe** derleyici seçenekleri Visual Studio 2015'te kullanım dışı.  
  
 Daha fazla bilgi için bkz.  
  
-   [AppDomain](../cpp/appdomain.md)  
  
-   [__clrcall](../cpp/clrcall.md)  
  
-   [Nasıl yapılır: pure'a Geçiş: Saf (C + +/ CLI)](../dotnet/how-to-migrate-to-clr-pure-cpp-cli.md)  
  
-   [işlem](../cpp/process.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)