---
description: 'Daha fazla bilgi edinin: desteklenen platformlar (Visual C++)'
title: Desteklenen Platformlar (Visual C++)
ms.date: 12/02/2019
ms.technology: cpp-tools
helpviewer_keywords:
- Visual C++, platforms supported
- platforms [C++]
ms.assetid: 0d893056-4008-411a-b3d1-5f57fd7da95c
ms.openlocfilehash: 80f8693a8cef7368953779d82100ce02e41f5cd8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207520"
---
# <a name="supported-platforms-visual-c"></a>Desteklenen Platformlar (Visual C++)

Visual Studio kullanılarak oluşturulan uygulamalar, aşağıdaki gibi çeşitli platformları hedefleyebilir.

|Operating System|x86|x64|ARM|ARM64\*\*\*\*|
|----------------------|---------|---------|---------|---------|
|Windows XP|Sayı\*|Sayı\*|||
|Windows Server 2003|Sayı\*|Sayı\*|||
|Windows Vista|X|X|||
|Windows Server 2008|X|X|||
|Windows 7|X|X|||
|Windows Server 2012 R2|X|X|||
|Windows 8|X|X|X||
|Windows 8.1|X|X|X||
|Windows 10|X|X|X|X|
|Android \*\*|X|X|X|X|
|Işlemine \*\*|X|X|X|X|
|'Un \*\*\*|X|X|X|X|

\* Windows XP ve Windows Server 2003 projeleri oluşturmak için Visual Studio 2017, Visual Studio 2015, Visual Studio 2013 ve Visual Studio 2012 güncelleştirme 1 ' de bulunan Windows XP platformu araç takımını kullanabilirsiniz. Bu platform araç takımını kullanma hakkında daha fazla bilgi için bkz. [WINDOWS XP Için programları yapılandırma](../build/configuring-programs-for-windows-xp.md). Platform araç takımını değiştirme hakkında daha fazla bilgi için bkz. [nasıl yapılır: hedef Framework ve platform araç takımını değiştirme](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

\*\* Visual Studio 2017 ve üzeri için yükleyicideki C++ iş yüküyle **Mobil geliştirmeyi** yükleyebilirsiniz. Visual Studio 2015 kurulumunda, **platformlar arası mobil geliştirme** bileşeninin IOS veya Android platformlarını hedeflemesini sağlamak için isteğe bağlı Visual C++ seçin. Yönergeler için bkz. [ınstall çoklu platform mobil uygulama geliştirme için Visual C++](/visualstudio/cross-platform/install-visual-cpp-for-cross-platform-mobile-development). İOS kodu oluşturmak için bir Mac bilgisayarınız olması ve diğer gereksinimleri karşılamanız gerekir. Önkoşulların ve Yükleme yönergelerinin bir listesi için bkz. [iOS kullanarak derlemek Için araçları yükleme ve yapılandırma](/visualstudio/cross-platform/install-and-configure-tools-to-build-using-ios). Hedef donanımla eşleştirmek için x86 veya ARM kodu oluşturabilirsiniz. İOS simülatörü, Android için Microsoft Visual Studio Öykünücüsü ve bazı Android cihazları için derlemek üzere x86 yapılandırması kullanın. İOS cihazlarını ve Android cihazlarını oluşturmak için ARM yapılandırması kullanın.

\*\*\* Linux platformunu hedeflemek için Visual Studio 2017 ve üzeri yükleyicisindeki C++ iş yüküyle **Linux geliştirmeyi** yükleyebilirsiniz. Yönergeler için bkz. [Linux Iş yükünü indirme, yükleme ve kurma](../linux/download-install-and-setup-the-linux-development-workload.md). Bu araç takımı, çalıştırılabilir dosyayı hedef makinede derler, böylece desteklenen herhangi bir mimari için derleyebilirsiniz.

\*\*\*\* ARM64 desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

Hedef platform yapılandırmasını ayarlama hakkında daha fazla bilgi için bkz. [nasıl yapılır: yapılandırma Visual C++ projeleri 64 bit, x64 platformları hedefleyecek şekilde](../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md).

## <a name="see-also"></a>Ayrıca bkz.

- [Visual Studio Sürümlerinde Visual C++ Araçları ve Özellikleri](visual-cpp-tools-and-features-in-visual-studio-editions.md)
- [Başlarken](/visualstudio/ide/getting-started-with-cpp-in-visual-studio)
