---
description: 'Daha fazla bilgi edinin: C/C++ yalıtılmış uygulamaları oluşturma'
title: C/C++ Yalıtılmış Uygulamaları Derleme
ms.date: 05/06/2019
helpviewer_keywords:
- isolated applications [C++]
ms.assetid: 8a2fe4fa-0489-433e-bfc6-495844d8d73a
ms.openlocfilehash: a8cd99032c27d21efaec7f213c470017e52777c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163216"
---
# <a name="building-cc-isolated-applications"></a>C/C++ Yalıtılmış Uygulamaları Derleme

Yalıtılmış bir uygulama yalnızca yan yana derlemelere bağlıdır ve bir bildirim kullanarak bağımlılıklarına bağlar. Uygulamanızın Windows 'da düzgün çalışması için tamamen yalıtılmış olması gerekmez; Bununla birlikte, uygulamanızı tamamen yalıtılmış hale getirerek, daha sonra uygulamanıza hizmet etmeniz gerekiyorsa zamandan tasarruf edebilirsiniz. Uygulamanızı tamamen yalıtılmış hale getirme avantajları hakkında daha fazla bilgi için bkz. [Yalıtılmış uygulamalar](/windows/win32/SbsCs/isolated-applications).

Visual Studio kullanarak yerel C/C++ uygulamanızı yapılandırdığınızda, varsayılan olarak Visual Studio proje sistemi, uygulamanızın Visual Studio kitaplıklarında bağımlılıklarını açıklayan bir bildirim dosyası oluşturur. Bunlar, uygulamanızın sahip olduğu tek bağımlılıklardır, Visual Studio ile yeniden oluşturulduktan hemen sonra yalıtılmış bir uygulama haline gelir. Uygulamanız çalışma zamanında başka kitaplıklar kullanıyorsa, bu kitaplıkları [C/C++ yan yana derlemeler oluşturma](building-c-cpp-side-by-side-assemblies.md)bölümünde açıklanan adımları izleyerek yan yana derlemeler olarak yeniden oluşturmanız gerekebilir.

## <a name="see-also"></a>Ayrıca bkz.

[Yalıtılmış uygulamalar ve yan yana derlemeler için kavramlar](concepts-of-isolated-applications-and-side-by-side-assemblies.md)<br/>
[C/C++ yalıtılmış uygulamaları ve yan yana derlemeler oluşturma](building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)
