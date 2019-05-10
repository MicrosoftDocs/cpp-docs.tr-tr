---
title: C/C++ Yalıtılmış Uygulamaları Derleme
ms.date: 05/06/2019
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: 42192ad9388a8e69b70947c20c6fa7ee428a2bb9
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220963"
---
# <a name="building-cc-isolated-applications"></a>C/C++ Yalıtılmış Uygulamaları Derleme

Yalıtılmış bir uygulama, yan yana derlemelerini bağlıdır ve bir bildiri kullanarak bağımlılıklarını bağlar. Windows üzerinde düzgün şekilde çalıştırmak için tamamen yalıtılmış olarak uygulamanız için gerekli değildir; Gelecekte uygulamanıza bakım yapmak gerekiyorsa ancak uygulamanızın tam yalıtılmış yaparken yatırım tarafından zamandan tasarruf. Uygulamanızı tamamen yalıtılmış yapma avantajları hakkında daha fazla bilgi için bkz: [yalıtılmış uygulamalar](/windows/desktop/SbsCs/isolated-applications).

Yapı kurarken, yerel C /C++ Visual Studio Proje sistemi varsayılan olarak Visual Studio kullanarak uygulamayı Visual Studio kitaplıklarındaki uygulama bağımlılıklarınızın tanımlayan bir bildirim dosyası oluşturur. Bunların yalnızca bağımlılık olması halinde Visual Studio ile yeniden olarak yalıtılmış bir uygulama haline gelir sonra uygulamanız vardır. Uygulamanızın çalışma zamanında diğer kitaplıkları kullanan sonra yan yana derlemeler içinde açıklanan adımları izleyerek bu kitaplıkları yeniden gerekebilir [C/C++ yan yana derlemeler oluşturuluyor](building-c-cpp-side-by-side-assemblies.md).

## <a name="see-also"></a>Ayrıca bkz.

[Yalıtılmış Uygulama ve Yan Yana Derleme Kavramları](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ Yalıtılmış Uygulamaları ve Yan Yana Derlemeleri Oluşturma](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
