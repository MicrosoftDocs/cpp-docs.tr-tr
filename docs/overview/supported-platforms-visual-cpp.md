---
title: Desteklenen Platformlar (Visual C++)
ms.date: 11/04/2016
ms.technology: cpp-tools
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
author: mikeblome
ms.author: mblome
ms.openlocfilehash: 39be17904f19bebdd9313a767de91a7315c3ca66
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787635"
---
# <a name="supported-platforms-visual-c"></a>Desteklenen Platformlar (Visual C++)

Visual Studio kullanılarak oluşturulmuş uygulamalar gibi çeşitli platformlar için hedeflenebilir.

|İşletim sistemi|x86|X64|ARM|
|----------------------|---------|---------|---------|
|Windows XP|X\*|X\*||
|Windows Server 2003|X\*|X\*||
|Windows Vista|X|X||
|Windows Server 2008|X|X||
|Windows 7|X|X||
|Windows Server 2012 R2|X|X||
|Windows 8|X|X|X|
|Windows 8.1|X|X|X|
|Windows 10|X|X|X|
|Android \*\*|X|X|X|
|iOS \*\*|X|X|X|
|Linux \*\*\*|X|X|X|

\* Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 ve Visual Studio 2012 güncelleştirme 1 veya daha sonra Windows XP ve Windows Server 2003 projeleri derlemek için dahil Windows XP platform araç takımını kullanabilirsiniz. Bu platform Araç Takımı'nı kullanma hakkında daha fazla bilgi için bkz: [yapılandırma programlar için Windows XP](../build/configuring-programs-for-windows-xp.md). Platform araç kümesini değiştirme hakkında ek bilgi için bkz: [nasıl yapılır: Hedef Framework ve Platform araç kümesini değiştirme](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

\*\* Yükleyebileceğiniz **C++ ile Mobil Geliştirme** iş yüküyle Visual Studio 2017 (veya isteğe bağlı **platformlar arası Mobil Geliştirme için Visual C++** Visual Studio 2015 kurulumundaki bileşen) için Hedef iOS veya Android platformlarını. Yönergeler için [platformlar arası Mobil Geliştirme için Visual C++ yükleme](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development). İOS Kodu derlemek için bir Mac bilgisayara sahip ve diğer gereksinimleri karşılaması gerekir. Önkoşullar ve yükleme yönergeleri bir listesi için bkz. [yükleme ve yapılandırma araçları iOS kullanarak derlemeye](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios). X86 veya hedef donanım eşleştirmek için ARM kodu oluşturabilirsiniz. İOS simülatörü, Android için Microsoft Visual Studio öykünücü ve bazı Android cihazlar için oluşturmak için yapılandırmaları x86 kullan. İOS cihazları ve çoğu Android cihazlar için oluşturmak için ARM yapılandırmalar kullanın.

\*\*\* Yükleyebileceğiniz **C++ ile Linux geliştirme** Linux platformlarını hedeflemek için Visual Studio 2017 yükleyicisindeki iş yükü. Yönergeler için [indirin, yükleyin ve Linux iş yükünü Kurulum](../linux/download-install-and-setup-the-linux-development-workload.md). Desteklenen her mimari için oluşturmanıza yardımcı olacak bu araç takımı, hedef makinede, yürütülebilir dosyanın derler.

Hedef platform yapılandırmasını ayarlama hakkında daha fazla bilgi için bkz: [nasıl yapılır: 64-Bit, hedeflemek için Visual C++ projeleri x64 yapılandırma platformları](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio Sürümlerinde Visual C++ Araçları ve Özellikleri](visual-cpp-tools-and-features-in-visual-studio-editions.md)
- [Başlarken](/visualstudio/ide/getting-started-with-cpp-in-visual-studio)
