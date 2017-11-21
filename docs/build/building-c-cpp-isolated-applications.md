---
title: "C/C++ yalıtılmış uygulamaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5af0dde80a143166d9824d2739632ca7e7ed4382
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="building-cc-isolated-applications"></a>C/C++ Yalıtılmış Uygulamaları Derleme
Yalıtılmış bir uygulama, yalnızca yan yana derlemelerini bağlıdır ve bir bildirim kullanarak bağımlılıklarını bağlar. Windows üzerinde düzgün çalışması için tam yalıtılmış olması, uygulamanız için gerekli değildir; Uygulamanızı gelecekte hizmet gerekiyorsa, ancak, tam olarak yalıtılmış uygulamanızı yaparken yatırım tarafından zamandan tasarruf. Tamamen yalıtılmış uygulamanızı yapmadan avantajları hakkında daha fazla bilgi için bkz: [yalıtılmış uygulamalar](http://msdn.microsoft.com/library/aa375190).  
  
 Visual C++ kullanarak yerel C/C++ uygulamanızı oluşturma sırasında varsayılan olarak Visual Studio Proje sistemi Visual C++ kitaplıkları, uygulamanızın bağımlılıkları tanımlayan bir bildirim dosyası oluşturur. Bunlar yalnızca bağımlılıkları ise Visual Studio ile yeniden hemen yalıtılmış bir uygulama olur sonra uygulamanızın yoktur. Uygulamanızın çalışma zamanında diğer kitaplıklarını kullanarak sonra bu kitaplıkları açıklanan adımları izleyerek yan yana derlemeleri olarak yeniden oluşturma gerekebilir [yapı C/C++ yan yana derlemeler](../build/building-c-cpp-side-by-side-assemblies.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Yalıtılmış uygulamalar ve yan yana derlemeler kavramları](../build/concepts-of-isolated-applications-and-side-by-side-assemblies.md)   
 [C/C++ yalıtılmış uygulamaları ve yan yana derlemeler](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)